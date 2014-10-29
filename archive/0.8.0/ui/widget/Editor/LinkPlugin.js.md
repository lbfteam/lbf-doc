#ui/ui.widget.Editor.LinkPlugin

Link plugin for editor

####Example

     editor.plug(LinkPlugin, {
         validate: function(event, value){
             // filter blank string
             if(value.replace(/\s/g/, '').length === 0){
                 // suggest return error object
                 return new Error('No empty string is allowed');
             }

             // if validated ( passed ), return null
             return null;
         }
     });

**Extends**: ui.Plugins.Plugin

##Properties

###wrapTemplate

Wrap template of link panel

**type**: String

###wrapTemplate

Link input panel template

**type**: String

###ns

Plugin's namespace

**type**: String

###settings

Default settings

**type**: Object

##Methods

###render

Render link panel

**Chainable**: true

###bindUI

Bind UI events

**Chainable**: true

###showPanel

Show link input panel

**Chainable**: true

###hidePanel

Hide link input panel

**Chainable**: true

###addLink

Add link text ( from input ) to editor

**Chainable**: true

**Params**:  
*   link _String_

    Link text


##Events

###LinkPlugin.validateError

Fire when adding an invalidate ( according to link input panel's validation ) link to editor

**Params**:  
*   event _Event_JQuery event
*   error _Error_Validation error
*   link _String_Link intended to add


###LinkPlugin.addLink

Fire when add an link to editor

**Params**:  
*   event _Event_JQuery event
*   link _String_Link text add to editor


