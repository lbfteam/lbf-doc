#app/app.Collection

Model collection. For easy and fast management of models.

####Example

     var SomeCollection = Collection.extend({
         model: SomeModel, // assign a model class to manage

         url: 'CGI_URL', // CGI URL for sync data, use model's URL when leave it blank

         initialize: function(){
             // initialization things
         }
     });

     (new SomeCollection()).fetch(); // fetch on initialization,
     // initialize with client-side data is also acceptable
     // data format should be an array of objects
     new SomeCollection([
         {
             id: 1,
             attr: 'data1'
         },
         {
             id: 1,
             attr: 'data1'
         }
     ]);

**Extends**: lib.Backbone.Collection

##Methods

###_handlerServiceError

Handle remote-server's service error by using this function to wrap error callback.

**Chainable**: true

**Params**:  
*   method _String_

    Sync method type
*   collection _app.Collection_

    Instance to sync
*   options _Object_

    Sync options
    * error _Function_ - Sync error callback, will be replaced.


###onServiceError

Bind service error event handler

**Chainable**: true

**Returns**: _app.Collection_ - 

**Params**:  
*   status _Number_

    HTTP status to be listened to.
*   callback _Function_

    Event handler
    * event _Event_ - Error event
    * collection _Collection_ - The collection instance that error occurs
    * response _String|Object_ - The response text, would be parsed if in JSON format
    * xhr _XMLHTTPRequest_ - The original XMLHTTPRequest object
    * options _Object_ - The request options
*   context _Object_

    Context the callback is going to run in

####Example

     collection.onServiceError(508, function(event, collection, response, xhr, options){
         // handle error
         // collection === this
         // response is object if xhr.responseText is JSON
     }, collection);

###onceServiceError

Bind once service error event handler

**Chainable**: true

**Returns**: _app.Collection_ - 

**Params**:  
*   status _Number_

    HTTP status to be listened to.
*   callback _Function_

    Event handler
    * event _Event_ - Error event
    * collection _Collection_ - The collection instance that error occurs
    * response _String|Object_ - The response text, would be parsed if in JSON format
    * xhr _XMLHTTPRequest_ - The original XMLHTTPRequest object
    * options _Object_ - The request options
*   context _Object_

    Context the callback is going to run in

####Example

     collection.onceServiceError(508, function(event, collection, response, xhr, options){
         // handle error
         // this will at most be invoked once
         // collection === this
         // response is object if xhr.responseText is JSON
     }, collection);

###offServiceError

Unbind service error event handler

**Chainable**: true

**Returns**: _app.Collection_ - 

**Params**:  
*   status _Number_

    HTTP status to be listened to.
*   callback _Function_

    Event handler
*   context _Object_

    Context the callback is going to run in


###sync

Sync with server. Wrap Backbone.Collection.sync and add _handlerServiceError

**Chainable**: true

**Returns**: _app.Collection_ - 

**Params**:  
*   method _String_

    Sync method type
*   collection _app.Collection_

    Instance to sync
*   options _Object_

    Sync options


###ajax

Ajax. Wrap Backbone.Collection.Ajax and add _handlerServiceError

**Chainable**: true

**Returns**: _app.Collection_ - 

**Params**:  
*   options _Object_

    Sync options


