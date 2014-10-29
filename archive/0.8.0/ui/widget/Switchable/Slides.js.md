#ui/ui.widget.Switchable.Slides

Simple image slider for switching images.

####Example

     new Slides({
         container: 'someContainerSelector',

         defaultIndex: 0,

         // specialize tab and content html
         itemSettings: {
             tabTemplate: '<li class="lbf-slides-btn-item"><a class="lbf-slides-btn" href="javascript:;"><%==tab%></a></li>',
             contentTemplate: '<li class="lbf-slides-item"><%==content%></li>'
         },

         // all items
         items: [
             {
                 tab: 'tab1',
                 content: 'tab1 content',

                 // use different template for a specific tab
                 tabTemplate: '<li class="lbf-slides-btn-item"><a class="lbf-slides-btn" href="javascript:;"><%==tab%></a></li>',
                 contentTemplate: '<li class="lbf-slides-item"><%==content%></li>'
             },
             {
                 tab: 'tab2',
                 content: 'tab2 content'
             }
         ],

         viewportSize: 365
     });

**Extends**: ui.widget.Switchable.Switchable  
**Uses**: 
* util.Attribute


##Properties

###events

Delegate events for default UI action

**type**: 

###elements

Fast access to frequently used elements

**type**: 

###$tabs

Tab's container ( wrap )

**type**: 

###$tab

Tab

**type**: 

###$tabsBtn

Tab's button ( wrap )

**type**: 

###$contents

Content's container ( wrap )

**type**: 

###$contentItems

Content's items ( wrap )

**type**: 

###$prevBtn

Prevous button

**type**: 

###$nextBtn

Next button

**type**: 

##Methods

###update

Update all state and cache size for animations

**Chainable**: true

###switchTab

Switch the selected tab and the one to be selected. Tip: you can add additional effects of switching tab by overwriting this method

**Chainable**: true

**Params**:  
*   index _Number_

    The tab index to be selected


###mouseOverTab

Callback when mouse in a btn

**Params**:  
*   event _Event_

    


###_onMouseOutBtn

Callback when mouse out a btn

**Params**:  
*   event _Event_

    


###_onClickBtn

Callback when click a btn

**Params**:  
*   event _Event_

    


###startPlay

Start auto play sliders

**Chainable**: true

###stopPlay

Stop auto play sliders

**Chainable**: true

###prev

Switch to previous slider

**Chainable**: true

###next

Switch to next slider

**Chainable**: true

