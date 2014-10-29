#lang.proxy

Proxy function with assigned context.
By proxy function's context, inner function will get the assigned context instead of the invoking one

####Example

     var a = {
         x: 1,
         fn: function(){
             alert(this.x);
         }
     };

     // this point to a
     a.fn(); // alert 1

     var b = { x: 2};
     a.fn = proxy(a.fn, b);

     // this point to b
     a.fn(); // alert 2

