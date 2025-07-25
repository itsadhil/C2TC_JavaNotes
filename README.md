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
