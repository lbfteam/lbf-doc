#ui/ui.Nodes.Textarea

Base textarea component

####Example

     new Textarea({
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
     new Textarea({
         selector: 'textarea[name=abc]',
         value: 'hello',
         readonly: true,
         disabled: true
     });

**Extends**: ui.Nodes.Node

##Properties

###elements

Nodes default UI element，this.$element

**type**: Object

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

###prop

Setter and getter of node's property, including some cross-browser solutions.

**Chainable**: true

**Params**:  
*   property _String_

    Property name
*   value _String|Number|Boolean_

    Property value

####Example

     node.prop('maxlength', 200);,
     node.prop('placeholder', 'default tip when empty');

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

###remove

Remove not only the node itself, but the whole wrap including placeholder label

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

###prepend

Prepend text

**Chainable**: true

**Params**:  
*   text _String_

    Text to be prepended


###append

Append text

**Chainable**: true

**Params**:  
*   text _String_

    Text to be appended


###insert

Insert text to assigned position

**Chainable**: true

**Params**:  
*   position _Number_

    Position to insert text
*   text _String_

    Text to be inserted


###_textareaFocus

Focus the textarea

**Chainable**: true

###_textareaBlur

Blur the textarea

**Chainable**: true

###_textareaMouseenter

Mouseenter the textarea

**Chainable**: true

###_textareaMouseleave

Mouseleave the textarea

**Chainable**: true

###_textareaPropertychange

Propertychange the textarea

**Chainable**: true

###_setPlaceholder

Set placeholder property

**Chainable**: true

**Params**:  
*   placeholder _String_

    


###_setMaxlength

Set maxlength property. For early version of IE and opera, manually limit string length

**Chainable**: true

**Params**:  
*   maxlength _Number_

    


###renderAll

**Returns**: _Array_ - Array of nodes that is rendered

**Params**:  
*   selector _String|documentElement|jQuery|Node_

    Selector of node
*   opts _Object_

    options for node

####Example

     var nodeArray = Textarea.renderAll();,
     var nodeArray = Textarea.renderAll('.textarea');,
     var nodeArray = Textarea.renderAll({
         //options
         events: {
             error: function(e, error){
                 alert(error.message);
             }
         }
     });,
     var nodeArray = Textarea.renderAll('.textarea', {
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


