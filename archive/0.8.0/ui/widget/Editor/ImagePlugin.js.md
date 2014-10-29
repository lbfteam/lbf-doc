#ui/ui.widget.Editor.ImagePlugin

Image plugin for editor. Select a local image, upload and submit with editor's content

####Example

     editor.plug(ImagePlugin, {
         name: 'someImage',
         url: 'someCGI',
         maxWidth: 200,
         maxHeight: 200,
         callbackName: 'uploaded' // CGI use a fixed callback name 'uploaded'
     });

**Extends**: ui.Plugins.Plugin

##Properties

###ns

Plugin's namespace

**type**: String

###settings

Default settings

**type**: Object

##Methods

###render

Render image panel and add to editor's top panel

**Chainable**: true

###showImgViewer

Show image viewer

**Chainable**: true

###hideImgViewer

Hide image viewer

**Chainable**: true

###_uploaded

Uploaded callback function

**Chainable**: true

**Params**:  
*   event _Event_

    JQuery Event
*   response _Object_

    Upload response


###_addImage

Add image to panel

**Chainable**: true

**Params**:  
*   response _Object_

    Upload response


###_removeImage

Remove uploaded image

**Chainable**: true

##Events

###ImagePlugin.uploaded

Fire when image uploaded

**Params**:  
*   event _Event_JQuery Event
*   response _Object_Upload response


###ImagePlugin.fail

Fire when image upload failed

**Params**:  
*   event _Event_JQuery Event
*   response _Object_Upload response


###ImagePlugin.addImage

Fire when add a image

**Params**:  
*   event _Event_JQuery event
*   response _Object_Upload response


###ImagePlugin.removeImage

Fire when remove uploaded image

**Params**:  
*   event _Event_JQuery event


