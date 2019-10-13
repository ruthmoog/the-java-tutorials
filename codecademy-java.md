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

### Java Program Structure

- java is case-sensitive
- classes are pascal case, methods and variables are camel case
- curly braces mark the scope of a class `{}`
- every program has a `main()` method which holds all of the program instructions
- objects are packages of state and behavior
- `System` is an object responsible for representing our computer within the program

[Twitter Java style guide](https://github.com/twitter/commons/blob/master/src/java/com/twitter/common/styleguide.md)

## Variables

### Introduction

- Declaring a variable requires that we specify the type and name
- Types include `int`, `double`, `char` and, `boolean` - all primitives
- To assign a value to a variable, use the assignment operator `=`

> :pencil: Print out the `name` and the `yearCreated` variables:

```java
public class Creator {
	public static void main(String[] args) {
    String name = "James Gosling";
    int yearCreated = 1995;
    
    System.out.println(name);
    System.out.println(yearCreated);
	}
}
```

```shell
> James Gosling
> yearCreated
```

### ints

- In Java, whole numbers are stored in the int primitive data type
- `ints` hold positive numbers, negative numbers, and zero: between -2,147,483,648 and 2,147,483,647, inclusive
- They do not store _fractions_ or numbers with _decimals_ in them

> :pencil: Declare a variable that stores the number of comments in the program, then print it to console:

```java
//This is the class declaration
public class CountComment {
  //This is the main method that runs when you compile
	public static void main(String[] args) {
    //This is where you will define your variable
    int numComments = 6;
    //This is where you will print your variable
    System.out.println(numComments);
	}
  
  //This is the end of the class
}

//This is outside the class
```

```shell
> 6
```

### doubles

- `double` can hold decimals and, very large and very small numbers
- The maximum value is 1.797,693,134,862,315,7 E+308, which is approximately 17 followed by 307 zeros
- The minimum value is 4.9 E-324, which is 324 decimal places

> :pencil: Create a variable to hold the % market share of Android phones, then print it:

```java
public class MarketShare {
	public static void main(String[] args) {
    double androidShare = 81.7;
    System.out.println(androidShare);
	}
}
```

```shell
> 81.7
```

### booleans

- it's for booleans!

### char

- The char data type can hold any character, like a letter, space, or punctuation mark
- Use single quotes `'`

> :pencil: Create a variable `expectedGrade` fill it with your grade on this java course:

```java
public class Char {
	public static void main(String[] args) {   
		char expectedGrade = 'A';
    System.out.println(expectedGrade);
	}
}
```

```shell
> A
```

### Strings

- `String`s are objects with built-in behavior

### Static Checking

- Java is _statically typed_
- The program will not compile if the declared type of the variable does not match the type of the assigned value
- This is a type declaration bug
- If bugs are not caught they'll cause runtime errors & crash the program

```shell
> error: incompatible types: String cannot be converted to int
>     int greeting = "Hello World";
```

> `Mess.java` will crash:

```java
public class Mess {
	public static void main(String[] args) {   
		String year = 2001;
    double title = "Shrek";
    int genre = 'C';
    boolean runtime = 1.58;
    char isPG = true;
	}
}
```

```shell
$ javac Mess.java
> Mess.java:3: error: incompatible types: int cannot be converted to String
>                 String year = 2001;
>                               ^
> Mess.java:4: error: incompatible types: String cannot be converted to double
>     double title = "Shrek";
>                    ^
> Mess.java:6: error: incompatible types: double cannot be converted to boolean
>     boolean runtime = 1.58;
>                       ^
> Mess.java:7: error: incompatible types: boolean cannot be converted to char
>     char isPG = true;
>                 ^
> 4 errors
$ 
```

> :pencil: Correct the variable types & recompile:

```java
public class Mess {
	public static void main(String[] args) {   
		int year = 2001;
    String title = "Shrek";
    char genre = 'C';
    double runtime = 1.58;
    boolean isPG = true;
	}
}
```

```shell
$ javac Mess.java
$
```

### Naming

- Valid variable names start with a _letter_, `$`, or `_`

> `BadNames.java` will error:

```java
public class BadNames {
	public static void main(String[] args) {   
		String 1stName = "Samira";
    String blah = "Smith";
    String .com = "samira@google.com";
    int salaryexpectation = 100000;
    int year_of_birth = 1955;
    
    System.out.println("The program runs!");
	}
}
```

```shell
> BadNames.java:3: error: not a statement
> 		String 1stName = "Samira";
> 		^
> BadNames.java:3: error: ';' expected
> 		String 1stName = "Samira";
> 		      ^
> 2 errors
```

> :pencil: Correct the bad names:

```java
public class BadNames {
	public static void main(String[] args) {   
		String firstName = "Samira";
    String lastName = "Smith";
    String emailAddress = "samira@google.com";
    int salaryExpectation = 100000;
    int birthYear = 1955;
    
    System.out.println("The program runs!");
	}
}
```

```shell
> The program runs!
```

### Variables Review

- `ints` store whole numbers
- `doubles` store bigger whole numbers and decimal numbers
- `booleans` store true and false
- `chars` store single characters using single quotes
- `Strings` store multiple characters using double quotes

- Static typing is one of the safety features of Java
- Java has naming conventions for variables

> :pencil: Create a very accurate job profile using different variable types:

```java
public class MyProfile {
	public static void main(String[] args) {   
		String name = "Ruth";
    int age = 99;
    double desiredSalary = 900000584008372.65;
    char gender = 'f';
    boolean lookingForJob = false;
	}
}
```

## Manipulating Variables

- `+`, `-`, `*`, `%`, `>`, `<`, `==`, `<==`, `>==`, `!=` all work as expected
- `/` divides to an `int` so doesn't handle floating points well
- `equals()` is used to compare Strings
- concatinate Strings with `+`, there's no interpolation

## Introduction to Classes

- `System` is a predefined Java class
- `public` is an _access level modifier_ that allows other classes to interact with that class
- The `main()` runs when the compiled class files is executed
- Constructors share the name of the class
- Create class _instances_ by calling the constructor within `main()`
- use the keyword `new` to indicate creating an instance; omitting `new` causes an error
- Instance fields allow for state
- Access the value of the instance field with the dot operator
- Order matters for multiple instance fields/parameters

> :pencil: Create a `Store` class with an instance of store:

```java
public class Store {
    String stock;
    int units;
  
  // new method: constructor!
  public Store(String whatsForSale, int howMany) {
		System.out.println("I am inside the constructor method.");
    stock = whatsForSale;
    units = howMany;
  }
  
  // main method is where we create instances!
  public static void main(String[] args) {
    System.out.println("Start of the main method.");

    
    // create the instance below
    Store lemonadeStand = new Store("lemonade", 25);
    // print the instance below
    System.out.println(lemonadeStand);
    System.out.println("There are " + lemonadeStand.units + " " + lemonadeStand.stock + "'s for sale.");
  }
}
```

```shell
> Start of the main method.
> I am inside the constructor method.
> Store@2aae9190
> There are 25 lemonade's for sale.
```

0. Running the program invokes main()
0. We create an instance so we move from main() to Store()
0. The code inside Store() runs
0. When Store() finishes execution, we return to main()

## Methods

- `public` means that other classes can access this method
- A method is a task that an object of a class performs

> Call a variable from outside the method scope:

```shell
> Store.java:12: error: cannot find symbol
>     String message = "Selling " + cookie + "!";
>                                   ^
>   symbol:   variable cookie
>   location: class Store
> 1 error
```

> Use a method with params:

```java
// method requires String param
public void greetCustomer(String customer) {}

// ...

// call the method with a string argument
// inside main()
lemonadeStand.greetCustomer("Pepper");
```

### Returns

- `void` means that there is no specific output from the method
- use datatype keywords (`int`, `char`, etc.) to specify that a method should return a value of that type

> Create a method that returns a `double`:

```java
public double getPriceWithTax() {
  //create the variable first
  double totalPrice = price + (price * 0.08);
  // after the variable is created it is explicitly returned
  return totalPrice
}
```

- Defining a `toString()` method for a class can return a `String` that will print object info

```java
  public String toString() {
    return "This store sells " + productType + " at a price of $" + price + ".";
  }

  //then
  System.out.println(lemonadeStand)
```

```java
// without toString():
> Store@2aae9190

// with toString():
> "This store sells Lemonade at a price of $3.75."
```

### Review...

- Defining a method : Methods have a method signature that declares their return type, name, and parameters
- Changing Instance Fields : Methods can be used to change the value of an instance field
- Scope : Variables only exist within the domain that they are created in
- Return : The type of the variables that are output are declared in the method signature

## Introduction to Control Flow

- Multi-line conditional statements use curly braces after the boolean
- Single-line conditional statements don't need curly braces
- Conditional statements do not end in a semicolon
- Switch blocks are not marked by curly braces and use the `break` keyword to exit the switch statement

> :pencil: basic `if` statement:

```java
  if (itemCost > 24.00) {
      System.out.println("High value item!");
    }
```

> :pencil: and an `else if` statement:

```java
if (shipping == "Regular") {
      return 0;
    } else if (shipping == "Express") {
      return 1.75;
    } else {
      return .50;
    }
```

> :pencil: use a switch instead:

```java
public double calculateShipping() {
    double shippingCost;
	 	// declare switch statement here
    switch (shipping) {
      case "Regular":
        shippingCost = 0;
        break;
      case "Express":
        shippingCost = 1.75;
        break;
      default:
        shippingCost = .50;
    }
    
    return shippingCost;
 	}
```

## Introduction to Conditional Operators

- and `&&`, or `||`, not `!`
- _not_, `!` is known as the unary operator

## Arrays

- To create an array, first declare the type of data it holds eg, `double[] <name>` then explicitly initialize the array containing data eg, `= {22.99, 22.50, 19.00};`
- Returning an array will return the location in memory, so convert to string (`toString()`) to see the array output
- You'll need to import Java's arrays package, `import java.util.Arrays;`
- Array elements are 0 indexed
- Empty arrays must be created with a fixed size (heartbreaking!) (you'd want to import java.util and use stacks or array lists...google it!)
- Get the length of an array using `.length`
- Use the argument array `args` to pass args into the main() class

> :pencil: create a public method that returns an array of strings:

```java
  public String[] getTopics() {
    String[] topics = {
      "Opinion",
      "Tech",
      "Science",
      "Health",
    };
    return topics;
  }
```

if we call that method from main()...
```shell
> [Ljava.lang.String;@2aae9190
```

> :pencil: import the array package & use the `toString()` method:

```java
// import the Arrays package at the top of the file
import java.util.Arrays;

public class Newsfeed {

  public Newsfeed(){
    
  }
    
  public String[] getTopics(){
    String[] topics = {"Opinion", "Tech", "Science", "Health"};
    return topics;
  }
  
  public static void main(String[] args){
    Newsfeed sampleFeed = new Newsfeed();
    String[] topics = sampleFeed.getTopics();
  // here's the toString() method...
    System.out.println(Arrays.toString(topics));
  }
}
```
```shell
> [Opinion, Tech, Science, Health]
```

## Array Lists

- Use Array Lists to store elements of the same type, access elements by index, & add and Remove elements
- They need to be imported from the util package, `import java.util.ArrayList;`
- Use **generics** inside angle brackets to state the type of objects in an ArrayList, eg `<Integer>` or `<Double>` instead of primitives like `int` or `double`

> :pencil: Import the util and create a `new` Array List:
> :pencil: Add some To Dos:

```java
// import the ArrayList package here:
import java.util.ArrayList;

class ToDos {
  public static void main(String[] args) {
    
    // Create toDoList below:
    ArrayList<String> toDoList = new ArrayList<String>();

        // Create to-dos:
    String toDo1 = "Water plants";
    String toDo2 = "Feed cat";

    // Add to-dos to toDoList
    toDoList.add(toDo1);
    toDoList.add(toDo2);
    toDoList.add("Take out bins");
    
    System.out.println(toDoList);
  }
}
```

### Helpful methods on Array Lists

- Use the `size()` method to find the length of the array list
- Use the `get()` method to find an elements at a given index (unlike arrays which use brackets), and `indexOf` to find an elements index
- Use the `set()` method to change an item, and `remove()` to delete an item

:seedling: :dog: :bin:
```java
    // ...
    toDoList.size();              // 3

    toDoList.get(0);              // Water plants
    toDoList.indexOf("Feed cat"); // 1

    toDoList.set(0, "Walk dog");  // change Water plants to Walk dog
    toDoList.get(0);              // Walk dog

    toDoList.remove(2);           // removes Take out bins
    toDoList.remove("Walk dog");  // removes (first) instance of Walk dog
    toDoList.size();              // 1
```

### Looping through Array Lists

- You can use `while`, `for` and `for each` loops
- Increment with `++` (if your counter is at 1, `counter++` will count 1, 2, 3, and `++counter` will count 2, 3, 4)
- For loops are initialised as per eg `(int i = 0; i < 5; i++)`
- If looping through an arrays length, use `<` rather than `<=` to account for the length being 1 more than the index

> :pencil: Use `Random` with a `while` loop

```java
// Import the Random library
import java.util.Random;

class LuckyFive {
  public static void main(String[] args) {

    // Create a random number generator
    Random randomGenerator = new Random();
    
    // Generate a number between 1 and 6
    int dieRoll = randomGenerator.nextInt(6) + 1;

    // Repeat while roll isn't 5
    while (dieRoll != 5) {
      System.out.println(dieRoll);
      dieRoll = randomGenerator.nextInt(6) + 1;
    }
  }
}
```

> :pencil: "Refactor" using a for loop

```java
    // ... 
    for (int cupsOfCoffee = 1; cupsOfCoffee <= 100; cupsOfCoffee++) {
      System.out.println("Fry drinks cup of coffee #" + cupsOfCoffee);
    }
```

> Example of iterating through items in an array list

```java
    for (double expense : expenses) {
      if (expense > mostExpensive) {
        mostExpensive = expense;
      }
    }
```