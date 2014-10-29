#lang.extend

Extend(copy) attributes from an object to another

####Example

     // plain extend
     // returns {a: 1, b:1}
     extend({a: 1}, {b: 1});

     // recursive extend
     var b = { x: 1};
     var ret = extend(true, {}, { b: b});
     b.x = 2;
     b.x !== ret.b.x;

