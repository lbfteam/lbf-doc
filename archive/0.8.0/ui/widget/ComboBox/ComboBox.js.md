#ui/ui.widget.Menu

Simple lbf-combobox component for select-like cases

####Example

     new ComboBox({
         container: 'someContainerSelector',
         options: [
             {
                 text: 'text1',
                 value: 1
             },
             {
                 text: 'text2',
                 value: 2
             },
             {
                 text: 'text3',
                 value: 3
             }
         ],
         defaultIndex: 2,
         events: {
             select: function(event, name, value){
                 alert('select');
             },

             change: function(event, name, value, oldValue){
                 alert('change');
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

###renderOptionPanel

Render options panel

**Chainable**: true

###selectItem

Invoke When an item is selected

**Chainable**: true

**Params**:  
*   event _Event_

    


###select

Select a item by index or function

**Chainable**: true

**Params**:  
*   index _Number|Function_

    The index or comparator of item to be selected, or a locate function
    * value _*_ - When index is a filter function, the 1st argument is item's value
    * name _*_ - When index is a filter function, the 2nd argument is item's name

####Example

     lbf-combobox.select(0); // select the 1st item,
     // select by a filter function
     lbf-combobox.select(function(value, name){
         return value < 10; // filter out the 1st item that lower than 10
     });

###hide

Show optionPanel

**Chainable**: true

###hide

Hide optionPanel

**Returns**: _*_ - 

###addOption

add option

**Chainable**: true

**Params**:  
*   option _Object_

    Options of combobox option
*   options.value __

    Value of option
*   options.text __

    Text of option
*   pos _Number_

    The position options to be inserted


###updateOptions

update option

**Chainable**: true

**Params**:  
*   option _Object_

    Options of combobox option
*   index _Number_

    Index of option to be updated


###removeOptionByValue

Remove option by value

**Chainable**: true

**Params**:  
*   value __

    Value of option to be removed
*   [removeAll _Boolean_

    = false] Remove all options that have the value


###removeOptionByIndex

Remove option by value

**Chainable**: true

**Params**:  
*   index __

    Index of option to be removed


###clearAllOption

Clear all the options

**Returns**: _*_ - 

###reset

Reset options

**Chainable**: true

###index

Get index of option by value

**Returns**: _Number_ - Index of the option which has the given value. No match returns -1. Multiple returns index of the first one.

**Params**:  
*   value __

    Value of option


###val

Get selected item's value

**Returns**: _*_ - 

##Events

###select

Fire when an item selected, no matter it changes or not

**Params**:  
*   event _Event_JQuery event
*   newValue __New value
*   oldValue __Old value


###change

Fire when value changed

**Params**:  
*   event _Event_JQuery event
*   newValue __New value
*   oldValue __Old value


###reset

Fired when options have been reset

**Params**:  
*   event _jQuery.Event_


