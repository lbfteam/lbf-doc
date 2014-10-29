#util/util.Uploader

Common file uploader. Will extend to support n files upload in near future.

####Example

     new Uploader({
         target: 'uploadName',
         cbName: 'uploadCallback',
         trigger: 'fileSelectBtnSelector',
         url: 'address'
     });

**Extends**: ui.Nodes.Node

##Properties

###settings

Default settings

**type**: Object

##Methods

###render

Render and bind UI events. Invisible file input should be place exactly on top of trigger node.

**Chainable**: true

###update

Update file input position. In some cases, trigger node could be moved. Therefore, input position needs to be updated

**Chainable**: true

###setURL

Set(Update) upload target

**Chainable**: true

**Params**:  
*   url _String_

    The target to be submit to. Use ? as placeholder of cbName.


###upload

Submit form and upload file

**Chainable**: true

**Params**:  
*   url _String_

    Submit target


###cancel

Cancel uploading

**Chainable**: true

###reset

Reset file input to empty(No file is selected)

**Chainable**: true

###_uploaded

Uploaded callback. Clear global point, and fire uploaded event

**Chainable**: true

##Events

###upload

Fire when a file starts uploading

**Params**:  
*   event _Event_JQuery event
*   node _Node_Node object


###cancel

Fire when upload canceled

**Params**:  
*   event _Event_JQuery event
*   node _Node_Node object


###uploaded

Fire when file uploaded, event payload depends on callback arguments

**Params**:  
*   event _Event_JQuery event

####Example

     // assume callback name is 'cb'
     // upload response is cb(attr1, attr2, ...)
     uploader.bind('uploaded', function(event, attr1, attr2, ..){
         // uploaded handler
     });

