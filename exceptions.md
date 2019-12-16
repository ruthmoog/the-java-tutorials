# Exceptions

> :pencil: https://docs.oracle.com/javase/tutorial/essential/exceptions/index.html

### Summary

- Exceptions allow you to seperate the main logic code from the 'what if something goes wrong'
- Only the method concerned with the error needs to handle it, so if the error occurs in a method further along the flow it will still be caught by the responsible method
- Exceptions are grouped naturally by the class hierarchy.  Exception handlers should be as specific as possible, you want them to identify the error first before instructing how to handle it.
- If a client can reasonably be expected to recover from an exception, make it a checked exception. If a client cannot do anything to recover from the exception, make it an unchecked exception.

>A program can use exceptions to indicate that an error occurred. To throw an exception, use the throw statement and provide it with an exception object — a descendant of Throwable — to provide information about the specific error that occurred. A method that throws an uncaught, checked exception must include a throws clause in its declaration.

> :bulb: A program can catch exceptions by using a combination of the `try`, `catch`, and `finally` blocks.

>- The `try` block identifies a block of code in which an exception can occur.
>- The `catch` block identifies a block of code, known as an exception handler, that can handle a particular type of exception.
>- The `finally` block identifies a block of code that is guaranteed to execute, and is the right place to close files, recover resources, and otherwise clean up after the code enclosed in the `try` block.

>The `try` statement should contain at least one `catch` block or a `finally` block and may have multiple `catch` blocks.

>The class of the exception object indicates the type of exception thrown. The exception object can contain further information about the error, including an error message. With exception chaining, an exception can point to the exception that caused _it_, which can in turn point to the exception that caused it, and so on.

-----

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

## How to throw an exception

- use the `throw` statement to throw an exception
- `throw` requires 1 argument, a throwable object (an instance of a subclass of the `Throwable` class)

Most programs you'll write will throw & catch Exceptions as opposed to Errors.  This is because Errors are for serious hard errors in the system, including those that mean JVM can't run.

### Chained Exceptions

This is when one exception is written to trigger another exception.

Here, when an IOException is caught, a new SampleException is created with the original cause attached.  The chain of exceptions is thrown up to the next level exception handler.

```java
try {
  // something...
} catch (IOException e) {
  throw new SampleException("Other IOException", e);
}
```

### Exception Classes

Java has many built in exception classes or you can write your own.

>You should write your own exception classes if you answer yes to any of the following questions; otherwise, you can probably use someone else's.
>- Do you need an exception type that isn't represented by those in the Java platform?
>- Would it help users if they could differentiate your exceptions from those thrown by classes written by other vendors?
>- Does your code throw more than one related exception?
>- If you use someone else's exceptions, will users have access to those exceptions? A similar question is, should your package be independent and self-contained?

It's good practice to append "Exception" to the end of class names that inherit from the `Exception` class - it might not always be the case in legacy code and you'll need to explore to find out which Exceptions are suitable (ie, when it's not appropriate to use an error exception).

## Exercises

> :pencil2: https://github.com/ruthmoog/the-java-tutorials/blob/master/ListOfNumbers.java

> :pencil2:
```java
public static void cat(File file) {
    RandomAccessFile input = null;
    String line = null;

    try {
        input = new RandomAccessFile(file, "r");
        while ((line = input.readLine()) != null) {
            System.out.println(line);
        }
		return;
    } catch(FileNotFoundException fnf) {
		System.err.format("File not found", file);
	} catch(IOException e) {
		System.err.println(e.toString());
	} finally {
        if (input != null) {
			try {
            input.close();
			} catch(IOException io) {
			}
        }
    }
}
```
