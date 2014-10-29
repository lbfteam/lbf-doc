#lang/lang.Class

Base Class

####Example

     // SubClass extends Class
     var SubClass = Class.extend({
         // overwritten constructor
         initialize: function(){

         },

         someMethod: function(){
         }
     });

     // add static methods and attributes
     SubClass.include({
         staticMethod: function(){
         },

         staticAttr: 'attrValue'
     });

     // Extension is always available for sub class
     var SubSubClass = SubClass.extend({
         // methods to be extended
     });

##Properties

###constructor

Instance's constructor, which initialized the instance

**type**: {lang.Class}

###superclass

Superclass of the instance

**type**: {lang.Class}

###superclass

Superclass the Class inherited from

**type**: {lang.Class}

##Methods

###mixin

Mix in methods and attributes. Instead of inherit from base class, mix provides a lighter way to extend object.

**Chainable**: true

**Params**:  
*   mixin _Object_

    The object to be mixed in

####Example

     var someInstance = new Class;

     someInstance.mix({
         sayHello: function(){
             alert('hello');
         }
     });

###inherit

Extend a sub Class

**Chainable**: true

**Params**:  
*   ext _Object_

    Prototype extension. Multiple exts are allow here.

####Example

    var SubClass = Class.extend(ext1);,
     // multiple extensions are acceptable
     var SubClass = Class.extend(ext1, ext2, ...);

###include

Extend static attributes

**Chainable**: true

**Params**:  
*   included _Object_

    Static attributes to be extended

####Example

    Class.include(include1);,
    // multiple includes are acceptable
    Class.include(include1, include2, ...);

###extend

Inherit base class and add/overwritten some new methods or properties.
This is a deprecated method for it's easily misunderstood. It's just for backward compatible use and will be removed in the near future.
We recommend inherit for a replacement

