#util.Event

[mixable] Common event handler. Can be extended to any object that wants event handler.

####Example

     // mix in instance example
     // assume classInstance is instance of lang.Class or its sub class

     // use class's mix method
     classInstance.mix(Attribute);

     // set your attributes
     classInstance.set('a', 1);
     classInstance.get('a') // returns 1,
     // extend a sub class example

     // use class's extend method
     var SubClass = Class.extend(Attribute, {
         // some other methods
         method1: function(){
         },

         method2: function(){
         }
     });

     // initialize an instance
     classInstance = new SubClass;

     // set your attributes
     classInstance.set('a', 1);
     classInstance.get('a') // returns 1

##Methods

###on

Bind events

**Chainable**: true

**Params**:  
*   eventNames _String_

    Event names that to be subscribed and can be separated by a blank space
*   callback _Function_

    Callback to be invoked when the subscribed events are published


###off

Unbind events

**Chainable**: true

**Params**:  
*   eventNames _String_

    Event names that to be subscribed and can be separated by a blank space
*   callback _Function_

    Callback to be invoked when the subscribed events are published. Leave blank will unbind all callbacks on this event


###trigger

Publish an event

**Chainable**: true

**Params**:  
*   eventName _String_

    
*   arg __

    Arguments to be passed to callback function. No limit of arguments' length


###one

Bind event callback to be triggered only once

**Chainable**: true

**Params**:  
*   eventNames _String_

    Event names that to be subscribed and can be separated by a blank space
*   callback _Function_

    Callback to be invoked when the subscribed events are published. Leave blank will unbind all callbacks on this event


