#util.Callbacks

Create a callback list (written in actory mode)
By default a callback list will act like an event callback list and can be
'fired' multiple times.
Borrowed from jQuery.Callbacks

####Example

 var list = Callbacks('once memory');

##Methods

###add

Add a callback or a collection of callbacks to the list

**Returns**: _util.Callbacks_ - 

###remove

Remove a callback from the list

**Returns**: _util.Callbacks_ - 

###has

Check if a given callback is in the list.
If no argument is given, return whether or not list has callbacks attached.

**Returns**: _util.Callbacks_ - 

###empty

Remove all callbacks from the list

**Returns**: _util.Callbacks_ - 

###disable

Have the list do nothing anymore

**Returns**: _util.Callbacks_ - 

###disabled

Is it disabled?

**Returns**: _util.Callbacks_ - 

###lock

Lock the list in its current state

**Returns**: _util.Callbacks_ - 

###locked

Is it locked?

**Returns**: _Boolean_ - 

###fireWith

Call all callbacks with the given context and arguments

**Returns**: _util.Callbacks_ - 

###fire

Call all the callbacks with the given arguments

**Returns**: _util.Callbacks_ - 

###fired

To know if the callbacks have already been called at least once

**Returns**: _util.Callbacks_ - 

