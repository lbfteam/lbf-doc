#monitor/monitor.logger

Frontend log utilities with uls service

####Example

 logger.config({
     writeConsole: true,
     proj: 'lbf demo',
     reportLevel: logger.WARN
 });

 var logOptions = {
     module: 'demo.logger',
     fn: 'LBF.use',
     line: 102,
     errorID: 1
 };

 logger.error('error test', logOptions);

 logOptions.line = 109;
 logger.warn('warn test', logOptions);

 logOptions.line = 112;
 logger.notice('notice test', logOptions);

 logOptions.line = 114;
 logger.info('info test', logOptions);

 logOptions.line = 118;
 logger.debug('debug test', logOptions);

##Methods

###error

Write an error log

**Params**:  
*   msg _String_

    The log message
*   opts _Object_

    The options for log
    * module _String_ - The module that writes the log
    * fn _String_ - The function that writes the log
    * lien _Number_ - The line num that writes the log
    * errorID _Number_ - The error ID


###warn

Write an warn log

**Params**:  
*   msg _String_

    The log message
*   opts _Object_

    The options for log
    * module _String_ - The module that writes the log
    * fn _String_ - The function that writes the log
    * lien _Number_ - The line num that writes the log
    * errorID _Number_ - The error ID


###notice

Write an notice log

**Params**:  
*   msg _String_

    The log message
*   opts _Object_

    The options for log
    * module _String_ - The module that writes the log
    * fn _String_ - The function that writes the log
    * lien _Number_ - The line num that writes the log
    * errorID _Number_ - The error ID


###info

Write an info log

**Params**:  
*   msg _String_

    The log message
*   opts _Object_

    The options for log
    * module _String_ - The module that writes the log
    * fn _String_ - The function that writes the log
    * lien _Number_ - The line num that writes the log
    * errorID _Number_ - The error ID


###debug

Write an debug log

**Params**:  
*   msg _String_

    The log message
*   opts _Object_

    The options for log
    * module _String_ - The module that writes the log
    * fn _String_ - The function that writes the log
    * lien _Number_ - The line num that writes the log
    * errorID _Number_ - The error ID


###log

Write an debug log

**Params**:  
*   msg _String_

    The log message
*   opts _Object_

    The options for log
    * module _String_ - The module that writes the log
    * fn _String_ - The function that writes the log
    * lien _Number_ - The line num that writes the log
    * errorID _Number_ - The error ID


###config

Set config
Options available are:
 writeConsole {Boolean} Write to browser console or not
 reportLevel {String} Report level of log, beyond which will be logged into uls
 proj {String} Project name, which will be logged with log object

**Params**:  
*   key _String|Object_

    The name of config option to be set, or the key-value pairs of config options to be set when it's an object
*   value __

    Value of config option


###report

Report logs to uls

**Params**:  
*   opts _Object_

    The additional options for log object
    * reportUrl _String_ - The report url of remote server


