#ui/ui.Nodes.Node

All ui components' base. All jQuery methods and template engine are mixed in.

####Example

     new Node('#someElement'); // Turn element, which id is 'someElement', into a node,
     // jQuery object or Node object or document element object are all acceptable
     new Node($('#someElement'));
     new Node(new Node('#someElement'));
     new Node(document.getElementById('someElement'));

**Extends**: lang.Class  
**Uses**: 
* lib.jQuery
* util.Attributes
* lang.Inject


##Methods

###$

###jQuery

###template

###mergeOptions

Merge options with defaults and cache to node.opts

**Chainable**: true

**Params**:  
*   opts _Object_

    Options to be merged

####Example

     node.mergeOptions({
         //options
     });

###render

Render node
Most node needs overwritten this method for own logic

**Chainable**: true

###setElement

Set node's $el. $el is the base of a node ( UI component )
Cautious: direct change of node.$el may be dangerous

**Chainable**: true

**Params**:  
*   el _String|documentElement|jQuery|Node_

    The element to be core $el of the node


###delegateEvents

Delegate events to node

**Chainable**: true

**Params**:  
*   events _Object_

    Events to be delegated

####Example

     node.delegateEvents({
         'click .child': function(){
             alert('child clicked');
         }
     });

###defaultActions

All default actions bound to node's $el

###initEvents

Bind options.events

**Chainable**: true

**Params**:  
*   delegate _Object_

    Object to be apply as this in callback


###initElements

Find this.elements, wrap them with jQuery and cache to this, like this.$name

**Chainable**: true

###prop

Node element's property getter and setter

**Params**:  
*   name _String_

    Property name
*   value __

    Property value, if you are using getter mode, leave it blank


###trigger

Event trigger

**Returns**: _Boolean_ - Prevent default actions or not

**Params**:  
*   type _String_

    Event type
*   event _jQuery.Event_

    Original event
*   data _Object_

    Additional data as arguments for event handlers


###plug

Plug a plugin to node

**Chainable**: true

**Params**:  
*   Plugin _Plugin_

    Plugin class, not instance of Plugin
*   opts _Object_

    Options for plugin
    * ns _String_ - Namespace of Plugin

####Example

     node.plug(Drag);,
     node.plug(Drag, {
         //plugin options
         handler: '.handler',
         proxy: true
     });

###unplug

Unplug a plugin

**Chainable**: true

**Params**:  
*   ns _String|Object_

    Namespace of Plugin or Plugin object

####Example

     node.unplug('Drag'); || node.unplug(Drag);

###remove

Remove node and unplug all plugins. 'onUnload' event will be triggered.

**Chainable**: true

##Events

###load

Fire when node initialized

**Params**:  
*   event _Event_JQuery event
*   node _Node_Node object


###onUnload

Fire when node removed

**Params**:  
*   event _Event_JQuery event
*   node _Node_Node object


