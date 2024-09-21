What is oop?
**Object-Oriented Programming (OOP)** is a programming paradigm that structures software design around **objects**, which are instances of **classes**. These objects bundle data (attributes) and methods (functions) together, allowing for modular, reusable, and scalable code. OOP is based on four key
# what is four pillars of oop ?
1. **Encapsulation**:
    
    - **Definition**: Encapsulation is the concept of wrapping data (attributes) and methods (functions) into a single unit, usually a class. It helps to hide the internal state of the object and only expose a controlled interface.
    - **Example**: In a class representing a bank account, the account balance is private, and public methods like `deposit()` and `withdraw()` are provided to interact with the balance.
2. **Abstraction**:
    
    - **Definition**: Abstraction involves simplifying complex systems by modeling classes based on the essential properties and behaviors an object should have, while ignoring the irrelevant details. It focuses on what an object does rather than how it does it.
    - **Example**: A `Vehicle` class might define methods like `start()` and `stop()`, without specifying how these actions are implemented. Specific types of vehicles (like `Car` or `Bike`) will inherit from `Vehicle` and implement these methods.
3. **Inheritance**:
    
    - **Definition**: Inheritance is a mechanism by which one class (the subclass or derived class) inherits attributes and methods from another class (the superclass or base class). This promotes code reusability and establishes a natural hierarchy between classes.
    - **Example**: A `Bird` class might be a superclass, with `Sparrow` and `Eagle` as subclasses. Both `Sparrow` and `Eagle` inherit common behaviors from `Bird` but can also have their unique attributes or methods.
4. **Polymorphism**:
    
    - **Definition**: Polymorphism allows objects of different classes to be treated as objects of a common superclass. It enables a single function or method to operate on objects of different types and classes, often through method overriding or method overloading.
    - **Example**: A `Shape` class with a method `draw()` could be inherited by `Circle` and `Square` classes. Each class implements the `draw()` method differently, but you can call `draw()` on a `Shape` object, and the appropriate method will be executed based on the actual object type. 

# ==what is consturctor?==
  A constructor is a special type of method in a class that is automatically called when an object is instantiated. Its primary purpose is to initialize the object's attributes and allocate resources if needed. Constructors typically have the same name as the class and do not have a return type.
There are mainly three types of constructors in object-oriented programming (OOP):
### 1. **Default Constructor**:
   - **Definition**: A constructor that takes no arguments. It initializes the object with default values.
   - **Example**: 
     ```cpp
     class MyClass {
     public:
         int x;
         MyClass() {  // Default constructor
             x = 0;   // Assign a default value
         }
     };
     ```

   - **Behavior**: If you don’t define any constructor, many programming languages (like C++) will automatically generate a default constructor.

### 2. **Parameterized Constructor**:
   - **Definition**: A constructor that takes parameters to initialize an object with specific values. It allows customization when creating an object.
   - **Example**:
     ```cpp
     class MyClass {
     public:
         int x;
         MyClass(int value) {  // Parameterized constructor
             x = value;
         }
     };
     ```
   - **Usage**: You pass values to the constructor when you create an object, allowing each object to be initialized differently.

### 3. **Copy Constructor**:
   - **Definition**: A constructor that creates a new object as a copy of an existing object. It copies the attributes of one object to another.
   - **Example**:
     ```cpp
     class MyClass {
     public:
         int x;
         MyClass(const MyClass &obj) {  // Copy constructor
             x = obj.x;
         }
     };
     ```

   - **Behavior**: The copy constructor is used when you pass an object by value, return an object from a function, or explicitly copy an object.
### Additional Specialized Constructor Types:
- **Static Constructor** (specific to languages like C#):
  - **Definition**:  a static class can't be instantiated. In other words, you can't use the [new](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/operators/new-operator) operator to create a variable of the class type. Because there's no instance variable, you access the members of a static class by using the class name itself.
  - **Example**:
    ```csharp
    static class MyClass {
        static int count;
        static MyClass() {  // Static constructor
            count = 0;
        }
    }
    ```
1. only static members allowed 
2. can not be instantiated
3. is sealed by default (there is no inheritance)
4. cannot create instance constructor 

# ==what is interface?==
An **interface** in object-oriented programming (OOP) is a contract that defines a set of abstract methods (without implementation) that a class must implement. It specifies _what_ methods a class should have but does not provide the actual code for those methods (the _how_ part). By implementing an interface, a class agrees to provide implementations for the methods defined in the interface.

# what is the difference between abstract class and interface?
### Summary Table:

| Feature                  | Abstract Class                            | Interface                                             |
| ------------------------ | ----------------------------------------- | ----------------------------------------------------- |
| **Methods**              | Can have abstract and concrete methods    | Only abstract methods (or default methods in Java 8+) |
| **Fields**               | Can have fields (state)                   | Can only have constants (no state)                    |
| **Constructor**          | Can have constructors                     | Cannot have constructors                              |
| **Multiple Inheritance** | Does not support multiple inheritance     | Supports multiple inheritance                         |
| **Access Modifiers**     | Methods can have any access modifier      | Methods are implicitly `public`                       |
| **Use Case**             | Used for related classes with shared code | Used for defining contracts across unrelated classes  |
- Use an **abstract class** when you want to provide a common base with shared code among related classes, but also want some methods to be overridden by subclasses.
- Use an **interface** when you want to define a contract that unrelated classes can implement, or when you need multiple inheritance.

# ==What is diamond problem?==
The diamond problem occurs in languages with multiple inheritance when a class inherits from two classes that both inherit from a common base class, leading to ambiguity in method resolution. Various languages address this problem through mechanisms like virtual inheritance, interfaces, or method resolution algorithms to ensure that the correct method is called and that only one instance of the base class is used.

# ==What is the difference between type value and reference?== 
| Feature        | Value Type                       | Reference Type                          |
| -------------- | -------------------------------- | --------------------------------------- |
| **Storage**    | Stored directly on the stack     | Stored on the heap; reference on stack  |
| **Assignment** | Creates a copy of the value      | Copies the reference to the same object |
| **Equality**   | Compares actual values.          | Compares references (memory addresses)  |
| **Mutability** | Typically immutable.             | Typically mutable                       |
| **Examples**   | `int`, `float`, `bool`, `struct` | `class`, `array`, `string`, `object`    |

### Conclusion:

- **Value Types**: Store data directly and are copied when assigned or passed to methods. They are typically stored on the stack and are usually immutable.
- **Reference Types**: Store references to data objects and are passed by reference. They are stored on the heap, and modifications affect all references to the same object. They are generally mutable.
# what is access modifiers?
#### **Public**

- **Syntax**: `public`
- **Access Level**: **Full access**. Members declared as `public` are accessible from **anywhere** in the program.
 **Private**

- **Syntax**: `private`
- **Access Level**: **Restricted**. Members declared as `private` are only accessible **within the class** itself. They cannot be accessed or modified directly from outside the class.
#### **Protected**

- **Syntax**: `protected`
- **Access Level**: **Limited**. Members declared as `protected` are accessible within the **class itself**, **derived (subclass)** classes, and **friend classes** (in some languages like C++).
# ==what is the namespace?==
A **namespace** is a container that helps organize code elements and prevent name conflicts in large projects. It enables hierarchical organization, reduces ambiguity, and enhances code readability and maintainability.

# what is the difference between static and const?
### **Key Differences:**

1. **Purpose:**
    - `static` is used to define class-level data and methods that are shared across all instances.
    - `const` is used to define data and methods that should not change after they are set.
2. **Scope and Lifetime:**
    - A `static` variable is shared and has a lifetime that extends across the entire program.
    - A `const` variable can have different lifetimes depending on its context (local, global, class member), but its value cannot be changed once initialized.
3. **Usage Context:**
    - `static` is often used for shared data between all objects, utility functions, or to limit the scope of functions to a specific file in C/C++.
    - `const` is used to protect data from modification and to enforce immutability.
# What is the difference between class and object?
### **Key Differences:**

1. **Definition:**
    
    - **Class:** A blueprint or template that defines properties and behaviors.
    - **Object:** A specific instance of a class with actual values for properties.
- **Existence:**
- **Class:** Does not occupy memory space by itself until objects are created.
- **Object:** Occupies memory space as it holds actual data values and can be manipulated.

# ==what is pure virtual funtion?==
A **pure virtual function** is a function in C++ that is declared in a base class but has no implementation in that class. It is intended to be overridden by derived classes, forcing them to provide their own implementation of that function. A class containing at least one pure virtual function becomes an abstract class, meaning it cannot be instantiated directly.

# ==what is delegates?==
A **delegate** in C# is a type that represents references to methods with a specific signature and return type. They are similar to function pointers in C++ but are type-safe and secure. Delegates allow methods to be passed as parameters and can be used to define callback methods.

# ==what is event?==
An **event** in C# is a specialized delegate designed for use with the publisher-subscriber model. Events provide a way for a class to notify other classes or objects when something of interest occurs. They are essentially "wrappers" around delegates that enforce encapsulation and help manage method invocation in a safe and controlled manner.

- **`Event`:** يُستخدم لإعلام النظام أو الأجزاء الأخرى من البرنامج بأن حدثًا معينًا قد وقع.
- **`Delegate`:** يُستخدم لتحديد وتخزين دالة أو مجموعة دوال يمكن استدعاؤها في وقت لاحق، إما لتنفيذ كود معين بناءً على حدث أو لأي غرض آخر.
# what is applent?
### **Applet in Java:**

1. **Definition:**
    
    - An **`Applet`** is a small program written in Java that is designed to be embedded within a web page. It is executed inside a web browser or with a special Applet viewer.