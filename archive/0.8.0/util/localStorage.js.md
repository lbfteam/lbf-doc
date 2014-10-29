#util/util.localStorage.localStorage

LocalStorage with compatible solution for IE
use cookie as IE solution
user data in IE, because of secure concern, is limited to same dir which is not suitable for common uses
Cautions:
 Storage events haven't been add to compatible solution
 Non-IE browser counts on window.localStorage only, it means this tool is useless to those old non-IE browsers

##Properties

###length

The number of key/value pairs currently present in the list associated with the localStorage.

**type**: 

##Methods

###key

Get the value of the nth key in the localStorage list

**Returns**: _String | Null_ - 

**Params**:  
*   index _Number_

    Index of key


###getItem

Get the current value associated with the given key.

**Returns**: _String | Null_ - 

**Params**:  
*   key _String_

    


###setItem

Set ( add/update ) value of the given key
If it couldn't set the new value, the method must throw a QuotaExceededError exception.
Setting could fail if, e.g., the user has disabled storage for the site, or if the quota has been exceeded.

**Params**:  
*   key _String_

    
*   value _String_

    


###removeItem

Remove the key/value pair with the given key

**Params**:  
*   key _String_

    


###clear

Empty all key/value pairs

