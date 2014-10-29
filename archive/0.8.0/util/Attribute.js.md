#util.Attribute

[mixable] Common attributes handler. Can be extended to any object that wants event handler.

####Example

     // mix in instance example
     // assume classInstance is instance of lang.Class or its sub class

     // use class's mix method
     classInstance.mix(Event);

     // watch events
     classInstance.bind('someEvent', function(){
         // do sth
     });,
     // extend a sub class example

     // use class's extend method
     var SubClass = Class.extend(Event, {
         // some other methods
         method1: function(){
         },

         method2: function(){
         }
     });

     // initialize an instance
     classInstance = new SubClass;

     // watch events
     classInstance.bind('someEvent', function(){
         // do sth
     });

##Methods

###set

Set an attribute

**Chainable**: true

**Params**:  
*   attr _String_

    Attribute name
*   value _*_

    
*   options _Object_

    Other options for setter
    * silence _Boolean_ - Silently set attribute without fire change event


###get

Get attribute

**Returns**: _*_ - 

**Params**:  
*   attr _String_

    Attribute name


###attributes

Get all attributes.
Be sure it's ready-only cause it's not a copy!

**Returns**: _Object_ - All attributes

###addValidate

Add validate for attributes

**Chainable**: true

**Params**:  
*   validate _Function_

    Validate function, return false when failed validation

####Example

     instance.addValidate(function(event, attrs){
         if(attrs.someAttr !== 1){
             return false; // return false when failed validation
         }
     });

###removeValidate

Remove a validate function

**Chainable**: true

**Params**:  
*   validate _Function_

    Validate function

####Example

     instance.removeValidate(someExistValidate);

###validate

Validate all attributes

**Returns**: _Boolean_ - Validation result, return false when failed validation

##Events

###change:attr

Fire when an attribute changed
Fire once for each change and trigger method is needed

**Params**:  
*   JQuery _Event_event
*   Current _Object_attributes


###change

Fire when attribute changed
Fire once for each change and trigger method is needed

**Params**:  
*   JQuery _Event_event
*   Current _Object_attributes


