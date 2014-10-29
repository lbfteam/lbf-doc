#ui/ui.widget.ImageCrop

图片裁切组件

####Example

     new ImageCrop({
          url: 'demo.php',
          cropWidth: 300,
          cropHeight: 200,
          dropbox: '.dragdrop',
          container: '.lbf-ImageCrop',
          resizable: true,
          cropRange: '100|600|100|600',
          panelText: {
              title:'头像裁切',
              size:'头像尺寸：'
          }
      });

**Extends**: ui.Nodes.Node

##Properties

###settings

Default settings

**type**: Object

##Methods

###showPanel

显示裁切窗口

**Params**:  
*   裁切图片的地址 _String|Object_

    | [imgobj] 裁切图片的一些参数值
*   imgobj.url _String_

    图片地址
*   imgobj.show_url _String_

    用作显示的图片地址（针对https的情况）
*   imgobj.width _Number_

    图片宽度
*   imgobj.height _Number_

    图片高度
*   silence _Boolean_

    显示裁切窗口时是否显示裁切图片


###loadImg

加载需要裁切的图片

**Params**:  
*   src _String_

    图片地址


###setCropSize

设置图片裁切尺寸

**Params**:  
*   opts _Object_

    需要设置的宽高值
    * width _Number_ - 需要设置的宽度
    * height _Number_ - 需要设置的高度


##Events

###cropSuccess

Fire when crop success

**Params**:  
*   event _Event_JQuery event
*   opts _Object_server response data


###cropError

Fire when crop error

**Params**:  
*   event _Event_JQuery event
*   opts _Object_server response data


###cropComplete

Fire when crop complete

**Params**:  
*   event _Event_JQuery event
*   opts _Object_server response data


###cropCancel

Fire when crop canceled

**Params**:  
*   event _Event_JQuery event
*   node _Object_Node object


###uploadSuccess

Fire when upload successed

**Params**:  
*   event _Event_JQuery event
*   opts _Object_server response data
    * r _Object_ - status code
    * msg _Object_ - message
    * data _Object_ - {url: '', show_url:''}


###uploadError

Fire when upload error

**Params**:  
*   event _Event_JQuery event
*   opts _Object_server response data


