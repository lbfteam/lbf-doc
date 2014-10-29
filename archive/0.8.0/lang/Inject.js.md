#lang/lang.Inject

[mixable] Inject function before/after a method

##Methods

###inject

Inject function

**Returns**: _lang.MethodInjection_ - 

**Params**:  
*   type _String_

    Inject before or after
*   method _String_

    Name of method which to be injected
*   injection _Function_

    The function to be injected before or after the original method


###restore

Restore a method, revert injections

**Returns**: _lang.MethodInjection_ - 

**Params**:  
*   method _String_

    Name of method injected


###before

Inject function before original method

**Returns**: _lang.MethodInjection_ - 

**Params**:  
*   method _String_

    Name of method which to be injected
*   injection _Function_

    The function to be injected before or after the original method


###after

Inject function after original method

**Returns**: _lang.MethodInjection_ - 

**Params**:  
*   method _String_

    Name of method which to be injected
*   injection _Function_

    The function to be injected before or after the original method


