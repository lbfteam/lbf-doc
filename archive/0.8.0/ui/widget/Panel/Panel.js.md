#ui/ui.widget.Panel.Panel

Base panel component

####Example

     // simple demo
     new Panel({
         container: 'someContainerSelector',
         title: 'hello',
         msg: 'hello LBF'
     });,
     // full options demo
     new Panel({
         title: 'hello',
         content: 'hello LBF',
         modal: false,
         drag: false,
         zIndex: 10,
         centered: true,
         buttons: [
             // button option @see ui.Nodes.Button
             {
                 value: 'confirm',
                 type: 'strong',
                 events: {
                     click: function(){
                         // context here is panel itself
                         // feel free to use this
                         this.remove();
                     }
                 }
             }
         ],
         events: {
             close: function(){
                 alert('close');
             }
         }
     });

**Extends**: ui.Nodes.Popup  
**Uses**: 
* ui.Plugin.Drag
* ui.Plugin.Overlay


##Properties

###elements

快捷访问，this.$element

**type**: Object

###settings

Default settings

**type**: Object

##Methods

###render

Render panel and initialize events and elements

**Chainable**: true

###addButton

Add a button to panel's buttons

**Returns**: _ui.Nodes.Button_ - 

**Params**:  
*   opts _Object_

    @see ui.Nodes.Button

####Example

     // button option @see ui.Nodes.Button
     node.addButton({
         text: 'confirm',
         type: 'strong',
         events: {
             click: function(){
                 // context here is panel itself
                 // feel free to use this
                 this.remove();
             }
         }
     });

###remove

Remove node and it's buttons

**Chainable**: true

##Events

###exit

Fired when esc is pressed as the panel is shown

