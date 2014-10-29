#ui/ui.widget.Editor.FacePlugin

Face plugin for editor. Select a face icon and insert its code to content

####Example

     editor.plug(FacePlugin);

**Extends**: ui.Plugins.Plugin

##Properties

###ns

Plugin's namespace

**type**: String

##Methods

###render

Render face display and add to editor's top panel

**Chainable**: true

###bindUI

Bind UI events for face panel

**Chainable**: true

###addFace

Add face code to content and trigger FacePlugin.addFace event

**Chainable**: true

**Params**:  
*   face _String_

    


##Events

###FacePlugin.addFace

Fire when a face code inserted, to editor, not plugin itself

**Params**:  
*   event _Event_JQuery event
*   face _String_Face code


