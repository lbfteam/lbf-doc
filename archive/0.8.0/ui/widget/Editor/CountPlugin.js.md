#ui/ui.widget.Editor.CountPlugin

Count plugin for editor. Specialized in content length counting.

####Example

     editor.plug(CountPlugin, {
         // 100 in max
         limit: 100,

         // count without blanks
         count: function(){
             var str = this.node.val(); // get content
             str.replace(/\s/g, ''); // remove all blanks
             return str.length;
         },

         // replace with a new template
         wordingTemplate: '<p>remaining <%=remain%></p>'
     });

**Extends**: ui.Plugins.Plugin

##Properties

###ns

Plugin's namespace

**type**: String

###settings

Default settings

**type**: Object

##Methods

###render

Render count display and add to editor's bottom panel

**Chainable**: true

###update

Update count display

**Chainable**: true

###count

Count host content's length. Can be overwrite to change count logic

**Returns**: _Number_ - 

###limit

Set limit num

**Chainable**: true

**Params**:  
*   num _Number_

    The limited max num


