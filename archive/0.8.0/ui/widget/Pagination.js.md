#ui/ui.widget.Pagination

Extensive pagination with plenty options, events and flexible template

####Example

     new Pagination({
         container: 'someContainerSelector',
         page: 2,
         startPage: 1,
         endPage: 10
     });,
     new Pagination({
         container: 'someContainerSelector',
         page: 2,
         startPage: 1,
         endPage: 10,
         headDisplay: 2,
         tailDisplay: 2,
         maxDisplay: 3,
         prevText: '&lt;上页',
         nextText: '下页&gt;',
         tagName: 'span',
         ellipsis: '--',
         events: {
             change: function(e, options){
                 alert('changed');
             }
         }
     });

**Extends**: ui.Nodes.Node

##Properties

###events

Widget default UI events

**type**: Object

###settings

Default settings

**type**: Object

##Methods

###mergeOptions

Overwritten mergeOptions method

**Chainable**: true

###render

Render pagination and append it to it's container if assigned

**Chainable**: true

###page

Page redirection

**Chainable**: true

**Params**:  
*   page _Number_

    Target page


###focusInput

Select the input's value

**Chainable**: true

###jumpBykeyboard

Bind the keyboard events

**Chainable**: true

###prePage

Redirect to first page

**Chainable**: true

###prePage

Redirect to previous page

**Chainable**: true

###nextPage

Redirect to next page

**Chainable**: true

###lastPage

Redirect to last page

**Chainable**: true

