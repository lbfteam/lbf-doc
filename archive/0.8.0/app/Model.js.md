#app/app.Model

Model for data management

####Example

     var SomeModel = Model.extend({
         // model's default values
         defaults: {
             attr1: 'defaultAttrValue1',
             attr2: 'defaultAttrValue2'
         },

         url: 'CGI_URL', // CGI URL for sync data

         initialize: function(){
             // initialization things
         }
     });

     (new SomeModel()).fetch(); // fetch on initialization,
     // initialize with client-side data is also acceptable
     // data format should be an array of objects
     new SomeModel([
         {
             id: 1,
             attr: 'data1'
         },
         {
             id: 1,
             attr: 'data1'
         }
     ]);

**Extends**: lib.Backbone.Model

##Methods

###_handlerServiceError

Handle remote-server's service error by using this function to wrap error callback.

**Params**:  
*   method _String_

    Sync method type
*   model _app.Model_

    Instance to sync
*   options _Object_

    Sync options
    * error _Function_ - Sync error callback, will be replaced.


###onServiceError

Bind service error event handler

**Returns**: _app.Model_ - 

**Params**:  
*   status _Number_

    HTTP status to be listened to.
*   callback _Function_

    Event handler
    * event _Event_ - Error event
    * model _Model_ - The collection instance that error occurs
    * response _String|Object_ - The response text, would be parsed if in JSON format
    * xhr _XMLHTTPRequest_ - The original XMLHTTPRequest object
    * options _Object_ - The request options
*   context _Object_

    Context the callback is going to run in

####Example

     model.onServiceError(508, function(event, model, response, xhr, options){
         // handle error
         // model === this
         // response is object if xhr.responseText is JSON
     }, model);

###onceServiceError

Bind once service error event handler

**Returns**: _app.Model_ - 

**Params**:  
*   status _Number_

    HTTP status to be listened to.
*   callback _Function_

    Event handler
    * event _Event_ - Error event
    * model _Model_ - The collection instance that error occurs
    * response _String|Object_ - The response text, would be parsed if in JSON format
    * xhr _XMLHTTPRequest_ - The original XMLHTTPRequest object
    * options _Object_ - The request options
*   context _Object_

    Context the callback is going to run in

####Example

     model.onceServiceError(508, function(event, model, response, xhr, options){
         // handle error
         // this will at most be invoked once
         // model === this
         // response is object if xhr.responseText is JSON
     }, model);

###offServiceError

Unbind service error event handler

**Returns**: _app.Model_ - 

**Params**:  
*   status _Number_

    HTTP status to be listened to.
*   callback _Function_

    Event handler
*   context _Object_

    Context the callback is going to run in


###sync

Sync with server. Wrap Backbone.Model.sync and add _handlerServiceError

**Returns**: _app.Model_ - 

**Params**:  
*   method _String_

    Sync method type
*   model _app.Model_

    Instance to sync
*   options _Object_

    Sync options


###ajax

Ajax. Wrap Backbone.Model.Ajax and add _handlerServiceError

**Returns**: _app.Model_ - 

**Params**:  
*   options _Object_

    Sync options


