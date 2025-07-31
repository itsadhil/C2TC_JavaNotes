─────────────────────────────────────────────
Java Notes
─────────────────────────────────────────────

Java Terminologies
─────────────────────────────────────────────
- JDK (Java Development Kit): The complete toolkit for Java development. Includes the compiler (javac), libraries, and various tools required to build, debug, and run Java applications.
- JVM (Java Virtual Machine): The engine that executes Java bytecode, enabling platform independence by abstracting the underlying hardware and OS.
- JRE (Java Runtime Environment): Contains the JVM and core libraries needed to run Java applications, but not development tools.
- ByteCode: The intermediate, platform-independent code generated after compilation. The JVM interprets and executes this code.

─────────────────────────────────────────────
Running Java Programs Without Main Method
─────────────────────────────────────────────
- In older Java versions, programs could run using only static blocks, without a main method.
- This approach is deprecated and unsupported in modern Java versions.
- Today, every Java application must have a main method as the entry point.

─────────────────────────────────────────────
Example: Static Blocks and Main Method
─────────────────────────────────────────────
package day1.basics;

public class SampleDemo {

	static {
		System.out.println("Hello I am Static");
	}

	public static void main(String[] args) {
		System.out.println("Welcome to C2TC........");
		System.out.println("New Lines");
	}

	static {
		System.out.println("I am Static block 2");
	}
}

Static Block Execution Order
─────────────────────────────────────────────
- Static blocks execute in the order they appear in the class, before the main method.
- Output sequence:
	1. "Hello I am Static"
	2. "I am Static block 2"
	3. Main method output

─────────────────────────────────────────────
Method Signature
─────────────────────────────────────────────
- A method signature includes:
	- Method name
	- Parameter types
	- Modifiers (e.g., public, static)
- It uniquely identifies a method for invocation and overloading.

─────────────────────────────────────────────
Example: Multiple Main Methods
─────────────────────────────────────────────
package day1.basics;

public class SampleDemo {

	public static void main() {
		System.out.println("Welcome from Main 1");
	}

	public static void main(char c[]) {
		System.out.println("Welcome from Main 2");
	}

	public void main(String ar) {
		System.out.println("Welcome from Main 3");
	}

	public static void main(String[] args) {
		System.out.println("Welcome to C2TC........");
		System.out.println("New Lines");
	}
}

Main Method Execution
─────────────────────────────────────────────
- Only the main method with the signature:
	public static void main(String[] args)
  is executed by the JVM as the program entry point.

─────────────────────────────────────────────
Encapsulation in Java
─────────────────────────────────────────────
- Encapsulation wraps data (fields) and methods into a single unit (class).
- Achieved by making fields private and providing public getter/setter methods.
- Promotes data hiding, modularity, and maintainability.

─────────────────────────────────────────────
Input Classes in Java
─────────────────────────────────────────────
- Scanner: Reads user input from various sources (keyboard, files).
- BufferedReader: Efficiently reads text from character input streams.

Scanner Class
─────────────────────────────────────────────
- Used for reading input from the user.
- Syntax:
	Scanner input = new Scanner(System.in);

Common Scanner Methods
─────────────────────────────────────────────
- next(): Reads a single word.
- nextLine(): Reads an entire line.
- nextInt(): Reads an integer.
- nextFloat(): Reads a float.
- nextDouble(): Reads a double.

Example:
	char c = reader.next().charAt(0); // Gets first character from input

Other Scanner Methods:
- hasNextDouble(), hasNextInt(), hasNextLine(), hasNext()

BufferedReader Object Creation
─────────────────────────────────────────────
- BufferedReader uses an internal buffer (default: 8192 characters) for efficient reading.
- Example:
	FileReader fr = new FileReader("filename.txt");
	BufferedReader br = new BufferedReader(fr);

─────────────────────────────────────────────
Constructors in Java
─────────────────────────────────────────────
- Special methods to initialize objects.
- Same name as class, no return type.
- Called automatically when an object is created.

Types:
- Default Constructor: No parameters, provided by compiler if none defined.
- Parameterized Constructor: Accepts parameters for custom initialization.

Restrictions:
- Cannot be abstract, static, final, or synchronized.

Example:
	public SampleDemo() { }
	public SampleDemo(int x) { }
	public SampleDemo(String name, int age) { }

Implicit vs Explicit Constructors
─────────────────────────────────────────────
- Implicit: Provided by compiler if none defined.
- Explicit: Defined by programmer, can have parameters.

─────────────────────────────────────────────
Inheritance from Object Class
─────────────────────────────────────────────
- Every Java class implicitly inherits from Object.
- Object class provides:
	- toString(): String representation.
	- equals(Object obj): Equality check.
	- hashCode(): Hash code.
	- getClass(): Runtime class info.
	- clone(): Copy object.
	- finalize(): Called before destruction.
- These methods can be overridden for custom behavior.

─────────────────────────────────────────────
Constructor vs Methods
─────────────────────────────────────────────
Purpose:
- Constructor: Initializes objects.
- Method: Defines behaviors/actions.

Name:
- Constructor: Same as class name.
- Method: Any name except class name.

Return Type:
- Constructor: No return type.
- Method: Must have a return type.

Invocation:
- Constructor: Called automatically during object creation.
- Method: Called explicitly via object reference.

Inheritance:
- Constructor: Not inherited.
- Method: Inherited (unless private).

Overloading:
- Both can be overloaded.
- Methods can be overridden.

Modifiers:
- Constructor: Cannot be abstract, static, final, synchronized.
- Method: Can have these modifiers.

Example:
	// Constructor
	public SampleDemo() { }
	// Method
	public void display() { }

─────────────────────────────────────────────
Custom Data Structures
─────────────────────────────────────────────
- User-defined ways to organize and store data.
- Examples:
	- Linked List: Nodes pointing to next node.
	- Stack: Last-In-First-Out (LIFO).
	- Queue: First-In-First-Out (FIFO).
	- Tree: Hierarchical nodes.
	- Graph: Nodes connected by edges.

Example:
	class Node {
		int data;
		Node next;
	}

Benefits:
- Tailored for specific problems.
- Optimized performance for certain tasks.

─────────────────────────────────────────────
Game Development in Java
─────────────────────────────────────────────
- Designing and programming interactive games.

Key Concepts:
- Game Loop: Updates state and renders graphics.
- Graphics: Drawing shapes, sprites, animations.
- Input Handling: Keyboard, mouse, touch events.
- Physics: Movement, collisions, forces.
- Sound: Music and effects.
- Assets: Images, sounds, resources.

Popular Libraries:
- libGDX
- LWJGL (Lightweight Java Game Library)

Example (Simple Game Loop):
	while (gameRunning) {
		updateGameState();
		renderGraphics();
		handleInput();
	}

─────────────────────────────────────────────
Constructor Overloading
─────────────────────────────────────────────
- Multiple constructors with different parameter lists.
- Allows flexible object creation.

Example:
	class SampleDemo {
		SampleDemo() { }
		SampleDemo(int x) { }
		SampleDemo(String name, int age) { }
	}

- The appropriate constructor is called based on arguments.

─────────────────────────────────────────────
Packages in Java
─────────────────────────────────────────────
- Packages organize related classes, interfaces, and sub-packages.
- Prevent naming conflicts, improve modularity and maintainability.

Syntax:
	package packageName;

Example:
	package day1.basics;

- Built-in packages: java.util, java.io, java.lang, etc.
- Import classes:
	import java.util.Scanner;

- Nested packages create hierarchy.
- Use fully qualified name or import statement to access classes.

Benefits:
- Encapsulation
- Easier maintenance
- Access control via modifiers

Example:
	// File: day1/basics/SampleDemo.java
	package day1.basics;

	public class SampleDemo {
		public void display() {
			System.out.println("Hello from SampleDemo in day1.basics package!");
		}
	}

	// Usage in another file:
	// File: Main.java
	import day1.basics.SampleDemo;

	public class Main {
		public static void main(String[] args) {
			SampleDemo demo = new SampleDemo();
			demo.display();
		}
	}

─────────────────────────────────────────────
Project Structure Example: ShoppingMall
─────────────────────────────────────────────
- Company: IBM
- Client: Amazon

Modules:
- Utils
- Entity
- Services
- Repositories
- Controllers

ShoppingMall Packages:
- com.ibm.amazon.utils
- com.ibm.amazon.entity
- com.ibm.amazon.services
- com.ibm.amazon.repositories
- com.ibm.amazon.controllers

─────────────────────────────────────────────
Common Built-in Java Packages
─────────────────────────────────────────────
Java provides several built-in packages for common programming tasks:

- java.lang: Core language classes (String, Math, System, Object, etc.). Imported by default.
- java.util: Utility classes (collections, Date, Scanner, Random, etc.).
- java.io: Input/output classes (File, BufferedReader, InputStream, etc.).
- java.net: Networking classes (Socket, URL, HttpURLConnection, etc.).
- java.sql: Database connectivity (Connection, Statement, ResultSet, etc.).
- java.awt: Abstract Window Toolkit for GUI programming.
- javax.swing: GUI components (JFrame, JButton, etc.).

These packages are part of the Java Standard Library and are widely used.

─────────────────────────────────────────────
User-defined Packages
─────────────────────────────────────────────
- Created by developers to organize their own classes and interfaces.
- Help structure large projects, avoid naming conflicts, and improve maintainability.

Syntax:
	package com.companyname.clientname.module;

Example:
	// File: com/companyname/clientname/entity/MyClass.java
	package com.companyname.clientname.entity;

	public class MyClass {
		public void show() {
			System.out.println("Hello from MyClass in com.companyname.clientname.entity!");
		}
	}

	// Usage in another file:
	// File: Main.java
	import com.companyname.clientname.entity.MyClass;

	public class Main {
		public static void main(String[] args) {
			MyClass obj = new MyClass();
			obj.show();
		}
	}

Benefits:
- Better code organization
- Encapsulation
- Easier maintenance
- Clear project structure for large applications

─────────────────────────────────────────────
Example Package Structure
─────────────────────────────────────────────
com.zoho.capgemini.stressreducerapp.entity
com.zoho.capgemini.stressreducerapp.utilities
com.zoho.capgemini.stressreducerapp.exceptions
com.zoho.capgemini.stressreducerapp.main

─────────────────────────────────────────────
Access Modifiers in Java
─────────────────────────────────────────────
- Control the visibility of classes, methods, and variables.

Types:
- public: Accessible from any other class.
- protected: Accessible within the same package and subclasses.
- default (no modifier): Accessible only within the same package.
- private: Accessible only within the same class.

Example:
	public int x;        // Accessible everywhere
	protected int y;     // Accessible in package & subclasses
	int z;               // Accessible in package (default)
	private int w;       // Accessible only in this class

Benefits:
- Encapsulation
- Security
- Controlled access to class members

─────────────────────────────────────────────
Private Access Modifier
─────────────────────────────────────────────
- Only accessible within the same class.
- Not accessible from outside, including subclasses and other classes in the same package.
- Used for encapsulation and data hiding.

Example:
	class Example {
		private int secret;
		private void showSecret() {
			System.out.println(secret);
		}
	}

─────────────────────────────────────────────
Default Access Modifier
─────────────────────────────────────────────
- No modifier specified.
- Accessible only within the same package.

Example:
	class Example {
		int value; // default access
		void showValue() {
			System.out.println(value);
		}
	}

─────────────────────────────────────────────
Protected Access Modifier
─────────────────────────────────────────────
- Accessible within the same package and in subclasses (even in different packages).

Example:
	class Example {
		protected int number;
		protected void showNumber() {
			System.out.println(number);
		}
	}

─────────────────────────────────────────────
Public Access Modifier
─────────────────────────────────────────────
- Accessible from any other class, regardless of package.

Example:
	public class Example {
		public int data;
		public void showData() {
			System.out.println(data);
		}
	}

─────────────────────────────────────────────
Real-world Example: Encapsulation
─────────────────────────────────────────────
Suppose you are developing a banking application. Sensitive data like account balance and transaction history should be hidden from direct access. Use private fields and public methods for secure access.

Example:
	public class BankAccount {
		private double balance; // private field

		public double getBalance() { // public method
			return balance;
		}

		public void deposit(double amount) {
			if (amount > 0) {
				balance += amount;
			}
		}

		public void withdraw(double amount) {
			if (amount > 0 && amount <= balance) {
				balance -= amount;
			}
		}
	}

─────────────────────────────────────────────
Multiple Inheritance in Java
─────────────────────────────────────────────
- Java does not support multiple inheritance (a class extending more than one class) to avoid ambiguity (diamond problem).
- Instead, Java uses interfaces for multiple inheritance of type.

Example:
	interface A {
		void methodA();
	}

	interface B {
		void methodB();
	}

	class C implements A, B {
		public void methodA() { /* implementation */ }
		public void methodB() { /* implementation */ }
	}

─────────────────────────────────────────────
Constructor Inheritance
─────────────────────────────────────────────
- Constructors are not inherited, but you can call a parent constructor using super().

Example:
	class Parent {
		Parent() {
			System.out.println("Parent constructor");
		}
	}

	class Child extends Parent {
		Child() {
			super(); // Calls Parent constructor
			System.out.println("Child constructor");
		}
	}

─────────────────────────────────────────────
Constructor Modifiers
─────────────────────────────────────────────
- private: Allowed. Used for Singleton, utility, or factory patterns.
- abstract: Not allowed. Constructors cannot be abstract.
- final: Not allowed. Constructors cannot be final.

─────────────────────────────────────────────
Accessing Base Class Variables
─────────────────────────────────────────────
- public: Accessible in derived class.
- protected: Accessible in derived class (even in different packages).
- default: Accessible only if derived class is in same package.
- private: Not accessible directly in derived class.

─────────────────────────────────────────────
Object Access from Main Program
─────────────────────────────────────────────
- You cannot directly access the object from the main program to the class. Use the this keyword to refer to the current object within the class.

─────────────────────────────────────────────
Static Keyword
─────────────────────────────────────────────
The static keyword in Java is used to create elements that belong to the class itself rather than to instances (objects) of the class.

Static Variables
─────────────────────────────────────────────
- Shared across all instances of the class (class variables).
- Only one copy exists, regardless of how many objects are created.
- Accessed directly through the class name: ClassName.variableName.
- Initialized when the class is loaded by the JVM.
- Used mainly for memory management.

Example:
	class Example {
		static int counter = 0;
	}

Static Methods
─────────────────────────────────────────────
- Belong to the class, not to objects.
- Called through the class name: ClassName.methodName().
- Cannot access non-static (instance) variables/methods directly.
- Cannot use this or super keywords.
- Cannot be overridden (only hidden in subclasses).

Example:
	class Example {
		static void show() {
			System.out.println("Static method");
		}
	}

Static Blocks
─────────────────────────────────────────────
- Execute when the class is loaded.
- Used to initialize static variables or perform one-time setup.
- Multiple static blocks execute in the order they appear.

Example:
	class Example {
		static {
			System.out.println("Static block executed");
		}
	}

Static Classes
─────────────────────────────────────────────
- Only nested classes can be static.
- Static nested classes do not need an instance of the outer class.
- Can only access static members of the outer class.

Example:
	class Outer {
		static class Inner {
			void display() {
				System.out.println("Static nested class");
			}
		}
	}

Common Use Cases
─────────────────────────────────────────────
- Utility methods (e.g., Math.random(), Arrays.sort()).
- Constants (e.g., Math.PI, Integer.MAX_VALUE).
- Factory methods (e.g., getInstance()).
- Counters and shared resources.
- Main method (program entry point).


Features of Static Keyword
─────────────────────────────────────────────
- The static keyword in Java can be applied to:
	- Variables (static variables)
	- Methods (static methods)
	- Blocks (static initialization blocks)
	- Inner classes (static nested classes)
- Static members belong to the class, not to any specific object.
- Static members are shared among all instances of the class.
- Static methods cannot access non-static (instance) members directly.
- Static blocks are executed when the class is loaded.
- Static nested classes can access only static members of the outer class.

Can we overload the Static method?

Yes, you can overload static methods in Java. Method overloading means having multiple methods with the same name but different parameter lists (different number or types of parameters).

For static methods, the rules of overloading are the same as for instance methods:

The method name must be identical
The parameter list must be different (different types, number, or order of parameters)
Return type alone is not sufficient for overloading


Instance Method  ----- Invoke ---tick---- Instance Method
                   |
                   --- Access ---tick---- Instance Variables (Data field)
                   |
                   --- Invoke ---tick---- Static Method
                   |
                   --- Access ---tick---- Static Variables

Static Method    ----- Invoke ---tick---- Static Method
                   |
                   --- Access ---tick---- Static Variables
                   |
                   --- Invoke ---cross--- Instance Method (directly)
                   |
                   --- Access ---cross--- Instance Variables (directly)

-------------------------------------------------------------------------------

Static Blocks in Java
Static blocks (also called static initialization blocks) are sections of code that execute when a class is loaded into memory by the Java Virtual Machine (JVM).

-------------------------------------------------------------------------------

Key Features
Execute once when the class is first loaded
Run before any instance of the class is created
Execute before the main method
Multiple static blocks run in the order they appear in the class
Used to initialize static variables or perform one-time setup operations

-------------------------------------------------------------------------------

Static Block Execution in Java:
Static blocks execute when a class is loaded into memory, following these rules:

Execution timing:
Static blocks execute when the class is first loaded by the JVM
This happens before any instance of the class is created
Static blocks run before the main method executes

Execution order:
Multiple static blocks execute in the order they appear in the class
All static blocks complete before any constructor or method runs

--------------------------------------------------------------------------------

public class Example {
    static {
        System.out.println("First static block");
    }
    
    public static void main(String[] args) {
        System.out.println("Main method");
    }
    
    static {
        System.out.println("Second static block");
    }
}

Output:

First static block
Second static block
Main method

Class loading triggers:

First reference to a static member of the class
Creation of an instance of the class
Explicit loading via Class.forName()
Static blocks are ideal for one-time initialization tasks that need to happen before the class is used.

----------------------------------------------------------------------------------

─────────────────────────────────────────────
Real-World Static Example: Flight Booking System
─────────────────────────────────────────────

In a flight booking application:
• The total number of available seats is static
• This count is shared across all user sessions
• When any user books a seat, the count decreases
• All users immediately see the updated availability
• Prevents overbooking and maintains data consistency

Example Code:
public class FlightBookingSystem {
	private static int availableSeats = 180;  // Boeing 737 capacity
	
	public static synchronized boolean bookSeat() {
		if (availableSeats > 0) {
			availableSeats--;
			return true;  // Booking successful
		}
		return false;  // No seats available
	}
	
	public static int getAvailableSeats() {
		return availableSeats;
	}
}

---------------------------------------------------------------------------------------------------------

Final Keyword:
The final keyword is declared with variable, method and class indicated that this cannot be modified

- the value of the final varaiable cannot be changed.
- A final method cannot be overridden.
- A final class cannot be inherited.

----------------------------------------------------------------------------------------------------------

What is blank static final variable?

	We can declare the variable with static and the final without initialization.

----------------------------------------------------------------------------------------------------------

Can we override the final method?

	We cannot override the final method.

----------------------------------------------------------------------------------------------------------

Can we inherit the final class?

	No we cannot inherit the final class

----------------------------------------------------------------------------------------------------------

Tell some final inbuilt classes.

String - Immutable sequence of characters
Integer - Wrapper class for int primitive type
Double - Wrapper class for double primitive type
Float - Wrapper class for float primitive type
Boolean - Wrapper class for boolean primitive type
Long - Wrapper class for long primitive type
Short - Wrapper class for short primitive type
Byte - Wrapper class for byte primitive type
Character - Wrapper class for char primitive type
Math - Contains methods for performing basic numeric operations
System - Provides access to system resources
Collections - Utility methods for collections
Arrays - Utility methods for arrays
BigDecimal - Immutable, arbitrary-precision signed decimal numbers
BigInteger - Immutable arbitrary-precision integers

-----------------------------------------------------------------------------------------------------------

Use of Final Keyword in Java
The final keyword in Java is used to impose restrictions on classes, methods, and variables. It indicates that the entity cannot be modified or extended further.

Final Variables
Value cannot be changed after initialization
Makes the variable a constant
Often used for configuration values or mathematical constants
Convention: named in ALL_CAPS with underscores

Final Methods
Cannot be overridden by subclasses
Ensures the method's behavior remains consistent across all subclasses
Often used for critical methods where functionality should not be altered

Final Classes
Cannot be inherited/extended
Ensures the class design and behavior cannot be modified
Used for security-sensitive classes or when inheritance might break functionality

Final Parameters
Cannot be reassigned within a method
Ensures the parameter reference cannot be changed

Blank Final Variables
Declared without initialization
Must be initialized in every constructor (instance variables)
Must be initialized in a static block (static final variables)
 
-----------------------------------------------------------------------------------------------------------

Abstract Class in Java

- An abstract class in Java is a class that cannot be instantiated directly and is designed to be subclassed. It serves as a blueprint for other classes and can contain a mix of abstract methods (methods without implementation) and concrete methods (methods with implementation)
- Abstract is a non access modifier in java which is applicable for classes, interfaces, methods and inner classes.
- It represents an incomplete class that depends on subclasses for its implementation creating subclass is compulsory for abstract class.
- A non substract class is sometimes called a concrete class.
- An abstract concept is not applicable to variables.

------------------------------------------------------------------------------------------------------------

Abstract Classes and Methods in Java
Abstract Methods

    An abstract method is declared without an implementation (no method body):

    java
    abstract void display();

    Abstract methods can only be declared inside an abstract class.

    Subclasses must provide concrete implementations for all inherited abstract methods unless they are also abstract.

Abstract Classes

    An abstract class is a class that cannot be instantiated and may contain abstract methods.

    java
    abstract class Shape {
        abstract void draw();
    }

    You cannot create objects of an abstract class directly.

Reference Assignments

    An abstract class reference can refer to any object of its derived (sub) classes.

    This enables polymorphism: you can use a parent abstract class reference to point to a subclass object and call overridden methods.

    java
    abstract class Animal {
        abstract void sound();
    }

    class Dog extends Animal {
        void sound() { System.out.println("Woof!"); }
    }

    class Cat extends Animal {
        void sound() { System.out.println("Meow!"); }
    }

    public class Main {
        public static void main(String[] args) {
            Animal a1 = new Dog(); // abstract class reference to Dog object
            Animal a2 = new Cat(); // abstract class reference to Cat object

            a1.sound(); // Output: Woof!
            a2.sound(); // Output: Meow!
        }
    }

Summary Table
Feature	Abstract Class	Abstract Method
Can be instantiated?	❌ No	N/A
Can have abstract methods?	✔️ Yes	Only in abstract classes
Can contain implemented (concrete) methods?	✔️ Yes	❌ No (no body allowed)
Used for	Inheritance, polymorphism	Defer implementation to subclass

-----------------------------------------------------------------------------------------------------------------------

Polymorphism in Java
What is Polymorphism?

    Polymorphism is the ability of an object to take on many forms.

    The word comes from Greek: poly means many, morph means forms.

    In Java, polymorphism allows one interface to be used for a general class of actions.

    The same method or operation can show different behaviors (functionality) depending on the context—also called “one thing, many forms.”

    It enables:

        Reusing code

        Cleaner, more extensible programs

        Different logic execution for the same operation

Types of Polymorphism

Java supports two main types of polymorphism:

    Compile-Time Polymorphism (Static Binding / Method Overloading)

        The method to be executed is determined at compile time.

        Achieved using method overloading (same method name, different parameters).

java
class MathUtils {
    int add(int a, int b)        { return a + b; }
    double add(double a, double b) { return a + b; }
}

Run-Time Polymorphism (Dynamic Binding / Method Overriding)

    The method to be executed is determined at run time.

    Achieved using method overriding, where a subclass provides a specific implementation of a method declared in the parent class.

    java
    class Animal {
        void sound() { System.out.println("Animal makes a sound"); }
    }
    class Dog extends Animal {
        void sound() { System.out.println("Woof!"); }
    }
    // Usage:
    Animal myDog = new Dog();
    myDog.sound(); // Output: Woof!

Why Use Polymorphism?

    Code flexibility: Easily swap out or extend functionalities.

    Extensibility: Add new child classes with different behaviors without changing client code.

    Abstraction: Write code that works on the superclass/interface, not specific subclasses.

How Polymorphism Works in Java

    Method Overloading: Same method name, different argument lists within a class.

    Method Overriding: Subclass redefines a parent class method with the same name and parameters.

    Superclass Reference: A superclass reference can point to a subclass object, enabling dynamic method dispatch.

    java
    Shape s;
    s = new Circle();
    s.draw(); // Calls Circle's draw()
    s = new Rectangle();
    s.draw(); // Calls Rectangle's draw()

Summary Table
Type	Description	Example
Compile-Time	Overloading – resolved during compilation	add(), print() with different parameters
Run-Time	Overriding – resolved at runtime (dynamic)	sound() in Animal/Dog classes

------------------------------------------------------------------------

Characteristics and Advantages of Polymorphism in Java
Characteristics

    Multiple Forms: Objects can exhibit different behaviors for the same operation, depending on their actual subclass type.

    Method Overloading: Supports defining multiple methods with the same name but different signatures within a class (compile-time polymorphism).

    Method Overriding: Subclasses can provide their own implementation of a parent class method (run-time polymorphism).

    Superclass References: A superclass reference can point to objects of its subclasses, enabling dynamic method dispatch at runtime.

    Abstraction Support: Enables programming to interfaces or abstract classes, not concrete implementations.

Advantages

    Code Reusability: Write generic, reusable code that works with superclasses or interfaces, reducing duplication.

    Extensibility: Easily add new child classes or logic without altering existing code, promoting easier maintenance and updates.

    Flexibility: Swap out implementations dynamically at runtime, depending on application logic.

    Easier Maintenance: Centralizes logic in parent classes, while subclasses can change specific behaviors, making bug fixes and enhancements simpler.

    Improved Readability: Code is cleaner and more organized, as the same method call can handle different object types seamlessly.

Disadvantages of Polymorphism in Java

    Complexity: Polymorphism can make code harder to understand and maintain, especially when multiple classes override the same methods or there are deep inheritance hierarchies. Developers may need to trace through several classes to figure out which method gets executed at runtime.

    Performance Overhead: Run-time polymorphism involves dynamic method dispatch, which introduces some extra processing to determine the correct method implementation during execution. This can slightly degrade performance, especially in performance-critical applications.

    Debugging Difficulty: Because the actual method that runs is determined at runtime, debugging polymorphic code can be challenging. It may be difficult to know exactly which method implementation is being called, making troubleshooting more complex.

    Hidden Behavior: Polymorphism can lead to less transparent code, where the behavior of a method depends on the object's actual runtime type rather than its declared type, which may confuse readers or maintainers unfamiliar with the code.

    Increased Memory Usage: Polymorphism and inheritance hierarchies can lead to more objects and method tables in memory, potentially increasing memory consumption.

    Potential for Misuse or Overuse: Excessive abstraction with polymorphism can make code unnecessarily complicated, reducing readability and increasing maintenance burden.

    Limited Compiler Optimization: Due to dynamic method lookup, compilers may not optimize polymorphic method calls as aggressively as static calls, which may impact runtime efficiency.

    Type Safety and Casting Issues: Downcasting parent references to child types can lead to runtime errors if not handled correctly.

    Design Constraints: Poorly designed inheritance hierarchies supporting polymorphism can cause fragile base class problems or the diamond problem, making code brittle to changes.

--------------------------------------------------------------------------

Types of Polymorphism in Java

Polymorphism in Java mainly has two types:
1. Compile-Time Polymorphism (Static Polymorphism)

    Also called Static Binding or Early Binding.

    Resolved during compile time by the compiler.

    Achieved via Method Overloading (same method name, different parameter lists within the same class).

    Also includes Operator Overloading in languages that support it, but Java primarily uses method overloading.

    Provides fast execution since method calls are resolved early.

Example:

java
class Calculator {
    int add(int a, int b) {
        return a + b;
    }
    int add(int a, int b, int c) {
        return a + b + c;
    }
}

2. Run-Time Polymorphism (Dynamic Polymorphism)

    Also called Dynamic Binding or Late Binding.

    Resolved during run time by the JVM based on the object's actual type.

    Achieved via Method Overriding (subclass implements a method declared in superclass with the same signature).

    Enables dynamic method dispatch, where the call to overridden methods is resolved at runtime.

    More flexible but involves slight performance overhead compared to compile-time polymorphism.

Example:

java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("Woof!");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal a = new Dog(); // Animal reference to Dog object
        a.sound(); // Output: Woof! (resolved at runtime)
    }
}

Summary Table
Type	Description	Example	Binding Time
Compile-Time Polymorphism	Method Overloading (same method name, different parameters)	add(int, int) vs add(int, int, int)	Compile Time
Run-Time Polymorphism	Method Overriding (subclass changes superclass method)	sound() in Animal and overridden in Dog	Run Time

--------------------------------------------------------------------------------

Compile-Time Polymorphism (Static Polymorphism / Early Binding) in Java
What is Compile-Time Polymorphism?

    Also known as static polymorphism or early binding.

    The method to be executed is determined during compilation, not at runtime.

    Achieved primarily through method overloading (same method name with different parameter lists) within the same class.

    Fast execution, as the correct method version is matched and bound during compile time.

How is it Achieved?
1. Method Overloading

    Defining multiple methods with the same name but different parameter lists (types, number, or order).

    The compiler selects which method to call based on the method signature and arguments provided.

java
class Printer {
    void print(int num) {
        System.out.println("Printing integer: " + num);
    }
    void print(String str) {
        System.out.println("Printing string: " + str);
    }
}

Usage:

java
Printer p = new Printer();
p.print(100);       // Calls print(int num)
p.print("Hello");   // Calls print(String str)

2. Operator Overloading

    Note: Java does NOT support user-defined operator overloading, but some built-in types (like + for Strings) exhibit this characteristic internally.

Characteristics

    Binding Time: Occurs at compile time.

    Performance: Faster as method calling is direct, with no extra lookups at runtime.

    Flexibility: Limited to situations where variations can be resolved by the compiler.

Advantages

    Performance: Faster method execution since the compiler resolves the right method call.

    Readability: Overloaded methods with the same name increase code clarity when similar operations use different inputs.

Limitations

    Cannot be used for scenarios where the method to be called depends on the object's runtime type (i.e., run-time polymorphism).

    Strictly resolved by the compiler—only parameter types/numbers order can differ (return type alone is not enough).

Summary Table
Feature	Compile-Time Polymorphism
Also Known As	Static Polymorphism, Early Binding
Determined	At compile time
Achieved By	Method Overloading
Example	print(int), print(String)
Performance	Faster
Flexibility	Limited to known method signatures

In summary:
Compile-time polymorphism allows Java programs to use the same method names for similar functionalities with different input types, with which the compiler matches the correct method during compilation. This makes code easier to understand and more efficient, provided all variations are known before runtime.
 
-------------------------------------------------------------------------------

Types of Overloading in Java

Overloading in Java refers to defining multiple methods in the same class with the same name but different parameter lists. It is a key concept used for compile-time (static) polymorphism.
1. Method Overloading

    Definition: Two or more methods in the same class (or a subclass) that have the same name but differ in number, type, or order of parameters.

    Signature differences: The methods must differ by parameter list—not just the return type.

Examples:

java
class MathUtils {
    int add(int a, int b)           { return a + b; }
    double add(double a, double b)  { return a + b; }
    int add(int a, int b, int c)    { return a + b + c; }
}

Usage:

java
MathUtils m = new MathUtils();
m.add(5, 3);            // Calls add(int, int)
m.add(4.5, 3.2);        // Calls add(double, double)
m.add(1, 2, 3);         // Calls add(int, int, int)

Ways to Achieve Method Overloading:

    Vary the number of parameters (e.g., two vs. three arguments).

    Vary the types of parameters (e.g., int vs. double).

    Vary the order of parameter types (e.g., (int, double) vs. (double, int)).

2. Constructor Overloading

    Definition: A class can have multiple constructors, each with a unique parameter list.

    Purpose: Allows objects to be initialized in different ways.

Example:

java
class Student {
    Student() {}                          // Default constructor
    Student(String name) {}                // Single parameter constructor
    Student(String name, int age) {}       // Two parameter constructor
}

3. Operator Overloading (Not User-defined in Java)

    Java does not allow user-defined operator overloading (like C++). Only some built-in types (such as + for Strings) support internal overloading.

Summary Table
Type	Achieved By	Example	Purpose
Method Overloading	Methods with same name, different parameter lists	add(int, int) and add(double, double)	Multiple behaviors based on input types/count
Constructor Overloading	Constructors with different parameter lists	Student(), Student(String)	Multiple ways to create an object
Operator Overloading	Built-in only (not user-defined)	"a" + "b" for String concatenation	Internal String manipulation

In summary:
Java supports method overloading and constructor overloading—powerful tools for writing flexible code that can operate with different types and numbers of inputs. Operator overloading is not permitted at the user level in Java.

-------------------------------------------------------------------

Ctrl M to open the codebase
ctrl + f11 to run

-------------------------

Can we overload the constructor?

Yes.

-------------------------------------

Can we apply the final keyword the constructor?

NO.

----------------------------------------

Constructor overloading:

Can we override the static method?

The answer is No.

---------------------------------------------

## Interface in Java

An **interface** can be defined as a container that stores the signature of methods that must be implemented by the classes. It improves the levels of abstraction by specifying *what* a class must do, but not *how* it does it.

---

### Need for Interface

- **Achieves Abstraction:** Interfaces provide a way to achieve **100% abstraction** by declaring method signatures without implementations. This allows you to define a contract that implementing classes must fulfill.

- **Multiple Inheritance:** Java does not support multiple inheritance with classes, but a class can implement multiple interfaces. This allows a class to inherit behavior from multiple sources, solving the diamond problem.

- **Loose Coupling:** Interfaces help in reducing dependencies between classes. Code depending on interfaces rather than concrete classes is more flexible and easier to maintain or extend.

- **Standardization:** Defines a common set of methods that multiple unrelated classes can implement, ensuring consistency across different parts of an application.

- **Enhances Polymorphism:** Since multiple classes can implement the same interface, it allows objects of different types to be treated uniformly based on the common interface type.

---

### Example

interface Drawable {
void draw(); // method signature only
}

class Circle implements Drawable {
public void draw() {
System.out.println("Drawing Circle");
}
}

class Rectangle implements Drawable {
public void draw() {
System.out.println("Drawing Rectangle");
}
}

// Usage:
Drawable shape = new Circle();
shape.draw(); // Calls Circle's draw method

text

---

> **Summary:**  
> Interfaces are essential to design flexible, scalable, and extensible object-oriented programs by defining clear contracts, enabling multiple inheritance, and promoting abstraction and polymorphism.

Types of Interfaces in Java

Java interfaces specify a contract of method signatures that implementing classes must fulfill. They are used for abstraction, multiple inheritance of type, and improving modularity. There are several types of interfaces in Java based on their usage and characteristics:
1. Normal Interface

    Contains two or more abstract methods.

    Can also include default methods (with implementation) and static methods (since Java 8).

    Can declare constants (implicitly public static final).

    Used to define a set of behaviors that classes must implement.

    Example: java.util.List, java.util.Map.

2. Functional Interface (Single Abstract Method - SAM)

    Contains exactly one abstract method.

    Can have any number of default or static methods.

    Can be used as the target for lambda expressions and method references.

    Annotated optionally with @FunctionalInterface to indicate intent.

    Examples:

        java.lang.Runnable (method run())

        java.util.Comparator (method compare())

        java.awt.event.ActionListener (method actionPerformed())

3. Marker Interface

    Contains no methods or fields (completely empty).

    Used to "mark" classes for special behavior or metadata.

    The presence of the interface indicates to the JVM or frameworks that the class has certain properties or abilities.

    Examples:

        java.io.Serializable

        java.lang.Cloneable

        java.util.RandomAccess

Summary Table
Interface Type	Description	Example Interfaces
Normal Interface	Contains multiple abstract methods; can have static/default methods and constants	List, Map, Set
Functional Interface	Exactly one abstract method, usable with lambdas	Runnable, Comparator, ActionListener
Marker Interface	No methods or fields; used to mark classes for special treatment	Serializable, Cloneable
Additional Notes:

    Interfaces can extend multiple other interfaces (interface inheritance).

    Since Java 8, interfaces can have default and static methods with implementations.

    Functional interfaces enable functional programming features in Java.

-----------------------------------------------------------

Wrapper Class:

In Java, a wrapper class is a class that encapsulates (or "wraps") primitive data types so they can be used as objects. Each primitive data type in Java (like int, char, double, etc.) has a corresponding wrapper class in the java.lang package.
Common Java Wrapper Classes
Primitive Type	Wrapper Class
boolean	Boolean
byte	Byte
char	Character
short	Short
int	Integer
long	Long
float	Float
double	Double
Example Usage

java
// Using an int and its wrapper class Integer
int primitiveInt = 42;
Integer wrappedInt = Integer.valueOf(primitiveInt); // boxing
int backToPrimitive = wrappedInt.intValue();        // unboxing

// Autoboxing and unboxing (Java 5+ feature)
Integer autoBoxed = primitiveInt; // autoboxing
int autoUnboxed = autoBoxed;      // auto-unboxing

Why Use Wrapper Classes?

    Collection Framework: Java collections (like ArrayList) work with objects, not primitives.

    Utility Methods: Wrapper classes include useful methods (e.g., parsing strings to numbers).

    Nullability: Wrapper classes can be null, primitives cannot.

    Type Conversion: Useful for converting data types and parsing.

	----------------------------------------------------------------

	Where does the Wrapper Class data store?

	Wrapper class data in Java is stored in the heap memory. When you create a wrapper object, such as an Integer, Double, or any other wrapper class, the object itself is allocated on the heap, while the reference variable (if local) is on the stack. The primitive value is encapsulated as a field inside the wrapper object, which lives on the heap

.

    Primitive Types: Directly stored in stack memory if they are local variables.

    Wrapper Objects: The object (containing the value and object metadata) is allocated on the heap. The reference to the object may be on the stack (for local variables) or in other areas depending on scope

    .

Memory and optimization:

    Wrapper objects use more memory than primitives due to object overhead and, in many cases, a pointer to the object

.

For certain values (like Integer values from -128 to 127), Java uses a pooled cache, and valueOf() will refer to shared instances to optimize heap use

.

Using new for wrapper objects always creates a new heap allocation. Using valueOf() may reuse existing objects (for supported values), improving memory efficiency

    .

Summary Table:
Type	Value Storage	Reference Storage
int	Stack (local vars)	n/a
Integer	Heap (object data)	Stack (local ref)

Key Point:
Wrapper class data (the object and its primitive value) is stored on the heap, whereas primitive types live on the stack (for local variables). Reference variables to these objects are stored on the stack if they are local
.

Wrapping and unwrapping in java:

In Java, wrapping and unwrapping data are most commonly used in the context of cryptography, especially for secure key management.

Wrapping a key means encrypting (encapsulating) a cryptographic key using another key, so it can be safely stored or transmitted. Unwrapping is the process of decrypting (extracting) the original key from its wrapped byte form.
How to Wrap and Unwrap Keys in Java

    To wrap a key:

        Initialize a Cipher object in Cipher.WRAP_MODE.

        Call cipher.wrap(Key keyToWrap), which returns a byte array containing the wrapped key.

        Along with the wrapped key bytes, record the key algorithm (e.g., "AES") and key type (SECRET_KEY, PRIVATE_KEY, or PUBLIC_KEY), as you'll need them to unwrap the key later

    .

To unwrap a key:

    Initialize a Cipher in Cipher.UNWRAP_MODE.

    Call cipher.unwrap(byte[] wrappedKey, String algorithm, int type), where:

        wrappedKey is the byte array from the previous step.

        algorithm is the algorithm name obtained previously (such as by calling getAlgorithm() on the key before wrapping).

        type refers to the kind of key and must be one of Cipher.SECRET_KEY, Cipher.PRIVATE_KEY, or Cipher.PUBLIC_KEY

            .

Example (simplified):

java
// Setup
Cipher cipher = Cipher.getInstance("AESWrap");
cipher.init(Cipher.WRAP_MODE, wrappingKey);
byte[] wrapped = cipher.wrap(targetKey);

// Record algorithm/type for unwrapping
String algorithm = targetKey.getAlgorithm();
int type = Cipher.SECRET_KEY; // or Cipher.PRIVATE_KEY, etc.

// Later, unwrap
cipher.init(Cipher.UNWRAP_MODE, wrappingKey);
Key originalKey = cipher.unwrap(wrapped, algorithm, type);

The above shows the core logic, but you'll need to handle things like key generation/import, secure storage, and exceptions according to your use case

.

Important notes:

    The actual algorithm and provider vary (e.g., "AESWrap", "RSA/ECB/PKCS1Padding"). Choose based on your security requirements.

    When wrapping with block ciphers like AES, certain modes (e.g., RFC 3394 key wrap) are preferred for interoperability, but modes like CBC are sometimes used (be careful with IV handling!) 

.

You must keep track of both the key algorithm and key type when unwrapping

.

Key wrapping is not limited to keys; the concept can also apply to other sensitive data

    .

Reference APIs: See javax.crypto.Cipher methods: wrap(Key key), unwrap(byte[] data, String algorithm, int type), and initialization modes WRAP_MODE and UNWRAP_MODE
.

why do we need wrapper class:

Wrapper classes are necessary in Java because they allow primitive data types (like int, double, char) to be used as objects, which is essential for many of Java's features and APIs.

Main reasons wrapper classes are needed:

    Object compatibility: Many Java APIs, such as the Collection Framework (ArrayList, HashMap, etc.), only work with objects, not primitives. Wrapper classes convert primitives into objects so they can be stored in these collections

.

Autoboxing and unboxing: Java uses wrapper classes to automatically convert between primitives and their object counterparts (autoboxing and unboxing), making code more concise and readable

.

Nullability: Wrapper objects can be null, allowing you to express the absence of a value (important for things like database records or optional fields), which is not possible with primitive types

.

Utility methods: Wrapper classes provide useful methods for parsing, converting, and manipulating values, such as Integer.parseInt(), Double.valueOf(), and toString(). These make it easier to handle user input, formatting, and conversions

.

Generics support: Java generics cannot operate with primitives directly. Using wrapper classes makes it possible to use generic classes and methods with primitive values (e.g., List<Integer> but not List<int>)

.
s
Immutability and thread safety: All wrapper class objects in Java are immutable, which enhances safety for use in multi-threaded environments

.

Interoperability and advanced programming: Some features like synchronization and reflection require objects, so wrapper classes make primitives compatible with these patterns and APIs

    .

In summary, wrapper classes bridge the gap between primitive data types and Java's object-oriented ecosystem, enabling features and flexibility that primitives alone can't provide

.

Key examples: Storing integers in an ArrayList, parsing user input from String to int via Integer.parseInt(), or handling possibly-null numeric values returned from a database.

Exception Handling in Java:
─────────────────────────────────────────────

Exception handling in Java is a powerful mechanism that allows programs to handle runtime errors gracefully, maintaining normal application flow and preventing abrupt program termination.

What is an Exception?
─────────────────────────────────────────────
- An exception is an unwanted or unexpected event that occurs during program execution
- It disrupts the normal flow of program instructions
- Examples: division by zero, array index out of bounds, file not found, null pointer access

Benefits of Exception Handling
─────────────────────────────────────────────
- Prevents program crashes and maintains application stability
- Separates error-handling code from normal business logic
- Provides meaningful error messages to users and developers
- Enables graceful recovery from error conditions
- Improves code readability and maintainability

Exception Hierarchy in Java
─────────────────────────────────────────────
All exceptions inherit from the Throwable class:

Object
  └── Throwable
       ├── Error (Unchecked - System errors, cannot be handled)
       │    ├── OutOfMemoryError
       │    ├── StackOverflowError
       │    └── VirtualMachineError
       └── Exception
            ├── Checked Exceptions (Compile-time checking required)
            │    ├── IOException
            │    ├── SQLException
            │    ├── ClassNotFoundException
            │    └── InterruptedException
            └── RuntimeException (Unchecked - Runtime errors)
                 ├── NullPointerException
                 ├── ArrayIndexOutOfBoundsException
                 ├── ArithmeticException
                 ├── IllegalArgumentException
                 └── NumberFormatException

Types of Exceptions
─────────────────────────────────────────────

1. Checked Exceptions:
   - Must be handled at compile time using try-catch or throws
   - Compiler forces you to handle them
   - Examples: IOException, SQLException, ClassNotFoundException

2. Unchecked Exceptions (Runtime Exceptions):
   - Not required to be handled at compile time
   - Occur during program execution
   - Examples: NullPointerException, ArrayIndexOutOfBoundsException

3. Errors:
   - Serious problems that applications should not try to catch
   - Usually indicate system-level issues
   - Examples: OutOfMemoryError, StackOverflowError

Exception Handling Keywords
─────────────────────────────────────────────

try: Block that contains code that might throw an exception
catch: Block that handles the exception
finally: Block that always executes, regardless of exception occurrence
throw: Used to explicitly throw an exception
throws: Used in method signature to declare exceptions that method might throw

Basic Exception Handling Syntax
─────────────────────────────────────────────

try {
    // Code that might throw an exception
} catch (ExceptionType1 e) {
    // Handle ExceptionType1
} catch (ExceptionType2 e) {
    // Handle ExceptionType2
} finally {
    // Code that always executes
}

Example: Basic Exception Handling
─────────────────────────────────────────────

public class ExceptionExample {
    public static void main(String[] args) {
        try {
            int result = 10 / 0; // ArithmeticException
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            System.out.println("Error: Division by zero!");
            System.out.println("Exception message: " + e.getMessage());
        } finally {
            System.out.println("Finally block always executes");
        }
    }
}

Multiple Catch Blocks
─────────────────────────────────────────────

try {
    int[] arr = {1, 2, 3};
    System.out.println(arr[5]); // ArrayIndexOutOfBoundsException
    int result = 10 / 0; // ArithmeticException
} catch (ArrayIndexOutOfBoundsException e) {
    System.out.println("Array index error: " + e.getMessage());
} catch (ArithmeticException e) {
    System.out.println("Arithmetic error: " + e.getMessage());
} catch (Exception e) {
    System.out.println("General exception: " + e.getMessage());
}

Multi-catch Block (Java 7+)
─────────────────────────────────────────────

try {
    // Some code that might throw multiple exception types
} catch (IOException | SQLException e) {
    System.out.println("IO or SQL exception occurred: " + e.getMessage());
}

Throwing Custom Exceptions
─────────────────────────────────────────────

public class CustomException extends Exception {
    public CustomException(String message) {
        super(message);
    }
}

public class Example {
    public static void validateAge(int age) throws CustomException {
        if (age < 18) {
            throw new CustomException("Age must be 18 or older");
        }
    }
}

Method Exception Declaration
─────────────────────────────────────────────

public void readFile(String filename) throws IOException {
    FileReader file = new FileReader(filename);
    // File reading code
}

// Caller must handle the exception
public void someMethod() {
    try {
        readFile("data.txt");
    } catch (IOException e) {
        System.out.println("File reading failed: " + e.getMessage());
    }
}

Finally Block Rules
─────────────────────────────────────────────
- Always executes, whether exception occurs or not
- Used for cleanup operations (closing files, database connections)
- Executes even if return statement is in try or catch block
- Does not execute only if System.exit() is called or JVM crashes

Example with Resource Management:
FileInputStream file = null;
try {
    file = new FileInputStream("data.txt");
    // Process file
} catch (IOException e) {
    System.out.println("File error: " + e.getMessage());
} finally {
    if (file != null) {
        try {
            file.close();
        } catch (IOException e) {
            System.out.println("Error closing file");
        }
    }
}

Try-with-Resources (Java 7+)
─────────────────────────────────────────────
Automatically manages resources that implement AutoCloseable:

try (FileInputStream file = new FileInputStream("data.txt");
     BufferedReader reader = new BufferedReader(new InputStreamReader(file))) {
    
    // Use resources
    String line = reader.readLine();
    
} catch (IOException e) {
    System.out.println("File error: " + e.getMessage());
}
// Resources are automatically closed

Common Exception Types and Causes
─────────────────────────────────────────────

NullPointerException:
- Accessing methods/fields on null reference
- Example: String str = null; int len = str.length();

ArrayIndexOutOfBoundsException:
- Accessing array with invalid index
- Example: int[] arr = {1,2,3}; int x = arr[5];

ArithmeticException:
- Division by zero in integer arithmetic
- Example: int result = 10 / 0;

NumberFormatException:
- Invalid string to number conversion
- Example: int num = Integer.parseInt("abc");

IllegalArgumentException:
- Method receives inappropriate argument
- Example: Negative value for positive-only parameter

FileNotFoundException:
- File doesn't exist or cannot be accessed
- Example: new FileInputStream("nonexistent.txt");

Best Practices for Exception Handling
─────────────────────────────────────────────

1. Be Specific with Catch Blocks:
   - Catch specific exceptions rather than generic Exception
   - Order catch blocks from most specific to most general

2. Don't Ignore Exceptions:
   - Always handle or log exceptions appropriately
   - Avoid empty catch blocks

3. Use Finally for Cleanup:
   - Close resources in finally block or use try-with-resources
   - Ensure cleanup code always runs

4. Provide Meaningful Error Messages:
   - Include context about what operation failed
   - Help users understand what went wrong

5. Don't Use Exceptions for Flow Control:
   - Exceptions should be for exceptional circumstances
   - Use normal conditional logic for expected scenarios

6. Create Custom Exceptions When Needed:
   - For domain-specific error conditions
   - Extend appropriate exception class

7. Document Exceptions:
   - Use @throws in Javadoc
   - Specify what conditions cause exceptions

Example: Complete Exception Handling Program
─────────────────────────────────────────────

public class BankAccount {
    private double balance;
    
    public BankAccount(double initialBalance) {
        this.balance = initialBalance;
    }
    
    public void withdraw(double amount) throws InsufficientFundsException {
        if (amount < 0) {
            throw new IllegalArgumentException("Withdrawal amount cannot be negative");
        }
        if (amount > balance) {
            throw new InsufficientFundsException("Insufficient funds. Balance: " + balance);
        }
        balance -= amount;
        System.out.println("Withdrawal successful. New balance: " + balance);
    }
    
    public static void main(String[] args) {
        BankAccount account = new BankAccount(1000.0);
        
        try {
            account.withdraw(500.0);  // Success
            account.withdraw(600.0);  // Will throw InsufficientFundsException
        } catch (InsufficientFundsException e) {
            System.out.println("Transaction failed: " + e.getMessage());
        } catch (IllegalArgumentException e) {
            System.out.println("Invalid input: " + e.getMessage());
        } finally {
            System.out.println("Transaction processing complete");
        }
    }
}

class InsufficientFundsException extends Exception {
    public InsufficientFundsException(String message) {
        super(message);
    }
}

Exception Propagation
─────────────────────────────────────────────
- When an exception occurs in a method, it can be:
  1. Handled locally with try-catch
  2. Propagated to the caller using throws
  3. Allowed to bubble up the call stack until handled

Method Call Chain Example:
method1() calls method2() calls method3()
- If method3() throws exception and doesn't handle it
- Exception propagates to method2()
- If method2() doesn't handle it, propagates to method1()
- Continue until handled or program terminates

Checked vs Unchecked Exception Handling
─────────────────────────────────────────────

Checked Exception (must handle):
public void readFile() throws IOException {
    FileReader file = new FileReader("data.txt");
}

Unchecked Exception (optional to handle):
public void divide(int a, int b) {
    int result = a / b; // May throw ArithmeticException
}

Performance Considerations
─────────────────────────────────────────────
- Exception handling has performance overhead
- Creating exception objects is expensive
- Use exceptions for exceptional cases, not normal flow
- Avoid throwing exceptions in frequently called methods
- Consider alternative approaches for expected error conditions

Summary
─────────────────────────────────────────────
Exception handling is essential for robust Java applications. It provides:
- Graceful error recovery
- Better user experience
- Cleaner code separation
- Debugging information
- Application stability

Key points to remember:
- Handle specific exceptions appropriately
- Use try-with-resources for automatic resource management
- Create meaningful error messages
- Don't ignore exceptions
- Use finally for cleanup operations
- Follow exception handling best practices

Types of Exceptions in Java
─────────────────────────────────────────────

Java exceptions are primarily categorized into two main types: Checked and Unchecked exceptions. Understanding these types is crucial for effective exception handling.

1. Checked Exceptions
─────────────────────────────────────────────

Definition:
- Checked exceptions are compile-time exceptions that must be handled or declared
- The compiler checks these exceptions at compile time
- If not handled, the program will not compile
- Also known as compile-time exceptions

Characteristics:
- Must be caught using try-catch or declared using throws
- Occur due to external factors beyond programmer control
- Represent recoverable conditions
- Extend Exception class but not RuntimeException

Common Checked Exceptions:
- IOException: Input/output operations
- SQLException: Database operations
- ClassNotFoundException: Class loading issues
- InterruptedException: Thread interruption
- FileNotFoundException: File access problems
- ParseException: Data parsing errors

Example of Checked Exception:
public class CheckedExceptionExample {
    public static void main(String[] args) {
        // This will cause compile error without proper handling
        try {
            FileReader file = new FileReader("data.txt"); // IOException
        } catch (IOException e) {
            System.out.println("File not found: " + e.getMessage());
        }
    }
    
    // Or declare the exception
    public static void readFile() throws IOException {
        FileReader file = new FileReader("data.txt");
    }
}

2. Unchecked Exceptions (Runtime Exceptions)
─────────────────────────────────────────────

Definition:
- Unchecked exceptions are runtime exceptions that are not checked at compile time
- The compiler does not force you to handle these exceptions
- Also known as runtime exceptions
- Occur during program execution

Characteristics:
- Optional to handle with try-catch
- Usually caused by programming errors
- Extend RuntimeException class
- Can be prevented by proper programming practices

Common Unchecked Exceptions:
- NullPointerException: Accessing null reference
- ArrayIndexOutOfBoundsException: Invalid array index
- ArithmeticException: Mathematical errors (division by zero)
- IllegalArgumentException: Invalid method arguments
- NumberFormatException: Invalid number format conversion
- StringIndexOutOfBoundsException: Invalid string index
- ClassCastException: Invalid type casting

Example of Unchecked Exception:
public class UncheckedExceptionExample {
    public static void main(String[] args) {
        // These may throw unchecked exceptions
        int[] arr = {1, 2, 3};
        
        try {
            System.out.println(arr[5]); // ArrayIndexOutOfBoundsException
            int result = 10 / 0; // ArithmeticException
            String str = null;
            int length = str.length(); // NullPointerException
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Array index error: " + e.getMessage());
        } catch (ArithmeticException e) {
            System.out.println("Division by zero: " + e.getMessage());
        } catch (NullPointerException e) {
            System.out.println("Null pointer error: " + e.getMessage());
        }
    }
}

3. Errors (System Level)
─────────────────────────────────────────────

Definition:
- Errors represent serious problems that applications should not try to catch
- Indicate system-level issues or resource exhaustion
- Extend Error class
- Usually unrecoverable

Common Error Types:
- OutOfMemoryError: JVM runs out of memory
- StackOverflowError: Stack space exhausted
- VirtualMachineError: JVM malfunction
- NoClassDefFoundError: Class definition not found at runtime

Example:
public class ErrorExample {
    public static void main(String[] args) {
        // This will eventually cause StackOverflowError
        recursiveMethod();
    }
    
    public static void recursiveMethod() {
        recursiveMethod(); // Infinite recursion
    }
}

Comparison Table: Checked vs Unchecked Exceptions
─────────────────────────────────────────────

Aspect                  | Checked Exceptions      | Unchecked Exceptions
------------------------|-------------------------|-------------------------
Compile-time checking   | Yes                     | No
Handling requirement    | Mandatory               | Optional
Inheritance            | Exception (not Runtime) | RuntimeException
Cause                  | External factors        | Programming errors
Recovery possibility   | Usually recoverable     | Often programming bugs
Examples               | IOException, SQLException| NullPointer, ArithmeticException
Declaration needed     | Yes (throws clause)     | No
Performance impact     | Higher (compile checks) | Lower

When to Use Each Type
─────────────────────────────────────────────

Use Checked Exceptions when:
- The calling code can reasonably recover from the exception
- External resources are involved (files, network, database)
- The exception represents a condition the caller should know about
- The operation might fail due to external factors

Use Unchecked Exceptions when:
- The exception represents a programming error
- The caller cannot reasonably recover from the exception
- The condition should be prevented by proper programming
- Performance is critical and checking would be expensive

Best Practices for Exception Types
─────────────────────────────────────────────

For Checked Exceptions:
1. Don't catch and ignore - always handle appropriately
2. Use specific exception types rather than generic Exception
3. Provide meaningful error messages
4. Consider if the caller can actually recover

For Unchecked Exceptions:
1. Prevent them through defensive programming
2. Use assertions and parameter validation
3. Document when methods might throw unchecked exceptions
4. Handle them when graceful degradation is possible

Exception Hierarchy Summary
─────────────────────────────────────────────

java.lang.Object
    └── java.lang.Throwable
         ├── java.lang.Error (Unchecked - System errors)
         │    ├── OutOfMemoryError
         │    ├── StackOverflowError
         │    └── VirtualMachineError
         └── java.lang.Exception
              ├── Checked Exceptions (Compile-time)
              │    ├── IOException
              │    ├── SQLException
              │    ├── ClassNotFoundException
              │    └── InterruptedException
              └── java.lang.RuntimeException (Unchecked - Runtime)
                   ├── NullPointerException
                   ├── ArrayIndexOutOfBoundsException
                   ├── ArithmeticException
                   ├── IllegalArgumentException
                   └── NumberFormatException

Practical Example: Banking Application
─────────────────────────────────────────────

public class BankingExample {
    
    // Checked exception for external issues
    public void processTransaction(String accountFile) throws IOException {
        FileReader file = new FileReader(accountFile); // Checked: IOException
        // Process transaction from file
    }
    
    // Unchecked exception for programming errors
    public void withdraw(double amount) {
        if (amount < 0) {
            // Programming error - use unchecked exception
            throw new IllegalArgumentException("Amount cannot be negative");
        }
        // Process withdrawal
    }
    
    public static void main(String[] args) {
        BankingExample bank = new BankingExample();
        
        // Handle checked exception
        try {
            bank.processTransaction("accounts.txt");
        } catch (IOException e) {
            System.out.println("File processing failed: " + e.getMessage());
        }
        
        // Unchecked exception - optional to handle
        try {
            bank.withdraw(-100); // Will throw IllegalArgumentException
        } catch (IllegalArgumentException e) {
            System.out.println("Invalid withdrawal: " + e.getMessage());
        }
    }
}

Key Takeaways
─────────────────────────────────────────────

1. Checked exceptions ensure compile-time safety but can lead to verbose code
2. Unchecked exceptions provide runtime flexibility but require careful programming
3. Use checked exceptions for recoverable conditions
4. Use unchecked exceptions for programming errors
5. Errors should generally not be caught by application code
6. Choose the appropriate exception type based on the use case and recoverability
7. Always provide meaningful error messages regardless of exception type

Exception vs Errors Flow chart:
─────────────────────────────────────────────

                        java.lang.Throwable
                               │
                ┌──────────────┴──────────────┐
                │                             │
        java.lang.Exception            java.lang.Error
                │                             │
    ┌───────────┴───────────┐                 │
    │                       │                 │
Checked Exceptions    Unchecked Exceptions    │
(Compile-time)        (Runtime Exceptions)    │
    │                       │                 │
    │                       │                 │
    ▼                       ▼                 ▼
┌─────────────┐     ┌─────────────────┐   ┌─────────────────┐
│ Examples:   │     │ Examples:       │   │ Examples:       │
│             │     │                 │   │                 │
│ IOException │     │ NullPointer     │   │ OutOfMemory     │
│ SQLException│     │ Exception       │   │ Error           │
│ ClassNot    │     │                 │   │                 │
│ Found       │     │ ArithmeticEx    │   │ StackOverflow   │
│ Exception   │     │ ception         │   │ Error           │
│             │     │                 │   │                 │
│ FileNot     │     │ ArrayIndexOut   │   │ VirtualMachine  │
│ Found       │     │ OfBounds        │   │ Error           │
│ Exception   │     │ Exception       │   │                 │
└─────────────┘     └─────────────────┘   └─────────────────┘
       │                       │                     │
       ▼                       ▼                     ▼
┌─────────────┐     ┌─────────────────┐   ┌─────────────────┐
│ Must Handle │     │ Optional to     │   │ Should NOT      │
│ at Compile  │     │ Handle          │   │ be Caught       │
│ Time        │     │                 │   │                 │
│             │     │ Caused by       │   │ System Level    │
│ External    │     │ Programming     │   │ Issues          │
│ Factors     │     │ Errors          │   │                 │
│             │     │                 │   │ Usually         │
│ Recoverable │     │ Can be          │   │ Unrecoverable   │
│ Conditions  │     │ Prevented       │   │                 │
└─────────────┘     └─────────────────┘   └─────────────────┘

Decision Flow for Exception Handling:
─────────────────────────────────────────────

                    Exception Occurs
                          │
                          ▼
                ┌─────────────────────┐
                │ Is it an Error?     │
                │ (OutOfMemory,       │
                │ StackOverflow, etc.)│
                └─────────┬───────────┘
                         │
                    ┌────┴────┐
                 Yes│         │No
                    ▼         ▼
            ┌─────────────┐   ┌─────────────────────┐
            │ Don't Catch │   │ Is it a Checked     │
            │ Let it      │   │ Exception?          │
            │ Propagate   │   │ (IOException, SQL)  │
            │ or Log      │   └─────────┬───────────┘
            └─────────────┘            │
                                  ┌────┴────┐
                               Yes│         │No
                                  ▼         ▼
                      ┌─────────────────┐   ┌─────────────────┐
                      │ MUST Handle:    │   │ Runtime         │
                      │ - try-catch OR  │   │ Exception       │
                      │ - throws clause │   │ (Optional)      │
                      │                 │   └─────────┬───────┘
                      │ Compiler will   │            │
                      │ force handling  │            ▼
                      └─────────────────┘   ┌─────────────────┐
                                           │ Can Handle:     │
                                           │ - Validate input│
                                           │ - Use try-catch │
                                           │ - Let propagate │
                                           │                 │
                                           │ Prevention is   │
                                           │ better than     │
                                           │ handling        │
                                           └─────────────────┘

Memory and Performance Impact:
─────────────────────────────────────────────

┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│ Checked         │    │ Unchecked       │    │ Errors          │
│ Exceptions      │    │ Exceptions      │    │                 │
├─────────────────┤    ├─────────────────┤    ├─────────────────┤
│ • High compile  │    │ • Low compile   │    │ • No compile    │
│   time overhead │    │   overhead      │    │   overhead      │
│                 │    │                 │    │                 │
│ • Must declare  │    │ • No declaration│    │ • System level  │
│   or handle     │    │   required      │    │   issues        │
│                 │    │                 │    │                 │
│ • Code bloat    │    │ • Cleaner code  │    │ • Memory/Stack  │
│   possible      │    │   but risky     │    │   problems      │
│                 │    │                 │    │                 │
│ • Better error  │    │ • Runtime       │    │ • Application   │
│   tracking      │    │   surprises     │    │   termination   │
└─────────────────┘    └─────────────────┘    └─────────────────┘

When to Use Each Approach:
─────────────────────────────────────────────

Checked Exceptions - Use When:
═══════════════════════════════
• File operations (I/O)
• Network communications
• Database connections
• External API calls
• Resource management
• Caller can recover from error
• External factors beyond control

Unchecked Exceptions - Use When:
═══════════════════════════════
• Programming logic errors
• Invalid method parameters
• Array bounds violations
• Null pointer access
• Mathematical errors
• Caller cannot reasonably recover
• Prevention is possible through coding

Errors - System Handles:
═══════════════════════
• Memory exhaustion
• Stack overflow
• JVM internal errors
• Hardware failures
• System resource depletion
• Generally unrecoverable
• Let system handle or log

Best Practice Decision Tree:
─────────────────────────────────────────────

                Problem Occurs in Code
                         │
                         ▼
            ┌─────────────────────────┐
            │ Can caller reasonably   │
            │ recover from this?      │
            └─────────┬───────────────┘
                     │
                ┌────┴────┐
             Yes│         │No
                ▼         ▼
    ┌─────────────────┐   ┌─────────────────┐
    │ Is it caused by │   │ Is it a         │
    │ external factors│   │ programming     │
    │ (files, network)│   │ error?          │
    └─────────┬───────┘   └─────────┬───────┘
             │                     │
          Yes▼                  Yes▼
    ┌─────────────────┐   ┌─────────────────┐
    │ Use CHECKED     │   │ Use UNCHECKED   │
    │ Exception       │   │ Exception       │
    │                 │   │                 │
    │ Force caller to │   │ Document it,    │
    │ handle or       │   │ but optional    │
    │ declare         │   │ to handle       │
    └─────────────────┘   └─────────────────┘

Real-World Example Mapping:
─────────────────────────────────────────────

Banking Application Scenarios:

┌─────────────────────────────────────────────────────────────────┐
│ Scenario                    │ Exception Type  │ Reasoning       │
├─────────────────────────────┼─────────────────┼─────────────────┤
│ File not found for account │ Checked         │ External factor,│
│ data loading                │ (IOException)   │ recoverable     │
├─────────────────────────────┼─────────────────┼─────────────────┤
│ Database connection failed  │ Checked         │ External system,│
│                             │ (SQLException)  │ can retry       │
├─────────────────────────────┼─────────────────┼─────────────────┤
│ Negative withdrawal amount  │ Unchecked       │ Programming     │
│                             │ (IllegalArg)    │ error, validate │
├─────────────────────────────┼─────────────────┼─────────────────┤
│ Null account object access │ Unchecked       │ Programming     │
│                             │ (NullPointer)   │ error, check    │
├─────────────────────────────┼─────────────────┼─────────────────┤
│ JVM runs out of memory      │ Error           │ System issue,   │
│                             │ (OutOfMemory)   │ don't catch     │
└─────────────────────────────┴─────────────────┴─────────────────┘

Exception Handling Strategy Matrix:
─────────────────────────────────────────────

                  │ Checked    │ Unchecked  │ Error
──────────────────┼────────────┼────────────┼──────────
Handle at Source  │ Required   │ Optional   │ No
Declare in Method │ Required   │ Optional   │ No
Compile Checking  │ Yes        │ No         │ No
Recovery Possible │ Usually    │ Sometimes  │ Rarely
Prevention Method │ Validation │ Coding     │ System
Example Response  │ Retry/Alt  │ Fix Code   │ Restart

Why does Exception occur in program?
─────────────────────────────────────────────

Exceptions occur in Java programs due to various factors that disrupt the normal flow of execution. Understanding these causes helps developers write more robust and error-resistant code.

Major Categories of Exception Causes:
─────────────────────────────────────────────

1. Programming Errors (Most Common)
═══════════════════════════════════════════

Logic Errors:
• Incorrect algorithm implementation
• Wrong conditional statements
• Faulty loop conditions
• Improper variable calculations

Examples:
- ArrayIndexOutOfBoundsException: Accessing array[arr.length] instead of array[arr.length-1]
- NullPointerException: Not checking if object is null before use
- ArithmeticException: Division by zero in calculations

Code Example:
public class ProgrammingErrorExample {
    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 5};
        
        // Logic Error - accessing index equal to length
        System.out.println(numbers[5]); // ArrayIndexOutOfBoundsException
        
        // Logic Error - not checking for null
        String text = null;
        System.out.println(text.length()); // NullPointerException
        
        // Logic Error - division by zero
        int result = 10 / 0; // ArithmeticException
    }
}

2. External System Failures
═══════════════════════════════════════════

File System Issues:
• File not found or deleted
• Insufficient permissions
• Disk space exhaustion
• Corrupted files

Network Problems:
• Server unavailable
• Network timeout
• Connection refused
• DNS resolution failure

Database Issues:
• Database server down
• Invalid SQL queries
• Connection timeout
• Data integrity violations

Examples:
- FileNotFoundException: Trying to read a non-existent file
- IOException: Network connection interrupted during data transfer
- SQLException: Database table doesn't exist

Code Example:
public class ExternalSystemExample {
    public static void main(String[] args) {
        try {
            // File system failure
            FileReader file = new FileReader("nonexistent.txt"); // FileNotFoundException
            
            // Network failure
            URL url = new URL("http://unreachable-server.com");
            URLConnection conn = url.openConnection(); // IOException
            
            // Database failure
            Connection dbConn = DriverManager.getConnection(
                "jdbc:mysql://localhost:3306/nonexistent_db"); // SQLException
                
        } catch (Exception e) {
            System.out.println("External system error: " + e.getMessage());
        }
    }
}

3. Invalid User Input
═══════════════════════════════════════════

Data Format Issues:
• Invalid number formats
• Wrong data types
• Out-of-range values
• Special characters in numeric fields

Input Validation Failures:
• Missing required fields
• Invalid email formats
• Negative values where positive expected
• String input for numeric operations

Examples:
- NumberFormatException: Converting "abc" to integer
- IllegalArgumentException: Negative age value
- ParseException: Invalid date format

Code Example:
public class UserInputExample {
    public static void validateAndProcess(String input) {
        try {
            // User enters "abc" instead of number
            int number = Integer.parseInt(input); // NumberFormatException
            
            if (number < 0) {
                throw new IllegalArgumentException("Number cannot be negative");
            }
            
            // Process valid input
            System.out.println("Processing: " + number);
            
        } catch (NumberFormatException e) {
            System.out.println("Invalid number format: " + input);
        } catch (IllegalArgumentException e) {
            System.out.println("Invalid input: " + e.getMessage());
        }
    }
}

4. Resource Constraints
═══════════════════════════════════════════

Memory Issues:
• Heap memory exhaustion
• Stack overflow from deep recursion
• Memory leaks from unreleased objects

System Limitations:
• Too many open files
• Thread pool exhaustion
• CPU overload

Examples:
- OutOfMemoryError: Creating too many objects
- StackOverflowError: Infinite recursion

Code Example:
public class ResourceConstraintExample {
    public static void main(String[] args) {
        // Memory exhaustion example
        List<String> memoryEater = new ArrayList<>();
        try {
            while (true) {
                memoryEater.add(new String(new char[1000000])); // Eventually OutOfMemoryError
            }
        } catch (OutOfMemoryError e) {
            System.out.println("Memory exhausted!");
        }
    }
    
    // Stack overflow example
    public static void infiniteRecursion() {
        infiniteRecursion(); // StackOverflowError
    }
}

5. Environmental Factors
═══════════════════════════════════════════

Operating System Issues:
• File permission changes
• System resource unavailability
• Hardware failures

JVM Problems:
• Class loading failures
• Security manager restrictions
• Version compatibility issues

Examples:
- SecurityException: Insufficient permissions
- ClassNotFoundException: Missing JAR files
- UnsupportedOperationException: Platform limitations

6. Concurrent Programming Issues
═══════════════════════════════════════════

Threading Problems:
• Race conditions
• Deadlocks
• Resource contention
• Synchronization failures

Examples:
- ConcurrentModificationException: Modifying collection during iteration
- IllegalMonitorStateException: Improper synchronization

Code Example:
public class ConcurrencyExample {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("item1");
        list.add("item2");
        
        // Concurrent modification during iteration
        for (String item : list) {
            if (item.equals("item1")) {
                list.remove(item); // ConcurrentModificationException
            }
        }
    }
}

Root Cause Analysis Framework:
─────────────────────────────────────────────

When Exception Occurs, Ask:
═══════════════════════════
1. Is it a programming logic error?
   → Review algorithm and implementation
   
2. Is it external system related?
   → Check system status and connectivity
   
3. Is it user input validation failure?
   → Implement proper input validation
   
4. Is it resource constraint?
   → Monitor system resources and optimize
   
5. Is it environmental/configuration?
   → Verify setup and permissions

Exception Prevention Strategies by Cause:
─────────────────────────────────────────────

For Programming Errors:
══════════════════════
• Code reviews and pair programming
• Unit testing and integration testing
• Static code analysis tools
• Defensive programming practices
• Input validation at method entry points

For External System Failures:
═══════════════════════════
• Implement retry mechanisms
• Use circuit breaker patterns
• Add timeouts and fallback options
• Monitor external dependencies
• Cache frequently accessed data

For Invalid User Input:
════════════════════
• Client-side validation (first line of defense)
• Server-side validation (never trust client)
• Use parsing with error handling
• Provide clear error messages
• Implement input sanitization

For Resource Constraints:
═══════════════════════
• Memory profiling and optimization
• Connection pooling
• Resource cleanup (try-with-resources)
• Monitoring and alerting
• Graceful degradation strategies

For Environmental Issues:
═══════════════════════
• Configuration management
• Environment-specific testing
• Deployment automation
• Health checks and monitoring
• Rollback procedures

Common Exception Scenarios and Their Causes:
─────────────────────────────────────────────

┌─────────────────────────┬─────────────────────────┬─────────────────────────┐
│ Exception Type          │ Primary Cause           │ Prevention Strategy     │
├─────────────────────────┼─────────────────────────┼─────────────────────────┤
│ NullPointerException    │ Uninitialized objects   │ Null checks, Optional   │
├─────────────────────────┼─────────────────────────┼─────────────────────────┤
│ ArrayIndexOutOfBounds   │ Logic errors in loops   │ Bounds checking         │
├─────────────────────────┼─────────────────────────┼─────────────────────────┤
│ NumberFormatException   │ Invalid user input      │ Input validation        │
├─────────────────────────┼─────────────────────────┼─────────────────────────┤
│ FileNotFoundException   │ Missing files           │ File existence checks   │
├─────────────────────────┼─────────────────────────┼─────────────────────────┤
│ SQLException            │ Database connectivity   │ Connection validation   │
├─────────────────────────┼─────────────────────────┼─────────────────────────┤
│ OutOfMemoryError        │ Resource exhaustion     │ Memory management       │
├─────────────────────────┼─────────────────────────┼─────────────────────────┤
│ ClassCastException      │ Type casting errors     │ instanceof checks       │
├─────────────────────────┼─────────────────────────┼─────────────────────────┤
│ ConcurrentModification  │ Threading issues        │ Proper synchronization  │
└─────────────────────────┴─────────────────────────┴─────────────────────────┘

Exception Lifecycle - From Cause to Resolution:
─────────────────────────────────────────────

1. Trigger Event
   ↓
2. JVM Detects Abnormal Condition
   ↓
3. Exception Object Created
   ↓
4. Call Stack Unwinding Begins
   ↓
5. Search for Exception Handler
   ↓
6. Handler Found? → Yes: Execute catch block
   ↓              → No: Propagate up call stack
7. Finally block execution (if present)
   ↓
8. Program continues or terminates

Real-World Exception Scenarios:
─────────────────────────────────────────────

E-commerce Application Examples:
═══════════════════════════════

Scenario 1: User Registration
• Cause: User enters invalid email format
• Exception: IllegalArgumentException or custom ValidationException
• Prevention: Email format validation using regex

Scenario 2: Payment Processing
• Cause: Payment gateway timeout
• Exception: IOException or SocketTimeoutException
• Prevention: Retry logic with exponential backoff

Scenario 3: Inventory Check
• Cause: Database connection failure
• Exception: SQLException
• Prevention: Connection pooling and health checks

Scenario 4: File Upload
• Cause: File size exceeds limit
• Exception: IOException or custom FileSizeException
• Prevention: File size validation before processing

Banking Application Examples:
═══════════════════════════

Scenario 1: Account Balance Check
• Cause: Account number format invalid
• Exception: NumberFormatException
• Prevention: Account number format validation

Scenario 2: Fund Transfer
• Cause: Insufficient balance
• Exception: Custom InsufficientFundsException
• Prevention: Balance validation before transfer

Scenario 3: Transaction History
• Cause: Date range parsing error
• Exception: ParseException
• Prevention: Date format validation and default ranges

Exception Monitoring and Debugging:
─────────────────────────────────────────────

Effective Exception Tracking:
═══════════════════════════
• Log exception details with context
• Include stack traces for debugging
• Track exception patterns and frequencies
• Monitor system metrics during exceptions
• Set up alerts for critical exceptions

Debugging Techniques:
═══════════════════
• Use IDE debugger with breakpoints
• Add logging at critical points
• Review exception stack traces carefully
• Reproduce exceptions in test environment
• Use profiling tools for performance-related exceptions

Best Practices Summary:
─────────────────────────────────────────────

1. Prevention is Better Than Cure:
   • Validate inputs early and often
   • Use defensive programming techniques
   • Implement proper error checking

2. Handle Exceptions Gracefully:
   • Provide meaningful error messages
   • Implement appropriate recovery strategies
   • Don't hide exceptions from users

3. Monitor and Learn:
   • Track exception patterns
   • Continuously improve based on production issues
   • Use exceptions as feedback for code improvement

4. Design for Failure:
   • Assume external systems will fail
   • Implement fallback mechanisms
   • Design with error scenarios in mind

Key Takeaway: Exceptions are not always bad - they're Java's way of communicating problems that need attention. Understanding their causes helps in building more robust, maintainable, and user-friendly applications.

Errors in Java:
─────────────────────────────────────────────

Errors in Java represent serious problems that indicate system-level issues or abnormal conditions that applications typically cannot and should not attempt to handle. Unlike exceptions, errors are usually unrecoverable and suggest fundamental problems with the runtime environment.

What are Errors in Java?
─────────────────────────────────────────────

Definition:
• Errors are serious system-level problems that occur during program execution
• They extend the java.lang.Error class, which is a subclass of Throwable
• Represent abnormal conditions that applications should not try to catch
• Usually indicate issues beyond the control of the application
• Often result in program termination

Key Characteristics of Errors:
═══════════════════════════════
• Unchecked: No compile-time checking required
• Unrecoverable: Usually indicate fatal system problems
• System-level: Related to JVM, hardware, or operating system
• Non-catchable in practice: While technically possible to catch, it's not recommended
• Terminate program: Often lead to application shutdown

Error Hierarchy in Java:
─────────────────────────────────────────────

java.lang.Object
    └── java.lang.Throwable
         └── java.lang.Error
              ├── VirtualMachineError
              │    ├── OutOfMemoryError
              │    ├── StackOverflowError
              │    └── InternalError
              ├── LinkageError
              │    ├── NoClassDefFoundError
              │    ├── ClassFormatError
              │    └── UnsatisfiedLinkError
              ├── ThreadDeath
              ├── AssertionError
              └── IOError

Types of Errors in Java:
─────────────────────────────────────────────

1. VirtualMachineError
═══════════════════════════════════════════

OutOfMemoryError:
──────────────────
• Occurs when JVM runs out of memory
• Most common type of error encountered
• Can happen in different memory areas

Subtypes:
- Java heap space: Too many objects created
- GC overhead limit exceeded: Garbage collection consuming too much time
- PermGen space: Too many classes loaded (Java 7 and earlier)
- Metaspace: Class metadata space exhausted (Java 8+)
- Direct buffer memory: NIO direct buffers exhausted

Code Example - OutOfMemoryError:
public class OutOfMemoryExample {
    public static void main(String[] args) {
        // This will eventually cause OutOfMemoryError
        List<String> memoryEater = new ArrayList<>();
        try {
            while (true) {
                // Creating large strings continuously
                memoryEater.add(new String(new char[1000000]));
            }
        } catch (OutOfMemoryError e) {
            System.out.println("OutOfMemoryError caught: " + e.getMessage());
            System.out.println("List size when error occurred: " + memoryEater.size());
        }
    }
}

StackOverflowError:
───────────────────
• Occurs when the call stack exceeds its maximum size
• Usually caused by infinite or very deep recursion
• Each method call adds a frame to the stack

Code Example - StackOverflowError:
public class StackOverflowExample {
    public static void main(String[] args) {
        try {
            recursiveMethod(1);
        } catch (StackOverflowError e) {
            System.out.println("StackOverflowError caught");
            System.out.println("Stack trace depth exceeded");
        }
    }
    
    public static void recursiveMethod(int depth) {
        System.out.println("Recursion depth: " + depth);
        recursiveMethod(depth + 1); // Infinite recursion
    }
}

InternalError:
──────────────
• Indicates an error in the JVM itself
• Usually suggests a bug in the Java Virtual Machine
• Very rare and typically unrecoverable

2. LinkageError
═══════════════════════════════════════════

NoClassDefFoundError:
────────────────────
• Class was available at compile time but not at runtime
• Different from ClassNotFoundException (which is an exception)
• Often caused by missing JAR files or classpath issues

Code Example:
public class LinkageErrorExample {
    public static void main(String[] args) {
        try {
            // Trying to use a class that was available during compilation
            // but is missing at runtime
            SomeClass obj = new SomeClass(); // May throw NoClassDefFoundError
        } catch (NoClassDefFoundError e) {
            System.out.println("NoClassDefFoundError: " + e.getMessage());
        }
    }
}

ClassFormatError:
─────────────────
• Occurs when JVM attempts to read a class file with invalid format
• Usually indicates corrupted .class files
• Can happen due to version incompatibility

UnsatisfiedLinkError:
────────────────────
• Thrown when JVM cannot find a native method implementation
• Occurs with JNI (Java Native Interface) operations
• Usually indicates missing native libraries

3. ThreadDeath
═══════════════════════════════════════════

• Thrown when Thread.stop() method is called (deprecated)
• Not typically used in modern Java applications
• Extends Error but is somewhat recoverable

4. AssertionError
═══════════════════════════════════════════

• Thrown when an assertion fails
• Indicates a programming error or invalid assumption
• Used with the assert keyword

Code Example - AssertionError:
public class AssertionExample {
    public static void main(String[] args) {
        int age = -5;
        
        try {
            // Enable assertions with -ea JVM flag
            assert age >= 0 : "Age cannot be negative";
            System.out.println("Age is valid: " + age);
        } catch (AssertionError e) {
            System.out.println("AssertionError: " + e.getMessage());
        }
    }
}

5. IOError
═══════════════════════════════════════════

• Thrown when a serious I/O error occurs
• Usually indicates hardware or system-level I/O problems
• Different from IOException (which is an exception)

Common Error Scenarios and Causes:
─────────────────────────────────────────────

┌─────────────────────────┬─────────────────────────┬─────────────────────────┐
│ Error Type              │ Common Causes           │ Typical Scenarios       │
├─────────────────────────┼─────────────────────────┼─────────────────────────┤
│ OutOfMemoryError        │ Memory leaks, large     │ Image processing,       │
│                         │ data sets, infinite     │ data analytics,         │
│                         │ loops creating objects  │ caching systems         │
├─────────────────────────┼─────────────────────────┼─────────────────────────┤
│ StackOverflowError      │ Infinite recursion,     │ Recursive algorithms,   │
│                         │ very deep call stacks   │ parsing operations      │
├─────────────────────────┼─────────────────────────┼─────────────────────────┤
│ NoClassDefFoundError    │ Missing JAR files,      │ Deployment issues,      │
│                         │ classpath problems      │ dependency conflicts    │
├─────────────────────────┼─────────────────────────┼─────────────────────────┤
│ ClassFormatError        │ Corrupted class files,  │ Build tool issues,      │
│                         │ version mismatches      │ manual file corruption  │
├─────────────────────────┼─────────────────────────┼─────────────────────────┤
│ UnsatisfiedLinkError    │ Missing native libs,    │ JNI applications,       │
│                         │ incorrect library path  │ system integrations     │
└─────────────────────────┴─────────────────────────┴─────────────────────────┘

Memory Management and OutOfMemoryError:
─────────────────────────────────────────────

Types of OutOfMemoryError:
═══════════════════════════

1. Java Heap Space:
   • Most common type
   • Objects cannot be allocated in heap
   • Solution: Increase heap size (-Xmx) or optimize memory usage

2. GC Overhead Limit Exceeded:
   • Garbage collection taking too much time
   • Less than 2% of heap recovered after GC
   • Solution: Increase heap size or reduce object creation

3. Metaspace (Java 8+):
   • Class metadata storage exhausted
   • Too many classes loaded
   • Solution: Increase metaspace size (-XX:MetaspaceSize)

4. Direct Buffer Memory:
   • NIO direct memory exhausted
   • ByteBuffers allocated outside heap
   • Solution: Increase direct memory (-XX:MaxDirectMemorySize)

JVM Memory Areas and Related Errors:
───────────────────────────────────

┌─────────────────┬─────────────────────┬─────────────────────┐
│ Memory Area     │ Error Type          │ Typical Cause       │
├─────────────────┼─────────────────────┼─────────────────────┤
│ Heap           │ OutOfMemoryError    │ Too many objects    │
├─────────────────┼─────────────────────┼─────────────────────┤
│ Stack          │ StackOverflowError  │ Deep recursion      │
├─────────────────┼─────────────────────┼─────────────────────┤
│ Metaspace      │ OutOfMemoryError    │ Too many classes    │
├─────────────────┼─────────────────────┼─────────────────────┤
│ Direct Memory  │ OutOfMemoryError    │ NIO buffer overuse  │
└─────────────────┴─────────────────────┴─────────────────────┘

Error Prevention Strategies:
─────────────────────────────────────────────

For OutOfMemoryError:
════════════════════
• Memory Profiling: Use tools like VisualVM, JProfiler
• Proper Object Lifecycle: Remove references when done
• Optimize Data Structures: Use appropriate collections
• Streaming: Process large data in chunks
• Connection Pooling: Reuse database/network connections
• Garbage Collection Tuning: Optimize GC parameters

For StackOverflowError:
══════════════════════
• Limit Recursion Depth: Add base cases
• Iterative Solutions: Convert recursion to loops
• Tail Recursion Optimization: Use tail-recursive patterns
• Stack Size Configuration: Increase stack size (-Xss)

For LinkageErrors:
═════════════════
• Dependency Management: Use Maven/Gradle properly
• Classpath Verification: Ensure all required JARs are present
• Version Compatibility: Check library versions
• Build Process Validation: Test deployment packages

Code Examples - Error Handling Patterns:
─────────────────────────────────────────────

Memory-Safe Programming:
public class MemorySafeExample {
    private static final int MAX_ITEMS = 100000;
    
    public void processLargeDataSet(List<String> data) {
        // Process in chunks to avoid OutOfMemoryError
        int chunkSize = 1000;
        
        for (int i = 0; i < data.size(); i += chunkSize) {
            int endIndex = Math.min(i + chunkSize, data.size());
            List<String> chunk = data.subList(i, endIndex);
            
            processChunk(chunk);
            
            // Suggest garbage collection after each chunk
            System.gc(); // Not guaranteed, but may help
        }
    }
    
    private void processChunk(List<String> chunk) {
        // Process smaller chunk of data
        chunk.forEach(this::processItem);
    }
    
    private void processItem(String item) {
        // Process individual item
    }
}

Stack-Safe Recursion:
public class StackSafeExample {
    private static final int MAX_DEPTH = 1000;
    
    // Safe recursive method with depth limit
    public int calculateFactorial(int n, int depth) {
        if (depth > MAX_DEPTH) {
            throw new IllegalArgumentException("Recursion depth exceeded");
        }
        
        if (n <= 1) {
            return 1;
        }
        
        return n * calculateFactorial(n - 1, depth + 1);
    }
    
    // Iterative alternative to avoid stack issues
    public int calculateFactorialIterative(int n) {
        int result = 1;
        for (int i = 2; i <= n; i++) {
            result *= i;
        }
        return result;
    }
}

Error Monitoring and Diagnostics:
─────────────────────────────────────────────

JVM Monitoring Parameters:
═══════════════════════════
• -XX:+HeapDumpOnOutOfMemoryError: Generate heap dump on OOM
• -XX:HeapDumpPath=/path/to/dumps/: Specify dump location
• -XX:+PrintGCDetails: Print garbage collection information
• -XX:+PrintGCTimeStamps: Include timestamps in GC logs
• -Xloggc:/path/to/gc.log: Redirect GC logs to file

Memory Analysis Tools:
════════════════════
• VisualVM: Built-in profiling tool
• Eclipse MAT: Memory Analyzer Tool
• JProfiler: Commercial profiling solution
• YourKit: Advanced profiling platform
• JConsole: Built-in monitoring tool

Error Logging Best Practices:
═══════════════════════════
public class ErrorLoggingExample {
    private static final Logger logger = LoggerFactory.getLogger(ErrorLoggingExample.class);
    
    public void riskyOperation() {
        try {
            // Some operation that might cause an error
            performComplexCalculation();
        } catch (OutOfMemoryError e) {
            // Log the error with context
            logger.error("OutOfMemoryError occurred during complex calculation", e);
            
            // Attempt graceful degradation
            performSimpleCalculation();
        } catch (StackOverflowError e) {
            logger.error("StackOverflowError in calculation", e);
            throw new RuntimeException("Calculation failed due to stack overflow", e);
        }
    }
    
    private void performComplexCalculation() {
        // Complex operation
    }
    
    private void performSimpleCalculation() {
        // Fallback simple operation
    }
}

Error vs Exception Comparison:
─────────────────────────────────────────────

┌─────────────────────┬─────────────────────┬─────────────────────┐
│ Aspect              │ Errors              │ Exceptions          │
├─────────────────────┼─────────────────────┼─────────────────────┤
│ Nature              │ System-level issues │ Application issues  │
├─────────────────────┼─────────────────────┼─────────────────────┤
│ Recoverability      │ Usually fatal       │ Often recoverable   │
├─────────────────────┼─────────────────────┼─────────────────────┤
│ Should Catch?       │ Generally no        │ Yes, when appropriate│
├─────────────────────┼─────────────────────┼─────────────────────┤
│ Handling Strategy   │ Log and terminate   │ Handle and continue │
├─────────────────────┼─────────────────────┼─────────────────────┤
│ Typical Cause       │ JVM/System problems │ Business logic      │
├─────────────────────┼─────────────────────┼─────────────────────┤
│ Prevention          │ System configuration│ Code quality        │
└─────────────────────┴─────────────────────┴─────────────────────┘

When to Handle Errors:
─────────────────────────────────────────────

Generally Don't Catch Errors:
════════════════════════════
• OutOfMemoryError: Usually indicates fundamental problem
• StackOverflowError: Typically unrecoverable
• VirtualMachineError: JVM-level issues

Rare Cases for Error Handling:
═════════════════════════════
• AssertionError: In testing frameworks
• Specific recovery scenarios: When you have a fallback strategy
• Logging purposes: To capture error details before termination

Example of Appropriate Error Handling:
public class ErrorHandlingExample {
    private static final Logger logger = LoggerFactory.getLogger(ErrorHandlingExample.class);
    
    public boolean processLargeFile(String filename) {
        try {
            // Attempt to process large file
            return performFileProcessing(filename);
        } catch (OutOfMemoryError e) {
            // Log the error
            logger.error("OutOfMemoryError processing file: {}", filename, e);
            
            // Attempt alternative processing method
            return processFileInChunks(filename);
        }
    }
    
    private boolean performFileProcessing(String filename) {
        // Normal processing that might use lots of memory
        return true;
    }
    
    private boolean processFileInChunks(String filename) {
        // Memory-efficient alternative processing
        return true;
    }
}

Best Practices for Error Management:
─────────────────────────────────────────────

1. Prevention Over Handling:
   • Monitor memory usage regularly
   • Use appropriate data structures
   • Implement proper resource management
   • Test with realistic data volumes

2. System Configuration:
   • Set appropriate JVM heap sizes
   • Configure stack sizes based on application needs
   • Monitor system resources
   • Use profiling tools during development

3. Graceful Degradation:
   • Design fallback mechanisms
   • Implement circuit breaker patterns
   • Provide meaningful error messages
   • Ensure proper cleanup

4. Monitoring and Alerting:
   • Set up error monitoring
   • Configure alerts for critical errors
   • Maintain error logs
   • Analyze error patterns

Real-World Error Scenarios:
─────────────────────────────────────────────

Web Application Memory Issues:
════════════════════════════
Scenario: E-commerce site during flash sale
Problem: OutOfMemoryError due to massive concurrent user sessions
Solution: Implement session clustering, optimize caching, scale horizontally

Data Processing Pipeline:
═══════════════════════
Scenario: Big data processing with recursive algorithms
Problem: StackOverflowError in data transformation
Solution: Convert to iterative approach, implement streaming processing

Microservices Deployment:
═══════════════════════
Scenario: Service failing with NoClassDefFoundError
Problem: Missing dependency JARs in deployment package
Solution: Implement proper dependency management, automated testing

Summary - Key Points About Java Errors:
─────────────────────────────────────────────

1. Errors indicate serious system-level problems
2. Usually unrecoverable and should not be caught
3. Prevention through proper configuration is key
4. Monitoring and diagnostics are essential
5. Design applications to fail gracefully
6. OutOfMemoryError and StackOverflowError are most common
7. Proper resource management prevents many errors
8. Use profiling tools during development and testing

Remember: Errors are different from exceptions - they represent fundamental problems that typically require system-level solutions rather than programmatic handling.

Keywords for Exception Handling in Java:
─────────────────────────────────────────────

Exception handling in Java uses specific keywords that provide the mechanism to handle runtime errors and maintain normal application flow. Here are the essential keywords:

Core Exception Handling Keywords:
═══════════════════════════════════════════

1. try
──────
• Purpose: Defines a block of code that might throw an exception
• Usage: Contains the risky code that could potentially fail
• Must be followed by either catch, finally, or both
• Can have multiple catch blocks

Syntax:
try {
    // Code that might throw an exception
    int result = 10 / 0;
}

2. catch
────────
• Purpose: Handles specific exceptions thrown by the try block
• Usage: Contains the exception handling logic
• Can have multiple catch blocks for different exception types
• Order matters: more specific exceptions should come first

Syntax:
catch (ExceptionType variableName) {
    // Exception handling code
}

Examples:
catch (ArithmeticException e) {
    System.out.println("Division by zero error");
}
catch (NullPointerException e) {
    System.out.println("Null pointer error");
}
catch (Exception e) {
    System.out.println("General exception: " + e.getMessage());
}

3. finally
──────────
• Purpose: Executes code regardless of whether an exception occurs
• Usage: Used for cleanup operations (closing files, database connections)
• Always executes except when System.exit() is called or JVM crashes
• Optional but highly recommended for resource management

Syntax:
finally {
    // Cleanup code that always executes
    if (file != null) {
        file.close();
    }
}

4. throw
────────
• Purpose: Explicitly throws an exception
• Usage: Used to throw custom exceptions or re-throw caught exceptions
• Can throw both checked and unchecked exceptions
• Immediately transfers control to the nearest exception handler

Syntax:
throw new ExceptionType("Error message");

Examples:
throw new IllegalArgumentException("Age cannot be negative");
throw new ArithmeticException("Division by zero");
throw new RuntimeException("Something went wrong");

5. throws
─────────
• Purpose: Declares that a method might throw certain exceptions
• Usage: Used in method signature to indicate potential exceptions
• Mandatory for checked exceptions
• Helps callers know what exceptions to handle

Syntax:
public void methodName() throws ExceptionType1, ExceptionType2 {
    // Method implementation
}

Examples:
public void readFile(String filename) throws IOException {
    FileReader file = new FileReader(filename);
}

public void databaseOperation() throws SQLException, ClassNotFoundException {
    // Database code
}

Advanced Exception Handling Keywords:
═══════════════════════════════════════════

6. assert
─────────
• Purpose: Tests assumptions during development
• Usage: Validates conditions that should never be false
• Throws AssertionError if condition is false
• Must be enabled with -ea JVM flag

Syntax:
assert condition : "Error message";

Examples:
assert age >= 0 : "Age cannot be negative";
assert balance >= 0 : "Balance cannot be negative";

Exception Handling Combinations:
═══════════════════════════════════════════

1. try-catch:
try {
    // Risky code
} catch (Exception e) {
    // Handle exception
}

2. try-finally:
try {
    // Risky code
} finally {
    // Cleanup code
}

3. try-catch-finally:
try {
    // Risky code
} catch (Exception e) {
    // Handle exception
} finally {
    // Cleanup code
}

4. Multiple catch blocks:
try {
    // Risky code
} catch (IOException e) {
    // Handle IO exception
} catch (SQLException e) {
    // Handle SQL exception
} catch (Exception e) {
    // Handle any other exception
}

5. Multi-catch (Java 7+):
try {
    // Risky code
} catch (IOException | SQLException e) {
    // Handle both IO and SQL exceptions
}

6. try-with-resources (Java 7+):
try (FileInputStream file = new FileInputStream("data.txt")) {
    // Use file
} catch (IOException e) {
    // Handle exception
}
// File automatically closed

Related Keywords and Concepts:
═══════════════════════════════════════════

7. extends (for custom exceptions)
──────────────────────────────────────
• Purpose: Create custom exception classes
• Usage: Inherit from existing exception classes

Examples:
class CustomException extends Exception {
    public CustomException(String message) {
        super(message);
    }
}

class ValidationException extends RuntimeException {
    public ValidationException(String message) {
        super(message);
    }
}

8. super (in exception constructors)
───────────────────────────────────────
• Purpose: Call parent exception constructor
• Usage: Pass message and cause to parent class

Example:
public class DatabaseException extends Exception {
    public DatabaseException(String message) {
        super(message);
    }
    
    public DatabaseException(String message, Throwable cause) {
        super(message, cause);
    }
}

9. instanceof (for exception type checking)
──────────────────────────────────────────
• Purpose: Check exception type at runtime
• Usage: Conditional exception handling

Example:
try {
    // Some operation
} catch (Exception e) {
    if (e instanceof IOException) {
        // Handle as IO exception
    } else if (e instanceof SQLException) {
        // Handle as SQL exception
    }
}

Exception Handling Method Keywords:
═══════════════════════════════════════════

10. getMessage()
───────────────
• Purpose: Get exception message
• Returns: String description of the exception

Example:
catch (Exception e) {
    System.out.println("Error: " + e.getMessage());
}

11. printStackTrace()
────────────────────
• Purpose: Print the stack trace to console
• Usage: Debugging and error analysis

Example:
catch (Exception e) {
    e.printStackTrace();
}

12. getCause()
─────────────
• Purpose: Get the underlying cause of exception
• Returns: Throwable that caused this exception

Example:
catch (Exception e) {
    Throwable cause = e.getCause();
    if (cause != null) {
        System.out.println("Caused by: " + cause.getMessage());
    }
}

Exception Handling Best Practices with Keywords:
═══════════════════════════════════════════════

1. Specific Exception Handling:
// Good - Specific exceptions
try {
    // Code
} catch (FileNotFoundException e) {
    // Handle file not found
} catch (IOException e) {
    // Handle other IO issues
}

// Avoid - Too general
try {
    // Code
} catch (Exception e) {
    // Handles everything
}

2. Proper Resource Management:
// Using try-with-resources
try (FileInputStream fis = new FileInputStream("file.txt");
     BufferedReader reader = new BufferedReader(new InputStreamReader(fis))) {
    
    return reader.readLine();
} catch (IOException e) {
    throw new ProcessingException("Failed to read file", e);
}

3. Custom Exception Creation:
public class OrderProcessingException extends Exception {
    public OrderProcessingException(String message) {
        super(message);
    }
    
    public OrderProcessingException(String message, Throwable cause) {
        super(message, cause);
    }
}

4. Method Exception Declaration:
public void processOrder(Order order) 
    throws OrderProcessingException, ValidationException {
    
    if (order == null) {
        throw new ValidationException("Order cannot be null");
    }
    
    try {
        // Process order
    } catch (Exception e) {
        throw new OrderProcessingException("Failed to process order", e);
    }
}

Java Exception Hierarchy Keywords:
═══════════════════════════════════════════

Key Classes in Exception Hierarchy:
• Throwable - Root of all exceptions and errors
• Exception - Base class for all exceptions
• RuntimeException - Base class for unchecked exceptions
• Error - Base class for all errors

Common Exception Types:
• Checked Exceptions: IOException, SQLException, ClassNotFoundException
• Unchecked Exceptions: RuntimeException, NullPointerException, ArithmeticException
• Errors: OutOfMemoryError, StackOverflowError, NoClassDefFoundError

Summary of Exception Handling Keywords:
═══════════════════════════════════════════

Core Keywords:
1. try - Define risky code block
2. catch - Handle specific exceptions
3. finally - Cleanup code that always runs
4. throw - Explicitly throw an exception
5. throws - Declare method exceptions

Additional Keywords:
6. assert - Test development assumptions
7. extends - Create custom exceptions
8. super - Call parent exception constructor
9. instanceof - Check exception type

Modern Features:
10. try-with-resources - Automatic resource management
11. Multi-catch - Handle multiple exception types
12. Suppressed exceptions - Track cleanup exceptions

Key Points to Remember:
═════════════════════
• Use specific exception types in catch blocks
• Always clean up resources in finally or try-with-resources
• Don't catch exceptions you can't handle meaningfully
• Create custom exceptions for domain-specific errors
• Document exceptions in method signatures with throws
• Use assertions for development-time checks
• Log exceptions with proper context and stack traces

These keywords form the foundation of robust error handling in Java applications, enabling developers to write resilient code that can gracefully handle unexpected situations.

Try with Multiple Catch Blocks in Java:
─────────────────────────────────────────────

Multiple catch blocks allow you to handle different types of exceptions that might be thrown from a single try block. This provides more granular and specific exception handling, enabling appropriate responses to different error conditions.

Basic Syntax of Multiple Catch Blocks:
═══════════════════════════════════════════

try {
    // Code that might throw multiple types of exceptions
} catch (SpecificException1 e) {
    // Handle specific exception type 1
} catch (SpecificException2 e) {
    // Handle specific exception type 2
} catch (GeneralException e) {
    // Handle more general exception type
} finally {
    // Optional cleanup code
}

Key Rules for Multiple Catch Blocks:
═══════════════════════════════════════════

1. **Order Matters**: More specific exceptions must come before more general ones
2. **Only One Catch Executes**: Once an exception is caught, no other catch blocks are executed
3. **Exception Hierarchy**: Child exception classes must be caught before parent classes
4. **Compilation Error**: If a more general exception is caught before a specific one, compilation fails

Example 1: Basic Multiple Catch Blocks
─────────────────────────────────────────────

public class MultiCatchExample {
    public static void main(String[] args) {
        try {
            // Multiple operations that can throw different exceptions
            int[] numbers = {1, 2, 3};
            int divisor = 0;
            String text = null;
            
            System.out.println(numbers[5]);        // ArrayIndexOutOfBoundsException
            int result = 10 / divisor;             // ArithmeticException
            int length = text.length();            // NullPointerException
            
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Array index error: " + e.getMessage());
            System.out.println("Please check array bounds");
        } catch (ArithmeticException e) {
            System.out.println("Arithmetic error: " + e.getMessage());
            System.out.println("Division by zero is not allowed");
        } catch (NullPointerException e) {
            System.out.println("Null pointer error: " + e.getMessage());
            System.out.println("Object reference is null");
        } catch (Exception e) {
            System.out.println("General exception: " + e.getMessage());
            System.out.println("An unexpected error occurred");
        } finally {
            System.out.println("Cleanup operations completed");
        }
    }
}

Example 2: File Operations with Multiple Catch Blocks
─────────────────────────────────────────────────────

import java.io.*;

public class FileOperationExample {
    public static void readAndProcessFile(String filename) {
        BufferedReader reader = null;
        
        try {
            reader = new BufferedReader(new FileReader(filename));
            String line;
            int lineNumber = 1;
            
            while ((line = reader.readLine()) != null) {
                // Process each line
                processLine(line, lineNumber);
                lineNumber++;
            }
            
        } catch (FileNotFoundException e) {
            System.err.println("File not found: " + filename);
            System.err.println("Please check if the file exists and path is correct");
            logError("FILE_NOT_FOUND", e);
        } catch (IOException e) {
            System.err.println("IO error while reading file: " + e.getMessage());
            System.err.println("Check file permissions and disk space");
            logError("IO_ERROR", e);
        } catch (SecurityException e) {
            System.err.println("Security error: " + e.getMessage());
            System.err.println("Insufficient permissions to access the file");
            logError("SECURITY_ERROR", e);
        } catch (Exception e) {
            System.err.println("Unexpected error: " + e.getMessage());
            logError("UNEXPECTED_ERROR", e);
        } finally {
            // Cleanup resources
            if (reader != null) {
                try {
                    reader.close();
                } catch (IOException e) {
                    System.err.println("Error closing file: " + e.getMessage());
                }
            }
        }
    }
    
    private static void processLine(String line, int lineNumber) {
        // Process individual line
        System.out.println("Line " + lineNumber + ": " + line);
    }
    
    private static void logError(String errorType, Exception e) {
        // Log error for debugging
        System.err.println("Error Type: " + errorType);
        System.err.println("Timestamp: " + System.currentTimeMillis());
        e.printStackTrace();
    }
}

Example 3: Database Operations with Multiple Catch Blocks
─────────────────────────────────────────────────────────

import java.sql.*;

public class DatabaseExample {
    public static void performDatabaseOperation(String query) {
        Connection connection = null;
        PreparedStatement statement = null;
        ResultSet resultSet = null;
        
        try {
            // Database operations
            connection = DriverManager.getConnection(
                "jdbc:mysql://localhost:3306/mydb", "user", "password");
            statement = connection.prepareStatement(query);
            resultSet = statement.executeQuery();
            
            // Process results
            while (resultSet.next()) {
                System.out.println("Data: " + resultSet.getString(1));
            }
            
        } catch (SQLException e) {
            handleSQLException(e);
        } catch (ClassNotFoundException e) {
            System.err.println("Database driver not found: " + e.getMessage());
            System.err.println("Please ensure JDBC driver is in classpath");
        } catch (Exception e) {
            System.err.println("Unexpected database error: " + e.getMessage());
            e.printStackTrace();
        } finally {
            // Close resources in reverse order
            closeResource(resultSet, "ResultSet");
            closeResource(statement, "PreparedStatement");
            closeResource(connection, "Connection");
        }
    }
    
    private static void handleSQLException(SQLException e) {
        System.err.println("SQL Error Code: " + e.getErrorCode());
        System.err.println("SQL State: " + e.getSQLState());
        System.err.println("SQL Message: " + e.getMessage());
        
        // Handle specific SQL error codes
        switch (e.getErrorCode()) {
            case 1062:
                System.err.println("Duplicate entry error");
                break;
            case 1045:
                System.err.println("Access denied - check credentials");
                break;
            case 1049:
                System.err.println("Unknown database");
                break;
            default:
                System.err.println("General SQL error occurred");
        }
    }
    
    private static void closeResource(AutoCloseable resource, String resourceName) {
        if (resource != null) {
            try {
                resource.close();
            } catch (Exception e) {
                System.err.println("Error closing " + resourceName + ": " + e.getMessage());
            }
        }
    }
}

Example 4: Number Parsing with Multiple Catch Blocks
─────────────────────────────────────────────────────

public class NumberParsingExample {
    public static double parseAndCalculate(String[] numbers) {
        double result = 0.0;
        
        try {
            for (int i = 0; i < numbers.length; i++) {
                double num = Double.parseDouble(numbers[i]);
                result += num;
                
                // Simulate array access
                if (i > 0) {
                    result = result / Double.parseDouble(numbers[i - 1]);
                }
            }
            
        } catch (NumberFormatException e) {
            System.err.println("Invalid number format: " + e.getMessage());
            System.err.println("Please provide valid numeric values");
            return -1; // Error indicator
        } catch (ArithmeticException e) {
            System.err.println("Arithmetic error: " + e.getMessage());
            System.err.println("Division by zero or invalid operation");
            return -1;
        } catch (ArrayIndexOutOfBoundsException e) {
            System.err.println("Array access error: " + e.getMessage());
            System.err.println("Array index out of bounds");
            return -1;
        } catch (NullPointerException e) {
            System.err.println("Null pointer error: " + e.getMessage());
            System.err.println("Input array or element is null");
            return -1;
        } catch (Exception e) {
            System.err.println("Unexpected error during calculation: " + e.getMessage());
            e.printStackTrace();
            return -1;
        } finally {
            System.out.println("Calculation attempt completed");
        }
        
        return result;
    }
    
    public static void main(String[] args) {
        String[] validNumbers = {"10.5", "20.3", "30.7"};
        String[] invalidNumbers = {"10.5", "abc", "30.7"};
        String[] nullArray = null;
        
        System.out.println("Valid numbers result: " + parseAndCalculate(validNumbers));
        System.out.println("Invalid numbers result: " + parseAndCalculate(invalidNumbers));
        System.out.println("Null array result: " + parseAndCalculate(nullArray));
    }
}

Multi-Catch Block (Java 7+):
═══════════════════════════════════════════

Java 7 introduced the ability to catch multiple exception types in a single catch block using the pipe (|) operator.

Syntax:
try {
    // Risky code
} catch (ExceptionType1 | ExceptionType2 | ExceptionType3 e) {
    // Handle multiple exception types with same logic
}

Example: Multi-Catch Usage
─────────────────────────────────────────────

public class MultiCatchSyntaxExample {
    public static void processData(String data) {
        try {
            // Operations that might throw different exceptions
            int number = Integer.parseInt(data);
            int result = 100 / number;
            System.out.println("Result: " + result);
            
        } catch (NumberFormatException | ArithmeticException e) {
            // Handle both exceptions with same logic
            System.err.println("Input or calculation error: " + e.getMessage());
            System.err.println("Exception type: " + e.getClass().getSimpleName());
        } catch (Exception e) {
            System.err.println("Other error: " + e.getMessage());
        }
    }
    
    public static void fileAndNetworkOperations() {
        try {
            // File and network operations
            performFileOperation();
            performNetworkOperation();
            
        } catch (IOException | SecurityException | IllegalArgumentException e) {
            // Handle related exceptions together
            System.err.println("Operation failed: " + e.getMessage());
            logError(e);
        } catch (Exception e) {
            System.err.println("Unexpected error: " + e.getMessage());
        }
    }
    
    private static void performFileOperation() throws IOException {
        // File operation simulation
    }
    
    private static void performNetworkOperation() throws SecurityException {
        // Network operation simulation
    }
    
    private static void logError(Exception e) {
        // Error logging logic
        System.err.println("Logged: " + e.getClass().getSimpleName());
    }
}

Best Practices for Multiple Catch Blocks:
─────────────────────────────────────────────

1. **Specific to General Order**:
✅ Correct:
try {
    // code
} catch (FileNotFoundException e) {
    // Most specific
} catch (IOException e) {
    // More general
} catch (Exception e) {
    // Most general
}

❌ Incorrect:
try {
    // code
} catch (Exception e) {        // Too general first
    // This will catch everything
} catch (IOException e) {       // Unreachable code
    // This will never execute
}

2. **Meaningful Error Messages**:
catch (SQLException e) {
    System.err.println("Database error occurred:");
    System.err.println("Error Code: " + e.getErrorCode());
    System.err.println("Message: " + e.getMessage());
    System.err.println("Suggested Action: Check database connection and query syntax");
}

3. **Appropriate Recovery Actions**:
catch (FileNotFoundException e) {
    System.err.println("File not found, creating default file...");
    createDefaultFile();
} catch (IOException e) {
    System.err.println("IO error, retrying operation...");
    retryOperation();
}

4. **Resource Cleanup**:
try {
    // Use resources
} catch (SpecificException e) {
    // Handle specific exception
} finally {
    // Always cleanup resources
    closeResources();
}

Exception Handling Flow Chart for Multiple Catch:
─────────────────────────────────────────────────

                    Exception Thrown in Try Block
                              │
                              ▼
                    ┌─────────────────────┐
                    │ Check First Catch   │
                    │ Block Match?        │
                    └─────────┬───────────┘
                             │
                    ┌────────┴────────┐
                 Yes│                 │No
                    ▼                 ▼
            ┌─────────────────┐  ┌─────────────────┐
            │ Execute First   │  │ Check Next      │
            │ Catch Block     │  │ Catch Block     │
            └─────────────────┘  └─────────┬───────┘
                    │                     │
                    ▼                     ▼
            ┌─────────────────┐  ┌─────────────────┐
            │ Execute Finally │  │ Continue        │
            │ Block (if any)  │  │ Checking...     │
            └─────────────────┘  └─────────────────┘
                    │                     │
                    ▼                     ▼
            ┌─────────────────┐  ┌─────────────────┐
            │ Continue        │  │ If No Match:    │
            │ Program         │  │ Propagate       │
            │ Execution       │  │ Exception       │
            └─────────────────┘  └─────────────────┘

Common Exception Hierarchy for Multiple Catch:
─────────────────────────────────────────────

FileNotFoundException extends IOException extends Exception
NumberFormatException extends IllegalArgumentException extends RuntimeException extends Exception
ArithmeticException extends RuntimeException extends Exception
NullPointerException extends RuntimeException extends Exception

Catch Order Example:
try {
    // code
} catch (FileNotFoundException e) {      // Most specific
} catch (IOException e) {                // More general
} catch (NumberFormatException e) {      // Specific runtime exception
} catch (RuntimeException e) {           // General runtime exception
} catch (Exception e) {                  // Most general
}

Real-World Example: Web Application Error Handling
─────────────────────────────────────────────────

public class WebApplicationExample {
    public static void processUserRequest(String userId, String action) {
        try {
            // Validate user
            User user = validateUser(userId);
            
            // Perform action
            performAction(user, action);
            
            // Log success
            logSuccess(userId, action);
            
        } catch (UserNotFoundException e) {
            System.err.println("User not found: " + userId);
            sendErrorResponse("USER_NOT_FOUND", e.getMessage());
        } catch (InvalidActionException e) {
            System.err.println("Invalid action: " + action);
            sendErrorResponse("INVALID_ACTION", e.getMessage());
        } catch (AuthenticationException e) {
            System.err.println("Authentication failed for user: " + userId);
            sendErrorResponse("AUTH_FAILED", "Please login again");
        } catch (AuthorizationException e) {
            System.err.println("User not authorized: " + userId);
            sendErrorResponse("NOT_AUTHORIZED", "Insufficient permissions");
        } catch (DatabaseException e) {
            System.err.println("Database error: " + e.getMessage());
            sendErrorResponse("DATABASE_ERROR", "Please try again later");
        } catch (NetworkException e) {
            System.err.println("Network error: " + e.getMessage());
            sendErrorResponse("NETWORK_ERROR", "Service temporarily unavailable");
        } catch (Exception e) {
            System.err.println("Unexpected error: " + e.getMessage());
            e.printStackTrace();
            sendErrorResponse("INTERNAL_ERROR", "An unexpected error occurred");
        } finally {
            // Cleanup resources and close connections
            cleanupResources();
        }
    }
    
    // Helper methods (placeholder implementations)
    private static User validateUser(String userId) throws UserNotFoundException {
        // User validation logic
        return new User(userId);
    }
    
    private static void performAction(User user, String action) 
            throws InvalidActionException, AuthenticationException, 
                   AuthorizationException, DatabaseException, NetworkException {
        // Action performance logic
    }
    
    private static void logSuccess(String userId, String action) {
        System.out.println("Success: User " + userId + " performed " + action);
    }
    
    private static void sendErrorResponse(String errorCode, String message) {
        System.out.println("Error Response: " + errorCode + " - " + message);
    }
    
    private static void cleanupResources() {
        System.out.println("Resources cleaned up");
    }
    
    // Custom exception classes
    static class User {
        private String id;
        public User(String id) { this.id = id; }
    }
    
    static class UserNotFoundException extends Exception {
        public UserNotFoundException(String message) { super(message); }
    }
    
    static class InvalidActionException extends Exception {
        public InvalidActionException(String message) { super(message); }
    }
    
    static class AuthenticationException extends Exception {
        public AuthenticationException(String message) { super(message); }
    }
    
    static class AuthorizationException extends Exception {
        public AuthorizationException(String message) { super(message); }
    }
    
    static class DatabaseException extends Exception {
        public DatabaseException(String message) { super(message); }
    }
    
    static class NetworkException extends Exception {
        public NetworkException(String message) { super(message); }
    }
}

Summary - Multiple Catch Blocks:
─────────────────────────────────────────────

Key Benefits:
═══════════════════════════════════════════
• **Granular Error Handling**: Different responses for different error types
• **Better User Experience**: Specific error messages for different scenarios
• **Improved Debugging**: Easier to identify and fix specific issues
• **Flexible Recovery**: Different recovery strategies for different exceptions
• **Code Organization**: Clean separation of error handling logic

Important Rules:
═══════════════════════════════════════════
• **Order Matters**: More specific exceptions first, general exceptions last
• **One Catch Executes**: Only the first matching catch block runs
• **Compilation Check**: Compiler ensures unreachable catch blocks don't exist
• **Exception Hierarchy**: Understand inheritance relationships between exceptions

Best Practices:
═══════════════════════════════════════════
• Use specific exception types rather than generic Exception
• Provide meaningful error messages and recovery suggestions
• Log errors appropriately for debugging and monitoring
• Clean up resources in finally blocks or try-with-resources
• Don't catch exceptions you can't handle meaningfully
• Consider using multi-catch for exceptions with similar handling logic

Multiple catch blocks are essential for robust Java applications, enabling precise error handling and graceful recovery from various failure scenarios.

The throw Keyword in Java:
─────────────────────────────────────────────

The `throw` keyword in Java is used to explicitly throw an exception from a method or block of code. It allows developers to manually trigger exceptions when specific error conditions are detected, providing fine-grained control over error handling and program flow.

What is the throw Keyword?
═══════════════════════════════════════════

**Definition:**
- The `throw` keyword is used to explicitly throw an exception
- It can throw both checked and unchecked exceptions
- Immediately transfers control to the nearest exception handler
- Used for manual exception generation based on specific conditions

**Basic Syntax:**
```java
throw new ExceptionType("Error message");
```

**Key Characteristics:**
- **Manual Control**: Allows developers to throw exceptions based on business logic
- **Immediate Transfer**: Control immediately transfers to exception handling mechanism
- **Any Exception Type**: Can throw any type of exception (checked or unchecked)
- **Custom Messages**: Provides meaningful error messages for debugging

Basic Examples of throw Keyword:
═══════════════════════════════════════════

Example 1: Basic Exception Throwing
─────────────────────────────────────────────

public class BasicThrowExample {
    
    public static void validateAge(int age) {
        if (age < 0) {
            throw new IllegalArgumentException("Age cannot be negative: " + age);
        }
        if (age > 150) {
            throw new IllegalArgumentException("Age cannot exceed 150: " + age);
        }
        System.out.println("Valid age: " + age);
    }
    
    public static void divide(int dividend, int divisor) {
        if (divisor == 0) {
            throw new ArithmeticException("Division by zero is not allowed");
        }
        int result = dividend / divisor;
        System.out.println("Result: " + result);
    }
    
    public static void main(String[] args) {
        try {
            validateAge(25);    // Valid
            validateAge(-5);    // Throws IllegalArgumentException
        } catch (IllegalArgumentException e) {
            System.err.println("Validation error: " + e.getMessage());
        }
        
        try {
            divide(10, 2);  // Valid
            divide(10, 0);  // Throws ArithmeticException
        } catch (ArithmeticException e) {
            System.err.println("Math error: " + e.getMessage());
        }
    }
}
```

Example 2: Throwing Checked Exceptions
─────────────────────────────────────────────

import java.io.IOException;
import java.sql.SQLException;

public class CheckedExceptionThrowExample {
    
    // Method that throws checked exception
    public static void processFile(String filename) throws IOException {
        if (filename == null || filename.trim().isEmpty()) {
            throw new IOException("Filename cannot be null or empty");
        }
        
        if (!filename.endsWith(".txt")) {
            throw new IOException("Only .txt files are supported: " + filename);
        }
        
        System.out.println("Processing file: " + filename);
    }
    
    // Method that throws multiple types of checked exceptions
    public static void connectToDatabase(String url, String username, String password) 
            throws SQLException, IllegalArgumentException {
        
        if (url == null || url.trim().isEmpty()) {
            throw new IllegalArgumentException("Database URL cannot be null or empty");
        }
        
        if (username == null || username.trim().isEmpty()) {
            throw new SQLException("Username cannot be null or empty");
        }
        
        if (password == null || password.length() < 8) {
            throw new SQLException("Password must be at least 8 characters long");
        }
        
        System.out.println("Connected to database: " + url);
    }
    
    public static void main(String[] args) {
        // Handle checked exceptions
        try {
            processFile("document.txt");    // Valid
            processFile("document.pdf");    // Throws IOException
        } catch (IOException e) {
            System.err.println("File processing error: " + e.getMessage());
        }
        
        try {
            connectToDatabase("jdbc:mysql://localhost:3306/mydb", "user", "password123");
            connectToDatabase("", "user", "pass");  // Throws exceptions
        } catch (SQLException e) {
            System.err.println("Database error: " + e.getMessage());
        } catch (IllegalArgumentException e) {
            System.err.println("Argument error: " + e.getMessage());
        }
    }
}
```

Custom Exception Classes with throw:
═══════════════════════════════════════════

Example 3: Creating and Throwing Custom Exceptions
─────────────────────────────────────────────────

// Custom checked exception
class InsufficientFundsException extends Exception {
    private double balance;
    private double requestedAmount;
    
    public InsufficientFundsException(String message, double balance, double requestedAmount) {
        super(message);
        this.balance = balance;
        this.requestedAmount = requestedAmount;
    }
    
    public double getBalance() { return balance; }
    public double getRequestedAmount() { return requestedAmount; }
    public double getShortfall() { return requestedAmount - balance; }
}

// Custom unchecked exception
class InvalidAccountException extends RuntimeException {
    private String accountNumber;
    
    public InvalidAccountException(String message, String accountNumber) {
        super(message);
        this.accountNumber = accountNumber;
    }
    
    public String getAccountNumber() { return accountNumber; }
}

// Business logic class using custom exceptions
public class BankAccount {
    private String accountNumber;
    private double balance;
    
    public BankAccount(String accountNumber, double initialBalance) {
        if (accountNumber == null || accountNumber.trim().isEmpty()) {
            throw new InvalidAccountException("Account number cannot be null or empty", accountNumber);
        }
        
        if (initialBalance < 0) {
            throw new IllegalArgumentException("Initial balance cannot be negative: " + initialBalance);
        }
        
        this.accountNumber = accountNumber;
        this.balance = initialBalance;
    }
    
    public void withdraw(double amount) throws InsufficientFundsException {
        if (amount <= 0) {
            throw new IllegalArgumentException("Withdrawal amount must be positive: " + amount);
        }
        
        if (amount > balance) {
            throw new InsufficientFundsException(
                "Insufficient funds for withdrawal", 
                balance, 
                amount
            );
        }
        
        balance -= amount;
        System.out.println("Withdrawn: $" + amount + ", New balance: $" + balance);
    }
    
    public void deposit(double amount) {
        if (amount <= 0) {
            throw new IllegalArgumentException("Deposit amount must be positive: " + amount);
        }
        
        balance += amount;
        System.out.println("Deposited: $" + amount + ", New balance: $" + balance);
    }
    
    public double getBalance() {
        return balance;
    }
    
    public static void main(String[] args) {
        try {
            BankAccount account = new BankAccount("ACC123", 1000.0);
            
            account.deposit(500.0);     // Valid
            account.withdraw(800.0);    // Valid
            account.withdraw(1000.0);   // Throws InsufficientFundsException
            
        } catch (InsufficientFundsException e) {
            System.err.println("Transaction failed: " + e.getMessage());
            System.err.println("Current balance: $" + e.getBalance());
            System.err.println("Requested amount: $" + e.getRequestedAmount());
            System.err.println("Shortfall: $" + e.getShortfall());
        } catch (InvalidAccountException e) {
            System.err.println("Account error: " + e.getMessage());
            System.err.println("Invalid account: " + e.getAccountNumber());
        } catch (IllegalArgumentException e) {
            System.err.println("Invalid argument: " + e.getMessage());
        }
    }
}
```

Example 4: Input Validation with throw
─────────────────────────────────────────────

public class InputValidationExample {
    
    // Email validation
    public static void validateEmail(String email) {
        if (email == null) {
            throw new IllegalArgumentException("Email cannot be null");
        }
        
        if (email.trim().isEmpty()) {
            throw new IllegalArgumentException("Email cannot be empty");
        }
        
        if (!email.contains("@")) {
            throw new IllegalArgumentException("Email must contain @ symbol: " + email);
        }
        
        if (!email.contains(".")) {
            throw new IllegalArgumentException("Email must contain domain extension: " + email);
        }
        
        System.out.println("Valid email: " + email);
    }
    
    // Password validation
    public static void validatePassword(String password) {
        if (password == null) {
            throw new IllegalArgumentException("Password cannot be null");
        }
        
        if (password.length() < 8) {
            throw new IllegalArgumentException("Password must be at least 8 characters long");
        }
        
        if (!password.matches(".*[A-Z].*")) {
            throw new IllegalArgumentException("Password must contain at least one uppercase letter");
        }
        
        if (!password.matches(".*[a-z].*")) {
            throw new IllegalArgumentException("Password must contain at least one lowercase letter");
        }
        
        if (!password.matches(".*[0-9].*")) {
            throw new IllegalArgumentException("Password must contain at least one digit");
        }
        
        System.out.println("Valid password provided");
    }
    
    // Credit card validation
    public static void validateCreditCard(String cardNumber) {
        if (cardNumber == null) {
            throw new IllegalArgumentException("Card number cannot be null");
        }
        
        // Remove spaces and dashes
        String cleanCard = cardNumber.replaceAll("[\\s-]", "");
        
        if (cleanCard.length() != 16) {
            throw new IllegalArgumentException("Card number must be 16 digits: " + cardNumber);
        }
        
        if (!cleanCard.matches("\\d+")) {
            throw new IllegalArgumentException("Card number must contain only digits: " + cardNumber);
        }
        
        System.out.println("Valid credit card number");
    }
    
    public static void main(String[] args) {
        // Test email validation
        try {
            validateEmail("user@example.com");  // Valid
            validateEmail("invalid-email");     // Throws exception
        } catch (IllegalArgumentException e) {
            System.err.println("Email validation error: " + e.getMessage());
        }
        
        // Test password validation
        try {
            validatePassword("SecurePass123");  // Valid
            validatePassword("weak");           // Throws exception
        } catch (IllegalArgumentException e) {
            System.err.println("Password validation error: " + e.getMessage());
        }
        
        // Test credit card validation
        try {
            validateCreditCard("1234 5678 9012 3456");  // Valid
            validateCreditCard("123");                   // Throws exception
        } catch (IllegalArgumentException e) {
            System.err.println("Credit card validation error: " + e.getMessage());
        }
    }
}
```

Re-throwing Exceptions:
═══════════════════════════════════════════

Example 5: Exception Re-throwing and Wrapping
─────────────────────────────────────────────

import java.io.*;
import java.sql.*;

public class ExceptionRethrowExample {
    
    // Re-throw caught exception
    public static void readConfigFile(String filename) throws IOException {
        try {
            BufferedReader reader = new BufferedReader(new FileReader(filename));
            String line = reader.readLine();
            System.out.println("Config: " + line);
            reader.close();
        } catch (FileNotFoundException e) {
            System.err.println("Config file not found, using defaults");
            // Re-throw the exception
            throw e;
        } catch (IOException e) {
            System.err.println("Error reading config file");
            // Re-throw with additional context
            throw new IOException("Failed to read configuration from: " + filename, e);
        }
    }
    
    // Wrap and re-throw exceptions
    public static void performDatabaseOperation() throws SQLException {
        try {
            // Simulate database operation
            Connection conn = DriverManager.getConnection("invalid-url");
            // ... database operations
        } catch (SQLException e) {
            // Log the error and re-throw with more context
            System.err.println("Database operation failed: " + e.getMessage());
            throw new SQLException("Critical database error in user operation", e);
        }
    }
    
    // Convert checked to unchecked exception
    public static void processUserData(String data) {
        try {
            if (data == null) {
                throw new IOException("Data cannot be null");
            }
            // Process data
            System.out.println("Processing: " + data);
        } catch (IOException e) {
            // Convert checked exception to unchecked
            throw new RuntimeException("Data processing failed", e);
        }
    }
    
    public static void main(String[] args) {
        // Example of re-throwing
        try {
            readConfigFile("nonexistent.txt");
        } catch (IOException e) {
            System.err.println("Configuration error: " + e.getMessage());
            if (e.getCause() != null) {
                System.err.println("Caused by: " + e.getCause().getMessage());
            }
        }
        
        // Example of wrapped exception
        try {
            performDatabaseOperation();
        } catch (SQLException e) {
            System.err.println("Database error: " + e.getMessage());
        }
        
        // Example of converted exception
        try {
            processUserData(null);
        } catch (RuntimeException e) {
            System.err.println("Runtime error: " + e.getMessage());
        }
    }
}
```

Advanced throw Usage Patterns:
═══════════════════════════════════════════

Example 6: Conditional Exception Throwing
─────────────────────────────────────────────

public class ConditionalThrowExample {
    
    // State-based exception throwing
    public static class OrderProcessor {
        private boolean isSystemOnline = true;
        private int maxOrderAmount = 10000;
        
        public void processOrder(int amount, String customerType) {
            // Check system status
            if (!isSystemOnline) {
                throw new IllegalStateException("Order processing system is currently offline");
            }
            
            // Validate order amount
            if (amount <= 0) {
                throw new IllegalArgumentException("Order amount must be positive: " + amount);
            }
            
            // Check customer-specific limits
            switch (customerType.toLowerCase()) {
                case "standard":
                    if (amount > maxOrderAmount / 2) {
                        throw new IllegalArgumentException(
                            "Standard customers cannot place orders over $" + (maxOrderAmount / 2)
                        );
                    }
                    break;
                case "premium":
                    if (amount > maxOrderAmount) {
                        throw new IllegalArgumentException(
                            "Premium customers cannot place orders over $" + maxOrderAmount
                        );
                    }
                    break;
                case "vip":
                    // VIP customers have no limit
                    break;
                default:
                    throw new IllegalArgumentException("Unknown customer type: " + customerType);
            }
            
            System.out.println("Order processed: $" + amount + " for " + customerType + " customer");
        }
        
        public void setSystemOnline(boolean online) {
            this.isSystemOnline = online;
        }
    }
    
    // Resource validation with throw
    public static void validateSystemResources() {
        Runtime runtime = Runtime.getRuntime();
        long totalMemory = runtime.totalMemory();
        long freeMemory = runtime.freeMemory();
        long usedMemory = totalMemory - freeMemory;
        double memoryUsagePercent = (double) usedMemory / totalMemory * 100;
        
        if (memoryUsagePercent > 90) {
            throw new RuntimeException(
                String.format("Critical memory usage: %.2f%% (Used: %d MB, Total: %d MB)", 
                    memoryUsagePercent, usedMemory / 1024 / 1024, totalMemory / 1024 / 1024)
            );
        }
        
        if (memoryUsagePercent > 75) {
            throw new RuntimeException(
                String.format("High memory usage warning: %.2f%%", memoryUsagePercent)
            );
        }
        
        System.out.println("System resources OK: " + String.format("%.2f%% memory used", memoryUsagePercent));
    }
    
    public static void main(String[] args) {
        OrderProcessor processor = new OrderProcessor();
        
        try {
            processor.processOrder(3000, "standard");   // Valid
            processor.processOrder(8000, "standard");   // Throws exception
        } catch (IllegalArgumentException e) {
            System.err.println("Order error: " + e.getMessage());
        }
        
        try {
            processor.setSystemOnline(false);
            processor.processOrder(1000, "premium");    // Throws IllegalStateException
        } catch (IllegalStateException e) {
            System.err.println("System error: " + e.getMessage());
        }
        
        try {
            validateSystemResources();
        } catch (RuntimeException e) {
            System.err.println("Resource error: " + e.getMessage());
        }
    }
}
```

throw vs throws Comparison:
═══════════════════════════════════════════

| Aspect | throw | throws |
|--------|-------|--------|
| **Purpose** | Actually throws an exception | Declares that method might throw exceptions |
| **Usage** | Inside method body | In method signature |
| **Syntax** | `throw new Exception("message");` | `public void method() throws Exception` |
| **Number** | Can throw one exception at a time | Can declare multiple exception types |
| **When** | Runtime - when specific condition met | Compile time - declaration only |
| **Mandatory** | For checked exceptions in caller | For checked exceptions that aren't handled |

Example: throw vs throws
─────────────────────────────────────────────

public class ThrowVsThrowsExample {
    
    // Method using 'throws' declaration
    public static void methodWithThrows() throws IOException, SQLException {
        // This method might throw these exceptions but doesn't necessarily throw them
        System.out.println("Method declared to throw exceptions");
    }
    
    // Method using 'throw' statement
    public static void methodWithThrow(boolean shouldThrow) throws IOException {
        if (shouldThrow) {
            // Actually throwing an exception
            throw new IOException("Exception thrown using throw keyword");
        }
        System.out.println("No exception thrown");
    }
    
    // Method combining both
    public static void combinedExample(String input) throws IllegalArgumentException {
        if (input == null) {
            // Using throw to actually throw an exception
            throw new IllegalArgumentException("Input cannot be null");
        }
        // Method is declared with throws, but may not always throw
        System.out.println("Processing: " + input);
    }
    
    public static void main(String[] args) {
        try {
            methodWithThrows();         // Declared to throw, but doesn't
            methodWithThrow(false);     // Doesn't throw
            methodWithThrow(true);      // Actually throws
        } catch (IOException | SQLException e) {
            System.err.println("Caught exception: " + e.getMessage());
        }
        
        try {
            combinedExample("valid input");  // Doesn't throw
            combinedExample(null);           // Actually throws
        } catch (IllegalArgumentException e) {
            System.err.println("Validation error: " + e.getMessage());
        }
    }
}
```

Best Practices for throw Keyword:
═══════════════════════════════════════════

1. **Meaningful Exception Messages**:
```java
// Good - Specific and helpful
throw new IllegalArgumentException("Age must be between 0 and 150, but was: " + age);

// Poor - Generic and unhelpful
throw new IllegalArgumentException("Invalid age");
```

2. **Use Appropriate Exception Types**:
```java
// Good - Specific exception types
public void setPrice(double price) {
    if (price < 0) {
        throw new IllegalArgumentException("Price cannot be negative: " + price);
    }
    if (price > 1000000) {
        throw new IllegalStateException("Price exceeds maximum allowed limit");
    }
}
```

3. **Include Context Information**:
```java
public void processPayment(String cardNumber, double amount) {
    if (cardNumber == null || cardNumber.trim().isEmpty()) {
        throw new IllegalArgumentException(
            String.format("Invalid card number for payment of $%.2f", amount)
        );
    }
}
```

4. **Early Validation (Fail Fast)**:
```java
public void createUser(String username, String email, int age) {
    // Validate all inputs at the beginning
    if (username == null || username.trim().isEmpty()) {
        throw new IllegalArgumentException("Username cannot be null or empty");
    }
    if (email == null || !email.contains("@")) {
        throw new IllegalArgumentException("Valid email address required");
    }
    if (age < 0 || age > 150) {
        throw new IllegalArgumentException("Age must be between 0 and 150");
    }
    
    // Proceed with user creation only if all validations pass
    System.out.println("Creating user: " + username);
}
```

Common Use Cases for throw:
═══════════════════════════════════════════

1. **Input Validation**:
   - Null checks
   - Range validation
   - Format validation

2. **Business Rule Enforcement**:
   - Account balance checks
   - Permission validation
   - State validation

3. **Error Condition Detection**:
   - Resource unavailability
   - Configuration errors
   - Data corruption

4. **Exception Translation**:
   - Converting low-level exceptions to business exceptions
   - Adding context to caught exceptions

5. **Testing and Debugging**:
   - Simulating error conditions
   - Asserting expected states

Performance Considerations:
═══════════════════════════════════════════

- **Exception Creation Cost**: Creating exception objects is expensive
- **Stack Trace Generation**: Filling stack traces adds overhead
- **Use Judiciously**: Don't use exceptions for normal control flow
- **Pre-validate**: Check conditions before expensive operations

Example: Performance-Conscious Exception Throwing
─────────────────────────────────────────────────

public class PerformanceConsciousExample {
    
    // Pre-create exceptions for common cases to avoid repeated object creation
    private static final IllegalArgumentException NULL_INPUT_EXCEPTION = 
        new IllegalArgumentException("Input cannot be null");
    
    private static final IllegalArgumentException EMPTY_INPUT_EXCEPTION = 
        new IllegalArgumentException("Input cannot be empty");
    
    public static void processInput(String input) {
        // Fast null check
        if (input == null) {
            throw NULL_INPUT_EXCEPTION;
        }
        
        // Fast empty check
        if (input.isEmpty()) {
            throw EMPTY_INPUT_EXCEPTION;
        }
        
        // Expensive validation only after basic checks pass
        if (input.length() > 1000) {
            throw new IllegalArgumentException("Input too long: " + input.length() + " characters");
        }
        
        System.out.println("Processing: " + input);
    }
}
```

Summary - throw Keyword:
═══════════════════════════════════════════

**Key Points:**
- **Manual Control**: `throw` gives explicit control over when exceptions are raised
- **Immediate Transfer**: Execution immediately jumps to exception handling mechanism
- **Any Exception Type**: Can throw both checked and unchecked exceptions
- **Context Preservation**: Allows adding meaningful messages and context

**Best Practices:**
- Use specific exception types
- Provide clear, actionable error messages
- Include relevant context information
- Validate inputs early (fail fast principle)
- Don't use exceptions for normal program flow
- Consider performance implications

**Common Patterns:**
- Input validation and sanitization
- Business rule enforcement
- Resource state checking
- Exception wrapping and re-throwing
- Custom exception creation and throwing

The `throw` keyword is essential for robust Java applications, enabling developers to create reliable, well-behaved code that handles error conditions gracefully and provides meaningful feedback to users and other developers.

throw vs throws - Comprehensive Comparison:
─────────────────────────────────────────────

Understanding the difference between `throw` and `throws` is fundamental to mastering exception handling in Java. While both are related to exceptions, they serve completely different purposes and are used in different contexts.

Overview of throw vs throws:
═══════════════════════════════════════════

**throw:**
- Used to explicitly throw an exception from within a method
- Actual action of throwing an exception at runtime
- Used inside method body
- Can throw only one exception at a time

**throws:**
- Used to declare that a method might throw certain exceptions
- Declaration/signature statement at compile time
- Used in method signature
- Can declare multiple exception types

Detailed Comparison Table:
═══════════════════════════════════════════

┌─────────────────────┬─────────────────────────────┬─────────────────────────────┐
│ Aspect              │ throw                       │ throws                      │
├─────────────────────┼─────────────────────────────┼─────────────────────────────┤
│ **Purpose**         │ Actually throws an exception│ Declares potential exceptions│
├─────────────────────┼─────────────────────────────┼─────────────────────────────┤
│ **Location**        │ Inside method body          │ In method signature         │
├─────────────────────┼─────────────────────────────┼─────────────────────────────┤
│ **Syntax**          │ throw new Exception();      │ method() throws Exception   │
├─────────────────────┼─────────────────────────────┼─────────────────────────────┤
│ **Timing**          │ Runtime execution           │ Compile-time declaration    │
├─────────────────────┼─────────────────────────────┼─────────────────────────────┤
│ **Exception Count** │ One exception at a time     │ Multiple exceptions allowed │
├─────────────────────┼─────────────────────────────┼─────────────────────────────┤
│ **Control Flow**    │ Immediately stops execution │ No immediate effect         │
├─────────────────────┼─────────────────────────────┼─────────────────────────────┤
│ **Mandatory**       │ When condition is met       │ For uncaught checked exceptions│
├─────────────────────┼─────────────────────────────┼─────────────────────────────┤
│ **Object Creation** │ Creates exception object    │ No object creation          │
├─────────────────────┼─────────────────────────────┼─────────────────────────────┤
│ **Inheritance**     │ Can throw any Throwable     │ Can declare any Exception   │
├─────────────────────┼─────────────────────────────┼─────────────────────────────┤
│ **Compiler Role**   │ Checks if declared or handled│ Enforces declaration rules  │
└─────────────────────┴─────────────────────────────┴─────────────────────────────┘

Syntax Comparison:
═══════════════════════════════════════════

**throw Syntax:**
```java
// Basic throw
throw new ExceptionType("Error message");

// Examples
throw new IllegalArgumentException("Invalid input");
throw new IOException("File not found");
throw new RuntimeException("Something went wrong");
```

**throws Syntax:**
```java
// Single exception
public void method() throws ExceptionType {
    // method body
}

// Multiple exceptions
public void method() throws Exception1, Exception2, Exception3 {
    // method body
}

// Examples
public void readFile() throws IOException {
    // file reading code
}

public void databaseOp() throws SQLException, ClassNotFoundException {
    // database code
}
```

Basic Examples Demonstrating Differences:
═══════════════════════════════════════════

Example 1: throw - Actually Throwing Exceptions
─────────────────────────────────────────────

public class ThrowExample {
    
    // Method that uses throw to actually throw exceptions
    public static void validateAge(int age) {
        if (age < 0) {
            // throw keyword - actually throws the exception
            throw new IllegalArgumentException("Age cannot be negative: " + age);
        }
        if (age > 150) {
            // throw keyword - actually throws the exception
            throw new IllegalArgumentException("Age cannot exceed 150: " + age);
        }
        System.out.println("Valid age: " + age);
    }
    
    public static void divide(int a, int b) {
        if (b == 0) {
            // throw keyword - actually throws the exception
            throw new ArithmeticException("Division by zero is not allowed");
        }
        System.out.println("Result: " + (a / b));
    }
    
    public static void main(String[] args) {
        try {
            validateAge(25);    // Valid - no exception thrown
            validateAge(-5);    // throw executes - exception is thrown
        } catch (IllegalArgumentException e) {
            System.err.println("Validation failed: " + e.getMessage());
        }
        
        try {
            divide(10, 2);  // Valid - no exception thrown
            divide(10, 0);  // throw executes - exception is thrown
        } catch (ArithmeticException e) {
            System.err.println("Math error: " + e.getMessage());
        }
    }
}
```

Example 2: throws - Declaring Potential Exceptions
─────────────────────────────────────────────────

import java.io.*;
import java.sql.*;

public class ThrowsExample {
    
    // Method that uses throws to declare potential exceptions
    public static void readFile(String filename) throws IOException {
        // throws declaration - method might throw IOException
        FileReader file = new FileReader(filename);  // This might throw IOException
        BufferedReader reader = new BufferedReader(file);
        String line = reader.readLine();
        System.out.println("Read: " + line);
        reader.close();
        // Note: No actual throw statement, but method can throw IOException
    }
    
    // Method declaring multiple exceptions
    public static void databaseOperation() throws SQLException, ClassNotFoundException {
        // throws declaration - method might throw these exceptions
        Class.forName("com.mysql.cj.jdbc.Driver");  // Might throw ClassNotFoundException
        
        Connection conn = DriverManager.getConnection(
            "jdbc:mysql://localhost:3306/test", "user", "pass");  // Might throw SQLException
        
        Statement stmt = conn.createStatement();
        ResultSet rs = stmt.executeQuery("SELECT * FROM users");  // Might throw SQLException
        
        while (rs.next()) {
            System.out.println("User: " + rs.getString("name"));
        }
        conn.close();
    }
    
    // Method that might not throw but still declares
    public static void processData(String data) throws IOException {
        // throws declaration present, but method might not always throw
        if (data == null) {
            System.out.println("No data to process");
            return;  // No exception thrown in this case
        }
        
        if (data.length() > 1000) {
            // Here we might actually throw (but this is optional)
            throw new IOException("Data too large to process");
        }
        
        System.out.println("Processing: " + data);
        // Method completes normally - no exception thrown
    }
    
    public static void main(String[] args) {
        // Caller must handle declared exceptions
        try {
            readFile("test.txt");           // Must handle IOException
            databaseOperation();            // Must handle SQLException and ClassNotFoundException
            processData("sample data");     // Must handle IOException
        } catch (IOException e) {
            System.err.println("IO error: " + e.getMessage());
        } catch (SQLException e) {
            System.err.println("Database error: " + e.getMessage());
        } catch (ClassNotFoundException e) {
            System.err.println("Driver not found: " + e.getMessage());
        }
    }
}
```

Combined Usage - throw and throws Together:
═══════════════════════════════════════════

Example 3: Using Both throw and throws
─────────────────────────────────────────────

import java.io.*;

public class CombinedExample {
    
    // Method uses both throws (declaration) and throw (actual throwing)
    public static void validateAndProcessFile(String filename) throws IOException {
        // throws declaration - tells caller this method might throw IOException
        
        if (filename == null) {
            // throw statement - actually throws an exception
            throw new IOException("Filename cannot be null");
        }
        
        if (filename.trim().isEmpty()) {
            // throw statement - actually throws an exception
            throw new IOException("Filename cannot be empty");
        }
        
        if (!filename.endsWith(".txt")) {
            // throw statement - actually throws an exception
            throw new IOException("Only .txt files are supported");
        }
        
        // This might also throw IOException (declared by throws)
        FileReader file = new FileReader(filename);
        BufferedReader reader = new BufferedReader(file);
        
        String line;
        while ((line = reader.readLine()) != null) {
            if (line.contains("ERROR")) {
                reader.close();
                // throw statement - actually throws an exception
                throw new IOException("Error found in file: " + line);
            }
            System.out.println("Processing: " + line);
        }
        
        reader.close();
        System.out.println("File processed successfully");
    }
    
    // Method with conditional throwing
    public static void processOrder(double amount, String customerType) 
            throws IllegalArgumentException, IllegalStateException {
        // throws declaration - method might throw these exceptions
        
        if (amount <= 0) {
            // throw statement - actually throws when condition is met
            throw new IllegalArgumentException("Order amount must be positive: " + amount);
        }
        
        if (customerType == null) {
            // throw statement - actually throws when condition is met
            throw new IllegalArgumentException("Customer type cannot be null");
        }
        
        // Business logic that might throw
        switch (customerType.toLowerCase()) {
            case "standard":
                if (amount > 5000) {
                    // throw statement - actually throws when condition is met
                    throw new IllegalStateException("Standard customers cannot place orders over $5000");
                }
                break;
            case "premium":
                if (amount > 20000) {
                    // throw statement - actually throws when condition is met
                    throw new IllegalStateException("Premium customers cannot place orders over $20000");
                }
                break;
            case "vip":
                // VIP customers have no limits
                break;
            default:
                // throw statement - actually throws for unknown customer type
                throw new IllegalArgumentException("Unknown customer type: " + customerType);
        }
        
        System.out.println("Order processed: $" + amount + " for " + customerType + " customer");
    }
    
    public static void main(String[] args) {
        // Handle exceptions declared by throws
        try {
            validateAndProcessFile("data.txt");     // May or may not throw
            processOrder(1000, "standard");         // May or may not throw
            processOrder(-500, "premium");          // Will definitely throw
        } catch (IOException e) {
            System.err.println("File processing error: " + e.getMessage());
        } catch (IllegalArgumentException e) {
            System.err.println("Invalid argument: " + e.getMessage());
        } catch (IllegalStateException e) {
            System.err.println("Invalid state: " + e.getMessage());
        }
    }
}
```

Key Conceptual Differences:
═══════════════════════════════════════════

1. **Action vs Declaration:**
```java
// throws - DECLARES that method might throw
public void method() throws IOException {
    // Method might or might not throw IOException
}

// throw - ACTUALLY throws an exception
public void method() {
    throw new IOException("Error occurred");  // This WILL throw
}
```

2. **Timing:**
```java
// throws - Compile-time information
public void method() throws Exception {  // Compiler knows about potential exception
    // Method implementation
}

// throw - Runtime action
public void method() {
    if (condition) {
        throw new Exception();  // Exception thrown at runtime
    }
}
```

3. **Quantity:**
```java
// throws - Can declare multiple exceptions
public void method() throws IOException, SQLException, ClassNotFoundException {
    // Method might throw any of these exceptions
}

// throw - Can only throw one exception at a time
public void method() {
    throw new IOException();     // Only one exception per throw statement
    // throw new SQLException(); // This line would be unreachable
}
```

Real-World Scenarios:
═══════════════════════════════════════════

Scenario 1: File Processing Service
─────────────────────────────────────────────

public class FileProcessingService {
    
    // throws declares what exceptions callers should expect
    public void processFile(String filename) throws IOException, SecurityException {
        
        // Input validation with throw
        if (filename == null) {
            throw new IllegalArgumentException("Filename cannot be null");
        }
        
        // Security check with throw
        if (!hasPermission(filename)) {
            throw new SecurityException("No permission to access file: " + filename);
        }
        
        // File operations that might throw IOException (declared by throws)
        try (BufferedReader reader = new BufferedReader(new FileReader(filename))) {
            String line;
            while ((line = reader.readLine()) != null) {
                // Business rule validation with throw
                if (line.startsWith("FORBIDDEN")) {
                    throw new IOException("Forbidden content found in file");
                }
                processLine(line);
            }
        }
        // IOException from file operations is automatically propagated due to throws declaration
    }
    
    private boolean hasPermission(String filename) {
        // Permission checking logic
        return !filename.contains("restricted");
    }
    
    private void processLine(String line) {
        System.out.println("Processing: " + line);
    }
}
```

Scenario 2: Banking Transaction System
─────────────────────────────────────────────

public class BankingService {
    
    // throws declares potential exceptions for the caller
    public void transferFunds(String fromAccount, String toAccount, double amount) 
            throws InsufficientFundsException, AccountNotFoundException, TransactionException {
        
        // Validation with throw
        if (amount <= 0) {
            throw new IllegalArgumentException("Transfer amount must be positive");
        }
        
        // Business logic that uses throw for specific conditions
        Account from = findAccount(fromAccount);
        if (from == null) {
            throw new AccountNotFoundException("Source account not found: " + fromAccount);
        }
        
        Account to = findAccount(toAccount);
        if (to == null) {
            throw new AccountNotFoundException("Destination account not found: " + toAccount);
        }
        
        if (from.getBalance() < amount) {
            throw new InsufficientFundsException("Insufficient funds in account: " + fromAccount);
        }
        
        // Database operations that might throw (covered by throws declaration)
        try {
            from.withdraw(amount);
            to.deposit(amount);
            recordTransaction(fromAccount, toAccount, amount);
        } catch (DatabaseException e) {
            // Convert and re-throw with throw
            throw new TransactionException("Failed to complete transfer", e);
        }
    }
    
    private Account findAccount(String accountNumber) throws AccountNotFoundException {
        // This method declares it might throw, but doesn't always throw
        // Implementation would query database
        return null; // Simplified
    }
    
    private void recordTransaction(String from, String to, double amount) throws DatabaseException {
        // Database operation that might throw
        // Implementation would save to database
    }
    
    // Custom exception classes
    static class InsufficientFundsException extends Exception {
        public InsufficientFundsException(String message) { super(message); }
    }
    
    static class AccountNotFoundException extends Exception {
        public AccountNotFoundException(String message) { super(message); }
    }
    
    static class TransactionException extends Exception {
        public TransactionException(String message, Throwable cause) { super(message, cause); }
    }
    
    static class DatabaseException extends Exception {
        public DatabaseException(String message) { super(message); }
    }
    
    static class Account {
        private double balance;
        public double getBalance() { return balance; }
        public void withdraw(double amount) throws DatabaseException { /* implementation */ }
        public void deposit(double amount) throws DatabaseException { /* implementation */ }
    }
}
```

Method Signature Rules:
═══════════════════════════════════════════

**throws Rules:**
1. **Checked Exceptions**: Must be declared in throws clause if not handled
2. **Unchecked Exceptions**: Optional to declare in throws clause
3. **Multiple Exceptions**: Separate with commas
4. **Inheritance**: Overriding methods cannot add new checked exceptions

```java
// Valid throws declarations
public void method1() throws IOException {  // Single checked exception
}

public void method2() throws IOException, SQLException {  // Multiple checked exceptions
}

public void method3() throws RuntimeException {  // Unchecked (optional)
}

public void method4() {  // No throws needed for unchecked exceptions
    throw new RuntimeException("Error");
}
```

**throw Rules:**
1. **Single Exception**: Can only throw one exception per statement
2. **Any Throwable**: Can throw any subclass of Throwable
3. **Must Be Reachable**: Code after throw is unreachable
4. **Object Required**: Must throw an actual exception object

```java
// Valid throw statements
throw new IOException("File error");
throw new RuntimeException("Runtime error");
throw new CustomException("Custom error");

// Invalid - unreachable code
throw new Exception("Error");
System.out.println("This line is unreachable");  // Compilation error
```

Exception Propagation Patterns:
═══════════════════════════════════════════

Pattern 1: Handle or Declare
```java
public void callerMethod() {
    try {
        methodThatThrows();  // Handle the declared exception
    } catch (IOException e) {
        System.err.println("Handled: " + e.getMessage());
    }
}

// OR

public void callerMethod() throws IOException {  // Declare to pass it up
    methodThatThrows();  // Don't handle, let it propagate
}

public void methodThatThrows() throws IOException {
    throw new IOException("Something went wrong");
}
```

Pattern 2: Transform Exceptions
```java
public void businessMethod() throws BusinessException {  // Declare business exception
    try {
        lowLevelOperation();
    } catch (SQLException e) {
        // Transform technical exception to business exception using throw
        throw new BusinessException("Business operation failed", e);
    }
}

public void lowLevelOperation() throws SQLException {  // Declare technical exception
    // Database operation that might throw SQLException
}
```

Common Mistakes and Solutions:
═══════════════════════════════════════════

**Mistake 1: Confusing throw and throws**
```java
// WRONG - Using throw instead of throws in method signature
public void method() throw IOException {  // Compilation error
}

// CORRECT
public void method() throws IOException {  // Correct declaration
    throw new IOException("Error");  // Correct usage
}
```

**Mistake 2: Unnecessary throws declarations**
```java
// WRONG - Declaring unchecked exceptions unnecessarily
public void method() throws RuntimeException {  // Not required
    throw new RuntimeException("Error");
}

// BETTER - Clean method signature
public void method() {  // Unchecked exceptions don't need declaration
    throw new RuntimeException("Error");
}
```

**Mistake 3: Over-broad exception declarations**
```java
// WRONG - Too broad
public void method() throws Exception {  // Too general
    // Specific operations
}

// BETTER - Specific exceptions
public void method() throws IOException, SQLException {  // Specific
    // File and database operations
}
```

Best Practices Summary:
═══════════════════════════════════════════

**For throw:**
1. Use specific exception types
2. Provide meaningful error messages
3. Include context information
4. Fail fast - validate early
5. Don't use for normal control flow

**For throws:**
1. Declare only checked exceptions that aren't handled
2. Be specific about exception types
3. Document when and why exceptions are thrown
4. Consider the caller's perspective
5. Don't declare unchecked exceptions unless for documentation

**Combined Usage:**
1. Use throws to inform callers about potential exceptions
2. Use throw to actually raise exceptions when conditions are met
3. Handle exceptions at the appropriate level
4. Transform exceptions when crossing architectural boundaries
5. Maintain exception hierarchies for different abstraction levels

Visual Summary:
═══════════════════════════════════════════

```
Method Declaration:
public void method() throws IOException {  ← throws (declares)
    
    if (condition) {
        throw new IOException("Error");    ← throw (executes)
    }
    
    // Other code that might throw IOException
    // (handled by throws declaration)
}

Caller:
try {
    method();  ← Must handle IOException due to throws declaration
} catch (IOException e) {
    // Handle exception that was thrown by throw statement
}
```

**Key Takeaway:**
- **throws** = "This method MIGHT throw these exceptions" (promise/contract)
- **throw** = "I am NOW throwing this exception" (action/execution)

Understanding this fundamental difference is crucial for effective exception handling in Java applications.

Advanced Exception Handling Concepts and Patterns:
─────────────────────────────────────────────

This section explores advanced exception handling topics, design patterns, and best practices that go beyond the basic try-catch-finally constructs. These concepts are essential for building robust, maintainable, and scalable Java applications.

Exception Chaining and Cause Analysis:
═══════════════════════════════════════════

Exception chaining allows you to preserve the original cause of an exception while wrapping it in a more appropriate exception type for the current context. This is crucial for debugging and maintaining the exception trail.

**Concepts:**
- **Root Cause Preservation**: Keep track of the original exception
- **Context Enhancement**: Add meaningful context at each layer
- **Exception Translation**: Convert low-level exceptions to business exceptions
- **Stack Trace Integrity**: Maintain complete error information

Example 1: Exception Chaining Patterns
─────────────────────────────────────────────

import java.io.*;
import java.sql.*;

public class ExceptionChainingExample {
    
    // Data Access Layer - Low-level exceptions
    public static class DataAccessLayer {
        public void saveUser(String userData) throws SQLException {
            // Simulate database error
            throw new SQLException("Connection timeout", "08001", 1042);
        }
        
        public String readConfig(String filename) throws IOException {
            // Simulate file error
            throw new FileNotFoundException("Configuration file not found: " + filename);
        }
    }
    
    // Service Layer - Business exceptions with chaining
    public static class UserService {
        private DataAccessLayer dataLayer = new DataAccessLayer();
        
        public void createUser(String username, String email) throws UserCreationException {
            try {
                String userData = formatUserData(username, email);
                dataLayer.saveUser(userData);
            } catch (SQLException e) {
                // Chain the original exception with business context
                throw new UserCreationException(
                    "Failed to create user: " + username, e);
            }
        }
        
        public void loadConfiguration() throws ConfigurationException {
            try {
                String config = dataLayer.readConfig("app.properties");
                processConfiguration(config);
            } catch (IOException e) {
                // Chain with specific configuration context
                throw new ConfigurationException(
                    "Unable to load application configuration", e);
            }
        }
        
        private String formatUserData(String username, String email) {
            return username + ":" + email;
        }
        
        private void processConfiguration(String config) {
            // Process configuration
        }
    }
    
    // Custom exception classes with chaining support
    public static class UserCreationException extends Exception {
        public UserCreationException(String message) {
            super(message);
        }
        
        public UserCreationException(String message, Throwable cause) {
            super(message, cause);
        }
    }
    
    public static class ConfigurationException extends Exception {
        public ConfigurationException(String message) {
            super(message);
        }
        
        public ConfigurationException(String message, Throwable cause) {
            super(message, cause);
        }
    }
    
    // Application Layer - Exception analysis and handling
    public static void main(String[] args) {
        UserService userService = new UserService();
        
        try {
            userService.createUser("john_doe", "john@example.com");
        } catch (UserCreationException e) {
            System.err.println("Business Error: " + e.getMessage());
            
            // Analyze the exception chain
            Throwable cause = e.getCause();
            if (cause instanceof SQLException) {
                SQLException sqlEx = (SQLException) cause;
                System.err.println("Database Error Details:");
                System.err.println("  SQL State: " + sqlEx.getSQLState());
                System.err.println("  Error Code: " + sqlEx.getErrorCode());
                System.err.println("  Original Message: " + sqlEx.getMessage());
            }
            
            // Print the complete stack trace showing the chain
            e.printStackTrace();
        }
        
        try {
            userService.loadConfiguration();
        } catch (ConfigurationException e) {
            System.err.println("Configuration Error: " + e.getMessage());
            
            // Walk through the exception chain
            Throwable current = e;
            int level = 0;
            while (current != null) {
                System.err.println("Level " + level + ": " + 
                    current.getClass().getSimpleName() + " - " + current.getMessage());
                current = current.getCause();
                level++;
            }
        }
    }
}
```

Try-with-Resources Advanced Patterns:
═══════════════════════════════════════════

The try-with-resources statement, introduced in Java 7, provides automatic resource management. Here are advanced patterns and best practices.

Example 2: Advanced Try-with-Resources
─────────────────────────────────────────────

import java.io.*;
import java.sql.*;
import java.util.zip.*;

public class TryWithResourcesAdvanced {
    
    // Multiple resources with proper ordering
    public static void processFileWithBackup(String inputFile, String outputFile, String backupFile) 
            throws IOException {
        
        // Resources are closed in reverse order of declaration
        try (
            FileInputStream input = new FileInputStream(inputFile);
            BufferedInputStream bufferedInput = new BufferedInputStream(input);
            
            FileOutputStream output = new FileOutputStream(outputFile);
            BufferedOutputStream bufferedOutput = new BufferedOutputStream(output);
            
            FileOutputStream backup = new FileOutputStream(backupFile);
            GZIPOutputStream compressedBackup = new GZIPOutputStream(backup)
        ) {
            
            byte[] buffer = new byte[1024];
            int bytesRead;
            
            while ((bytesRead = bufferedInput.read(buffer)) != -1) {
                // Write to both output and compressed backup
                bufferedOutput.write(buffer, 0, bytesRead);
                compressedBackup.write(buffer, 0, bytesRead);
            }
            
            System.out.println("File processing completed successfully");
            
        } catch (IOException e) {
            System.err.println("Error during file processing: " + e.getMessage());
            
            // Clean up partial output files
            cleanupFile(outputFile);
            cleanupFile(backupFile);
            
            throw e; // Re-throw to caller
        }
    }
    
    // Custom resource implementation
    public static class DatabaseConnection implements AutoCloseable {
        private String connectionString;
        private boolean isOpen;
        
        public DatabaseConnection(String connectionString) throws SQLException {
            this.connectionString = connectionString;
            this.isOpen = true;
            System.out.println("Database connection opened: " + connectionString);
            
            // Simulate connection failure
            if (connectionString.contains("invalid")) {
                throw new SQLException("Invalid connection string");
            }
        }
        
        public void executeQuery(String sql) throws SQLException {
            if (!isOpen) {
                throw new SQLException("Connection is closed");
            }
            System.out.println("Executing query: " + sql);
        }
        
        @Override
        public void close() throws SQLException {
            if (isOpen) {
                System.out.println("Closing database connection: " + connectionString);
                isOpen = false;
                
                // Simulate close operation that might fail
                if (connectionString.contains("error-on-close")) {
                    throw new SQLException("Error while closing connection");
                }
            }
        }
        
        public boolean isOpen() {
            return isOpen;
        }
    }
    
    // Nested try-with-resources and exception handling
    public static void performDatabaseOperations() {
        
        // Outer try-with-resources for connection
        try (DatabaseConnection connection = new DatabaseConnection("jdbc:mysql://localhost:3306/test")) {
            
            connection.executeQuery("SELECT * FROM users");
            
            // Inner try-with-resources for transaction-like operations
            try (DatabaseConnection transactionConnection = 
                     new DatabaseConnection("jdbc:mysql://localhost:3306/test_transaction")) {
                
                transactionConnection.executeQuery("BEGIN TRANSACTION");
                transactionConnection.executeQuery("INSERT INTO logs VALUES (1, 'Operation started')");
                transactionConnection.executeQuery("UPDATE users SET last_login = NOW()");
                transactionConnection.executeQuery("COMMIT");
                
            } catch (SQLException e) {
                System.err.println("Transaction failed: " + e.getMessage());
                // Transaction connection automatically closed due to try-with-resources
            }
            
        } catch (SQLException e) {
            System.err.println("Database operation failed: " + e.getMessage());
            // Main connection automatically closed due to try-with-resources
        }
    }
    
    // Handling suppressed exceptions
    public static void demonstrateSuppressedExceptions() {
        try (DatabaseConnection connection = new DatabaseConnection("jdbc:error-on-close://test")) {
            
            connection.executeQuery("SELECT * FROM users");
            
            // This will throw an exception
            throw new RuntimeException("Business logic error");
            
        } catch (Exception e) {
            System.err.println("Primary exception: " + e.getMessage());
            
            // Check for suppressed exceptions (from close() method)
            Throwable[] suppressedExceptions = e.getSuppressed();
            for (int i = 0; i < suppressedExceptions.length; i++) {
                System.err.println("Suppressed exception " + i + ": " + 
                    suppressedExceptions[i].getMessage());
            }
        }
    }
    
    private static void cleanupFile(String filename) {
        try {
            File file = new File(filename);
            if (file.exists() && !file.delete()) {
                System.err.println("Warning: Could not delete partial file: " + filename);
            }
        } catch (Exception e) {
            System.err.println("Error during cleanup of " + filename + ": " + e.getMessage());
        }
    }
    
    public static void main(String[] args) {
        try {
            processFileWithBackup("input.txt", "output.txt", "backup.txt.gz");
        } catch (IOException e) {
            System.err.println("File processing failed: " + e.getMessage());
        }
        
        performDatabaseOperations();
        demonstrateSuppressedExceptions();
    }
}
```

Exception Handling Design Patterns:
═══════════════════════════════════════════

Several design patterns can improve exception handling in complex applications.

Example 3: Exception Handling Patterns
─────────────────────────────────────────────

import java.util.*;
import java.util.function.*;

public class ExceptionHandlingPatterns {
    
    // 1. Exception Translation Pattern
    public static class ExceptionTranslationPattern {
        
        // Low-level operation that throws technical exceptions
        private void lowLevelOperation(String data) throws IOException {
            if (data == null) {
                throw new IOException("Data stream is null");
            }
            if (data.contains("corrupt")) {
                throw new IOException("Data corruption detected");
            }
        }
        
        // High-level operation that translates to business exceptions
        public void processBusinessData(String businessData) throws BusinessException {
            try {
                lowLevelOperation(businessData);
                System.out.println("Business data processed successfully");
            } catch (IOException e) {
                // Translate technical exception to business exception
                throw new BusinessException("Failed to process business data", e);
            }
        }
    }
    
    // 2. Exception Facade Pattern
    public static class ExceptionFacadePattern {
        
        public void performComplexOperation(String input) throws OperationException {
            try {
                validateInput(input);
                processData(input);
                saveResults(input);
            } catch (ValidationException | ProcessingException | PersistenceException e) {
                // Unify different exception types under a single facade
                throw new OperationException("Complex operation failed for input: " + input, e);
            }
        }
        
        private void validateInput(String input) throws ValidationException {
            if (input == null || input.trim().isEmpty()) {
                throw new ValidationException("Input cannot be null or empty");
            }
        }
        
        private void processData(String input) throws ProcessingException {
            if (input.contains("error")) {
                throw new ProcessingException("Processing error in data: " + input);
            }
        }
        
        private void saveResults(String input) throws PersistenceException {
            if (input.contains("save-error")) {
                throw new PersistenceException("Failed to save data: " + input);
            }
        }
    }
    
    // 3. Retry Pattern with Exception Handling
    public static class RetryPattern {
        private static final int MAX_RETRIES = 3;
        private static final long RETRY_DELAY_MS = 1000;
        
        public <T> T executeWithRetry(Supplier<T> operation, String operationName) 
                throws OperationException {
            
            Exception lastException = null;
            
            for (int attempt = 1; attempt <= MAX_RETRIES; attempt++) {
                try {
                    System.out.println("Attempt " + attempt + " for " + operationName);
                    return operation.get();
                    
                } catch (Exception e) {
                    lastException = e;
                    System.err.println("Attempt " + attempt + " failed: " + e.getMessage());
                    
                    if (attempt < MAX_RETRIES) {
                        try {
                            Thread.sleep(RETRY_DELAY_MS * attempt); // Exponential backoff
                        } catch (InterruptedException ie) {
                            Thread.currentThread().interrupt();
                            throw new OperationException("Operation interrupted", ie);
                        }
                    }
                }
            }
            
            throw new OperationException(
                "Operation failed after " + MAX_RETRIES + " attempts: " + operationName, 
                lastException);
        }
        
        // Usage example
        public String fetchDataWithRetry(String url) throws OperationException {
            return executeWithRetry(() -> {
                // Simulate network operation that might fail
                if (Math.random() < 0.7) { // 70% failure rate
                    throw new RuntimeException("Network timeout");
                }
                return "Data from " + url;
            }, "fetch data from " + url);
        }
    }
    
    // 4. Circuit Breaker Pattern
    public static class CircuitBreakerPattern {
        private enum State { CLOSED, OPEN, HALF_OPEN }
        
        private State state = State.CLOSED;
        private int failureCount = 0;
        private long lastFailureTime = 0;
        private final int failureThreshold = 5;
        private final long timeoutDuration = 60000; // 1 minute
        
        public <T> T execute(Supplier<T> operation, String operationName) 
                throws CircuitBreakerException {
            
            if (state == State.OPEN) {
                if (System.currentTimeMillis() - lastFailureTime > timeoutDuration) {
                    state = State.HALF_OPEN;
                    System.out.println("Circuit breaker transitioning to HALF_OPEN");
                } else {
                    throw new CircuitBreakerException("Circuit breaker is OPEN for " + operationName);
                }
            }
            
            try {
                T result = operation.get();
                
                if (state == State.HALF_OPEN) {
                    state = State.CLOSED;
                    failureCount = 0;
                    System.out.println("Circuit breaker reset to CLOSED");
                }
                
                return result;
                
            } catch (Exception e) {
                failureCount++;
                lastFailureTime = System.currentTimeMillis();
                
                if (failureCount >= failureThreshold) {
                    state = State.OPEN;
                    System.out.println("Circuit breaker opened due to failures");
                }
                
                throw new CircuitBreakerException("Operation failed: " + operationName, e);
            }
        }
    }
    
    // Custom Exception Classes
    public static class BusinessException extends Exception {
        public BusinessException(String message, Throwable cause) {
            super(message, cause);
        }
    }
    
    public static class ValidationException extends Exception {
        public ValidationException(String message) {
            super(message);
        }
    }
    
    public static class ProcessingException extends Exception {
        public ProcessingException(String message) {
            super(message);
        }
    }
    
    public static class PersistenceException extends Exception {
        public PersistenceException(String message) {
            super(message);
        }
    }
    
    public static class OperationException extends Exception {
        public OperationException(String message, Throwable cause) {
            super(message, cause);
        }
    }
    
    public static class CircuitBreakerException extends Exception {
        public CircuitBreakerException(String message) {
            super(message);
        }
        
        public CircuitBreakerException(String message, Throwable cause) {
            super(message, cause);
        }
    }
    
    // Demonstration
    public static void main(String[] args) {
        // Test Exception Translation Pattern
        ExceptionTranslationPattern translator = new ExceptionTranslationPattern();
        try {
            translator.processBusinessData("corrupt data");
        } catch (BusinessException e) {
            System.err.println("Business error: " + e.getMessage());
            System.err.println("Root cause: " + e.getCause().getClass().getSimpleName());
        }
        
        // Test Retry Pattern
        RetryPattern retryPattern = new RetryPattern();
        try {
            String result = retryPattern.fetchDataWithRetry("http://api.example.com/data");
            System.out.println("Successfully fetched: " + result);
        } catch (OperationException e) {
            System.err.println("Retry pattern failed: " + e.getMessage());
        }
        
        // Test Circuit Breaker Pattern
        CircuitBreakerPattern circuitBreaker = new CircuitBreakerPattern();
        for (int i = 0; i < 10; i++) {
            try {
                String result = circuitBreaker.execute(() -> {
                    if (Math.random() < 0.8) { // 80% failure rate to trigger circuit breaker
                        throw new RuntimeException("Service unavailable");
                    }
                    return "Success";
                }, "external service call");
                
                System.out.println("Call " + i + " succeeded: " + result);
                
            } catch (CircuitBreakerException e) {
                System.err.println("Call " + i + " failed: " + e.getMessage());
            }
        }
    }
}
```

Functional Programming and Exception Handling:
═══════════════════════════════════════════

Modern Java applications often use functional programming patterns. Here's how to handle exceptions in functional contexts.

Example 4: Functional Exception Handling
─────────────────────────────────────────────

import java.util.*;
import java.util.function.*;
import java.util.stream.*;

public class FunctionalExceptionHandling {
    
    // Functional interface that can throw exceptions
    @FunctionalInterface
    public interface CheckedFunction<T, R> {
        R apply(T t) throws Exception;
    }
    
    @FunctionalInterface
    public interface CheckedConsumer<T> {
        void accept(T t) throws Exception;
    }
    
    // Utility class for handling exceptions in streams
    public static class Exceptions {
        
        // Convert checked function to unchecked
        public static <T, R> Function<T, R> unchecked(CheckedFunction<T, R> checkedFunction) {
            return t -> {
                try {
                    return checkedFunction.apply(t);
                } catch (Exception e) {
                    throw new RuntimeException(e);
                }
            };
        }
        
        // Convert checked consumer to unchecked
        public static <T> Consumer<T> unchecked(CheckedConsumer<T> checkedConsumer) {
            return t -> {
                try {
                    checkedConsumer.accept(t);
                } catch (Exception e) {
                    throw new RuntimeException(e);
                }
            };
        }
        
        // Handle exceptions with a default value
        public static <T, R> Function<T, R> withDefault(CheckedFunction<T, R> function, R defaultValue) {
            return t -> {
                try {
                    return function.apply(t);
                } catch (Exception e) {
                    System.err.println("Error processing " + t + ": " + e.getMessage());
                    return defaultValue;
                }
            };
        }
        
        // Handle exceptions by filtering out failures
        public static <T, R> Function<T, Optional<R>> safely(CheckedFunction<T, R> function) {
            return t -> {
                try {
                    return Optional.of(function.apply(t));
                } catch (Exception e) {
                    System.err.println("Error processing " + t + ": " + e.getMessage());
                    return Optional.empty();
                }
            };
        }
    }
    
    // Result type for functional error handling
    public static class Result<T> {
        private final T value;
        private final Exception error;
        private final boolean success;
        
        private Result(T value, Exception error, boolean success) {
            this.value = value;
            this.error = error;
            this.success = success;
        }
        
        public static <T> Result<T> success(T value) {
            return new Result<>(value, null, true);
        }
        
        public static <T> Result<T> failure(Exception error) {
            return new Result<>(null, error, false);
        }
        
        public boolean isSuccess() {
            return success;
        }
        
        public T getValue() {
            if (!success) {
                throw new RuntimeException("Cannot get value from failed result", error);
            }
            return value;
        }
        
        public Exception getError() {
            return error;
        }
        
        public <R> Result<R> map(Function<T, R> mapper) {
            if (success) {
                try {
                    return Result.success(mapper.apply(value));
                } catch (Exception e) {
                    return Result.failure(e);
                }
            } else {
                return Result.failure(error);
            }
        }
        
        public <R> Result<R> flatMap(Function<T, Result<R>> mapper) {
            if (success) {
                try {
                    return mapper.apply(value);
                } catch (Exception e) {
                    return Result.failure(e);
                }
            } else {
                return Result.failure(error);
            }
        }
        
        public T orElse(T defaultValue) {
            return success ? value : defaultValue;
        }
        
        public T orElseGet(Supplier<T> supplier) {
            return success ? value : supplier.get();
        }
        
        public void ifSuccess(Consumer<T> action) {
            if (success) {
                action.accept(value);
            }
        }
        
        public void ifFailure(Consumer<Exception> action) {
            if (!success) {
                action.accept(error);
            }
        }
    }
    
    // Practical examples
    public static void demonstrateFunctionalExceptionHandling() {
        List<String> numbers = Arrays.asList("1", "2", "invalid", "4", "5", "bad");
        
        System.out.println("=== Unchecked Exception Handling ===");
        // Using unchecked wrapper - will throw RuntimeException on invalid input
        try {
            List<Integer> parsed = numbers.stream()
                .map(Exceptions.unchecked(Integer::parseInt))
                .collect(Collectors.toList());
            System.out.println("Parsed numbers: " + parsed);
        } catch (RuntimeException e) {
            System.err.println("Stream failed: " + e.getCause().getMessage());
        }
        
        System.out.println("\n=== Default Value Handling ===");
        // Using default value for errors
        List<Integer> parsedWithDefaults = numbers.stream()
            .map(Exceptions.withDefault(Integer::parseInt, -1))
            .collect(Collectors.toList());
        System.out.println("Parsed with defaults: " + parsedWithDefaults);
        
        System.out.println("\n=== Safe Handling with Optional ===");
        // Using Optional to filter out failures
        List<Integer> safelyParsed = numbers.stream()
            .map(Exceptions.safely(Integer::parseInt))
            .filter(Optional::isPresent)
            .map(Optional::get)
            .collect(Collectors.toList());
        System.out.println("Safely parsed: " + safelyParsed);
        
        System.out.println("\n=== Result Type Handling ===");
        // Using Result type for comprehensive error handling
        List<Result<Integer>> results = numbers.stream()
            .map(s -> {
                try {
                    return Result.success(Integer.parseInt(s));
                } catch (NumberFormatException e) {
                    return Result.failure(e);
                }
            })
            .collect(Collectors.toList());
        
        // Process successful results
        List<Integer> successfulResults = results.stream()
            .filter(Result::isSuccess)
            .map(Result::getValue)
            .collect(Collectors.toList());
        System.out.println("Successful results: " + successfulResults);
        
        // Process failures
        List<String> failureMessages = results.stream()
            .filter(r -> !r.isSuccess())
            .map(r -> r.getError().getMessage())
            .collect(Collectors.toList());
        System.out.println("Failure messages: " + failureMessages);
        
        // Chain operations with Result
        System.out.println("\n=== Result Chaining ===");
        Result<String> chainedResult = Result.success("42")
            .map(Integer::parseInt)
            .map(i -> i * 2)
            .map(i -> "Result: " + i);
        
        chainedResult.ifSuccess(System.out::println);
        chainedResult.ifFailure(e -> System.err.println("Chain failed: " + e.getMessage()));
    }
    
    public static void main(String[] args) {
        demonstrateFunctionalExceptionHandling();
    }
}
```

Exception Testing and Validation:
═══════════════════════════════════════════

Testing exception scenarios is crucial for robust applications.

Example 5: Exception Testing Patterns
─────────────────────────────────────────────

import java.util.*;

public class ExceptionTestingPatterns {
    
    // Service class to test
    public static class CalculatorService {
        
        public double divide(double dividend, double divisor) {
            if (divisor == 0) {
                throw new IllegalArgumentException("Division by zero is not allowed");
            }
            return dividend / divisor;
        }
        
        public int factorial(int n) {
            if (n < 0) {
                throw new IllegalArgumentException("Factorial is not defined for negative numbers");
            }
            if (n > 20) {
                throw new IllegalStateException("Factorial too large to compute");
            }
            
            int result = 1;
            for (int i = 2; i <= n; i++) {
                result *= i;
            }
            return result;
        }
        
        public List<Integer> processNumbers(List<Integer> numbers) {
            if (numbers == null) {
                throw new IllegalArgumentException("Input list cannot be null");
            }
            
            List<Integer> result = new ArrayList<>();
            for (Integer num : numbers) {
                if (num == null) {
                    throw new IllegalArgumentException("List cannot contain null values");
                }
                if (num < 0) {
                    throw new IllegalStateException("Negative numbers not supported");
                }
                result.add(num * 2);
            }
            return result;
        }
    }
    
    // Exception testing utility
    public static class ExceptionTester {
        
        // Test that an exception is thrown
        public static <T extends Exception> void assertThrows(
                Class<T> expectedType, 
                Runnable code, 
                String testDescription) {
            
            try {
                code.run();
                System.err.println("FAIL: " + testDescription + " - Expected " + 
                    expectedType.getSimpleName() + " but no exception was thrown");
            } catch (Exception e) {
                if (expectedType.isInstance(e)) {
                    System.out.println("PASS: " + testDescription + " - Correctly threw " + 
                        expectedType.getSimpleName() + ": " + e.getMessage());
                } else {
                    System.err.println("FAIL: " + testDescription + " - Expected " + 
                        expectedType.getSimpleName() + " but got " + 
                        e.getClass().getSimpleName() + ": " + e.getMessage());
                }
            }
        }
        
        // Test that no exception is thrown
        public static void assertNoException(Runnable code, String testDescription) {
            try {
                code.run();
                System.out.println("PASS: " + testDescription + " - No exception thrown");
            } catch (Exception e) {
                System.err.println("FAIL: " + testDescription + " - Unexpected exception: " + 
                    e.getClass().getSimpleName() + ": " + e.getMessage());
            }
        }
        
        // Test specific exception message
        public static <T extends Exception> void assertThrowsWithMessage(
                Class<T> expectedType,
                String expectedMessage,
                Runnable code,
                String testDescription) {
            
            try {
                code.run();
                System.err.println("FAIL: " + testDescription + " - Expected exception but none was thrown");
            } catch (Exception e) {
                if (expectedType.isInstance(e)) {
                    if (e.getMessage().contains(expectedMessage)) {
                        System.out.println("PASS: " + testDescription + " - Correct exception and message");
                    } else {
                        System.err.println("FAIL: " + testDescription + " - Correct exception type but wrong message. " +
                            "Expected: '" + expectedMessage + "', Got: '" + e.getMessage() + "'");
                    }
                } else {
                    System.err.println("FAIL: " + testDescription + " - Wrong exception type. " +
                        "Expected: " + expectedType.getSimpleName() + ", Got: " + e.getClass().getSimpleName());
                }
            }
        }
    }
    
    // Comprehensive exception tests
    public static void runExceptionTests() {
        CalculatorService calculator = new CalculatorService();
        
        System.out.println("=== Testing Division Method ===");
        
        // Test normal operation
        ExceptionTester.assertNoException(
            () -> calculator.divide(10, 2),
            "Normal division should not throw exception"
        );
        
        // Test division by zero
        ExceptionTester.assertThrows(
            IllegalArgumentException.class,
            () -> calculator.divide(10, 0),
            "Division by zero should throw IllegalArgumentException"
        );
        
        // Test exception message
        ExceptionTester.assertThrowsWithMessage(
            IllegalArgumentException.class,
            "Division by zero",
            () -> calculator.divide(5, 0),
            "Division by zero should have specific message"
        );
        
        System.out.println("\n=== Testing Factorial Method ===");
        
        // Test normal operation
        ExceptionTester.assertNoException(
            () -> calculator.factorial(5),
            "Normal factorial should not throw exception"
        );
        
        // Test negative input
        ExceptionTester.assertThrows(
            IllegalArgumentException.class,
            () -> calculator.factorial(-1),
            "Negative factorial should throw IllegalArgumentException"
        );
        
        // Test too large input
        ExceptionTester.assertThrows(
            IllegalStateException.class,
            () -> calculator.factorial(25),
            "Large factorial should throw IllegalStateException"
        );
        
        System.out.println("\n=== Testing ProcessNumbers Method ===");
        
        // Test normal operation
        ExceptionTester.assertNoException(
            () -> calculator.processNumbers(Arrays.asList(1, 2, 3)),
            "Normal list processing should not throw exception"
        );
        
        // Test null list
        ExceptionTester.assertThrows(
            IllegalArgumentException.class,
            () -> calculator.processNumbers(null),
            "Null list should throw IllegalArgumentException"
        );
        
        // Test list with null values
        ExceptionTester.assertThrows(
            IllegalArgumentException.class,
            () -> calculator.processNumbers(Arrays.asList(1, null, 3)),
            "List with null values should throw IllegalArgumentException"
        );
        
        // Test list with negative values
        ExceptionTester.assertThrows(
            IllegalStateException.class,
            () -> calculator.processNumbers(Arrays.asList(1, -2, 3)),
            "List with negative values should throw IllegalStateException"
        );
    }
    
    // Exception boundary testing
    public static void testExceptionBoundaries() {
        CalculatorService calculator = new CalculatorService();
        
        System.out.println("\n=== Boundary Testing ===");
        
        // Test edge cases for factorial
        ExceptionTester.assertNoException(
            () -> calculator.factorial(0),
            "Factorial of 0 should work (boundary case)"
        );
        
        ExceptionTester.assertNoException(
            () -> calculator.factorial(20),
            "Factorial of 20 should work (upper boundary)"
        );
        
        ExceptionTester.assertThrows(
            IllegalStateException.class,
            () -> calculator.factorial(21),
            "Factorial of 21 should fail (over boundary)"
        );
        
        // Test edge cases for division
        ExceptionTester.assertNoException(
            () -> calculator.divide(0, 1),
            "Zero divided by number should work"
        );
        
        ExceptionTester.assertNoException(
            () -> calculator.divide(Double.MAX_VALUE, 2),
            "Large number division should work"
        );
        
        ExceptionTester.assertNoException(
            () -> calculator.divide(1, Double.MIN_VALUE),
            "Division by very small number should work"
        );
    }
    
    public static void main(String[] args) {
        runExceptionTests();
        testExceptionBoundaries();
        
        System.out.println("\n=== Test Summary ===");
        System.out.println("Exception testing completed. Review output for any failures.");
    }
}
```

Performance Considerations in Exception Handling:
═══════════════════════════════════════════════

Exception handling has performance implications that should be considered in high-performance applications.

Example 6: Exception Performance Patterns
─────────────────────────────────────────────

public class ExceptionPerformancePatterns {
    
    // Performance-conscious exception handling
    public static class PerformanceOptimizedService {
        
        // Pre-created exceptions to avoid object creation overhead
        private static final IllegalArgumentException NEGATIVE_INPUT_EXCEPTION = 
            new IllegalArgumentException("Input cannot be negative");
        
        private static final IllegalStateException INVALID_STATE_EXCEPTION = 
            new IllegalStateException("Service is in invalid state");
        
        // Flag to control expensive validation
        private boolean strictValidation = false;
        
        // Fast path validation without exception creation
        public boolean isValidInput(int input) {
            return input >= 0 && input <= 1000;
        }
        
        // Performance-optimized method with early validation
        public int processInputOptimized(int input) {
            // Fast validation without exception overhead
            if (input < 0) {
                throw NEGATIVE_INPUT_EXCEPTION; // Reuse pre-created exception
            }
            
            if (strictValidation && input > 1000) {
                // Only create new exception when necessary
                throw new IllegalArgumentException("Input exceeds maximum allowed value: " + input);
            }
            
            return input * 2;
        }
        
        // Method that avoids exceptions for control flow
        public Result<Integer> processInputSafe(int input) {
            if (input < 0) {
                return Result.failure(new IllegalArgumentException("Input cannot be negative"));
            }
            
            if (input > 1000) {
                return Result.failure(new IllegalArgumentException("Input too large"));
            }
            
            return Result.success(input * 2);
        }
        
        // Batch processing with minimal exception overhead
        public List<Integer> processBatch(List<Integer> inputs) {
            List<Integer> results = new ArrayList<>();
            List<String> errors = new ArrayList<>();
            
            for (int i = 0; i < inputs.size(); i++) {
                Integer input = inputs.get(i);
                
                if (input == null) {
                    errors.add("Null input at index " + i);
                    continue;
                }
                
                if (input < 0) {
                    errors.add("Negative input at index " + i + ": " + input);
                    continue;
                }
                
                results.add(input * 2);
            }
            
            // Throw single exception with all errors if any validation failed
            if (!errors.isEmpty()) {
                throw new IllegalArgumentException("Batch processing failed: " + String.join(", ", errors));
            }
            
            return results;
        }
        
        public void setStrictValidation(boolean strict) {
            this.strictValidation = strict;
        }
    }
    
    // Result type for avoiding exceptions (from previous example)
    public static class Result<T> {
        private final T value;
        private final Exception error;
        private final boolean success;
        
        private Result(T value, Exception error, boolean success) {
            this.value = value;
            this.error = error;
            this.success = success;
        }
        
        public static <T> Result<T> success(T value) {
            return new Result<>(value, null, true);
        }
        
        public static <T> Result<T> failure(Exception error) {
            return new Result<>(null, error, false);
        }
        
        public boolean isSuccess() { return success; }
        public T getValue() { return value; }
        public Exception getError() { return error; }
    }
    
    // Performance benchmarking
    public static void performanceBenchmark() {
        PerformanceOptimizedService service = new PerformanceOptimizedService();
        int iterations = 100000;
        
        System.out.println("=== Exception Performance Benchmark ===");
        
        // Benchmark 1: Exception-based validation vs boolean validation
        long startTime = System.nanoTime();
        int exceptionCount = 0;
        
        for (int i = 0; i < iterations; i++) {
            try {
                service.processInputOptimized(i % 50 - 25); // Some negative values
            } catch (IllegalArgumentException e) {
                exceptionCount++;
            }
        }
        
        long exceptionTime = System.nanoTime() - startTime;
        System.out.println("Exception-based validation: " + (exceptionTime / 1_000_000) + " ms, " + 
                          exceptionCount + " exceptions thrown");
        
        // Benchmark 2: Result-based validation (no exceptions)
        startTime = System.nanoTime();
        int failureCount = 0;
        
        for (int i = 0; i < iterations; i++) {
            Result<Integer> result = service.processInputSafe(i % 50 - 25);
            if (!result.isSuccess()) {
                failureCount++;
            }
        }
        
        long resultTime = System.nanoTime() - startTime;
        System.out.println("Result-based validation: " + (resultTime / 1_000_000) + " ms, " + 
                          failureCount + " failures handled");
        
        // Benchmark 3: Pre-validation to avoid exceptions
        startTime = System.nanoTime();
        int processedCount = 0;
        
        for (int i = 0; i < iterations; i++) {
            int input = i % 50 - 25;
            if (service.isValidInput(input)) {
                service.processInputOptimized(input);
                processedCount++;
            }
        }
        
        long preValidationTime = System.nanoTime() - startTime;
        System.out.println("Pre-validation approach: " + (preValidationTime / 1_000_000) + " ms, " + 
                          processedCount + " items processed");
        
        System.out.println("\nPerformance Summary:");
        System.out.println("Result-based is " + ((double) exceptionTime / resultTime) + "x faster than exception-based");
        System.out.println("Pre-validation is " + ((double) exceptionTime / preValidationTime) + "x faster than exception-based");
    }
    
    // Memory-conscious exception handling
    public static void memoryOptimizedExceptionHandling() {
        System.out.println("\n=== Memory-Optimized Exception Handling ===");
        
        // Example of pooling exceptions for frequently thrown scenarios
        class ExceptionPool {
            private static final Map<String, RuntimeException> cachedExceptions = new HashMap<>();
            
            static {
                cachedExceptions.put("NULL_INPUT", new IllegalArgumentException("Input cannot be null"));
                cachedExceptions.put("EMPTY_INPUT", new IllegalArgumentException("Input cannot be empty"));
                cachedExceptions.put("INVALID_FORMAT", new IllegalArgumentException("Invalid input format"));
            }
            
            public static RuntimeException get(String key) {
                RuntimeException cached = cachedExceptions.get(key);
                if (cached != null) {
                    return cached;
                }
                // Fallback to new exception if not cached
                return new RuntimeException("Unknown error: " + key);
            }
        }
        
        // Usage of exception pooling
        String[] testInputs = {null, "", "invalid", "valid"};
        
        for (String input : testInputs) {
            try {
                if (input == null) {
                    throw ExceptionPool.get("NULL_INPUT");
                }
                if (input.isEmpty()) {
                    throw ExceptionPool.get("EMPTY_INPUT");
                }
                if ("invalid".equals(input)) {
                    throw ExceptionPool.get("INVALID_FORMAT");
                }
                
                System.out.println("Processed: " + input);
                
            } catch (RuntimeException e) {
                System.out.println("Caught cached exception: " + e.getMessage());
            }
        }
    }
    
    public static void main(String[] args) {
        performanceBenchmark();
        memoryOptimizedExceptionHandling();
        
        System.out.println("\n=== Performance Guidelines ===");
        System.out.println("1. Avoid using exceptions for normal control flow");
        System.out.println("2. Use pre-validation when possible to avoid exception creation");
        System.out.println("3. Consider Result types for operations that frequently fail");
        System.out.println("4. Cache commonly thrown exceptions in performance-critical code");
        System.out.println("5. Batch validation to reduce exception overhead");
        System.out.println("6. Profile exception-heavy code paths in your application");
    }
}
```

**Summary of Advanced Exception Handling Concepts:**

1. **Exception Chaining**: Preserve context while translating exceptions across layers
2. **Try-with-Resources**: Automatic resource management with proper exception handling
3. **Design Patterns**: Structured approaches to exception handling in complex systems
4. **Functional Programming**: Integration of exception handling with modern Java features
5. **Testing Strategies**: Comprehensive testing of exception scenarios
6. **Performance Optimization**: Balancing robustness with performance requirements

These advanced concepts enable the development of robust, maintainable, and efficient Java applications with sophisticated error handling capabilities.

User Defined Exceptions (Custom Exceptions):
─────────────────────────────────────────────

User-defined exceptions, also known as custom exceptions, are exception classes created by developers to handle specific error conditions that are unique to their applications. These exceptions provide more meaningful error information and enable better error handling strategies tailored to specific business logic requirements.

What are User Defined Exceptions?
═══════════════════════════════════════════

**Definition:**
- Custom exception classes created by extending existing exception classes
- Designed to represent specific error conditions in your application domain
- Provide more meaningful and context-specific error information
- Enable fine-grained exception handling for different business scenarios

**Key Benefits:**
- **Domain-Specific**: Represent errors specific to your application's business logic
- **Meaningful Names**: Self-documenting exception names that clearly indicate the problem
- **Enhanced Information**: Can include additional data relevant to the specific error
- **Better Debugging**: Easier to identify and fix issues with specific exception types
- **Cleaner Code**: More readable exception handling with domain-specific exception types

Basic Custom Exception Creation:
═══════════════════════════════════════════

**Exception Class Hierarchy:**
```
Throwable
├── Error (system errors)
└── Exception
    ├── RuntimeException (unchecked exceptions)
    │   ├── NullPointerException
    │   ├── IllegalArgumentException
    │   └── Your Custom Runtime Exceptions
    └── Checked Exceptions
        ├── IOException
        ├── SQLException
        └── Your Custom Checked Exceptions
```

Example 1: Basic Custom Exception Classes
─────────────────────────────────────────────

```java
// Custom checked exception
class InsufficientFundsException extends Exception {
    private double requestedAmount;
    private double availableBalance;
    
    // Default constructor
    public InsufficientFundsException() {
        super("Insufficient funds in account");
    }
    
    // Constructor with message
    public InsufficientFundsException(String message) {
        super(message);
    }
    
    // Constructor with detailed information
    public InsufficientFundsException(double requestedAmount, double availableBalance) {
        super(String.format("Insufficient funds: Requested %.2f, Available %.2f", 
              requestedAmount, availableBalance));
        this.requestedAmount = requestedAmount;
        this.availableBalance = availableBalance;
    }
    
    // Constructor with message and cause
    public InsufficientFundsException(String message, Throwable cause) {
        super(message, cause);
    }
    
    // Getters for additional information
    public double getRequestedAmount() { return requestedAmount; }
    public double getAvailableBalance() { return availableBalance; }
    public double getShortfall() { return requestedAmount - availableBalance; }
}

// Custom unchecked exception
class InvalidAccountNumberException extends RuntimeException {
    private String accountNumber;
    private String validationRule;
    
    public InvalidAccountNumberException(String accountNumber) {
        super("Invalid account number: " + accountNumber);
        this.accountNumber = accountNumber;
    }
    
    public InvalidAccountNumberException(String accountNumber, String validationRule) {
        super(String.format("Invalid account number '%s': %s", accountNumber, validationRule));
        this.accountNumber = accountNumber;
        this.validationRule = validationRule;
    }
    
    public String getAccountNumber() { return accountNumber; }
    public String getValidationRule() { return validationRule; }
}

// Usage example
public class BankingSystemExample {
    
    public static class BankAccount {
        private String accountNumber;
        private double balance;
        
        public BankAccount(String accountNumber, double initialBalance) {
            validateAccountNumber(accountNumber);
            this.accountNumber = accountNumber;
            this.balance = initialBalance;
        }
        
        private void validateAccountNumber(String accountNumber) {
            if (accountNumber == null || accountNumber.trim().isEmpty()) {
                throw new InvalidAccountNumberException(accountNumber, "Account number cannot be null or empty");
            }
            
            if (accountNumber.length() != 10) {
                throw new InvalidAccountNumberException(accountNumber, "Account number must be exactly 10 digits");
            }
            
            if (!accountNumber.matches("\\d{10}")) {
                throw new InvalidAccountNumberException(accountNumber, "Account number must contain only digits");
            }
        }
        
        public void withdraw(double amount) throws InsufficientFundsException {
            if (amount <= 0) {
                throw new IllegalArgumentException("Withdrawal amount must be positive");
            }
            
            if (amount > balance) {
                throw new InsufficientFundsException(amount, balance);
            }
            
            balance -= amount;
            System.out.println("Withdrawn: $" + amount + ", New balance: $" + balance);
        }
        
        public void deposit(double amount) {
            if (amount <= 0) {
                throw new IllegalArgumentException("Deposit amount must be positive");
            }
            
            balance += amount;
            System.out.println("Deposited: $" + amount + ", New balance: $" + balance);
        }
        
        public double getBalance() { return balance; }
        public String getAccountNumber() { return accountNumber; }
    }
    
    public static void main(String[] args) {
        try {
            // Test custom exception scenarios
            BankAccount account = new BankAccount("1234567890", 100.0);
            
            // Normal operations
            account.deposit(50.0);
            account.withdraw(30.0);
            
            // This will throw InsufficientFundsException
            account.withdraw(200.0);
            
        } catch (InvalidAccountNumberException e) {
            System.err.println("Account validation error: " + e.getMessage());
            System.err.println("Invalid account: " + e.getAccountNumber());
            System.err.println("Validation rule: " + e.getValidationRule());
        } catch (InsufficientFundsException e) {
            System.err.println("Transaction failed: " + e.getMessage());
            System.err.println("Shortfall: $" + e.getShortfall());
        } catch (IllegalArgumentException e) {
            System.err.println("Invalid input: " + e.getMessage());
        }
        
        try {
            // Test invalid account number
            BankAccount invalidAccount = new BankAccount("123", 100.0);
        } catch (InvalidAccountNumberException e) {
            System.err.println("Account creation failed: " + e.getMessage());
        }
    }
}
```

Advanced Custom Exception Patterns:
═══════════════════════════════════════════

Example 2: Exception Hierarchy for Complex Domain
─────────────────────────────────────────────

```java
// Base business exception
abstract class BusinessException extends Exception {
    private final String errorCode;
    private final long timestamp;
    
    protected BusinessException(String errorCode, String message) {
        super(message);
        this.errorCode = errorCode;
        this.timestamp = System.currentTimeMillis();
    }
    
    protected BusinessException(String errorCode, String message, Throwable cause) {
        super(message, cause);
        this.errorCode = errorCode;
        this.timestamp = System.currentTimeMillis();
    }
    
    public String getErrorCode() { return errorCode; }
    public long getTimestamp() { return timestamp; }
    
    public abstract String getCategory();
    public abstract int getSeverityLevel(); // 1=Low, 2=Medium, 3=High, 4=Critical
}

// Validation exceptions
class ValidationException extends BusinessException {
    private final String fieldName;
    private final Object invalidValue;
    
    public ValidationException(String fieldName, Object invalidValue, String message) {
        super("VAL_001", message);
        this.fieldName = fieldName;
        this.invalidValue = invalidValue;
    }
    
    @Override
    public String getCategory() { return "VALIDATION"; }
    
    @Override
    public int getSeverityLevel() { return 2; }
    
    public String getFieldName() { return fieldName; }
    public Object getInvalidValue() { return invalidValue; }
}

// Authentication exceptions
class AuthenticationException extends BusinessException {
    private final String username;
    private final String authenticationMethod;
    
    public AuthenticationException(String username, String authenticationMethod, String message) {
        super("AUTH_001", message);
        this.username = username;
        this.authenticationMethod = authenticationMethod;
    }
    
    @Override
    public String getCategory() { return "AUTHENTICATION"; }
    
    @Override
    public int getSeverityLevel() { return 3; }
    
    public String getUsername() { return username; }
    public String getAuthenticationMethod() { return authenticationMethod; }
}

// Authorization exceptions
class AuthorizationException extends BusinessException {
    private final String username;
    private final String requiredPermission;
    private final String resource;
    
    public AuthorizationException(String username, String requiredPermission, String resource) {
        super("AUTHZ_001", 
              String.format("User '%s' lacks permission '%s' for resource '%s'", 
                          username, requiredPermission, resource));
        this.username = username;
        this.requiredPermission = requiredPermission;
        this.resource = resource;
    }
    
    @Override
    public String getCategory() { return "AUTHORIZATION"; }
    
    @Override
    public int getSeverityLevel() { return 3; }
    
    public String getUsername() { return username; }
    public String getRequiredPermission() { return requiredPermission; }
    public String getResource() { return resource; }
}

// Business rule exceptions
class BusinessRuleException extends BusinessException {
    private final String ruleName;
    private final Map<String, Object> context;
    
    public BusinessRuleException(String ruleName, String message, Map<String, Object> context) {
        super("BUS_001", message);
        this.ruleName = ruleName;
        this.context = new HashMap<>(context);
    }
    
    @Override
    public String getCategory() { return "BUSINESS_RULE"; }
    
    @Override
    public int getSeverityLevel() { return 2; }
    
    public String getRuleName() { return ruleName; }
    public Map<String, Object> getContext() { return new HashMap<>(context); }
}

// Data access exceptions
class DataAccessException extends BusinessException {
    private final String operation;
    private final String entityType;
    private final Object entityId;
    
    public DataAccessException(String operation, String entityType, Object entityId, String message, Throwable cause) {
        super("DATA_001", message, cause);
        this.operation = operation;
        this.entityType = entityType;
        this.entityId = entityId;
    }
    
    @Override
    public String getCategory() { return "DATA_ACCESS"; }
    
    @Override
    public int getSeverityLevel() { return 3; }
    
    public String getOperation() { return operation; }
    public String getEntityType() { return entityType; }
    public Object getEntityId() { return entityId; }
}
```

Example 3: Exception Builder Pattern
─────────────────────────────────────────────

```java
// Custom exception with builder pattern for complex construction
class ApplicationException extends Exception {
    private final String errorCode;
    private final String category;
    private final int severityLevel;
    private final Map<String, Object> metadata;
    private final long timestamp;
    private final String userMessage;
    private final String technicalMessage;
    
    private ApplicationException(Builder builder) {
        super(builder.technicalMessage, builder.cause);
        this.errorCode = builder.errorCode;
        this.category = builder.category;
        this.severityLevel = builder.severityLevel;
        this.metadata = new HashMap<>(builder.metadata);
        this.timestamp = builder.timestamp;
        this.userMessage = builder.userMessage;
        this.technicalMessage = builder.technicalMessage;
    }
    
    // Getters
    public String getErrorCode() { return errorCode; }
    public String getCategory() { return category; }
    public int getSeverityLevel() { return severityLevel; }
    public Map<String, Object> getMetadata() { return new HashMap<>(metadata); }
    public long getTimestamp() { return timestamp; }
    public String getUserMessage() { return userMessage; }
    public String getTechnicalMessage() { return technicalMessage; }
    
    // Builder class
    public static class Builder {
        private String errorCode;
        private String category;
        private int severityLevel = 2; // default medium severity
        private Map<String, Object> metadata = new HashMap<>();
        private long timestamp = System.currentTimeMillis();
        private String userMessage;
        private String technicalMessage;
        private Throwable cause;
        
        public Builder errorCode(String errorCode) {
            this.errorCode = errorCode;
            return this;
        }
        
        public Builder category(String category) {
            this.category = category;
            return this;
        }
        
        public Builder severityLevel(int severityLevel) {
            this.severityLevel = severityLevel;
            return this;
        }
        
        public Builder addMetadata(String key, Object value) {
            this.metadata.put(key, value);
            return this;
        }
        
        public Builder metadata(Map<String, Object> metadata) {
            this.metadata = new HashMap<>(metadata);
            return this;
        }
        
        public Builder timestamp(long timestamp) {
            this.timestamp = timestamp;
            return this;
        }
        
        public Builder userMessage(String userMessage) {
            this.userMessage = userMessage;
            return this;
        }
        
        public Builder technicalMessage(String technicalMessage) {
            this.technicalMessage = technicalMessage;
            return this;
        }
        
        public Builder cause(Throwable cause) {
            this.cause = cause;
            return this;
        }
        
        public ApplicationException build() {
            // Validation
            if (errorCode == null || errorCode.trim().isEmpty()) {
                throw new IllegalArgumentException("Error code is required");
            }
            if (technicalMessage == null || technicalMessage.trim().isEmpty()) {
                throw new IllegalArgumentException("Technical message is required");
            }
            
            return new ApplicationException(this);
        }
    }
    
    // Static factory methods for common scenarios
    public static ApplicationException validationError(String fieldName, Object value, String message) {
        return new Builder()
            .errorCode("VAL_001")
            .category("VALIDATION")
            .severityLevel(2)
            .userMessage("Please check your input and try again")
            .technicalMessage(message)
            .addMetadata("fieldName", fieldName)
            .addMetadata("invalidValue", value)
            .build();
    }
    
    public static ApplicationException authenticationError(String username, String method) {
        return new Builder()
            .errorCode("AUTH_001")
            .category("AUTHENTICATION")
            .severityLevel(3)
            .userMessage("Authentication failed. Please check your credentials")
            .technicalMessage("Authentication failed for user: " + username)
            .addMetadata("username", username)
            .addMetadata("authMethod", method)
            .build();
    }
    
    public static ApplicationException systemError(String operation, Throwable cause) {
        return new Builder()
            .errorCode("SYS_001")
            .category("SYSTEM")
            .severityLevel(4)
            .userMessage("A system error occurred. Please try again later")
            .technicalMessage("System error during operation: " + operation)
            .cause(cause)
            .addMetadata("operation", operation)
            .build();
    }
}

// Usage example
public class ExceptionBuilderExample {
    public static void validateUser(String username, String email, int age) throws ApplicationException {
        if (username == null || username.trim().isEmpty()) {
            throw ApplicationException.validationError("username", username, "Username cannot be empty");
        }
        
        if (email == null || !email.contains("@")) {
            throw ApplicationException.validationError("email", email, "Invalid email format");
        }
        
        if (age < 0 || age > 150) {
            throw ApplicationException.validationError("age", age, "Age must be between 0 and 150");
        }
    }
    
    public static void authenticateUser(String username, String password) throws ApplicationException {
        // Simulate authentication logic
        if (!"validUser".equals(username) || !"validPassword".equals(password)) {
            throw ApplicationException.authenticationError(username, "password");
        }
    }
    
    public static void performDatabaseOperation() throws ApplicationException {
        try {
            // Simulate database operation that fails
            throw new SQLException("Connection timeout");
        } catch (SQLException e) {
            throw ApplicationException.systemError("database_save_user", e);
        }
    }
    
    public static void main(String[] args) {
        // Test validation exception
        try {
            validateUser("", "invalid-email", -5);
        } catch (ApplicationException e) {
            System.err.println("Validation Error:");
            System.err.println("  Error Code: " + e.getErrorCode());
            System.err.println("  Category: " + e.getCategory());
            System.err.println("  User Message: " + e.getUserMessage());
            System.err.println("  Technical Message: " + e.getTechnicalMessage());
            System.err.println("  Metadata: " + e.getMetadata());
        }
        
        // Test authentication exception
        try {
            authenticateUser("invalidUser", "wrongPassword");
        } catch (ApplicationException e) {
            System.err.println("\nAuthentication Error:");
            System.err.println("  Error Code: " + e.getErrorCode());
            System.err.println("  Severity: " + e.getSeverityLevel());
            System.err.println("  User Message: " + e.getUserMessage());
        }
        
        // Test system exception
        try {
            performDatabaseOperation();
        } catch (ApplicationException e) {
            System.err.println("\nSystem Error:");
            System.err.println("  Error Code: " + e.getErrorCode());
            System.err.println("  Category: " + e.getCategory());
            System.err.println("  Severity: " + e.getSeverityLevel());
            System.err.println("  Cause: " + e.getCause().getClass().getSimpleName());
            System.err.println("  Cause Message: " + e.getCause().getMessage());
        }
    }
}
```

Exception Translation and Wrapping Patterns:
═══════════════════════════════════════════

Example 4: Exception Translation Layers
─────────────────────────────────────────────

```java
// Service layer exceptions
class ServiceException extends Exception {
    private final String serviceName;
    private final String operation;
    
    public ServiceException(String serviceName, String operation, String message, Throwable cause) {
        super(String.format("Service '%s' failed during '%s': %s", serviceName, operation, message), cause);
        this.serviceName = serviceName;
        this.operation = operation;
    }
    
    public String getServiceName() { return serviceName; }
    public String getOperation() { return operation; }
}

// Repository layer that translates low-level exceptions
class UserRepository {
    
    public void saveUser(User user) throws ServiceException {
        try {
            // Simulate database operation
            if (user.getUsername().equals("duplicate")) {
                throw new SQLException("Duplicate key violation", "23000", 1062);
            }
            if (user.getUsername().equals("timeout")) {
                throw new SQLException("Connection timeout", "08S01", 0);
            }
            // Successful save
            System.out.println("User saved: " + user.getUsername());
            
        } catch (SQLException e) {
            // Translate SQL exceptions to service exceptions
            if ("23000".equals(e.getSQLState())) {
                throw new ServiceException("UserRepository", "saveUser", 
                    "User with username '" + user.getUsername() + "' already exists", e);
            } else if ("08S01".equals(e.getSQLState())) {
                throw new ServiceException("UserRepository", "saveUser", 
                    "Database connection timeout", e);
            } else {
                throw new ServiceException("UserRepository", "saveUser", 
                    "Database operation failed", e);
            }
        }
    }
    
    public User findUser(String username) throws ServiceException {
        try {
            // Simulate file system operation
            if ("notfound".equals(username)) {
                throw new FileNotFoundException("User file not found: " + username + ".dat");
            }
            if ("accessdenied".equals(username)) {
                throw new IOException("Access denied to user file: " + username + ".dat");
            }
            
            return new User(username, username + "@example.com");
            
        } catch (FileNotFoundException e) {
            throw new ServiceException("UserRepository", "findUser", 
                "User '" + username + "' not found", e);
        } catch (IOException e) {
            throw new ServiceException("UserRepository", "findUser", 
                "Failed to access user data for '" + username + "'", e);
        }
    }
}

// Service layer that provides business-level exceptions
class UserService {
    private UserRepository repository = new UserRepository();
    
    public void registerUser(String username, String email) throws UserRegistrationException {
        try {
            // Validate input
            validateUserInput(username, email);
            
            // Create user
            User user = new User(username, email);
            
            // Save user (may throw ServiceException)
            repository.saveUser(user);
            
            System.out.println("User registered successfully: " + username);
            
        } catch (ValidationException e) {
            throw new UserRegistrationException("User validation failed", e);
        } catch (ServiceException e) {
            // Determine if this is a business error or system error
            if (e.getMessage().contains("already exists")) {
                throw new UserRegistrationException("Username '" + username + "' is already taken", e);
            } else {
                throw new UserRegistrationException("Registration failed due to system error", e);
            }
        }
    }
    
    public User getUser(String username) throws UserNotFoundException, SystemException {
        try {
            return repository.findUser(username);
        } catch (ServiceException e) {
            if (e.getMessage().contains("not found")) {
                throw new UserNotFoundException("User '" + username + "' does not exist", e);
            } else {
                throw new SystemException("Failed to retrieve user data", e);
            }
        }
    }
    
    private void validateUserInput(String username, String email) throws ValidationException {
        if (username == null || username.trim().isEmpty()) {
            throw new ValidationException("Username cannot be empty");
        }
        if (username.length() < 3) {
            throw new ValidationException("Username must be at least 3 characters long");
        }
        if (email == null || !email.contains("@")) {
            throw new ValidationException("Invalid email format");
        }
    }
}

// Business-level exception classes
class UserRegistrationException extends Exception {
    public UserRegistrationException(String message, Throwable cause) {
        super(message, cause);
    }
}

class UserNotFoundException extends Exception {
    public UserNotFoundException(String message, Throwable cause) {
        super(message, cause);
    }
}

class SystemException extends Exception {
    public SystemException(String message, Throwable cause) {
        super(message, cause);
    }
}

class ValidationException extends Exception {
    public ValidationException(String message) {
        super(message);
    }
}

// Simple User class
class User {
    private String username;
    private String email;
    
    public User(String username, String email) {
        this.username = username;
        this.email = email;
    }
    
    public String getUsername() { return username; }
    public String getEmail() { return email; }
}

// Application layer demonstrating exception handling
public class ExceptionTranslationExample {
    public static void main(String[] args) {
        UserService userService = new UserService();
        
        // Test successful registration
        try {
            userService.registerUser("john_doe", "john@example.com");
        } catch (UserRegistrationException e) {
            System.err.println("Registration failed: " + e.getMessage());
        }
        
        // Test duplicate user registration
        try {
            userService.registerUser("duplicate", "duplicate@example.com");
        } catch (UserRegistrationException e) {
            System.err.println("Registration failed: " + e.getMessage());
            System.err.println("Root cause: " + getRootCause(e).getClass().getSimpleName());
        }
        
        // Test database timeout
        try {
            userService.registerUser("timeout", "timeout@example.com");
        } catch (UserRegistrationException e) {
            System.err.println("Registration failed: " + e.getMessage());
            System.err.println("Root cause: " + getRootCause(e).getMessage());
        }
        
        // Test user lookup - not found
        try {
            User user = userService.getUser("notfound");
        } catch (UserNotFoundException e) {
            System.err.println("User lookup failed: " + e.getMessage());
        } catch (SystemException e) {
            System.err.println("System error during user lookup: " + e.getMessage());
        }
        
        // Test user lookup - access denied
        try {
            User user = userService.getUser("accessdenied");
        } catch (UserNotFoundException e) {
            System.err.println("User lookup failed: " + e.getMessage());
        } catch (SystemException e) {
            System.err.println("System error during user lookup: " + e.getMessage());
        }
        
        // Test validation error
        try {
            userService.registerUser("", "invalid");
        } catch (UserRegistrationException e) {
            System.err.println("Registration failed: " + e.getMessage());
            System.err.println("Root cause type: " + getRootCause(e).getClass().getSimpleName());
        }
    }
    
    // Utility method to find root cause
    private static Throwable getRootCause(Throwable throwable) {
        Throwable cause = throwable;
        while (cause.getCause() != null) {
            cause = cause.getCause();
        }
        return cause;
    }
}
```

Best Practices for Custom Exceptions:
═══════════════════════════════════════════

1. **Naming Conventions:**
```java
// Good naming - descriptive and follows convention
class InsufficientFundsException extends Exception { }
class InvalidAccountNumberException extends RuntimeException { }
class PaymentProcessingException extends Exception { }

// Poor naming - generic and unclear
class MyException extends Exception { }
class ErrorException extends Exception { }
class BadInputException extends Exception { }
```

2. **Exception Hierarchy Design:**
```java
// Well-designed hierarchy
abstract class BankingException extends Exception {
    protected BankingException(String message) { super(message); }
    protected BankingException(String message, Throwable cause) { super(message, cause); }
}

class AccountException extends BankingException {
    protected AccountException(String message) { super(message); }
    protected AccountException(String message, Throwable cause) { super(message, cause); }
}

class InsufficientFundsException extends AccountException {
    public InsufficientFundsException(double requested, double available) {
        super(String.format("Insufficient funds: requested=%.2f, available=%.2f", requested, available));
    }
}

class InvalidAccountException extends AccountException {
    public InvalidAccountException(String accountNumber) {
        super("Invalid account number: " + accountNumber);
    }
}
```

3. **Constructor Patterns:**
```java
class WellDesignedException extends Exception {
    private final String errorCode;
    private final Object context;
    
    // Default constructor
    public WellDesignedException() {
        this("DEFAULT_ERROR", "An error occurred", null, null);
    }
    
    // Message constructor
    public WellDesignedException(String message) {
        this("DEFAULT_ERROR", message, null, null);
    }
    
    // Message and cause constructor
    public WellDesignedException(String message, Throwable cause) {
        this("DEFAULT_ERROR", message, cause, null);
    }
    
    // Full constructor
    public WellDesignedException(String errorCode, String message, Throwable cause, Object context) {
        super(message, cause);
        this.errorCode = errorCode;
        this.context = context;
    }
    
    public String getErrorCode() { return errorCode; }
    public Object getContext() { return context; }
}
```

4. **Documentation and Usage:**
```java
/**
 * Thrown when a financial transaction cannot be completed due to insufficient funds.
 * 
 * This exception provides detailed information about the failed transaction,
 * including the requested amount, available balance, and account information.
 * 
 * @author Your Name
 * @version 1.0
 * @since 1.0
 */
public class InsufficientFundsException extends Exception {
    
    /**
     * Creates an exception for insufficient funds scenario.
     * 
     * @param requestedAmount the amount that was requested for withdrawal
     * @param availableBalance the current account balance
     * @param accountNumber the account number where the transaction was attempted
     * @throws IllegalArgumentException if any amount is negative
     */
    public InsufficientFundsException(double requestedAmount, double availableBalance, String accountNumber) {
        super(formatMessage(requestedAmount, availableBalance, accountNumber));
        
        if (requestedAmount < 0 || availableBalance < 0) {
            throw new IllegalArgumentException("Amounts cannot be negative");
        }
        
        this.requestedAmount = requestedAmount;
        this.availableBalance = availableBalance;
        this.accountNumber = accountNumber;
    }
    
    private static String formatMessage(double requested, double available, String account) {
        return String.format(
            "Insufficient funds in account %s: requested $%.2f, available $%.2f (shortfall: $%.2f)",
            account, requested, available, requested - available
        );
    }
    
    // Additional methods and fields...
}
```

**Summary - User Defined Exceptions:**

**Key Benefits:**
- **Domain Clarity**: Exception names clearly indicate what went wrong
- **Enhanced Information**: Can include specific data relevant to the error
- **Better Error Handling**: Enables precise catch blocks for different scenarios
- **Improved Debugging**: Easier to trace and fix specific types of errors
- **Code Documentation**: Self-documenting code through meaningful exception names

**Design Principles:**
- **Single Responsibility**: Each exception should represent one specific error condition
- **Hierarchy**: Use inheritance to create logical groupings of related exceptions
- **Immutability**: Exception objects should be immutable once created
- **Serialization**: Consider implementing Serializable for distributed applications
- **Performance**: Be mindful of exception creation overhead in performance-critical code

**Best Practices:**
- Extend appropriate base classes (Exception for checked, RuntimeException for unchecked)
- Provide multiple constructors for different use cases
- Include relevant context information in exception objects
- Use descriptive names that clearly indicate the error condition
- Document when and why exceptions are thrown
- Consider exception translation at architectural boundaries
- Don't use exceptions for normal control flow
- Preserve original exception information when wrapping

Custom exceptions are essential for building robust, maintainable Java applications that provide clear error information and enable sophisticated error handling strategies tailored to specific business requirements.
