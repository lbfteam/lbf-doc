# LBF
LBF全称Lazy Bullet Framework，致力于企业级前端解决方案

## Release
Edge Verision: [0.8.0](./archive/0.8.0)

Stable Version: 0.7.6

History Versions(待完善)

## Quick Start
```
<script src="//combo.b.qq.com/lbf/0.8.0/LBF.js"></script>
<script>
LBF.use('lib.jQuery', function($){
    $(document).ready(function(){
        // go!
    });
})
</script>
```

## Usage

### API Doc
待完善

### Samples
待完善

### FAQ
待完善

### 高级特性
- 自定义主题包
- 引入外部文件

## Features in future
- LESS编写主题包
- API Doc/Sample完善
- 代码本地存储
- 代码增量更新
- 移动端支持
- ICheckbox/IRadio优化重构
- AutoComplete优化

## Release log
0.8.1
> 1. [ui.Plugins.Drag] 修复drag组件导致页面元素不能选中的bug
2. [ui.widget.Dropdown.Dropdown] 修复dropdown位置计算的bug, 解决target不在整个文档流内则不做处理
3. [ui.widget.Dropdown.Dropdown] dropdown组件的close event修改为 close.Dropdown后导致 combobox的close失效
4. [ui.widget.Dropdown.Dropdown] 同步close命名空间到0.8.1， 同步container新特性到0.8.1
5. [ui.widget.Panel.Panel] Panel.js 对UI组件的'close'事件统一添加命名空间,对UI组件的'close'事件统一添加命名空间
6. [ui.widget.FileUploader.swfUpload] 上传裁切组件增加processData参数
7. [ui.Nodes.TextArea] 修复Textarea的validate bug
8. [ui.Nodes.TextInput] TextInput的validate方法,把this作用域传入
9. [ui.Nodes.Tip] Tip.js 增加setContent, 增加adjust方法
10. [ui.widget.Combobox.Combobox] ComboBox.js 修复对原生select的取值操作
11. [app.Model][app.Collection] add RESTFUL api to Model and Collection.js
12. [util.validates] 调整validates组件，可以和表单验证组件validform共用验证规则
13. [util.Promise] fix promise.js bug. isFunction is undefined
14. [util.region] 修复根据code查询地域的接口
15. [util.staticLocalStorage] 新增staticLocalStorage作localStorage静态文件缓存处理
16. [util.ptLoginHelper][util.TEA] add ptLoginHelper.js  update TEAJS add encodeBase64

[提bug或有任何问题请在此留言或讨论](https://github.com/lbfteam/lbf-doc/issues)
