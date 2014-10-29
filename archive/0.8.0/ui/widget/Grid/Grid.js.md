#ui/ui.widget.Grid

Grid组件可以对table的视觉、交互、可用性增强

####Example

    grid1 = new Grid({
       selector: '#demo-grid-html',
       isShowHeader: false,
       title: 'rainszhang',
       width: 'auto',
       height: 'auto',
       nowrap: false,
       sortStatus: 'down'
    });

**Extends**: ui.Nodes.Node

##Properties

###settings

Default settings

**type**: Object

##Methods

###render

Render Grid and initialize events and elements

**Chainable**: true

###addRows

增加数据行

**Chainable**: true

**Returns**: __ - Object

**Params**:  
*   需增加数据行的数据数组 _Array_

    
*   数据添加到索引行 _Number_

    


###removeRows

移除索引行，如index为索引值则删除索引行，如index为索引数组则一次移除多行，如果不传参则删除所有行

**Chainable**: true

**Returns**: __ - Object

**Params**:  
*   index _Number_

    移除行的索引值


###rowsLupdateRowsength

更新数据到索引行，一次只能更新一行

**Chainable**: true

**Returns**: __ - Object

**Params**:  
*   data _Array_

    更新的数据
*   需要更新行的索引值 _Number_

    


###rowsLength

获取数据数组的长度

**Chainable**: true

**Returns**: __ - Number

###selectedRows

返回选中行的数据数组

**Chainable**: true

**Returns**: __ - Array

###selectedRowsIndex

返回选中行索引的数组

**Chainable**: true

**Returns**: __ - Array

###rows

返回指定行的数据数组

**Chainable**: true

**Returns**: __ - Array

**Params**:  
*   index _Number_

    行索引值，不传参返回所有行的数据数组


###select

选中指定索引值的行

**Chainable**: true

**Returns**: __ - Object

**Params**:  
*   index _Number_

    行索引值，不传参选中所有行


