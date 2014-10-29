#app/app.REST

Restful sync component, provides CRUD methods for ajax programing.
REST component supports middle ware plugin and has built-in middle wares of auto error log, auto speed report, auto CSRF patch

##Methods

###ajax

An interface to jQuery.ajax

###sync

Main method for REST to communicate with backend

**Returns**: _util.Promise_ - Promise of sync action

**Params**:  
*   method _String_

    Accept CRUD methods only
*   options _Object_

    Sync options
    * data _Object_ - Data to be sent


###use

Use plugin ( middle ware )
3 built-in plugins (errorLog/speedReport/CSRFPatch) provided right now.

**Chainable**: true

**Params**:  
*   plugin _String|Function_

    Plugin name, or plugin function. A plugin is a middle ware that will be invoked before sync action (right before event beforeSend)

####Example


     // Plugin errorLog use monitor.logger and share it's config
     logger.config({
         writelogger: true,
         proj: 'REST test'
     });

     // Set plugin(middle ware) config
     REST.set({
         log: {
             module: 'test page',
             fn: 'test case'
         },
         CSRF: {
             token: '_bqq_csrf'
         }
     });

     // Use plugins
     REST
         // auto error log plugin
         .use('errorLog')

         // auto speed report plugin
         // speed report need additional option 'speedReport' when sync
         .use('speedReport')

         // auto CSRF patch
         .use('CSRFPatch');


     REST.read({
         uri: 'readApi',

         // Speed report plugin config
         // 3 flags & 1 point to identified the report point
         // Rate is the percentage to send speed report
         speed: {
             flag1: 1,
             flag2: 2,
             flag3: 3,
             point: 2,
             rate: 1
         }
     });

###create

Create operation on backend

**Returns**: _util.Promise_ - Promise of sync action

**Params**:  
*   options _Object_

    Sync options
    * data _Object_ - Data to be sent


###read

Read data from backend

**Returns**: _util.Promise_ - Promise of sync action

**Params**:  
*   options _Object_

    Sync options
    * data _Object_ - Data to be sent

####Example

     LBF.use(['app.REST'], function(REST){
         // Read data from backend
         // Create/update/del are mostly the same
         var readPromise = REST.read({
             url: 'readApi',

             // Success callback
             success: function(res, options){
                 logger.log('read success');
             },

             // Error callback
             error: function(err, xhr, jQErr){
                 logger.log('read error');
                 logger.log(err.message);
             }
         });

         // REST provides promise instance for flexible flow control
         readPromise
             .done(function(res, options){
                 logger.log('read done');
             })
             .fail(function(err, xhr, jQErr){
                 logger.log('read fail');
             })
             // Arguments to then callbacks depend on promise state
             .then(function(){
                 logger.log('read then');
             });
     });

###update

Update operation on backend

**Returns**: _util.Promise_ - Promise of sync action

**Params**:  
*   options _Object_

    Sync options
    * data _Object_ - Data to be sent


###del

delete operation on backend
use method name 'del' because 'delete' is reserved in IE

**Returns**: _util.Promise_ - Promise of sync action

**Params**:  
*   options _Object_

    Sync options
    * data _Object_ - Data to be sent


###wrapHandler

Wrap success and error handler, and exposes promise interface

**Returns**: _util.Promise_ - 

**Params**:  
*   REST __

    
*   options _Object_

    Sync options


##Events

###beforeSend

Event triggered when before sending a request

**Params**:  
*   promise __Promise of sync action
*   ajaxSettings __The final settings(params) of sync


###request

Event triggered when a request been made

**Params**:  
*   promise __Promise of sync action
*   xhr __The XMLHttpRequest instance from jQuery.ajax
*   ajaxSettings __The final settings(params) of sync


###status

Event triggered at a particular http status, like 500/404/509 etc
When status is 500, the name of triggered event is 500, not 'status'

**Params**:  
*   err _Error_Error instance
*   xhr _XMLHttpRequest_XMLHttpRequest instance created by jQuery.ajax
*   textStatus _String_Description text of the status
*   jQErr _JQueryError_Error instance created by jQuery.ajax

####Example

     // Watch http status 404
     REST.on(404, function(){
         logger.log(404);
     });

###errorCode

Event triggered when status is the specified one (like 509) and an error code come up

**Params**:  
*   err _Error_Error instance
*   xhr _XMLHttpRequest_XMLHttpRequest instance created by jQuery.ajax
*   textStatus _String_Description text of the status
*   jQErr _JQueryError_Error instance created by jQuery.ajax

####Example

     // Watch code 1001
     REST.on('error1001', function(){
         logger.log(1001);
     });

###sync

Event triggered when a sync succeeds

**Params**:  
*   res _Object_Response data
*   options _Object_Sync options


###error

Event triggered when a sync fails

**Params**:  
*   err _Object_Error object
    * code _Number_ - Error code, default to be -1 if not assign
*   xhr _XMLHttpRequest_XMLHttpRequest instance created by jQuery.ajax
*   jQErr _JQueryError_Error instance created by jQuery.ajax


