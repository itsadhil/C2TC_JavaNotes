# Java Notes

## Java Terminologies

- **JDK (Java Development Kit):** Toolkit for Java development. Includes the compiler (`javac`), libraries, and tools for building, debugging, and running Java applications.
- **JVM (Java Virtual Machine):** Executes Java bytecode, enabling platform independence by abstracting hardware and OS.
- **JRE (Java Runtime Environment):** Contains JVM and core libraries (not development tools).
- **ByteCode:** The platform-independent code generated after compilation; executed by JVM.

## Running Java Programs Without Main Method

- In older Java versions, you could run programs using only static blocks, without a main method.  
- This is deprecated and unsupported in modern Java.  
- Today, every Java application must have a `main` method.

## Example: Static Blocks and Main Method

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

**Static Block Execution Order:**
1. "Hello I am Static"
2. "I am Static block 2"
3. Main method output

## Method Signature

A method signature includes:
- Method name
- Parameter types
- Modifiers (e.g., public, static)

It uniquely identifies a method for invocation and overloading.

## Example: Multiple Main Methods

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

> Only the main method with this signature is executed:
```java
public static void main(String[] args)
```

## Encapsulation in Java

- Wrapping data (fields) and methods into a single unit (class)
- Achieved by marking fields `private` and providing public getter/setter methods
- Promotes data hiding, modularity, and maintainability

## Input Classes in Java

- **Scanner:** Reads user input from keyboard, files, etc.
- **BufferedReader:** Efficiently reads text from character input streams.

### Scanner Example

```java
Scanner input = new Scanner(System.in);
char c = input.next().charAt(0); // Gets first character
```

#### Common Scanner Methods

- `next()`: Reads a single word
- `nextLine()`: Reads a whole line
- `nextInt()`: Reads an integer
- `nextFloat()`: Reads a float
- `nextDouble()`: Reads a double

#### Other methods

- `hasNextDouble()`
- `hasNextInt()`
- `hasNextLine()`
- `hasNext()`

### BufferedReader Example

```java
FileReader fr = new FileReader("filename.txt");
BufferedReader br = new BufferedReader(fr);
```

## Constructors in Java

- Special methods with same name as class, no return type
- Called automatically when an object is created

Types:
- Default Constructor: No parameters, compiler provides if none defined
- Parameterized Constructor: Accepts custom parameters

Restrictions:
- Cannot be abstract, static, final, or synchronized

```java
public SampleDemo() { }
public SampleDemo(int x) { }
public SampleDemo(String name, int age) { }
```

### Implicit vs Explicit Constructors

- **Implicit:** Provided by compiler if none defined
- **Explicit:** Defined by programmer (can have parameters)

## Inheritance from Object Class

All Java classes implicitly inherit from `Object`. `Object` provides:
- `toString()`
- `equals(Object obj)`
- `hashCode()`
- `getClass()`
- `clone()`
- `finalize()`

These can be overridden for custom behavior.

## Constructor vs Methods

| Feature        | Constructor                    | Method                        |
|----------------|-------------------------------|-------------------------------|
| Purpose        | Initializes object             | Defines action/behavior       |
| Name           | Same as class                  | Any name except class name    |
| Return Type    | None                           | Must have a return type       |
| Invocation     | Called during creation         | Called explicitly             |
| Inheritance    | Not inherited                  | Inherited (unless private)    |
| Overloading    | Yes                            | Yes (can also override)       |
| Modifiers      | Not abstract, static, final    | Can have these modifiers      |

```java
// Constructor
public SampleDemo() { }
// Method
public void display() { }
```

## Custom Data Structures

User-defined ways to organize/store data:
- **Linked List:** Nodes point to next node
- **Stack:** Last-In-First-Out (LIFO)
- **Queue:** First-In-First-Out (FIFO)
- **Tree:** Hierarchical
- **Graph:** Nodes connected by edges

```java
class Node {
	int data;
	Node next;
}
```

## Game Development in Java

- **Game Loop:** Updates state & renders graphics
- **Graphics:** Drawing shapes, sprites, animations
- **Input Handling:** Keyboard, mouse, touch
- **Physics:** Movement, collisions, forces
- **Sound:** Music/effects
- **Assets:** Images, sounds, resources

**Popular libraries:** `libGDX`, `LWJGL`

### Simple Game Loop Example

```java
while (gameRunning) {
	updateGameState();
	renderGraphics();
	handleInput();
}
```

## Constructor Overloading

Multiple constructors with different parameter lists.

```java
class SampleDemo {
	SampleDemo() { }
	SampleDemo(int x) { }
	SampleDemo(String name, int age) { }
}
```

## Packages in Java

- Packs related classes, interfaces, sub-packages
- Prevents naming conflicts, improves modularity, maintainability

Syntax:
```java
package packageName;
```

Example:
```java
package day1.basics;
```

- **Built-in packages:** `java.util`, `java.io`, `java.lang`, etc.
- **Import** classes:
```java
import java.util.Scanner;
```
- Nested packages create hierarchy.

**Example:**
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

### Project Structure Example: ShoppingMall

- **Company:** IBM
- **Client:** Amazon

#### Modules
- utils
- entity
- services
- repositories
- controllers

Example package structure:
- `com.ibm.amazon.utils`
- `com.ibm.amazon.entity`
- `com.ibm.amazon.services`
- `com.ibm.amazon.repositories`
- `com.ibm.amazon.controllers`

## Common Built-in Java Packages

- `java.lang`: Core language (String, Math, System, Object)
- `java.util`: Collections, Date, Scanner, Random
- `java.io`: File, BufferedReader, InputStream
- `java.net`: Socket, URL, HttpURLConnection
- `java.sql`: Database connectivity
- `java.awt`: GUI (Abstract Window Toolkit)
- `javax.swing`: GUI components (JFrame, JButton)

## User-defined Packages

Created by developers to organize their own classes/interfaces.

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

## Example Package Structure

- `com.zoho.capgemini.stressreducerapp.entity`
- `com.zoho.capgemini.stressreducerapp.utilities`
- `com.zoho.capgemini.stressreducerapp.exceptions`
- `com.zoho.capgemini.stressreducerapp.main`

## Access Modifiers in Java

Controls visibility of classes, methods, and variables.

| Modifier   | Visibility                                         |
|------------|----------------------------------------------------|
| public     | Accessible everywhere                              |
| protected  | Accessible inside package & subclasses             |
| (default)  | Accessible in package                              |
| private    | Accessible only inside the same class              |

### Example

```java
public int x;
protected int y;
int z;           // Default
private int w;
```

## Examples of Access Modifiers

### Private

```java
class Example {
	private int secret;
	private void showSecret() {
		System.out.println(secret);
	}
}
```

### Default

```java
class Example {
	int value; // default access
	void showValue() {
		System.out.println(value);
	}
}
```

### Protected

```java
class Example {
	protected int number;
	protected void showNumber() {
		System.out.println(number);
	}
}
```

### Public

```java
public class Example {
	public int data;
	public void showData() {
		System.out.println(data);
	}
}
```

## Real-world Example: Encapsulation

Suppose you are developing a banking application — sensitive data like account balance should be hidden from direct access.

```java
public class BankAccount {
	private double balance;

	public double getBalance() {
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

## Multiple Inheritance in Java

- A class **cannot extend more than one class** (avoids diamond problem)
- Achieved via **interfaces**

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

## Constructor Inheritance

- Constructors are **not inherited**, but you can call parent with `super()`

```java
class Parent {
	Parent() {
		System.out.println("Parent constructor");
	}
}

class Child extends Parent {
	Child() {
		super();
		System.out.println("Child constructor");
	}
}
```

## Constructor Modifiers

- `private`: Allowed (Singleton, utility, factory patterns)
- `abstract`: Not allowed
- `final`: Not allowed

## Accessing Base Class Variables

- `public`: Accessible in derived class
- `protected`: Accessible in derived class (even in different packages)
- `default`: Accessible in derived class only if in same package
- `private`: Not accessible directly in derived class

## Object Access from Main Program

You cannot directly access the object from the main program to the class. Use the `this` keyword to refer to current object within the class.

## Static Keyword

The `static` keyword in Java creates elements that belong to the **class**, not to instances (objects).

**Static Variables**
- Shared across all instances (class variables)
- Only one copy (regardless of object count)
- Accessed via `ClassName.variableName`

**Example:**
```java
class Example {
	static int counter = 0;
}
```

**Static Methods**
- Belong to the class (not objects)
- Called via `ClassName.methodName()`
- Cannot access non-static members directly
- Cannot use `this` or `super` keywords
- Cannot be overridden (only hidden)

```java
class Example {
	static void show() {
		System.out.println("Static method");
	}
}
```

**Static Blocks**
- Execute when the class is loaded
- Initialize static variables/one-time setup
- Multiple blocks run in order

```java
class Example {
	static {
		System.out.println("Static block executed");
	}
}
```

**Static Classes**
- Only nested classes can be static
- Don't require an instance of the outer class
- Can access only static members of outer class

```java
class Outer {
	static class Inner {
		void display() {
			System.out.println("Static nested class");
		}
	}
}
```

### Common Use Cases

- Utility methods (e.g., `Math.random()`, `Arrays.sort()`)
- Constants (e.g., `Math.PI`)
- Factory methods
- Counters/shared resources
- The main method

### Features of `static` Keyword

- Can be applied to variables, methods, blocks, inner classes
- Members belong to the class, are shared
- Static methods can't access non-static members
- Static blocks executed when the class loads
- Static nested classes access only static members of outer

### Static Method Overloading

You can overload static methods in Java by changing their parameter list.

## Static vs Instance Member Table

| Case                   | Instance | Static        |
|------------------------|----------|--------------|
| Invoke Instance Method | ✔️       |              |
| Access Instance Var.   | ✔️       |              |
| Invoke Static Method   | ✔️       | ✔️           |
| Access Static Var.     | ✔️       | ✔️           |
| Invoke Instance (from static) |    | ❌ (directly) |
| Access Instance Var. (from static) | | ❌ (directly) |

## Static Blocks in Java

- Execute **once** when class is loaded
- Run **before any instance** is created
- **Before main method**
- Run in order of appearance

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
// Output:
// First static block
// Second static block
// Main method
```

**Static blocks are ideal for:** one-time setups before the class is used.

### Real-World Static Example: Flight Booking System

All users see the same seat count; changes are reflected everywhere.

```java
public class FlightBookingSystem {
	private static int availableSeats = 180; // Boeing 737 capacity

	public static synchronized boolean bookSeat() {
		if (availableSeats > 0) {
			availableSeats--;
			return true; // Booking successful
		}
		return false; // No seats available
	}

	public static int getAvailableSeats() {
		return availableSeats;
	}
}
```

## Final Keyword

- Declared with variable, method, or class indicating it **cannot be modified**
	- Final variable: value cannot change
	- Final method: cannot be overridden
	- Final class: cannot be inherited

### Blank static final variable?

Can be declared without initialization, must be initialized in a static block.

### Overriding and Inheritance

- **Cannot override** a final method
- **Cannot inherit** a final class

### Some final inbuilt classes

- `String`, `Integer`, `Double`, `Float`, `Boolean`, `Long`, `Short`, `Byte`, `Character`, `Math`, `System`, `Collections`, `Arrays`, `BigDecimal`, `BigInteger`

### Use of Final Keyword

- Imposes restrictions
- **Final Variables:** Constants (use `ALL_CAPS`)
- **Final Methods:** Can't be overridden (critical methods)
- **Final Classes:** Can't be extended (security-sensitive, design integrity)
- **Final Parameters:** Reference can't change within the method

### Blank Final Variables

- Declared without initialization
- Must be initialized in every constructor (instance)
- Must be initialized in a static block (static final)
