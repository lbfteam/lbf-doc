#ui/ui.widget.Panel.AlertPanel

Alert component. Panel with only a button for confirmation.

####Example

     new AlertPanel({
         container: 'someContainerSelector',
         title: 'hello',
         content: 'hello LBF'
     });,
     new AlertPanel({
         title: 'hello',
         content: 'hello LBF',
         modal: false,
         drag: false,
         zIndex: 10,
         centered: true,
         events: {
             ok: function(){
                 alert('ok');
                 this.remove();
             },
             close: function(){
                 alert('close');
                 this.remove();
             }
         }
     });

**Extends**: ui.widget.Panel.Panel

##Properties

###settings

Default settings

**type**: Object

##Events

###ok

Fire when confirm button is click

**Params**:  
*   event _Event_JQuery event
*   node _Node_Node object


