#ui/ui.widget.Switchable.Switchable

Simple switchable for switching views, slides etc.

####Example

     new Switchable({
         container: 'someContainerSelector',

         select: 0,

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

**Extends**: ui.Nodes.Node  
**Uses**: 
* util.Attribute


##Properties

###elements

Nodes default UI element，this.$element

**type**: Object

###events

Nodes default UI events

**type**: Object

###settings

Default settings

**type**: Object

##Methods

###render

Render the switchable and add items

**Chainable**: true

###addItem

Add a tab

**Chainable**: true

**Params**:  
*   itemSettings __

    Tab options
    * tab _String|jQuery|documentElement_ - Tab's innerHTML
    * content _String|jQuery|documentElement_ - Tab's innerHTML
    * tabTemplate _String_ - Template for the tab
    * contentTemplate _String_ - Template for the tab content
*   options _Object_

    Additional options
    * silence _Boolean_ - Use silence mode, won't fire addItem event when set silence true

####Example

     switchable.addItem({
         tab: 'tab1',
         content: 'tab1 content',

         // use different template for a specific tab
         tabTemplate: '<a class=".lbf-switchable-tab" href="javascript:;"><%==tab%></a>',
         contentTemplate: '<div class=".lbf-switchable-tab-content"><%==content%></div>'
     });

###removeItem

Remove a tab by it's index

**Chainable**: true

**Params**:  
*   index _Number_

    Index of tab to be removed


###selectItem

Select a tab by it's index

**Chainable**: true

**Params**:  
*   index _Number_

    Index of tab to be selected. Pass in a integer that is out of items' range means select nothing


###$contents

Click a tab by it's click event

**Chainable**: true

**Params**:  
*   event _Event_

    The event fire on it


###selectByTab

Select a tab by it's document element

**Chainable**: true

**Params**:  
*   node _DocumentElement_

    


###_switchTab

Switch the selected tab and the one to be selected. Tip: you can add additional effects of switching tab by overwriting this method

**Chainable**: true

**Params**:  
*   index _Number_

    The tab index to be selected


###getCurrentTab

Get current tab

**Returns**: _Object_ - Contains $tab and $content

###indexOf

Get the index of the items

**Returns**: _Number_ - Not found returns -1

**Params**:  
*   node _DocumentElement_

    


##Events

###addItem

Fired when a tab is add and options.silence is not true

**Params**:  
*   event _Event_JQuery event
*   node _Node_Node object
*   tab _Object_Collection of tab and content element
    * $tab _JQuery_ - Tab handler's jQuery instance
    * $content _JQuery_ - Tab content's jQuery instance


###removeItem

Fire when a tab is removed

**Params**:  
*   event _Event_JQuery event
*   node _Node_Node object
*   tab _Object_Collection of tab and content element
    * $tab _JQuery_ - Tab handler's jQuery instance
    * $content _JQuery_ - Tab content's jQuery instance


###selectItem

Fire when select a tab. When select the selected tab.

**Params**:  
*   event _Event_JQuery event
*   index _Number_Index of newly selected tab
*   node _Node_Node object
*   tab _Object_Collection of tab and content element
    * $tab _JQuery_ - Tab handler's jQuery instance
    * $content _JQuery_ - Tab content's jQuery instance
*   lastTab _Object_Collection of last selected tab and content element
    * $tab _JQuery_ - Tab handler's jQuery instance
    * $content _JQuery_ - Tab content's jQuery instance


