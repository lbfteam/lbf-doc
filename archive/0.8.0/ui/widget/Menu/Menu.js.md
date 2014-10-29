#ui/ui.widget.Menu

Simple menu component for select-like cases

####Example

       new Menu({
           container: $drawArea,
           items: [
               {
                   content: 'content1',
                   href: '#;',
                   value: '1',
                   direction: 'right',     //设置某级子菜单的方向
                   target: '_blank',
                   items: [
                       {
                           content: 'content11',
                           href: '#;',
                           value: '11',
                           items: [
                               {
                                   content: 'content111',
                                   href: '#;',
                                   value: '111',
                                   disabled: true,
                                   items: []
                               },
                               {
                                   type: 'split'
                               },
                               {
                                   content: 'content112',
                                   href: '#;',
                                   value: '112',
                                   items: []
                               },
                               {
                                   content: 'content113',
                                   href: '#;',
                                   value: '112',
                                   items: []
                               },
                               ......
                           ]
                       },
                       ......
                   ]
               },
               ......
           ],
           events: {
               select: function(event, conf, $item){
                   console.log(value);
                   console.log(conf);
                   console.log($item);
               }
           }
       });

**Extends**: ui.widget.Dropdown.Dropdown

##Properties

###settings

Default settings

**type**: Object

##Methods

###render

Render the node

**Chainable**: true

###initItems

init items

**Chainable**: true

###clickItem

Handler when item clicked

**Chainable**: true

**Params**:  
*   event _Event_

    


###mouseenterItem

Handler when mouseenter item

**Chainable**: true

**Params**:  
*   event _Event_

    


###mouseleaveMenu

Handler when mouseleave menu

**Chainable**: true

**Params**:  
*   event _Event_

    


###selectItem

Handler when item selected

**Chainable**: true

###select

Invoke When an item is selected

**Chainable**: true

**Params**:  
*   conf _Object_

    Config of selected item
*   $item _JQuery_

    JQuery instance of item to be selected


###getItemByIndex

Get item by index

**Returns**: _Object_ - JQuery instance of item and subMenu

**Params**:  
*   index _Number|Array_

    Index of item, array means item from sub menu


###disableItem

Disable item by index, multiple indexes are accepted as batch argument

**Chainable**: true

**Params**:  
*   index _Number|Array_

    Index of item, array means item from sub menu


###enableItem

Enable item by index, multiple indexes are accepted as batch argument

**Chainable**: true

**Params**:  
*   index _Number|Array_

    Index of item, array means item from sub menu


##Events

###mouseenterItem

Fired when mouse enter item

**Params**:  
*   event _jQuery.event_
*   conf _Object_Config of selected item
*   $menu _JQuery_JQuery instance of menu


###mouseleaveMenu

Fired when mouse leave menu (including sub menu)

**Params**:  
*   event _jQuery.event_
*   conf _Object_Config of selected item
*   $menu _JQuery_JQuery instance of menu


###select

Fired when item selected

**Params**:  
*   event _jQuery.event_
*   conf _Object_Config of selected item
*   $menu _JQuery_JQuery instance of menu


###disableItem

Fired when an item disabled

**Params**:  
*   index _Number|Array_Index of item, array means item from sub menu
*   item _JQuery_JQuery instance of item


###enableItem

Fired when an item disabled

**Params**:  
*   index _Number|Array_Index of item, array means item from sub menu
*   item _JQuery_JQuery instance of item


