**Java Notes**

Java Terminologies  
- JDK (Java Development Kit): The complete toolkit for Java development. Includes the compiler (javac), libraries, and various tools required to build, debug, and run Java applications.  
- JVM (Java Virtual Machine): The engine that executes Java bytecode, enabling platform independence by abstracting the underlying hardware and OS.  
- JRE (Java Runtime Environment): Contains the JVM and core libraries needed to run Java applications, but not development tools.  
- ByteCode: The intermediate, platform-independent code generated after compilation. The JVM interprets and executes this code.

Running Java Programs Without Main Method  
- In older Java versions, programs could run using only static blocks, without a main method.  
- This approach is deprecated and unsupported in modern Java versions.  
- Today, every Java application must have a main method as the entry point.

Example: Static Blocks and Main Method  

```java
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
```

Static Block Execution Order  
- Static blocks execute in the order they appear in the class, before the main method.  
- Output sequence:  
	1. "Hello I am Static"  
	2. "I am Static block 2"  
	3. Main method output

Method Signature  
- A method signature includes:  
	- Method name  
	- Parameter types  
	- Modifiers (e.g., public, static)  
- It uniquely identifies a method for invocation and overloading.

Example: Multiple Main Methods  

```java
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
```

Main Method Execution  
- Only the main method with the signature:  
	public static void main(String[] args)  
is executed by the JVM as the program entry point.

Encapsulation in Java  
- Encapsulation wraps data (fields) and methods into a single unit (class).  
- Achieved by making fields private and providing public getter/setter methods.  
- Promotes data hiding, modularity, and maintainability.

Input Classes in Java  
- Scanner: Reads user input from various sources (keyboard, files).  
- BufferedReader: Efficiently reads text from character input streams.

Scanner Class  
- Used for reading input from the user.  
- Syntax:  
	Scanner input = new Scanner(System.in);

Common Scanner Methods  
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
- BufferedReader uses an internal buffer (default: 8192 characters) for efficient reading.  
- Example:  
	FileReader fr = new FileReader("filename.txt");  
	BufferedReader br = new BufferedReader(fr);

Constructors in Java  
- Special methods to initialize objects.  
- Same name as class, no return type.  
- Called automatically when an object is created.

Types:  
- Default Constructor: No parameters, provided by compiler if none defined.  
- Parameterized Constructor: Accepts parameters for custom initialization.

Restrictions:  
- Cannot be abstract, static, final, or synchronized.

Example:  
```java
public SampleDemo() { }
public SampleDemo(int x) { }
public SampleDemo(String name, int age) { }
```

Implicit vs Explicit Constructors  
- Implicit: Provided by compiler if none defined.  
- Explicit: Defined by programmer, can have parameters.

Inheritance from Object Class  
- Every Java class implicitly inherits from Object.  
- Object class provides:  
	- toString(): String representation.  
	- equals(Object obj): Equality check.  
	- hashCode(): Hash code.  
	- getClass(): Runtime class info.  
	- clone(): Copy object.  
	- finalize(): Called before destruction.  
- These methods can be overridden for custom behavior.

Constructor vs Methods  

| Feature        | Constructor                    | Method                        |
|----------------|-------------------------------|------------------------------|
| Purpose        | Initializes objects            | Defines behaviors/actions     |
| Name           | Same as class                 | Any name except class name   |
| Return Type    | None                         | Must have a return type       |
| Invocation     | Called automatically during object creation | Called explicitly via object |
| Inheritance    | Not inherited                | Inherited (unless private)    |
| Overloading    | Yes                         | Yes                          |
| Modifiers      | Cannot be abstract, static, final, synchronized | Can have these modifiers |

Example:

```java
// Constructor
public SampleDemo() { }
// Method
public void display() { }
```

Custom Data Structures  
- User-defined ways to organize and store data.  
- Examples:  
	- Linked List: Nodes pointing to next node.  
	- Stack: Last-In-First-Out (LIFO).  
	- Queue: First-In-First-Out (FIFO).  
	- Tree: Hierarchical nodes.  
	- Graph: Nodes connected by edges.

Example:

```java
class Node {
	int data;
	Node next;
}
```

Game Development in Java  
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

```java
while (gameRunning) {
	updateGameState();
	renderGraphics();
	handleInput();
}
```

Constructor Overloading  
- Multiple constructors with different parameter lists.  
- Allows flexible object creation.

Example:

```java
class SampleDemo {
	SampleDemo() { }
	SampleDemo(int x) { }
	SampleDemo(String name, int age) { }
}
```

Packages in Java  
- Packages organize related classes, interfaces, and sub-packages.  
- Prevent naming conflicts, improve modularity and maintainability.

Syntax:

```java
package packageName;
```

Example:

```java
package day1.basics;
```

- Built-in packages: java.util, java.io, java.lang, etc.  
- Import classes:

```java
import java.util.Scanner;
```

Example:

```java
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
```

Project Structure Example: ShoppingMall  

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

Common Built-in Java Packages  
- java.lang: Core language classes (String, Math, System, Object, etc.). Imported by default.  
- java.util: Utility classes (collections, Date, Scanner, Random, etc.).  
- java.io: Input/output classes (File, BufferedReader, InputStream, etc.).  
- java.net: Networking classes (Socket, URL, HttpURLConnection, etc.).  
- java.sql: Database connectivity (Connection, Statement, ResultSet, etc.).  
- java.awt: Abstract Window Toolkit for GUI programming.  
- javax.swing: GUI components (JFrame, JButton, etc.).

User-defined Packages  
- Created by developers to organize their own classes and interfaces.  
- Help structure large projects, avoid naming conflicts, and improve maintainability.

Syntax:

```java
package com.companyname.clientname.module;
```

Example:

```java
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
```

Example Package Structure  
- com.zoho.capgemini.stressreducerapp.entity  
- com.zoho.capgemini.stressreducerapp.utilities  
- com.zoho.capgemini.stressreducerapp.exceptions  
- com.zoho.capgemini.stressreducerapp.main  

Access Modifiers in Java  
- Control the visibility of classes, methods, and variables.

Types:

| Modifier   | Visibility                                         |
|------------|----------------------------------------------------|
| public     | Accessible from any other class.                   |
| protected  | Accessible within the same package and subclasses.|
| default    | Accessible only within the same package.           |
| private    | Accessible only within the same class.             |

Example:

```java
public int x;        // Accessible everywhere
protected int y;     // Accessible in package & subclasses
int z;               // Accessible in package (default)
private int w;       // Accessible only in this class
```

Private Access Modifier  
- Accessible only within the same class.  
- Not accessible from outside, including subclasses and other classes in the same package.  
- Used for encapsulation and data hiding.

Example:

```java
class Example {
	private int secret;
	private void showSecret() {
		System.out.println(secret);
	}
}
```

Default Access Modifier  
- No modifier specified.  
- Accessible only within the same package.

Example:

```java
class Example {
	int value; // default access
	void showValue() {
		System.out.println(value);
	}
}
```

Protected Access Modifier  
- Accessible within the same package and in subclasses (even in different packages).

Example:

```java
class Example {
	protected int number;
	protected void showNumber() {
		System.out.println(number);
	}
}
```

Public Access Modifier  
- Accessible from any other class, regardless of package.

Example:

```java
public class Example {
	public int data;
	public void showData() {
		System.out.println(data);
	}
}
```

Real-world Example: Encapsulation  
Suppose you are developing a banking application. Sensitive data like account balance and transaction history should be hidden from direct access. Use private fields and public methods for secure access.

Example:

```java
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
```

Multiple Inheritance in Java  
- Java does not support multiple inheritance (a class extending more than one class) to avoid ambiguity (diamond problem).  
- Instead, Java uses interfaces for multiple inheritance of type.

Example:

```java
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
```

Constructor Inheritance  
- Constructors are not inherited, but you can call a parent constructor using super().

Example:

```java
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
```

Constructor Modifiers  
- private: Allowed. Used for Singleton, utility, or factory patterns.  
- abstract: Not allowed. Constructors cannot be abstract.  
- final: Not allowed. Constructors cannot be final.

Accessing Base Class Variables  
- public: Accessible in derived class.  
- protected: Accessible in derived class (even in different packages).  
- default: Accessible only if derived class is in same package.  
- private: Not accessible directly in derived class.

Object Access from Main Program  
- You cannot directly access the object from the main program to the class. Use the `this` keyword to refer to the current object within the class.

Static Keyword  
The `static` keyword in Java is used to create elements that belong to the class itself rather than to instances (objects) of the class.

Static Variables  
- Shared across all instances of the class (class variables).  
- Only one copy exists, regardless of how many objects are created.  
- Accessed directly through the class name: ClassName.variableName.  
- Initialized when the class is loaded by the JVM.  
- Used mainly for memory management.

Example:

```java
class Example {
	static int counter = 0;
}
```

Static Methods  
- Belong to the class, not to objects.  
- Called through the class name: ClassName.methodName().  
- Cannot access non-static (instance) variables/methods directly.  
- Cannot use this or super keywords.  
- Cannot be overridden (only hidden in subclasses).

Example:

```java
class Example {
	static void show() {
		System.out.println("Static method");
	}
}
```

Static Blocks  
- Execute when the class is loaded.  
- Used to initialize static variables or perform one-time setup.  
- Multiple static blocks execute in the order they appear.

Example:

```java
class Example {
	static {
		System.out.println("Static block executed");
	}
}
```

Static Classes  
- Only nested classes can be static.  
- Static nested classes do not need an instance of the outer class.  
- Can only access static members of the outer class.

Example:

```java
class Outer {
	static class Inner {
		void display() {
			System.out.println("Static nested class");
		}
	}
}
```

Common Use Cases  
- Utility methods (e.g., Math.random(), Arrays.sort()).  
- Constants (e.g., Math.PI, Integer.MAX_VALUE).  
- Factory methods (e.g., getInstance()).  
- Counters and shared resources.  
- Main method (program entry point).

Features of Static Keyword  
- Can be applied to variables, methods, blocks, inner classes.  
- Members belong to the class, not to any specific object.  
- Static members are shared among all instances of the class.  
- Static methods cannot access non-static (instance) members directly.  
- Static blocks are executed when the class is loaded.  
- Static nested classes can access only static members of the outer class.

Can we overload the Static method?  
- Yes, you can overload static methods in Java by changing their parameter list.

Static vs Instance Member Table  

| Case                              | Instance | Static |
|----------------------------------|----------|--------|
| Invoke Instance Method            | ✔        |        |
| Access Instance Variable          | ✔        |        |
| Invoke Static Method              | ✔        | ✔      |
| Access Static Variable            | ✔        | ✔      |
| Invoke Instance from Static       |          | ❌     |
| Access Instance Variable from Static |      | ❌     |

Static Blocks in Java  
- Execute **once** when class is loaded  
- Run **before any instance** is created  
- Before main method  
- Run in order of appearance

Example:

```java
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
```

Output:

```
First static block
Second static block
Main method
```

Static blocks are ideal for one-time setups before the class is used.

Real-World Static Example: Flight Booking System  

```java
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
```

Final Keyword  
- Used with variables, methods, or classes to indicate unchangeability.  
- Final variable: Value cannot change after initialization.  
- Final method: Cannot be overridden.  
- Final class: Cannot be inherited.

Blank static final variable?  
- Can declare static final without initialization but must initialize inside static block.

Abstract Classes and Methods in Java  

Abstract Methods:  
- An abstract method is declared without body.  
- Can only be declared inside abstract class.  
- Subclasses must override abstract methods unless subclass is also abstract.

Abstract Classes:  
- Cannot instantiate directly.  
- May contain abstract and concrete methods.

Example: 

```java
abstract class Shape {
	abstract void draw();
}
```

Reference Assignments:  
- Abstract class reference can refer to objects of derived classes enabling polymorphism.

Example:

```java
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
		Animal a1 = new Dog();
		Animal a2 = new Cat();
		a1.sound(); // Woof!
		a2.sound(); // Meow!
	}
}
```

Summary Table

| Feature                   | Abstract Class         | Abstract Method          |
|---------------------------|-----------------------|-------------------------|
| Can be instantiated?      | No                    | N/A                     |
| Can have abstract methods? | Yes                   | Only in abstract classes|
| Can contain concrete methods? | Yes               | No                      |
| Used for                  | Inheritance, polymorphism | Force subclass implementation |

Polymorphism in Java  

Definition:  
- Ability of an object to take many forms.  
- Greek origin: poly = many, morph = forms.  
- Same functionality with different logic execution.

Types:  

1. Compile-Time Polymorphism (Method Overloading)  
2. Run-Time Polymorphism (Method Overriding)

Characteristics of Polymorphism

- Multiple forms for same method call.  
- Method overloading (compile time).  
- Method overriding (runtime).  
- Superclass references to subclass objects.  
- Supports abstraction and flexibility.

Advantages:  

- Code reusability.  
- Extensibility.  
- Flexibility.  
- Easier maintenance.  
- Improved readability.

Disadvantages:  

- Complexity.  
- Performance overhead at runtime.  
- Debugging difficulty.  
- Hidden behavior confusion.  
- Increased memory usage.  
- Possible misuse and overuse.  
- Limited compiler optimization.  
- Casting risks.  
- Design constraints if poorly designed.

Types of Polymorphism

| Type                   | Description                                  | Binding    |
|------------------------|----------------------------------------------|------------|
| Compile-Time Polymorphism | Method Overloading (same name, different parameters) | Compile Time |
| Run-Time Polymorphism   | Method Overriding (subclass provides implementation) | Run Time   |

Compile-Time Polymorphism (Static Polymorphism)  

- Method selected at compile time.  
- Achieved via method overloading.  
- Fast performance.

Example:

```java
class Printer {
	void print(int num) {
		System.out.println("Printing integer: " + num);
	}
	void print(String str) {
		System.out.println("Printing string: " + str);
	}
}

Printer p = new Printer();
p.print(100);       // print(int)
p.print("Hello");   // print(String)
```

Types of Overloading in Java  

1. **Method Overloading**: Same method name, different parameter lists.  
2. **Constructor Overloading**: Multiple constructors with different parameters.  
3. **Operator Overloading**: Not user-defined in Java (built-in only for String concatenation).

Example Method Overloading:

```java
class MathUtils {
	int add(int a, int b)           { return a + b; }
	double add(double a, double b)  { return a + b; }
	int add(int a, int b, int c)    { return a + b + c; }
}
```

Constructor Overloading Example:

```java
class Student {
	Student() {}
	Student(String name) {}
	Student(String name, int age) {}
}
```
