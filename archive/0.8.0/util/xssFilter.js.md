#util/util.xssFilter

Filter all xss chars and replace them with legal ones.

##Methods

###htmlEncode

Filter used to filter the innerHTML and attributes of tag

**Returns**: _String_ - 

**Params**:  
*   str __

    


###uriComponentEncode

Filter used to filter the url parameters

**Returns**: _String_ - 

**Params**:  
*   str __

    

####Example

    // in fact we don't have to encode the whole url, but the parameters
    $('#needFilter).attr('src', xssFilter.uriComponentEncode('untrusted uri'));

###cssEncode

Filter used to filter the css code, mainly used in php

**Returns**: _String_ - 

**Params**:  
*   str __

    

####Example

    <style>
        #foo[id ~= 'xssFilter.cssEncode("untrusted data")'] { background-color: pink;}
    </style>

###cssColorValidate

Filter used to filter the css color, mainly used by php

**Returns**: _Boolean_ - 

**Params**:  
*   str __

    

####Example

    <style>
        #foo {
            background-color: xssFilter.cssColorValidate('untrusted data');
        }
    </style>

