# Learning Java with codecademy

## Hello World

### Introduction to Java

- Java programs have at least one class and one main() method.
- Each class represents one real-world idea.
- The main() method runs the tasks of the program.

```java
public class HelloWorld {
  public static void main(String[] args) {
    System.out.println("Hello World!");
  }
}
```

```shell
> Hello World!
```

### Hello Java File!

- Java files have a `.java` extension
- class names echo file names and are PascalCase
- `System.out.println()` will print a message to console

```java
public class HelloYou {
  public static void main(String[] args) {
    System.out.println("Hello Ruth!");
  }
}
```

```shell
> Hello Ruth!
```

### Commenting Code

- // single line comments
- /* multi line comments */

```java
public class Timeline {
  public static void main(String[] args) {
    System.out.println("Hello Java!");
    
    System.out.println("You were born in 1995");

    // Sun Microsystems announced the release of Java in 1995
    
    System.out.println("You were created by James Gosling");
    
		/* James Gosling is a Canadian engineer who 
		created Java while working at Sun Microsystems. 
		His favorite number is the square root of 2! */
    
    System.out.println("You are a fun language!");
  }
} 
```

```shell
> Hello Java!
> You were born in 1995
> You were created by James Gosling
> You are a fun language!
```

### Semicolons and Whitespace

- Java does _not_ interpret whitespace
- Java _does_ interpret semicolons.

```
public class LanguageFacts {
  public static void main(String[] args) {
    // Press enter or return on your keyboard after each semicolon!
    
    System.out.println("Java is a class-based language.");System.out.println("Java classes have a 'main' method.");System.out.println("Java statements end with a semicolon.");
  }
}
```

```java
public class LanguageFacts {
  public static void main(String[] args) {
    // Press enter or return on your keyboard after each semicolon!
    
    System.out.println("Java is a class-based language.");
    System.out.println("Java classes have a 'main' method.");
    System.out.println("Java statements end with a semicolon.");
    System.out.println("Programming is doin' the do");
  }
}
```

```shell
> Java is a class-based language.
> Java classes have a 'main' method.
> Java statements end with a semicolon.
> Programming is doin' the do
```

### Compilation: Catching Errors

- Java is a compiled programming language
- the compiler transforms java code (human readable) into byte code (_Java Virtual Machine_ readable)
- Code that does not the compiler checks will not be compiled and produce a list of errors

```java
public class Compiling {
  public static void main(String[] args) {
    
    System.out.println("Java is a class-based language.");
    System.out.println("Java classes have a 'main' method.");
    System.out.println("Java statements end with a semicolon.") //;

    System.out.println("Programming is... fun!");
    
  }
}
```

```shell
$ javac Compiling.java
Compiling.java:6: error: ';' expected
  System.out.println("Java statements end with a semicolon.")
                                                             ^

1 error
$ ls
Compiling.java
$
```

### Compilation: Creating Executables

- We can compile a `.java` file from the terminal with `javac FileName.java`
- If successful, this produces an executable class, `FileName.class`
- Run the executable with `java FileName`

```java
public class Compiling {
  public static void main(String[] args) {
    
    System.out.println("Java is a class-based language.");
    System.out.println("Java classes have a 'main' method.");
    System.out.println("Java statements end with a semicolon.");

    System.out.println("Programming is... fun!");
    
  }
}
```

```shell
$ ls
Compiling.java
$ javac Compiling.java
$ ls
Compiling.class Compiling.java
$ java Compiling
> Java is a class-based language.
> Java classes have a 'main' method.
> Java statements end with a semicolon.
> 
> Programming is... fun!
$
```

### Java Review: Putting It All Together

0. Define a public class named `Review`.
0. Define the main() method within the curly braces of the Review class.
0. Inside the main() method, write `The main method executes the tasks of the class` as a single-line comment.
0. Below the comment, write a statement that prints the following: `My first Java program from scratch!`.


```Java
public class Review {
  public static void main(String[] args) {
  	// The main method executes the tasks of the class
    System.out.println("My first Java program from scratch!");
  }
}
```
```shell
> My first Java program from scratch!
```

