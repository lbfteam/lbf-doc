#util.Promise

Promise module for complex handling async processed
Inspired by Promises/A of CommonJS
Partial borrowed from jQuery.Deferred

####Example

     // Take static method create as example
     // 'new Promise' style is the same

     var promise = Promise.create(function(promise){
         // do something

         // when things done
         promise.resolve();

         // or when error occurs
         promise.reject();

         // or when things are in progress
         promise.notify();
     });

     promise
         .done(function(){
             // success callback
         })
         .done(function(){
             // multiple callbacks are accepted in done/fail/progress methods
         })
         .fail(function(){
             // fail/error callback
         })
         .progress(function(){
             // progress callback
         })

