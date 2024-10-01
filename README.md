# Chapter-9-Head-First-Java
HEAD FIRST JAVA TEXTBOOK;
	Chapter 9:
	Lifecycle of objects in Java, from how they are created, initialized, and eventually garbage collected.
	Key concepts;
Memory allocation i.e (stack and heap),
Constructors,
Inheritance
 Garbage collection in Java programs - Java's garbage collector is automatic,

The Stack and the Heap: Where Things Live
•	Stack: The stack holds local variables for methods. When a method is called, Java creates a new frame on the stack for the method's variables.
•	Heap: Objects are stored on the heap, and they can be referenced by variables on the stack. The heap memory is shared among all parts of the program, and objects here remain alive as long as they are referenced.
Methods Are Stacked
•	Methods get added to the stack each time they are called, and removed when they return. This is how Java manages method execution, using the stack to track active methods.
Local Variables That Are Objects
•	Local variables are references that live on the stack, while the objects they reference live on the heap. When a local variable goes out of scope, the reference on the stack is removed, but the object itself remains on the heap as long as another reference to it exists.
Where Instance Variables Live
•	Instance variables, unlike local variables, are part of the object, so they live on the heap with the object. As long as the object exists, its instance variables exist.
The Miracle of Object Creation
•	Object creation in Java starts with the new keyword, which allocates memory for the object on the heap. Once memory is allocated, Java calls the appropriate constructor to initialize the object.
•	Object Construction Steps:
1.	Allocate memory on the heap.
2.	Call the constructor to initialize instance variables.
Constructors and Initialization
•	The constructor is a special method that runs when an object is created. It's used to initialize the object's state (its instance variables).
•	Constructor Rules:
o	If a class has no constructor, Java automatically provides a default no-argument constructor.
o	Constructors can be overloaded, meaning you can define multiple constructors with different parameters to initialize objects in different ways.
The Role of Superclass Constructors
•	When creating an object, Java not only creates the instance of the class but also ensures that the constructors of any parent classes (superclasses) are called.
•	If a subclass constructor doesn't explicitly call a superclass constructor, Java automatically calls the no-argument constructor of the superclass.
Superclass Constructors with Arguments
•	If a superclass doesn't have a no-argument constructor or if you want to call a specific superclass constructor, you must explicitly call it in the subclass constructor using super(arguments).
Overloaded Constructors
•	Constructors can call other constructors in the same class using this(arguments). This is useful for reducing code duplication when you have multiple ways to initialize an object but want to centralize the common logic in one constructor.
Object Lifetime
•	An object’s lifetime begins when it is created with new and ends when it becomes unreachable (i.e., no more references point to it).
•	Java’s garbage collector is responsible for freeing up memory by removing objects from the heap that are no longer reachable.
Garbage Collection
•	Java handles memory management with garbage collection, which automatically identifies and deletes objects that are no longer in use (i.e., not referenced by any variable).
•	This process helps prevent memory leaks and ensures that the heap doesn’t fill up with unused objects. However, it’s important to note that developers cannot directly control when garbage collection happens.
Reference Variables
•	Objects remain alive as long as there is at least one reference pointing to them. When an object no longer has any references, it becomes eligible for garbage collection.
•	References can be reassigned to point to different objects, potentially leaving the previous object without any references.
Memory Management Strategies
•	Although Java handles memory management through garbage collection, it is still important for developers to understand the lifecycle of objects to avoid holding onto references unnecessarily, which can lead to memory leaks.
Additional Concepts:
•	The finalize() Method: This method was historically used to perform cleanup before an object is garbage collected. However, its use is discouraged as garbage
•	collection is not guaranteed to happen in a timely manner.
•	Dangling References: These occur when an object has references pointing to it, but it's no longer needed. These objects will not be garbage collected, leading to inefficient memory use.




Working with Strings
String Class
•	Stores a sequence of unicode characters- UTF16 format – any character and language.
•	Literals specified in double quotes.
•	Values can be concatenated using + and +=
•	i.e   for example;
String name = "Jim";
String greeting = "Hello" + name;
System.out.println(greeting); // Hello Jim
greeting += " good to see you!" ;
System.out.println(greeting); // Hello Jim good to see you!

Strings Are Immutable
•	String variables do not directly hold the string value
•	- Hold a reference to the instance of string
•	- Changes in the value create a new instance of the string

String equality
String Equality
Comparing strings with the equality operator (==)
- Checks to see if both string variables reference the same string instance
Comparing strings with the equals method
- Performs a character-by-character comparison



i.e for example
String s1 = "I love";
s1 += " Java";
String s2 = "I";
s2 += " love Java"; if(s1 == s2) // false
// do something
if(s1. equals(s2)) //true
// do something
Checking string equality
- The equals method is the best choice in most cases
Interning a string
- Provides a canonicalized value
- Enables reliable == operator comparison
- Improves performance of frequently compared strings
String s1 = "I love":
s1 += " Java";
String s2 = "I":
s2 += " love Java";
1f(s1 == s2) // false
// do something
String
s3= s1. intern();
String
s4 =s2. intern();
1f( s3== S4)
// do something
String methods
Converting Non-string Types to String
Virtually all data types can be converted into a String
- Can use String.valueOf
- Conversion often happens implicitly
int iVal = 100;
String sVal = String.valueOf(1Val); //"100"
int 1 = 2, j = 3;
int result = i *j;
String output = i + " * “ + “ = “ +  result; // "2 * 3 = 6"

String conversions
StringBuilder class
