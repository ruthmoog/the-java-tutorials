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

## Try, Catch, Finally

```java
try {
  // attempty to do something
} // catch & finally blocks go here...
  ```

- you can put each line of code which may throw an exception in it's own `try` block, with seperate handlers for each
- or you can put all the code in a single `try` block and associate multiple handlers, using a `catch` block

catch blocks come immediately after the try block.

```java
try {
  // attempt something...
} catch (ExceptionType name) {
  //
} catch (ExceptionType name) {
  //
}
```

- Each `catch` is an exception handler
- The ExceptionType must be the name of a class which inherits from a `Throwable` class
- `catch` code will only be executed if that handler is envoked (if the thrown object can legally be assigned to the exception handlers argument
- Exception handlers can print errors, halt the program, do error recovery, prompt user to make a decision, move the error to a higher leverl handler using `chained exceptions`.

```java
try {

} catch (IndexOutOfBoundsException e) {
  System.err.println("IndexOutOfBoundsException: " + e.getMessage());
} catch (IOException e) {
  System.err.println("Caught IOException: " + e.getMessage());
}
```

It's possible to catch more than one type using the vertical bar

```java
catch (IOException|SQLException ex) {
    logger.log(ex);
    throw ex;
}
```

Here ^^ the catch parameter is implicitly `final`.  you cannot assign any values to `ex` in the catch block.

The finally block _always_ executes when the try block exits.  Put cleanup code here to be a badass.

> The `finally` block might not execute of the JVM exits during the `try` or `catch` code, or if the 'thread' is interrupted or killed.

```java
finally {
    if (out != null) { 
        System.out.println("Closing PrintWriter");
        out.close(); 
    } else { 
        System.out.println("PrintWriter not open");
    } 
} 
```

> :bulb: `finally` to make sure you close files and prevent resource leaks - a resource is an object which must be closed when finished with.

Use a [`try`-with-recourses statement](https://docs.oracle.com/javase/tutorial/essential/exceptions/tryResourceClose.html) to ensure a resource is closed at the end of the statement.

