#util/util.Tasks

Task list management.
util.Tasks is a single instance class
High performance version of setInterval and provide super easy task management.
Suitable for animation or timely running tasks

##Methods

###add

Add a new task
Newly added task is paused, manually run it when needed

**Returns**: _Task_ - Task instance for further control

**Params**:  
*   fn _Function_

    Things to be done each time is up
*   gap _Number|Function_

    The time gap between two execution


###once

Add an once task.
The task added by Tasks.once will only run once and automatically removed itself

**Returns**: _Task_ - Task instance for further control

**Params**:  
*   fn _Function_

    Things to be done each time is up
*   gap _Number|Function_

    The time gap between two execution


###loop

main loop, execute tasks in sequence and stop when loop time is up

###start

Start loop

**Chainable**: true

###stop

Stop loop

**Chainable**: true

#util/util.Task

Task control handler representing a function to be executed every certain time

##Methods

###run

Set task's state to running

**Chainable**: true

**Params**:  
*   immediately _Boolean_

    Run immediately or wait a gap


###pause

Set task's state to paused

**Chainable**: true

###drop

Drop ( remove ) the task
The task will be removed the next time it ought to be executed.
Reset task's state before it's really removed by calling run or pause can restore the task

**Chainable**: true

###delay

Delay execution time

**Chainable**: true

**Params**:  
*   delayedTime _Number_

    


###execute

Execution

**Returns**: _Boolean_ - 

###getGap

Get time gap

**Returns**: _Number_ - 

###setGap

Set time gap

**Chainable**: true

**Params**:  
*   newGap _Number_

    


###isRunning

Judge whether the task is in running state or not

**Returns**: _Boolean_ - 

###isPaused

Judge whether the task is paused or not

**Returns**: _Boolean_ - 

###isDropped

Judge whether the task is dropped or not

**Returns**: _Boolean_ - 

