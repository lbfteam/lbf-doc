#util/util.Style

Add stylesheet(style or link tag) page

##Methods

###add

Add style tag to DOM

**Returns**: _JQuery_ - JQuery object of style tag

**Params**:  
*   name _String_

    Style name
*   cssText _String_

    Style to be add


###load

Load remote CSS file with link tag

**Returns**: _lib.jQuery_ - JQuery object of link tag

**Params**:  
*   name _String_

    Style name
*   url _String_

    CSS file's url


###remove

Remove style or link tag by its name

**Chainable**: true

**Params**:  
*   name _String_

    Style or link name


