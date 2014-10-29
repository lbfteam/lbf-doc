#ui/ui.Plugins.Plugin

Plugin base

**Extends**: ui.Nodes.Node

##Properties

###ns

Plugin's namespace

**type**: String

##Methods

###initEvents

Bind options.events

**Chainable**: true

###injectMethods

Inject overlay's methods to host

**Chainable**: true

###addMethods

Add methods to host node

**Chainable**: true

**Params**:  
*   methods _String[]_

    Add methods to host


###bindEvents

Add events to host node

**Chainable**: true

**Params**:  
*   events _Array[]_

    added to the host


###bind

Bind events

**Chainable**: true

###unbind

Unbind events

**Chainable**: true

###trigger

Trigger event

**Chainable**: true

###remove

Remove plugin, including unplug it from it's host

**Chainable**: true

###remove

Unplug it from it's host

**Chainable**: true

