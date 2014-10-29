#ui/ui.widget.DatePicker.DatePicker

Base date picker component

####Example

     // Most common one
     new DatePicker({
         date: new Date(),
         startDate: +new Date() - 7*24*3600*1000, // 7 days ago
         endDate: +new Date() + 7*24*3600*1000 // 7 days later
     });,
     // DatePicker with assigned trigger
     new DatePicker({
         trigger: 'triggerElementSelector',
         format: 'y-m-d', // see lang.dateTool.format
     });,
     // DatePicker with multiple month views
     new DatePicker({
         monthStep: 3
     });,
     // DatePicker with highlight days
     new DatePicker({
         highlightDates: [new Date(), +new Date() + 24*3600*1000]
     });

**Extends**: ui.Nodes.Dropdown

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

Default render method of component, only to append elem into DOM

**Chainable**: true

**Params**:  
*   container _String|Object_

    Container of date picker


###renderViewport

Render viewport， the major date table

**Chainable**: true

###display

Display selected date in display element

**Chainable**: true

###selectDate

select a date of the date-mode

**Chainable**: true

**Params**:  
*   date _Date|Event_

    Date or event of which currentTarget contains data-date to be selected

####Example

     datePicker.selectDate(new Date()); // select today

###selectMonth

select a month of the month-mode

**Chainable**: true

**Params**:  
*   date _Date|Event_

    Date or event of the currentTarget contains date-month to be selected

####Example

     datePicker.selectMonth(new Date()); // select this month

###selectYear

select a year of the decade

**Chainable**: true

**Params**:  
*   date _Date|Event_

    date or event of the currentTarget contains date-year to be selected

####Example

     datePicker.selectYear(new Date()); // select this year

###showUpLevel

by click the caption to show up the up level of the date picker,
if current level is date-mode, the up level is month-mode date picker

###lastMonth

Set date picker to previous month

**Chainable**: true

###nextMonth

Set date picker to next month

**Chainable**: true

###lastYear

set date picker to last year

**Chainable**: true

###nextYear

set date picker to next year

**Chainable**: true

###lastDecade

set date picker to last decade

**Chainable**: true

###nextDecade

set date picker to next decade

**Chainable**: true

###disable

Disable date picker

**Chainable**: true

###enable

Enable date picker

**Chainable**: true

###isEnabledDate

If the array "discreteDates" is set, we judge the date is enabled or not by whether it's in the array.
else if the array is empty, we judge the date is enable or not by whether it's between start date and end date

**Returns**: _Boolean_ - 

**Params**:  
*   date _Date_

    
*   ignoreDiscreteDates _Boolean_

    . this parameter is internally used by isEnabledYearMonth

####Example

     datePicker.isEnabledDate(new Date()); // check if the date is available ( between start date and end date )

###isEnabledYearMonth

is any day of this month between the start date and end date
note that this method is to check if 'year-month' (exg: 2013-11) is bwtween the start date and end date.

**Returns**: _Boolean_ - 

**Params**:  
*   date _Date_

    

####Example

     datePicker.isEnabledYearMonth(new Date()); //check if this month of this year is available (between start date and end date)

###isEnabledYear

is any day of this year between the start date and end date

**Returns**: _Boolean_ - 

**Params**:  
*   date _Date_

    

####Example

     datePicker.isEnabledYear(new Date()); // check if this year is available (between start date and end date)

###show

Show date picker panel and update position

**Chainable**: true

###toggle

Toggle date picker panel and update position

**Chainable**: true

