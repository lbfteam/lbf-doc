#ui/ui.widget.Dropdown.Menu

Simple lbf-dropdown component for select-like cases

####Example

     new Dropdown({
         container: 'someContainerSelector',
         trigger: 'JQ selector'.
         content: '',
         show {
             mode: 'click',
             delay: 0,
             effect: function(){
                 this.show();
             }
         },
         hide: {
             delay: 0,
             effect: function(){
                 this.hide();
             }
         },
         events: {
             load: function(){},
             unload: function(){},
             show: function(){},
             hide: function(){},
             enable: function(){},
             disable: function(){}
         }
     });

**Extends**: ui.Nodes.Popup

##Properties

###settings

Default settings

**type**: Object

##Methods

###render

Render the node

**Chainable**: true

###resize

Resize width or height components, depending on drop direction

###show

Show option panel, which lists lbf-dropdown's all items

**Chainable**: true

###hide

Hide option panel, which lists lbf-dropdown's all items

**Chainable**: true

