#ui/ui.Nodes.Popup

Base popup component

####Example

     new Popup({
         container: 'someContainerSelector',
         events: {
             click: function(){
                 alert('clicked');
             },

             mouseover: function(){
                 alert('over me');
             }
         }
     });,
     new Popup({
         selector: 'someButtonSelector',
         centered: true,
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

###setToCenter

Set node to be centered to it's container

**Chainable**: true
####Example

     node.setToCenter();

