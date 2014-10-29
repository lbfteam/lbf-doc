#ui/ui.widget.Switchable.TabView

Simple tab view.

####Example

     new TabView({
         container: 'someContainerSelector',

         defaultIndex: 0,

         // specialize tab and content html
         itemSettings: {
             tabTemplate: '<a class="LBF-UI-widget-Switchable-tab" href="javascript:;"><%==tab%></a>',
             contentTemplate: '<div class="LBF-UI-widget-Switchable-tabContent"><%==content%></div>'
         },

         // all items
         items: [
             {
                 tab: 'tab1',
                 content: 'tab1 content',

                 // use different template for a specific tab
                 tabTemplate: '<a class="LBF-UI-widget-Switchable-tab" href="javascript:;"><%==tab%></a>',
                 contentTemplate: '<div class="LBF-UI-widget-Switchable-tabContent"><%==content%></div>'
             },
             {
                 tab: 'tab2',
                 content: 'tab2 content'
             }
         ]
     });

**Extends**: ui.widget.Switchable.Switchable  
**Uses**: 
* util.Attribute


##Properties

###elements

Nodes default UI element，this.$element

**type**: Object

###events

Nodes default UI events

**type**: Object

##Methods

###_switchTab

switch tab - 私有方法是不是以_开头命名，对外应该暴露selectItem而不是switchTab

###clickCloseTab

Click close button

**Chainable**: true

###mouseOverTab

Mouse hover tab

**Chainable**: true

###mouseOutTab

Mouse out of tab

**Chainable**: true

