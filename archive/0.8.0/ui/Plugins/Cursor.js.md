#ui/ui.Plugins.Cursor

Add cursor related methods to host. Usually useful to input and textarea.

####Example

     hostNode.plug(Cursor);

**Extends**: ui.Plugins.Plugin

##Properties

###ns

Plugin's namespace

**type**: String

###methods

Methods to be mix in host node

**type**: Array

##Methods

###getCursorPosition

Get cursor's position

**Returns**: _Number_ - Index out of content string at cursor's position
####Example

     hostNode.plug(Cursor);
     // do something
     // ...
     hostNode.getCursorPosition(); // returns the position of cursor

###selectRange

Select a range

**Chainable**: true
####Example

     hostNode.plug(Cursor);
     // do something
     // ...
     hostNode.selectRange(2, 10); // select from 2nd char to 10th

