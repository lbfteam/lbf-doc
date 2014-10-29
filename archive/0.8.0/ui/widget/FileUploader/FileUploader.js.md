#ui/ui.widget.FileUploader

文件上传组件，会根据浏览器不同选用ajax、iframe、flash等三种上传方式.

####Example

     new FileUploader({
	        url: 'demo.php',
	        flashUrl: 'swfupload.swf',
	        dropbox: '.dragdrop',
	        selector: '.lbf-ImageCrop',
         data: {
              user: 'sean',
              age: 18
         },
         container: '.lbf-ImageCrop',
         singleUpload: true,
         file_size_limit: '200kb'
    })

**Extends**: ui.Nodes.Node

##Properties

###settings

Default settings

**type**: Object

##Methods

###cancel

取消上传

###disable

禁用上传

**Params**:  
*   index _Number_

    指定第几个按钮被禁用, 不传入会禁用所有按钮


###enable

启用上传

**Params**:  
*   index _Number_

    指定第几个按钮被启用，不传入会启用所有按钮


##Events

###uploadStart

Fire when upload start

**Params**:  
*   event _Event_JQuery event
*   node _Node_Node object
*   stats _Object_uploaded files stats


###cancel

Fire when upload canceled

**Params**:  
*   event _Event_JQuery event
*   node _Node_Node object


###uploadError

Fire when upload error

**Params**:  
*   event _Event_JQuery event
*   opts _Object_server response data
*   stats _Object_uploaded files stats


###uploadSuccess

Fire when upload successed

**Params**:  
*   event _Event_JQuery event
*   opts _Object_server response data
    * r _Object_ - status code
    * msg _Object_ - message
    * data _Object_ - {url: '', show_url:''}
*   stats _Object_uploaded files stats


###uploadComplete

Fire when upload complete

**Params**:  
*   event _Event_JQuery event
*   opts _Object_server response data
*   stats _Object_uploaded files stats


