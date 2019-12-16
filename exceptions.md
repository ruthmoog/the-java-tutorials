# Exceptions

> :pencil: https://docs.oracle.com/javase/tutorial/essential/exceptions/index.html

Java using `exceptions` to handle errors and exceptional events.
Exceptions are events.  They disrupt the flow of the program.  

**Throwing an exception**: When the error occurs in a method, the method creates an object (with info on the type and state of the program at the moment of the problem) and gives it to the runtime system.

Runtime system works it's way back through the call stack from the method where the error ocurred and looks for a way to handle the exception, the **exception handler**.  

**Catching an exception**: The exceptional event object is passed to the exception handler.  If the exception isn't caught the program terminates.

## Catch or Specify

Code needs to meet this requirement to compile.  It needs to either:
- be wrapped in a `try` statement
- specify a `throws` clause in the method declaration

### Three kinds of exception

**Checked exception**
eg, `java.io.FileNotFoundException` - user has to input a file name, the input is used to open a file, but the file does not exsist.
The program should catch this, notify the user and ask for a correct file name.
This type of exception is subject to the catch or specify requirement.

**Error**
eg, `java.io.IOError` - app successfully opens a file, but cannot read the file due to a hardware malfunction.
These are external to the application and cannot be anticipated or recovered from. An application might choose to catch this to notify the user, or it might print a stack trace & exit.
Errors are *not* subject to catch or specify requirement.

**Runtime exception**
eg, `NullPointerException` - the application passes a file name to the FileReader, a logical mistake causes null to be passed to the constructor, and throws a null pointer.
These are internal to the application but cannot be anticipated or recovered from.  They usually indicate bugs like logic errors or incorrect use of an API.
Runtime Exceptions are *not* subject to catch or specify requirement.

> :bulb: Errors and runtime exceptions are known as unchecked exceptions



