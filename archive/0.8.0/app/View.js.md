#app/app.View

View management. Besides methods of Backbone.View, all jQuery methods are ready to use.

####Example

     var SomeView = View.extend({
         tagName: 'ul', // set the outer wrap tagName

         // delegate child-node event to view wrap
         events: {
             'click .someElement': 'clickHandler'
         },

         initialize: function(opts){
             // initialization things
             // argument opts is passed in when instantiation, like new View(opts)
         },

         // sample render function
         render: function(){
             // use template engine
             this.template('SomeTemplateStr', {
                 // render data
             });

             // bind UI event
         },

         clickHandler: function(){
             // handler click event on .someElement
         }
     });

     var view = new SomeView({
         // will be linked to view.model automatically
         // this also works out for collection
         model: someModel,

         // addition options are acceptable
         // initialize function will get this object
         someAdditionalOptions: someOptionObject
     });

     // View has mix in all jQuery APIs
     // all APIs are chainable
     view
         .html(someHTMLStringOrJQueryObject)
         .click(function(){
             alert('click');
         });

**Extends**: lib.Backbone.View  
**Uses**: 
* lib.Backbone.View
* lib.jQuery
* util.template


##Methods

###$

Find element inside view

###jQuery

Import lib.jQuery as this.jQuery

###template

Import util.template as this.template

