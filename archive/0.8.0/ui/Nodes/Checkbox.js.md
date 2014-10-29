#ui/ui.Nodes.Checkbox

Base checkbox component

####Example

     new Checkbox({
         container: 'someContainerSelector',
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
             error: function(e, validateResult){
                 // handle error
                 alert(validateResult.message);
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

###renderAll

**Returns**: _Array_ - Array of nodes that is rendered

**Params**:  
*   selector _String|documentElement|jQuery|Node_

    Selector of nodes to be rendered
*   opts _Object_

    Options for node

####Example

     var nodeArray = Checkbox.renderAll();,
     var nodeArray = Checkbox.renderAll('.checkbox');,
     var nodeArray = Checkbox.renderAll({
         //options
         events: {
             error: function(e, error){
                 alert(error.message);
             }
         }
     });,
     var nodeArray = Checkbox.renderAll('.checkbox', {
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


