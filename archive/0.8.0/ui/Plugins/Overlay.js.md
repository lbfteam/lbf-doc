#ui/ui.Plugins.Overlay

Create overlay that covers the host

####Example

     node.plug(Overlay, {
         container: 'whereTheOverlayGoes',
         backgroundColor: '#000',
         opacity: 0.1,
         zIndex: 10
     });

**Extends**: ui.Plugins.Plugin

##Properties

###ns

Plugin's namespace

**type**: String

###settings

Default settings

**type**: Object

###cssText

Default styles

**type**: String

##Methods

###render

Render the node

**Chainable**: true

###show

Show overlay

**Chainable**: true

###expand

Expand to full width & height as container

**Chainable**: true

###unplug

Unplug overlay from host

**Chainable**: true

