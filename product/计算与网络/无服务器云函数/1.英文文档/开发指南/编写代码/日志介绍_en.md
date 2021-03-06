Log statement provides necessary execution information for functions, which is indispensable to the troubleshooting of codes. SCF platform writes all the logs generated when the user uses log statement in code to the log system. If you use the console to call a function, the console displays the same log.

Users can use the following statement to generate log entry:

- print
- Logger function in logging module

## Using logging Statement to Write to Log

```
import logging
logger = logging.getLogger()
def my_logging_handler(event):
    logger.info('got event{}'.format(event))
    logger.error('something went wrong')
    return 'Hello World!'  
```

The above code writes information to log using logging module. You can view the log information in the code via the log module on the console or the API Acquire Operation Log of Functions. Log level identifies the type of log, such as `INFO`, `ERROR` and `DEBUG`.

## Using print Statement to Write to Log
You can also use print statement in code, as shown below:

```
def print_handler(event):
    print('this will show up in logging')
    return 'Hello World!' 
```   

When you call the function synchronously using the "Test" button on the console, the values of print statement and return statement will be displayed on the console.


## Acquiring Log

You can acquire the operation log of functions using the following methods

- If the function is called synchronously via the "Test" button on the console
 - The log for this call is displayed on the console after the execution
- If the function is called by the trigger
 - The log for each call is displayed in the Log tab of the function
 - The function log can also be acquired through API GetFunctionLogs
- If the function is called synchronously through Invoke API
 - The log for this call can be acquired in the logMsg field of returned value

