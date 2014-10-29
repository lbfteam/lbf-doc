#ui/ui.Plugins.Drag

Make a node draggable.

####Example

     node.plug(Drag, {
         proxy: true, // optimize performance
         handler: '.handler' // assign a handler for dragging
     });,
     node.plug(Drag, {
         area: 'areaSelector' // limit drag area to a certain area
     });

**Extends**: ui.Plugins.Plugin

##Properties

###ns

Plugin's namespace

**type**: String

###methods

Methods to be mix in host node

**type**: Array

###events

Events to be mix in host node

**type**: Array

###settings

Default settings

**type**: Object

##Methods

###render

Render the node

**Chainable**: true

###bindUI

Bind UI events like startDrag, watchDrag and endDrag

**Chainable**: true

###startDrag

**Returns**: _Boolean_ - 

**Params**:  
*   e _Event_

    


###watchDrag

**Returns**: _Boolean_ - 

**Params**:  
*   e _Event_

    


###endDrag

**Returns**: _Boolean_ - 

**Params**:  
*   e _Event_

    


###disableDrag

Disable drag

**Chainable**: true
####Example

     node.plug(Drag);
     // do something
     // ...
     node.disableDrag();

###enableDrag

Enable drag

**Chainable**: true
####Example

     node.plug(Drag);
     // do something
     // ...
     node.enableDrag();

###createProxy

Create proxy element

**Returns**: _JQuery_ - Proxy element

###removeProxy

Remove proxy element

**Chainable**: true

###enableProxy

Use proxy element instead of real element when dragging. This will improve performance effectively when real element is complex. Shortcut to set('proxy', proxy).

**Chainable**: true

**Params**:  
*   proxy _Boolean|String|jQuery|documentElement_

    Assign proxy element

####Example

     node.plug(Drag);
     // do something
     // ...
     node.enableProxy();

###disableProxy

Disable using proxy element. Shortcut to set('proxy', false).

**Chainable**: true
####Example

     node.plug(Drag, {
         proxy: true
     });
     // do something
     // ...
     node.disableProxy();

###setDragArea

Set draggable area

**Chainable**: true

**Params**:  
*   area _Object|jQuery|documentElement_

    Limited draggable area. Exactly positions of top, right, bottom and left or jQuery object/document element are ok.
    * top _Number_ - 
    * right _Number_ - 
    * bottom _Number_ - 
    * left _Number_ - 

####Example

     node.plug(Drag);
     // do something
     // ...
     node.setDragArea('restrictAreaSelector');,
     node.plug(Drag);
     // do something
     // ...
     // restrict to a square area width and height of which are both 100px
     node.setDragArea({
         top: 0,
         bottom: 100,
         left: 0,
         right: 100
     });

###remove

Remove drag, including clear proxy element

##Events

###beforeDrag

Fired befor drag starts

**Params**:  
*   dd _ui.Plugins.Drag_Instance of drag plugin instance
*   pageX _Number_Event's x direction location(pageX)
*   pageY _Number_Event's y direction location(pageY)
*   left _Number_Position left
*   top _Number_Position top


###drag

Fired when dragging

**Params**:  
*   dd _ui.Plugins.Drag_Instance of drag plugin instance
*   pageX _Number_Event's x direction location(pageX)
*   pageY _Number_Event's x direction location(pageY)
*   left _Number_Position left
*   top _Number_Position top


###drag

Fired when drag ends

**Params**:  
*   dd _ui.Plugins.Drag_Instance of drag plugin instance
*   pageX _Number_Event's x direction location(pageX)
*   pageY _Number_Event's x direction location(pageY)
*   left _Number_Position left
*   top _Number_Position top


###beforeDrop

Fired before drop

**Params**:  
*   dd _ui.Plugins.Drag_Instance of drag plugin instance
*   pageX _Number_Event's x direction location(pageX)
*   pageY _Number_Event's x direction location(pageY)
*   left _Number_Position left
*   top _Number_Position top


###drop

Fired when drop

**Params**:  
*   dd _ui.Plugins.Drag_Instance of drag plugin instance
*   pageX _Number_Event's x direction location(pageX)
*   pageY _Number_Event's x direction location(pageY)
*   left _Number_Position left
*   top _Number_Position top


###afterDrop

Fired after drop

**Params**:  
*   dd _ui.Plugins.Drag_Instance of drag plugin instance
*   pageX _Number_Event's x direction location(pageX)
*   pageY _Number_Event's x direction location(pageY)
*   left _Number_Position left
*   top _Number_Position top


