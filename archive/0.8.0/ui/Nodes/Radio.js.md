#ui/ui.Nodes.Radio

Base radio component

####Example

     new Radio({
         container: '#someContainer',
         checked: true,
         disabled: true,
         validate: function(event, checkState){
             if(!checkState){
                 return new Error('must be checked');
             }
         },
         events: {
             click: function(){
                 alert('clicked');
             },
             error: function(){
                 alert('error');
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

###getProp

Get a property

**Returns**: _String_ - property value

**Params**:  
*   propName _String_

    


###setProp

Get a property

**Chainable**: true

**Params**:  
*   propName _String_

    
*   propValue _String_

    


###error

Show error style

**Chainable**: true

###clearError

Clear error style

**Chainable**: true

###remove

Remove not only the node itself, but the whole wrap

**Chainable**: true

###renderAll

**Returns**: _Array_ - Array of nodes that is rendered

**Params**:  
*   selector _String|documentElement|jQuery|Node_

    Selector of node
*   opts _Object_

    options for node

####Example

     var nodeArray = Radio.renderAll();,
     var nodeArray = Radio.renderAll('.radio');,
     var nodeArray = Radio.renderAll({
         //options
         events: {
             error: function(e, error){
                 alert(error.message);
             }
         }
     });,
     var nodeArray = Radio.renderAll('.radio', {
         //options
         events: {
             error: function(e, error){
                 alert(error.message);
             }
         }
     });

##Events

###checked

Fire when the checkbox is checked or unchecked

###disabled

Fire when the checkbox is disabled or enabled

###error

Fire when check state changed and failed validation

**Params**:  
*   JQuery _Event_event
*   Validation _Error_result


