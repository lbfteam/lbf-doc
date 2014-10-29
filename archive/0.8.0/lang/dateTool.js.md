#lang/lang.dateTool

Date enhancement tools

##Methods

###format

格式化日期为字符串

**Returns**: _String_ - 字符串

**Params**:  
*   expr _String_

    表达式
*   [date=new _Number|Date_

    Date()] 日期

####Example

     format参数如下（来源于PHP的date函数的参数子集）：
	    日期：
		    d：月份中的第几天，有前导零的 2位数字，01 到 31
		    D：星期中的第几天，文本表示，3个字母，Mon 到 Sun
		    j：月份中的第几天，没有前导零，1 到 31
		    l: 星期几，完整的文本格式，Sunday 到 Saturday
		    N：ISO-8601 格式数字表示的星期中的第几天，1（表示星期一）到 7（表示星期天）
		    w：星期中的第几天，数字表示，0（表示星期天）到 6（表示星期六）
		    z: 一年中的第几天，0 到 366
	    月份：
		    F：月份，完整的文本格式，例如 January 或者 March，January 到 December
		    m：数字表示的月份，有前导零， 01 到 12
		    n：数字表示的月份，没有前导零，1 到 12
		    M：三个字母缩写表示的月份，Jan 到 Dec
	    年份：
		    Y：4 位数字表示的年份
		    y：2 位数字表示的年份
	    上下午标识：
		    a：显示am/pm
		    A：显示AM/PM
	    小时：
		    g：小时，12 小时格式，没有前导零，1 到 12
		    G：小时，24 小时格式，没有前导零，0 到 23
		    h：小时，12 小时格式，有前导零，01 到 12
		    H：小时，24 小时格式，有前导零，00 到 23
	    分钟：
		    i：有前导零的分钟数，00 到 59
	    秒数：
		    s：秒数，有前导零，00 到 59,
     date.format('Y-m-d H:i:s A l'); // output:2012-04-19 15:17:56 AM Thursday
     date.format('Y年m月d日 H:i:s A l'); // output:2012年04月19日 15:18:38 AM Thursday
     date.format('\\Y是Y'); // output:Y是2012

###isLeapYear

Is The year a leap year

**Returns**: _Boolean_ - 

**Params**:  
*   year _Date|String_

    

####Example

     dateTool.isLeapYear('2000'); // true
     dateTool.isLeapYear(new Date()); // it depends

###lastDay

Get last date ( One day before the given date ).

**Returns**: _Date_ - 

**Params**:  
*   date _Date|Number_

    

####Example

     dateTool.lastDay(new Date()); // returns yesterday
     dateTool.lastDay(new Date('2000-1-10')); // returns new Date('2000-1-9')

###nextDay

Get date of the next day

**Returns**: _Date_ - 

**Params**:  
*   date _Date|Number_

    

####Example

     dateTool.lastDay(new Date()); // returns tomorrow
     dateTool.lastDay(new Date('2000-1-10')); // returns new Date('2000-1-11')

###lastMonth

Get the date of the day one month before

**Returns**: _Date_ - 

**Params**:  
*   date _Date|Number_

    

####Example

     dateTool.lastDay(new Date()); // returns one month ago
     dateTool.lastDay(new Date('2000-1-10')); // returns new Date('1999-12-10')

###nextMonth

Get the date of the day in next month

**Returns**: _Date_ - 

**Params**:  
*   date _Date|Number_

    

####Example

     dateTool.nextMonth(new Date()); // returns one month later
     dateTool.nextMonth(new Date('2000-1-10')); // returns new Date('2000-2-10')

###lastYear

Get date of the day one year before

**Returns**: _Date_ - 

**Params**:  
*   date _Date|Number_

    

####Example

     dateTool.lastYear(new Date()); // returns one year ago
     dateTool.lastYear(new Date('2000-1-10')); // returns new Date('1999-1-10')

###nextYear

Get date of the day in next year

**Returns**: _Date_ - 

**Params**:  
*   date _Date|Number_

    

####Example

     dateTool.nextYear(new Date()); // returns one year later
     dateTool.nextYear(new Date('2000-1-10')); // returns new Date('2001-1-10')

###daysBetween

Get days between two date

**Returns**: _Number_ - if end date is before start date, returns a negative int

**Params**:  
*   start _Date|Number_

    Accept date object or timestamp ( in ms )
*   end _Date|Number_

    Accept date object or timestamp ( in ms )

####Example

     dateTool.daysBetween(new Date('2000-1-10'), new Date('2000-1-20')); // returns 10
     // when start date is later than end date returns negative int
     dateTool.daysBetween(new Date('2000-1-20'), new Date('2000-1-10')); // returns -10

###timestamp

Get timestamp in second. Usually for syncing with server

**Returns**: _Number_ - 

**Params**:  
*   date _Date|Number_

    

####Example

     dateTool.timestamp(new Date(1369808162919)); // returns 1369808162

