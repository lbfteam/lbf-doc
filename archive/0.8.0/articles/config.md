如何使用LBF中的config方法
==============

0.8.0之前的LBF版本使用 **set** 方法来进行LBF的一些全局变量的设置。0.8.0版本之后LBF采用了 **config** 的方法来进行设置。下面就 **config** 的使用进行详细说明。

下面是 **lbf.config** 方法中增加的几个属性: 
  
* alias
* paths
* vars
* map
* debug
* combo
* comboSyntax
* comboMaxLength
* comboSuffix
* comboExcludes

***
id2Uri是LBF中对define, use后面的id或ids进行处理的函数。先处理alias, nameSpace, 然后是paths, vars, 在加上base之后，再进行map操作。这个顺序对我们进行参数设定非常重要。
```javascript
function id2Uri(id, refUri) {
  if (!id) return ""

  id = parseAlias(id)
  id = parseNamespace(id)
  id = parseAlias(id)
  id = parsePaths(id)
  id = parseVars(id)
  id = normalize(id)

  var uri = addBase(id, refUri)
  uri = parseMap(uri)

  return uri
}
```
以下参数皆可通过LBF.data.alias || LBF.data.paths等进行直接获取。
###alias
别名，如果一个模块名超长，如a/b/c/d/e/f, 则可以用alias来进行别名，让代码更加短和易读。

```javascript
LBF.config({ 
        alias: { 
                'jQuery': 'lib.jQuery'', //Namespace
                'backbone': 'lib/Backbone.js' //路径模式
       }
    });
       LBF.use(['jQuery', 'backbone'], function($, b) {
               console.log($);
               console.log(b);
       });
```

可点击下面链接查看实例:
[alias example](http://jsfiddle.net/dapenggaofei/90ucfgd1/5/)


###paths
当目录层级比较深时，或需要跨目录调用模块时。可以使用paths来简化书写。paths在0.8.0之前大家也是用过的。没有太大区别。
```javascript
LBF.config({ 
        paths: { 
                'cssPath': 'http://combo.b.qq.com/lbf/0.7.7/ui/theme/default/lbfUI/css'
       }
    });
       LBF.use(['cssPath/Button.css'], function(buttonCss) {
       });
```
可点击下面链接查看实例:
[paths example](http://jsfiddle.net/dapenggaofei/kg1y3uft/1/)
###vars
对于有一些变量需要在运行的时候才能确定。比如更换UI包。之前LBF中的实现是通过\__THEME__来进行标识。现在0.8.0引入了vars对象。我们不仅可以对UI包进行替换，还能配置其他变量，load不同的js或css文件。
```javascript
LBF.config({
    vars: {
        theme: '//combo.b.qq.com/crm3/src/themes/default',
        env: 'debug'
    }
});
LBF.use(['{theme}/lbfUI/css/Button.css'], function(buttonCss) {

});
```
可点击下面链接查看实例:
[vars example](http://jsfiddle.net/dapenggaofei/n6d9ppjf/8/)

###map 

map可以对模块路径进行映射修改。可用于路径转换、在线调试。
```javascript
LBF.config({
    map: [
        ['http://devcombo.b.qq.com/lbf/0.8.0/lib/jQuery.js', 'http://combo.b.qq.com/lbf/0.8.0/lib/jQuery.js']
    ]
});

LBF.use(['lib.jQuery'], function($) {
    alert('loaded jQuery from online');
});
```
可点击下面链接查看实例:
[map example](http://jsfiddle.net/dapenggaofei/kojsw837/1/)

<b style="color:#cccccc">在这里我有一个问题，为哈这里用数组，而不是跟前面一样用对象呢</b>

###debug
debug开头。代码中只有一处对debug的处理。
```javascript
    if (!isCSS && !data.debug) {
      head.removeChild(node)
    }
```
我们可以通过LBF.data.debug来获取该值。来进行一些debug操作。

###combo
是否开启combo合并选项。如果静态资源服务器不支持combo合并，那这里就不要进行设定了。如果支持则设为true。下面几个参数都是针对combo=true时的一些设置。

###comboSyntax
我们不需要修改这个值。使用默认的就好。
```javascript
comboSyntax: ['c/=', ',']
```

###comboMaxLength
这个值也不需要修改。取1000是为了兼容低版本IE，get请求有最大值而设定的。

###comboSuffix
comboSuffix是在combo合并之后，附加在每一个请求后面的小尾巴。如果我们要更新版本号，更改的就是这个了。
```javascript
comboSuffix: '?v=20141014'
```

###comboExcludes
在开启了combo之后，如果对于一些请求不希望进行combo合并，我们可以在comboExcludes当中进行设置。可以为正则或函数。
```javascript
LBF.config({
    combo: true,
    comboExcludes: function(url) {
        //此处的url已经被处理过，是绝对路径
        if(url === 'http://devcombo.b.qq.com/lbf/0.8.0/lib/jQuery.js') {
            return true;
        }
        
    }
});
LBF.use(['lib.jQuery', 'lib.Backbone'], function($, bb) {});
可点击下面链接查看实例:
[comboExcludes example](http://jsfiddle.net/dapenggaofei/quhy6br1/6/)

```






