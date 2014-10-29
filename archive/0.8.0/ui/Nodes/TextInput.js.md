#ui/ui.Nodes.TextInput

Base text input component

####Example

     new TextInput({
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
     new TextInput({
         selector: 'input[name=abc]',
         value: 'hello',
         readonly: true,
         disabled: true
     });

**Extends**: ui.Nodes.Node

##Properties

###events

Nodes default UI events

**type**: Object

###settings

Default settings

**type**: Object

##Methods

###render

Render the node

**Chainable**: true

###error

Show error style

**Chainable**: true

###error

Show error style

**Chainable**: true

###error

Show error style

**Chainable**: true

###clearError

Clear error style

**Chainable**: true

###count

Count content string's length

**Returns**: _Number_ - Length of content string
####Example

     node.count(); // returns value string's length

###placeholder

modify placeholder

###val

get or set value

###value

get or set value

###remove

Remove not only the node itself, but the whole wrap including placeholder label

**Chainable**: true

###_inputFocus

Focus the input

**Chainable**: true

###_inputBlur

Blur the input

**Chainable**: true

###_inputMouseenter

Mouseenter the input

**Chainable**: true

###_inputMouseleave

Mouseleave the input

**Chainable**: true

###_inputPropertychange

Propertychange the input

**Chainable**: true

###_setPlaceholder

Set placeholder property. For early version of IE, use label to simulate placeholder

**Chainable**: true

**Params**:  
*   placeholder __

    


###renderAll

**Returns**: _Array_ - Array of nodes that is rendered

**Params**:  
*   selector _String|documentElement|jQuery|Node_

    input[type=password], input[type=email], input[type=email], input[type=search], input[type=tel], input[type=url]'] Selector of node
*   opts _Object_

    options for node

####Example

     var nodeArray = TextInput.renderAll();,
     var nodeArray = TextInput.renderAll('.textinput');,
     var nodeArray = TextInput.renderAll({
         //options
         events: {
             error: function(e, error){
                 alert(error.message);
             }
         }
     });,
     var nodeArray = TextInput.renderAll('.textinput', {
         //options
         events: {
             error: function(e, error){
                 alert(error.message);
             }
         }
     });

##Events

###error

Fire when check state changed and failed validation

**Params**:  
*   JQuery _Event_event
*   Validation _Error_result


