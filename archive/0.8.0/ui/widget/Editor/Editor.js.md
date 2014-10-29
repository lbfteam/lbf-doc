#ui/ui.widget.Editor.Editor



####Example

     new Editor({
         container: 'someContainerSelector',
         disabled: true,
         maxlength: 100,
         placeholder: 'i am placeholder',
         validate: function(event, value){
             if(!value){
                 return new Error('empty is not allowed');
             }
         },
         events: {
             click: function(){
                 alert('clicked');
             },
             error: function(e, validateResult){
                 // handle error
                 alert(validateResult.message);
             }
         }
     });,
     new Editor({
         selector: 'textarea[name=abc]',
         value: 'hello',
         readonly: true,
         disabled: true
     });

**Extends**: ui.Nodes.Textarea  
**Uses**: 
* ui.Plugins.Cursor


##Properties

###settings

Default settings

**type**: Object

##Methods

###render

Render editor, add top and bottom panel and plug cursor plugin

**Chainable**: true

