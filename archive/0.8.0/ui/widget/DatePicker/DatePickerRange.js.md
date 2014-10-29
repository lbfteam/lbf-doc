#ui/ui.widget.DatePickerRange

a range datepicker for date range select in datepicker
the monthstep is at least 2

####Example

     // simplest example
     new DatePickerRange({
         trigger: 'someTrigger',
         display: 'someInput or text container'
     });

     // customize variables and events
     new DatePickerRange({
         trigger: 'someTrigger',
         display: 'someInput or text container',

         // customize in the below
         // suggest to be at least 2 in datePickerRange for convenient selection
         monthStep: 2,

         // we can customize the shown text in the display by set the rangeStartDateFormat
         // rangeDateFormatConcat and rangeEndDateFormat, they can concated as
         // "rangeStartDateFormat" + "rangeDateFormatConcat" + "rangeEndDateFormat".
         rangeStartDateFormat: 'Y-m-d',
         rangeDateFormatConcat: ' to ',
         rangeEndDateFormat: 'Y-m-d',

         // we can also customize the datePickerTemplate, but it's not suggested.
         datePickerTemplate: "txt in artTemplate format',

         // we can initial the datePickerRange with the rangeStartDate and rangeEndDate
         // if the rangeStartDate is bigger than the rangeEndDate, we will automatically switch the value
         rangeStartDate : new Date() || '1403749868311',
         rangeEndDate: new Date() || '1403749868311'

         // events that can be listened to
         events: {

             // after the rangeEndDate is selected, we will trigger the 'confirmHide' event
             // let the user to deal with the action to hide or do something else
             // we have set the confirmHide to hide by default.
             // if you accept the action, just DONOT add this event
             'confirmHide': function() {
                 // do your things here
             },

             // when the rangeEndDate is selected, we will trigger the 'rangeEndSelected' event
             // and pass the lastRangeStartDate and lastRangeEndDate value.
             // If the lastRangeStartDate or lastRangeEndDate is null, that means this value doesn't
             // change after 'rangeEndSelected' triggered.
             // If you want to get the current value of rangeStartDate and rangeEndDate,
             // just use this.get('rangeStartDate') and this.get('rangeEndDate')
             'rangeEndSelected': function(e, lastRangeStartDate, lastRangeEndDate) {
                 // do your things here
             }
             'rangeStartSelected': function(e, lastRangeStartDate, lastRangeEndDate) {
                 // do your things here
             }
         }

     });


**Extends**: ui.widget.DatePicker

##Methods

###mergeOptions

override the mergeOptions in DatePicker

**Chainable**: true

**Returns**: _DatePickerRange_ - 

**Params**:  
*   opts __

    user passed options


###defaultActions

override the default actions in DatePicker

**Chainable**: true

**Returns**: _DatePickerRange_ - 

###selectDate

select a date of the date-mode

**Chainable**: true

**Params**:  
*   date _Date|Event_

    Date or event of which currentTarget contains data-date to be selected

####Example

     datePickerRange.selectDate(new Date()); // select today

###display

Display selected date in display element

**Chainable**: true

###renderViewport

Render viewport， the major date table

**Chainable**: true

###setElement

Overwritten setElement method to bind default validator and event action before setting up attributes

**Returns**: _DatePickerRange_ - 

##Events

###confirmHide

Fire when the rangeEndDate is selected.
Whether we should hide the DatePickerRange or not,
leave to the confirmHide callback.

###rangeEndSelected

Fire when the rangeEndDate is selected
trigger rangeSelected event, and pass the lastRangeStartDate and lastRangeEndDate value
if lastStartDate || lastEndDate is null, that means this value doesn't change in this process

###rangeStartSelected

Fire when the rangeStartDate is selected
Trigger the rangeStartSelected event, with the previous tmpStartDate and tmpEndDate

###selectDate

Fire when rangeStartDate or rangeEndDate is selected

