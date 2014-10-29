#ui/ui.Nodes.Button

Base button component

####Example

     new Button({
         container: 'someContainerSelector',
         content: 'i\'m a button',
         events: {
             click: function(){
                 alert('clicked');
             },

             mouseover: function(){
                 alert('over me');
             }
         }
     });,
     new Button({
         selector: 'someButtonSelector',
         events: {
             click: function(){
                 alert('click');
             }
         }
     });

**Extends**: ui.Nodes.Node

##Properties

###settings

Default settings

**type**: Object

##Methods

###render

Render the node

**Chainable**: true

###show

Show button.
Button is div and original show will set display to block and cause style bug

**Chainable**: true

###Hide

Hide button.

**Chainable**: true

###disable

Disable the button

**Chainable**: true

###enable

Enable the button

**Chainable**: true

###renderAll

**Returns**: _Array_ - Array of nodes that is rendered

**Params**:  
*   selector _String|documentElement|jQuery|Node_

    Selector of nodes to be rendered
*   opts _Object_

    Options for node

####Example

     var nodeArray = Button.renderAll();,
     var nodeArray = Button.renderAll('.button');,
     var nodeArray = Button.renderAll({
         //options
         events: {
             error: function(e, error){
                 alert(error.message);
             }
         }
     });,
     var nodeArray = Button.renderAll('.button', {
         //options
         events: {
             error: function(){
                 alert('hello');
             }
         }
     });

