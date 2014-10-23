# LBF 0.8.0
0.8.0版本目前仍是Edge版本，仍有bug泄露风险，预计在10月24日完成开发、测试并封版。

# Change Logs
## 引入grunt管理LBF开发工具、任务

- build构建核心文件LBF.js
```shell
make build
```

- release生成待发布版本
版本号以package.json中的version为准。生成目录为release/@version/
```shell
make release
```

- test运行单元测试用例
采用mocha+chai构建单元测试用例
```shell
make test
```

## 破坏性改造
### LBF.config替换~~LBF.set~~，配置参数大量调整
LBF重构了核心代码，在seajs的源码基础上进行改造和整合。

因此LBF的配置接口由config改为set，配置参数也做了相应调整。

详情请查看[LBF配置](./articles/config.md)
```javascript
LBF.config({
    // 命名域映射配置
    paths: {
        // crm3.**.* -> //combo.b.qq.com/crm3/src/**/*
        crm3: '//combo.b.qq.com/crm3/src'
    },

    // 变量替换配置
    vars: {
        // 主题包位置配置
        theme: '//combo.b.qq.com/crm3/src/themes/default'
    },

    // 开启文件合并功能
    combo: true,

    // combo连接符
    comboSyntax: ['c/=/', ',/'],

    // 单个uri最大长度，如果合并文件uri超过该长度，则会分拆请求
    comboMaxLength: 1000,

    // 添加小尾巴到合并后的uri尾部
    // 'http://combo.b.qq.com/c/=/a.js,/b.js'
    // ->
    // 'http://combo.b.qq.com/c/=/a.js,/b.js?v=20141014'
    comboSuffix: '?v=20141014',

    // 不需要做合并的文件
    // 可以为正则或函数
    comboExcludes: function(uri){
        // 返回true，则不合并
    }
});
```

### LBF.use & require.async
LBF从0.8.0版本起将严格遵循[CMD规范](https://github.com/seajs/seajs/issues/242)。

因此LBF.use和require.async的回调函数参数将做出调整,从[~~require~~, mod1, mod2, ...]改为[mod1, mod2, ...]。

[jsfiddle代码示例](http://jsfiddle.net/mice530/e8v8zx0p/6/)
```javascript
LBF.use(['lib.jQuery', 'util.template', 'util.dateTool'], function($, artTemplate, dateTool){
    $(body).html(
        artTemplate('<h1>Current Date: <%== date %></h1>'){
            date: dateTool.format('Y:M:D', new Date);
        }
    );
});
```

### monitor.logger替换~~monitor.console~~，避免与原生console冲突，具体参考[API文档](http://lbf.epc.oa.com/doc/classes/monitor.console.html#method_config)
```javascript
LBF.use('monitor.logger', function(logger){
    logger.config({
        // logger conf
    });

    logger.debug('debug info', {
        // additional options
    });
});
```

## 新特性
- 新增[lib.zepto](http://zeptojs.com/)，为webkit核心和移动端场景替换lib.jQuery，并增加tap特性

- 新增util.pinyin（从原ui.widget.AutoComplete.Pinyin迁移至此），支持汉字的拼音查询

- 新增lang.forEach，向后兼容[[].forEach方法](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)

- 新增util.jsonp，支持jsonp请求

- 新增lang.FormData，向后兼容[FormData对象](https://developer.mozilla.org/zh-CN/docs/Web/API/XMLHttpRequest/FormData)

- 增强lang.browser，增加移动端、MAC的判断

- 新增[ui.widget.JScrollPane](http://jscrollpane.kelvinluck.com/),支持浏拟滚动条

- 新增[util.mouseWheel](https://github.com/brandonaaron/jquery-mousewheel),支持鼠标滚动事件处理

- 更新Hightcharts版本到4.0.1，替换原有的~~2.3.5~~

- 优化ui.widget.ICheckbox
  - 增加hover、disabled状态
  - 标准化check和uncheck事件
  - 增加半选态

- 优化ui.widget.DatePicker
  - 新增ui.widget.DatePickerRange，支持日期范围选择
  - 引入dropdown作为基类，复用大量代码
  - 优化展示逻辑，减去展示和隐藏时不必要的多次toggle行为

- 优化ui.widget.Panel的快捷键esc，点击esc时触发exit事件

- 新增[instantclick](http://instantclick.io/)工具，提供预加载HTML功能

- ui.widget.Combobox新增resize方法，优化了options的处理逻辑

- ui.widget.ZTree新增exHide模块，支持隐藏指定节点逻辑

- util.Range新增selectTextRange方法，支持文本范围选择

- 新增util.eventProxy，支持事件代理机制

## bug修复
- 修复ui.Nodes.TextArea中maxlength的问题
- 修复ui.widget.Combobox在render模式下指定options却被清空的问题
- 修复ui.widget.Combobox的enable接口问题
- 修复ui.Plugin.Drag插件导致弹出层中input/textarea无法选择中文的问题
- 修复ui.Nodes.Button的disabled状态样式
- 修复ui.widget.Dropdown/ui.widget.Combobox的宽度设置逻辑
- 修复ui.widget.Pagination对selector模式的支持
- 修复ui.widget.Clipboard无法复制的问题
- 修复lang.dateTool.isSameDay在设置1970.1.1 8:00:00 GMT8时的问题

