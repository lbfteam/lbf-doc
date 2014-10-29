#util/util.Validform

通用表单验证方法

####Example

new Validform({
    selector: '.demoform', // 必需, '.demoform'指明是哪一表单需要验证,名称需加在form表单上;
    html5: false, //可选项 true | false，true：使用html5验证，false：使用Validform统一验证，默认false;
    btnSubmit: "#btn_sub", //#btn_sub是该表单下要绑定点击提交表单事件的按钮;如果form内含有submit按钮该参数可省略;
    btnReset: ".btn_reset", //可选项 .btn_reset是该表单下要绑定点击重置表单事件的按钮;
    tiptype:1, //可选项 1=>pop box,2=>side tip(parent.next.find; with default pop),3=>side tip(siblings; with default pop),4=>side tip(siblings; none pop)，默认为1，也可以传入一个function函数，自定义提示信息的显示方式（可以实现你想要的任何效果）;, tiptype ==> function:
                 tiptype:function(type, msg, curObj, curform, cssctl){
                           //type指示提示的状态，值为1、2、3、4， 1：正在检测/提交数据，2：通过验证，3：验证失败，4：提示ignore状态;
                           //msg：提示信息;
                           //curObj 是当前验证的表单元素（或表单对象）;
                           //curform 当前所在表单;
                           //cssctl:内置的提示信息样式控制函数，该函数需传入两个参数：显示提示信息的对象 和 当前提示的状态（既形参o中的type）;
                           $curObj = $(curObj);
                           if(!$curObj.is("form")){//验证表单元素时o.obj为该表单元素，全部验证通过提交表单时o.obj为该表单对象;
                               var objtip=$curObj.siblings(".Validform_checktip");
                               cssctl(objtip,type);
                               objtip.html(msg);
                           }
                       }
    ignoreHidden: false, //可选项 true | false 默认为false，当为true时对:hidden的表单元素将不做验证;
    dragonfly: false, //可选项 true | false 默认false，当为true时，值为空时不做验证；
    tipSweep: true, //可选项 true | false 默认为false，只在表单提交时触发检测，blur事件将不会触发检测（实时验证会在后台进行，不会显示检测结果）;
    label: ".label", //可选项 选择符，在没有绑定nullmsg时查找要显示的提示文字，默认查找".Validform_label"下的文字;
    showAllError: false, //可选项 true | false，true：提交表单时所有错误提示信息都会显示，false：一碰到验证不通过的就停止检测后面的元素，只显示该元素的错误信息;
    postonce: true, //可选项 表单是否只能提交一次，true开启，不填则默认关闭;
    ajaxPost: true, //使用ajax方式提交表单数据，默认false，提交地址就是action指定地址;
    datatype: {//传入自定义datatype类型，可以是正则，也可以是函数（函数内会传入一个参数）;
        "*6-20": /^[^\s]{6,20}$/,
        "z2-4" : /^[\u4E00-\u9FA5\uf900-\ufa2d]{2,4}$/,
        "username":function(inputval, input, curform, regxp){
            //参数inputval是获取到的表单元素值，input为当前表单元素，curform为当前验证的表单，regxp为内置的一些正则表达式的引用;
            var reg1=/^[\w\.]{4,16}$/,
            reg2=/^[\u4E00-\u9FA5\uf900-\ufa2d]{2,8}$/;

            if(reg1.test(inputval)){return true;}
            if(reg2.test(inputval)){return true;}
            return false;

            //注意return可以返回true 或 false 或 字符串文字，true表示验证通过，返回字符串表示验证失败，字符串作为错误提示显示，返回false则用errmsg或默认的错误提示;
        }
    },
    beforeCheck: function(curform){
        //在表单提交执行验证之前执行的函数，curform参数是当前表单对象。
        //这里明确return false的话将不会继续执行验证操作;
    },
    beforeSubmit: function(curform){
        //在验证成功后，表单提交前执行的函数，curform参数是当前表单对象。
        //这里明确return false的话表单将不会提交;
    },
    callback: function(data){
        //返回数据data是json格式，{"info":"demo info","status":"y"}
        //info: 输出提示信息;
        //status: 返回提交数据的状态,是否提交成功。如可以用"y"表示提交成功，"n"表示提交失败，在ajax_post.php文件返回数据里自定字符，主要用在callback函数里根据该值执行相应的回调操作;
        //你也可以在ajax_post.php文件返回更多信息在这里获取，进行相应操作；
        //ajax遇到服务端错误时也会执行回调，这时的data是{ status:**, statusText:**, readyState:**, responseText:** }；

        //这里执行回调操作;
        //注意：如果不是ajax方式提交表单，传入callback，这时data参数是当前表单对象，回调函数会在表单验证全部通过后执行，然后判断是否提交表单，如果callback里明确return false，则表单不会提交，如果return true或没有return，则会提交表单。
    }
});

Validform对象的方法和属性：
tipmsg：自定义提示信息，通过修改Validform对象的这个属性值来让同一个页面的不同表单使用不同的提示文字；
dataType：获取内置的一些正则；
eq(n)：获取Validform对象的第n个元素;
ajaxPost(flag, sync, url)：以ajax方式提交表单。flag为true时，跳过验证直接提交，sync为true时将以同步的方式进行ajax提交，传入了url地址时，表单会提交到这个地址；
abort()：终止ajax的提交；
submitForm(flag, url)：以参数里设置的方式提交表单，flag为true时，跳过验证直接提交，传入了url地址时，表单会提交到这个地址；
resetForm()：重置表单；
resetStatus()：重置表单的提交状态。传入了postonce参数的话，表单成功提交后状态会设置为"posted"，重置提交状态可以让表单继续可以提交；
getStatus()：获取表单的提交状态，normal：未提交，posting：正在提交，posted：已成功提交过；
setStatus(status)：设置表单的提交状态，可以设置normal，posting，posted三种状态，不传参则设置状态为posting，这个状态表单可以验证，但不能提交；
ignore(selector)：忽略对所选择对象的验证；
unignore(selector)：将ignore方法所忽略验证的对象重新获取验证效果；
addRule(rule)：可以通过Validform对象的这个方法来给表单元素绑定验证规则；
check(selector, bool): 对指定对象进行验证(默认验证当前整个表单)，通过返回true，否则返回false（绑定实时验证的对象，格式符合要求时返回true，而不会等ajax的返回结果），bool为true时则只验证不显示提示信息；
config(setup): 可以通过这个方法来修改初始化参数，指定表单的提交地址，给表单ajax和实时验证的ajax里设置参数；
showmsg(msg, curObj, type);

**Extends**: ui.Nodes.Node

##Properties

###dataType

dataype的引用

**type**: 

###settings

Default settings

**type**: Object

##Methods

###eq

获取第n个表单

**Params**:  
*   n _Number_

    获取第n个表单


###resetStatus

重置表单状态

###setStatus

设置表单状态

**Params**:  
*   status _String_

    设置表单状态


###getStatus

设置表单状态

###ignore

忽略对某个或某些元素的验证

**Params**:  
*   selector _String_

    选择符，会在当前表单下查找


###unignore

恢复对某个或某些元素的验证

**Params**:  
*   selector _String_

    选择符，会在当前表单下查找


###addRule

给表单元素绑定验证规则

**Params**:  
*   rule _Array_

    


###showmsg

显示提示信息

**Params**:  
*   msg _String_

    文字消息
*   curObj _Object_

    当前dom元素
*   type _String_

    消息类型 'success', 'checking', 'reset', 'wrong' 分别对应 验证通过、正在验证、重置状态和验证失败, 默认wrong;


###ajaxPost

ajax提交表单

**Params**:  
*   flag _Boolean_

    是否不做验证直接提交表单
*   sync _Boolean_

    是否使用同步模式
*   url _String_

    表单提交地址，会覆盖form的action和config方法指定的地址;


###submitForm

提交表单

**Params**:  
*   flag _Boolean_

    是否不做验证直接提交表单
*   url _String_

    表单提交地址，会覆盖form的action和config方法指定的地址;


###resetForm

重置表单

###abort

取消ajax提交表单

###check

验证指定表单元素

**Params**:  
*   selector _String_

    是否不做验证直接提交表单
*   bool _Boolean_

    是否只检测不显示提示信息


###config

配置表单初始化参数

**Params**:  
*   setup _Object_

    

####Example

setup = {
      url:"ajaxpost.php",//指定了url后，数据会提交到这个地址;
      ajaxurl:{
           timeout:1000,
           ...
      },
      ajaxpost:{
           timeout:1000,
           ...
      }
  }

