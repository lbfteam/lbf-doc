#ui/ui.widget.Panel.ConfirmPanel

Confirm component. Panel with two buttons, one for confirmation and the other for cancel

####Example

     new ConfirmPanel({
         container: 'someContainerSelector',
         title: 'hello'
     });,
     new ConfirmPanel({
         title: 'hello',
         modal: false,
         drag: false,
         zIndex: 10,
         centered: true,
         events: {
             ok: function(){
                 alert('ok');
                 this.remove();
             },
             cancel: function(){
                 alert('cancel');
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

