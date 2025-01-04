# Interview Preparation

- Core Java

  1 . Why Java is not 100% Object oriented?
    - Because of Primitive data types which are not objects eg: boolean, byte, char, int, float, double, long, short
    - We can use wrapper classes to wrap primitive data types into an object
    - Java allows the creation of static methods which are not tied to specific instance of a class
    - Lack of multiple inheritance which is a characteristic of some OOP languages

  2 . Why pointers are not used in java?
    - They are unsafe, increases the complexity of the program, JVM is responsible for memory allocation thus pointers
      are not needed in java

  3 . What is JIT compiler in Java?
    - Just In Time compiler which is a component of JVM that dynamically compiles byte codes into machine codes and to
      improve performance in java application

  4 . Why String is immutable in java?
    - Thread safe
    - Immutability allows strings to be cached and reused, improving performance
    - Immutable strings prevent unintended changes, enhancing security
    - String literals are kept inside String pool, and it requires Strings to be immutable. If there is a String in the
      pool it will get referenced otherwise a new String object will be created and will get a reference

  5 . What is a marker interface?
    - A marker interface is an empty interface. eg: Serializable, Cloneable(To get an exact duplicate object)
    - By implementing a marker interface classes will get additional behaviour at compile time
    - You can create your own marker interface, but need to do some customizations to the JVM

  6 . Can you override a private or static method in Java?
    - Cannot override a private or static methods in java
    - We cannot override a private method in subclass because it is not accessible there
    - For static methods if we create a similar method with same return type and same method arguments in child class
      then it will hide the superclass method, also known as method hiding

  7 . Does finally always execute in Java?
    - This will not execute in System.exit() or in System crash

  8 . What methods does the Object class have?
    - clone(): Creates and return a copy of the object
    - equals(): Compares the object with another object
    - finalize(): Called by the GC on an object when GC determines that there are no more references to that object
    - hashCode(): Returns a hash code value for the object
    - toString(): Returns a string representation of the object
    - getClass(): Returns the runtime class of this object

  9 . How to make a class Immutable?
    - Declare the class as final
    - Make all fields private and final
    - Don't provide setter methods for variables
    - Don't provide any method that modify the objects state

  10 . Boxing and unBoxing in Java?
    - Boxing is the process of converting a primitive datatype into an object wrapper datatype
    - Unboxing is the process of converting a value from an object wrapper type back to the native primitive value
    - Boxing allows primitive data types to be used in collections and other contexts where objects are required

  11 . What is JDK, JRE and JVM
    - JDK > JRE > JVM
    - JDK: Java Development Kit which includes JRE, tools for compiling, debugging and running the java programs, along
      with libraries and documentation
    - JRE: Java Runtime Environment for the bytecode to execute
    - JVM: Java Virtual Machine interprets compiled java code and translate it into machine code for execution
    - Java Program ---Java compiler--> Java ByteCode ---JVM---> Machine Code

  12 . Why main() method is public static?
    - So that the JVM can directly invoke it without instantiating class object

  13 . What are mutable and immutable String objects?
    - String is immutable while StringBuilder and StringBuffer are mutable

  14 . Difference between == and equals() method in Java?
    - equals() method available in Javas Object class which used for content comparison
    - == checks objects points to the same memory location

  15 . Difference between StringBuilder and StringBuffer?
    - StringBuilder
        - Not thread safe
        - Faster compared to StringBuffer
        - Suitable for single thread environments
    - StringBuffer
        - Thread safe
        - Slower compared to StringBuilder
        - Suitable for multiple thread environments

  16 . Difference between List and Set
    - List allow duplicates, Set doesn't allow duplicates
    - List maintains insertion order, Set doesn't maintain insertion order
    - List allows any number of null values, Set can have only a single null value at most
    - Lists are typically implemented using arrays or linked lists, while sets are implemented using hash table and
      trees
    - Lists are generally more efficient for access by index, while sets are optimized for membership testing and
      uniqueness

  17 . Difference between ArrayList and LinkedList
    - ArrayList internally uses a dynamic array to store elements, LinkedList internally uses a doubly linked list to
      store elements
    - Manipulation of ArrayList is slow, while LinkedList is faster
    - ArrayList consumes less memory, while LinkedList consumes more memory since it stores references to previous and
      next elements
    - ArrayList implements List interface only, LinkedList implements List and Deque interfaces
    - ArrayList provides fast access to elements by index, while in LinkedList accessing elements by index is slower

  18 . Difference between Collections and Streams
    - Collections are concrete data structures like lists, sets and maps, while Streams are not data structures
    - Collections are used to store and group the data while streams are used to perform filtering,matching,mapping
      operations(aggregate operations)
    - Can add or remove elements from Collections but cannot do that in Streams

  19 . What are the new features in Java 8?
    - Lambda Expressions
    - Method References
        1. What ware different kind of method references?
            - Reference to a static method
            - Reference to a constructor
            - Reference to an instance method reference of an object
            - Reference to an instance method reference of a class type

    - Optional
        1. What are the advantages of Optionals?
            - Null checks are not required
            - No more NullPointerException at run time
            - Clean neat APIs

    - Functional Interfaces
        - Consumer: Accept One argument but does not return anything
        - Function: Accept One argument and return one argument
        - Predicate: Accept One argument and return Boolean
        - Supplier: Do not accept arguments but return One argument
    - Default Methods
        1. What is a default method and when do we use it?
            - Default method is a method with an implementation which can be found in an interface

    - Stream API
    - Date and Time API

  20 . What are the rules to define a Functional Interface?
    - Define an interface with one and only one abstract method
    - We cannot define more than one abstract method
    - Use @FunctionalInterface annotation in the interface definition - this is optional
    - We can define any number of other methods like default methods, static methods

  21 . What is the order of JVM matching method arguments?
    - Exact match: JVM looks for an exact match between the method parameters and the arguments passed.
    - Widening primitive conversion: If an exact match isn't found, JVM looks for widening primitive conversions.
    - Autoboxing: If no match is found with widening primitive conversions, autoboxing is attempted.
    - Varargs: Finally, if no exact match is found, the JVM considers varargs as a last resort.

  22 . Why do we need OOP?
    - It helps us to think in terms of Real world objects
    - Pillars of OOP?
        1. Abstraction: Show only what is necessary, hiding the complexity. It helps in reducing programming complexity
           and effort by providing simplified view of objects
            - Abstract methods do not have an implementation, it only has method signatures
            - If a class have abstract method then the class needs to be declared abstract
            - An abstract class does not necessarily have an abstract method
            - Cannot be instantiated but abstract classes can have constructors: constructor can only be called during
              constructor chaining
            - Can have static methods and final methods
            - Abstract class implements interfaces, but it does not need to implement all methods
            - Abstract classes cannot be final because making an abstract class final will stop the abstract class from
              being extended

        2. Polymorphism: Objects of different classes treated as objects of a common superclass, it enables methods to
           do different things based on the object that they are acting upon
            - There are 2 types of polymorphism
                1. Static polymorphism(Overloading)
                2. Dynamic polymorphism(Overriding)

        3. Inheritance: Where a class(child) inherits properties and behaviours from another class(parent)
            - It's implemented using the extends
            - Inheritance establishes an "IS-A" relationship between classes

        4. Encapsulation: Is bundling of data and methods inside a single unit or class
            - To hide the internal state of an object and only allow access through public methods
            - Use private access modifier for fields to restrict direct access, and public methods to manipulate or
              access the fields
            - Getters and setters are typical encapsulation techniques used to control access to object fields

  23 . What is a class and an object?
    - A class is a blueprint of an object, it defines the attributes and behaviours that objects of that type will have
    - An object is an instance of a class with its own unique set of attributes and behaviours

  24 . Is-A relationship and Has-A relationship?
    - Whenever one class inherits another class it is called an Is-A relationship(extends)
    - Whenever an instance of one class has a reference to an instance of another class or same class it is known as
      Has-A relationship

  25 . What is method overriding and overloading?
    - Overloading is same method name with different signatures, return types can be same or different
    - Overriding is same method name with same signature, need to have parent child relationship and any method in
      parent class can be overridden in child class

  26 . Static(Compile) vs Dynamic(Runtime) Polymorphism?
    - Static Polymorphism is implemented by Method Overloading resolved at compile time
    - Dynamic Polymorphism is implemented by Method Overriding resolved at runtime

  27 . What is an Abstract Class
    - Abstract class is a class that cannot be instantiated on its own and typically contains abstract methods
    - It serves as a blueprint for other classes to inherit from and implement its abstract methods

  28 . What is an Interface?
    - Interface is a reference type that defines a set of abstract methods.
    - Interfaces allows for abstraction, enabling the decoupling of implementation from the behaviour
    - Java supports implementing from multiple interfaces
    - We cant write logic in interface
    - All the methods are public in an interface
    - Multiple Inheritance helps to add new methods without affecting the old interfaces
    - Can have default method implementations

  29 . What are static blocks and static initializers in Java?
    - Static blocks or static initializers are used to initialize static fields in java.
    - Static blocks gets executed exactly once when the class is loaded
    - Static blocks are executed even before the constructors are executed.

  30 . How to call one constructor from the other constructor ?
    - If we want to call one constructor from other we use this() method. Based on the number of parameters we pass
      appropriate this() method is called
    - 'this()' must be the first statement in the constructor
    - We cannot use two this() methods in the constructor

  31 . Difference between method overloading and method overriding in java ?
    - Overloading
        1. Method Overloading occurs with in the same class
        2. Since it involves with only one class inheritance is not involved
        3. In overloading return type need not be the same
        4. Parameters must be different
        5. In overloading one method can’t hide the another
    - Overriding
        1. Method Overriding occurs between two classes superclass and subclass
        2. Since method overriding occurs between superclass and subclass inheritance is involved
        3. In overriding return type must be same
        4. Parameters must be same
        5. In overriding subclass method hides that of the superclass method

  32 . Why java is platform independent?
    - In any programming language source code is compiled in to executable code. When javac compiles a java program it
      generates an executable file called .class file.
    - .class file contains byte codes. Byte codes are interpreted only by JVM
    - We can execute this byte code in any platform and this makes Java platform independent

  33 . Difference between this() and super() in java ?
    - this() is used to access one constructor from another with in the same class while super() is used to access
      superclass constructor. Either this() or super() exists it must be the first statement in the constructor.

  34 . Explain about instanceOf operator in java?
    - \<reference expression> instanceOf \<destination type>: will return true if reference is an instance of
      destination type
    - There will be a compile time check, so that if it's not a subtype then compile time error will be shown

  35 . Can we define package statement after import statement in java?
    - We can’t define package statement after import statement in java. package statement must be the first statement in
      source file.
    - We can have comments before the package statement

  36 . What are identifiers in java?
    - Identifiers are names in java
    - Identifiers must start with letter,Underscore or dollar($) sign
    - Identifiers can’t start with numbers
    - Case sensitive
    - From second letter we can have numbers
    - We cant use reserved words for identifiers

  37 . What access modifiers can be used for class?
    - public: Can access from anywhere
    - default: Accessible only within the same package
    - final: Prevents the class from being subclassed

  38 . Explain what access modifiers can be used for methods?
    - All access modifiers
        - private: Only in same class
        - protected: Can access in same class, same package subclass, same package non subclass, different package
          subclass only
        - default: Can access in same class, same package subclass, same package non subclass only
        - public: Can access in same class, same package subclass, same package non subclass, different package
          subclass, different package non subclass

  39 . What is an error in Java?
    - Error is the subclass of Throwable class in java
    - Exceptions which cannot be recovered are called as errors in java
    - They cannot be handled by the application code, and they are not meant to be caught or handled using exception
      handling mechanisms like try-catch blocks
    - They are caused by problems outside the control of the application, such as system failures or resource exhaustion
    - ex: OutOfMemoryError, StackOverflowError

  40 . Can we have try block without catch block?
    - Each try block requires at-least one catch block or finally block

  41 . What is checked and unchecked Exception in Java?
    - Checked Exception(Compile time exception)
        1. All the subclasses of Throwable except RuntimeException and its subclasses are checked Exception
        2. Checked Exception should be thrown with keyword throws or provided try catch block else program would not
           compile
        3. Examples
            - FileNotFoundException: Occurs when a file specified cannot be found by a FileInputStream or a
              RandomAccessFile
            - IOException: A broad exception indicating an I/O problem, such as the failure of reading from or writing
              to a file
            - SQLException: Indicates a problem accessing a database through JDBC
            - ClassNotFoundException: Occurs when the specified class is not found by the ClassLoader
            - InvocationTargetException
    - Unchecked Exception
        1. All subclasses of RuntimeException are called unchecked Exception
        2. Program compiles even if we do not catch the exception or throws the exception
        3. Examples
            - ArithmeticException: Performing arithmetic operations that result in an error, like dividing by zero
            - IndexOutOfBoundsException: Thrown when attempting to access an array element at an index that is outside
              the bounds of the array
            - NullPointerException: Occurs when you try to access or manipulate an object reference that has a null
              value
            - NumberFormatException: Arises when attempting to convert a string to a numeric type, but the string does
              not contain a valid numeric value
            - UnsupportedOperationException

  42 . Explain the importance of finally over return statement?
    - 'finally' block is more important than return statement when both are present in a program
    - For resource cleanup
    - Guaranteed execution
    - Centralized cleanup code in one place
    - 'finally' will not work in JVM shutdowns

  43 . Explain when ClassNotFoundException will be raised ?
    - Occurs when the JVM tries to load a class dynamically at runtime using Class.forName() or ClassLoader.loadClass(),
      but the specified class cannot be found in the classpath
    - This can occur due to a missing jar or classpath issue
    - This is a checked exception which occurs at runtime

  44 . Explain when NoClassDefFoundError will be raised ?
    - JVM tries to load the class but no definition for that class is found. The class may exist at compile time but
      unable to find at runtime

  45 . Explain about main thread in java?
    - Main thread is the first thread that starts immediately after a program is started
    - Main thread is important because,
        1. All the child threads are spawn from main thread
        2. It is responsible for executing the main method of the class specified when launching the program

  46 . Explain the life cycle of thread?
    - New: Threads are created either by extending the Thread class or implementing the Runnable interface
    - Runnable: When the start method is invoked but has not scheduled yet
    - Running: Thread scheduler allocates cpu time, then the thread will be in running state
    - Waiting/Blocked: A thread might transition to a blocked or waiting state due to synchronization
    - Dead: A thread is in dead state when thread’s run method execution is complete and it cannot be restarted

  47 . In how many ways we can do synchronization in java?
    - Synchronized methods
    - Synchronized blocks

  48 . When do we use synchronized methods in java?
    - Use synchronized methods in Java when you need to ensure thread safety by allowing only one thread to access the
      method at a time
    - Synchronized methods are used to prevent concurrent access to critical sections of code, ensuring data consistency
      in multithreaded environments

  49 . Can we use synchronized block for primitives?
    - Synchronized blocks are applicable only for objects

  50 . What are daemon threads in java?
    - Daemon threads are threads which run in background. These are service threads and works for the benefit of other
      threads.
    - Garbage collector is one of the good example for daemon threads

  51 . What are nested classes in java?
    - Class declared with in another class is defined as nested class
        1. Static nested class
        2. Non-static nested class

  52 . What are inner classes or non-static nested classes in java?
    - Nested classes without any static keyword declaration in class definition are defined as non-static nested
      classes. Generally non-static nested classes are referred as inner classes
    - There are 4 types of Inner classes
        1. Local Inner Class: A class defined within a method of another class. It can access all members of the
           enclosing class and local variables of the enclosing method
        2. Member Inner Class: A class defined at the member level of another class. It has access to all members of the
           enclosing class, including private members
        3. Static Nested Inner Class: A static nested class defined within another class. It cannot access non-static
           members of the outer class directly
        4. Anonymous Inner Class: A class defined without a name. It's typically used for instantiating interfaces or
           extending classes

  53 . Will the compiler creates a default constructor if I have a parameterized constructor in the class?
    - No compiler won’t create default constructor if there is parameterized constructor in the class.
    - For example if I have a class with no constructors, then compiler will create default constructor

  54 . Can Static methods access instance variables in java?
    - No. Instance variables can’t be accessed in static methods. When we try to access instance variable in static
      method we get compilation error

  55 . How many times finalize method will be invoked ? who invokes finalize() method in java?
    - Finalize() method will be called only when object is eligible for garbage collection

  56 . Explain about transient variables in java?
    - To save the state of an object to persistent state we use serialization. If we want a field or variable in the
      object not to be saved, then we declare that variable or field as transient

  57 . Can we define static methods inside interface?
    - Yes we can define static methods in interfaces but cannot override it

  58 . Define interface in java?
    - Interface is collection of abstract methods and constants. An interface is also defined as pure or 100 percent
      abstract class.Interfaces are implicitly abstract whether we define abstract access modifier or not.

  59 . Explain restrictions on using enum?
    - Enums cannot extend any other class or enum(immutable)
    - Enums ensure a single instance of each enum constant within a JVM
    - Enums provide type safety, ensuring that only valid enum constants can be assigned
    - We cannot instantiate an enum

  60 . What is collection ?
    - A collection is a container which holds group of objects
        1. Adding objects to collection
        2. Removing or deleting objects from collection
        3. Retrieving object from collection
        4. Iterating collection

  61 . What is Vector?
    - Vector is similar to arraylist used for random access
    - Vector is a dynamic array like arraylist
    - Vector size increases or decreases when elements are added and removed
    - Vector is synchronized

  62 . Difference between HashMap and Hashtable?
    - HashMap is not synchronized but Hashtable is synchronized
    - HashMap allows one null key and any number of null values but Hashtable does not allow any null values at all
    - Hashtable is slower compared to HashMap
    - HashMap introduced starting from collection framework but Hashtable was there even before collection framework

  63 . Explain about fail fast and fail-safe iterators in java?
    - Fail fast
        - Immediately throw a ConcurrentModificationException if the underlying collection is modified structurally
          while iterating
    - Fail safe
        - Fail-safe iterators work on the cloned copy of the underlying collection, ensuring that modifications to the
          collection don't affect ongoing iterations
        - These iterators do not throw exceptions if the collection is modified during iteration

  64 . What is serialization in java?
    - Serialization is the process of converting an object in to bytes, so that it can be transmitted over the
      network,or stored in a flat file and can be recreated later.
    - Serialized object is an object represented as sequence of bytes that includes objects data, object type, and the
      types of data stored in the object.

  65 . How to make object serializable in java?
    - Our class must implement serializable interface. If our object contains other objects those class must also
      implement serializable interface.
    - We use ObjectOutputStream which extends OutputStream used to write objects to a stream.
    - We use ObjectInputStream which extends InputStream used to read objects from stream.

  66 . If we don’t want some of the fields not to serialize How to do that?
    - If we don’t want to serialize some fields during serialization we declare those variables as transient

  67 . What is the difference between Comparable and Comparator interfaces?
    - Comparable(Single sorting sequence, actual class is modified)
        - compareTo(X x)
        - Collections.sort(list)
        - java.lang package
    - Comparator(Multiple sorting sequence, actual class is not modified)
        - compare(X x, X y)
        - Collections.sort(list, Comparator)
        - Best solution
        - java.util package

  67 . What is Serial Version UID?
    - It's used to ensure compatibility between serialized objects when the class definition changes
    - If serialVersionUID is not provided in a Serializable class, the JVM will generate one automatically
    - It's crucial for deserialization to determine if a serialized object can be successfully reconstructed

  68 . What are functional interfaces in Java?
    - An interface that contains one abstract method.
    - Can have any number of default methods
    - Functionality can be implemented using Lambda expression, anonymous class or method reference

  69 . Explain exception hierarchy?
    - Throwable
        - Exception(recoverable)
            - Checked
            - Runtime
        - Error(Non recoverable)

  70 . What is CountDownLatch?
    - Java synchronization utility used to allow one or more threads to wait until a set of threads completed
    - It's initialized with a count, and each thread that needs to wait calls await() method
    - As operations complete, the count is decremented using the countDown() method. When the count reaches zero,
      waiting threads are released

  71 . What is CyclicBarrier?
    - Allows fixed number of threads that must wait for each other to reach a common point before continuing execution

  72 . What are the types of inheritance in Java?
    - Single level: Only one class is derived from the parent class
    - Multi level: One class inherits the features from a parent class and the newly created subclass becomes the base
      class for another new class
    - Hierarchical: Many subclasses inherit from one single class is known as Hierarchical Inheritance
    - Multiple: Subclass can inherit features from more than one parent class
    - Hybrid: Combination of more than two types of inheritance

  73 . What is the difference between permgen and metaspace?
    - Permgen
        - Used prior to java 8
        - Stores class metadata, static variables
        - Has a fixed size which can lead to OutOfMemory errors if exceeded
        - Manual tuning needed to prevent these errors
    - Metaspace
        - Introduced in java 8
        - Stores metadata and reflective data
        - Dynamically resizable memory area
        - Can grow or shrink based on application demand
        - Automatically managed by JVM

  74 . Can you start a thread twice in java?
    - No, it will give IllegalThreadStateException

  75 . Why do we use Functional Interfaces in java?
    - Enables the use of Lambda expressions and method references
    - Compatible with stream API and parallel processing
    - Enhance code readability, maintainability and re-usability

  76 . What are the benefits of using Multithreading?
    - Allow the program to run continuously even if a part of it is blocked
    - Improve performance as compared to traditional parallel programs that use multiple processes
    - Saves time and parallelism tasks
    - Allows to write effective programs that utilize maximum CPU time
    - Improves the responsiveness of complex applications or programs

  77 . What's the difference between thread and process?
    - Thread
        - Smallest unit of a particular process and it can execute different parts of the program at the same time
        - Threads are easy to create
        - It requires less time for creation, termination, and context switching
        - Threads share the same memory address of the process they belong to
    - Process
        - A program that is in execution containing multiple threads
        - These are difficult to create
        - It requires more time for creation, termination, and context switching
        - Each process has different memory space or address

  78 . What are the wait() and sleep() methods?
    - wait(): Currently executing thread will wait until another thread notifies it to wake up until some other threads
      call notify() or notifyAll() method
    - sleep(): This method is used to temporarily suspend the execution of a thread for a specified amount of time

  79 . What is the start() and run() method of Thread class?
    - start(): A new thread is created and executes the task in run() method, and can only invoke this once
    - run(): No new thread is created and executes the task, and can invoke this multiple times

  80 . Explain the meaning of the deadlock and when it can occur?
    - Deadlock, as the name suggests, is a situation where multiple threads are blocked forever
    - It generally occurs when multiple threads hold locks on different resources and are waiting for other resources to
      complete their task

  81 . What is the use of join() in threads?
    - Join method is an instance method on the Thread class
    - join() method forces the execution of main method to stop until the specified thread with join method completes
      execution

  82 . What is the default access modifier if no access modifier is specified in Java?
    - default

- Spring

  1 . Explain Inversion Of Control, Dependency Inversion, Dependency Injection concepts in Spring?
    - Inversion Of Control(IoC):
        1. Control of object(beans) creation and management is shifted from the application itself to an external
           container or framework(Spring IoC container is responsible)
        2. The container manages the lifecycle of these beans and handles their dependencies, ensuring that the right
           dependencies are injected into the right places
        3. Overall architecture becomes more flexible and maintainable
        4. This allows for greater flexibility, easier testing and decoupling of components
    - Dependency Inversion(DI):
        1. High-level modules should not depend on low-level modules. Both should depend on abstractions
        2. This is achieved through interfaces or abstract classes, allowing for loose coupling between components
    - Dependency Injection:
        1. A design pattern used to implement dependency inversion, where dependencies are injected into a class rather
           than being created or managed by the class itself

  2 . What are the common design patterns used in Spring applications?
    - Singleton pattern: There is only one instance of a particular bean per Spring container. This ensures that beans
      are shared across the application reducing resource usage
    - DI pattern: Spring IoC container performs DI by injecting dependencies into classes either through constructor
      injection, setter injection or method injection using annotations
    - Prototype pattern: New instance per request
    - Factory pattern: Spring IoC container acts as a factory that creates and manages bean instances based on their
      configurations
    - Template Method pattern: Template classes provide a consistent approach to perform repetitive tasks such as
      database access(JdbcTemplate), transaction management(TransactionTemplate) and email sending(JavaMailSender)

  3 . Explain the difference between constructor and setter injection?
    - Constructor injection
        - Dependencies are injected via constructor parameters
        - Provides immutable objects, promoting thread safety
        - Requires all dependencies to be provided during object creation
        - Encourages better design by enforcing mandatory dependencies upfront
    - Setter injection
        - Dependencies are injected via setter methods
        - Allows for flexibility by allowing dependencies to be set after object creation
        - Facilitates optional dependencies and circular dependencies

  4 . What is a Spring Bean?
    - An object that is instantiated, assembled, and managed by the Spring IoC container is a Spring Bean
    - IOC manages the lifecycle of the Spring Beans
    - Dependency Injection injects dependencies into Beans
    - Bean scopes defines the lifecycle and visibility of a spring bean(Singleton, Prototype, Request, Session)
    - Component scanning is an automatic detection and instantiation of Spring beans based on classpath scanning and
      predefined rules
    - Methods like @PostConstruct and @PreDestroy to execute initialization and destruction logic respectively

  5 . @Value can help loading the values from?
    - Environment properties, VM arguments, properties file

  6 . What are the places @PropertySource extract values from?
    - Classpath
    - Another properties file from another project

  7 . How the singleton beans are initialized?
    - Singleton beans in Spring are initialized when the Spring container starts up
    - Spring container creates and manages a single instance of a singleton bean throughout the application lifecycle
    - Singleton beans are initialized lazily by default, meaning they are created upon first request
    - Initialization of singleton beans involves instantiation, property injection, and any required initialization
      methods
    - Once initialized, singleton beans are cached for subsequent requests, improving performance by avoiding repeated
      creation

  8 . Is @Bean a stereotype annotation?
    - No, If its stereotype it has a specific role
    - @Component, @Repository, @Service, and @Controller @value are stereotype annotations

  9 . Can you define private Beans using @Bean annotation inside a Configuration file that are annotated with
  @Configuration?
    - No

  10 . What are the places where @Profile annotation can be used?
    - Use @Profile on @Component, @Service, @Repository, or @Configuration to specify when a bean should be created
      based on the active profiles
    - Include or exclude components based on active profiles by annotating your configuration class with @ComponentScan
      and providing profile names
    - Use along with @ConditionalOnBean, @ConditionalOnClass to conditionally create beans or configure components based
      on profiles

  11 . Differences between Spring and Spring Boot?
    - Spring
        - Widely used Java EE framework for building web applications
        - Requires manual configuration for various components like data sources, security and logging
        - Requires more configuration and setup time
        - Provides a wide range of modules for different functionalities like spring MVC, spring data and spring
          security
    - Spring Boot
        - Widely used to developing microservices and standalone applications
        - Provides autoconfiguration for most common application needs
        - Rapid Application Development reducing boilerplate code
        - Simplifies application development by bundling necessary dependencies and providing starter modules for common
          tasks

  12 . What is auto wiring?
    - The process of injecting dependencies into a spring bean without explicitly configuring them

  13 . What is the difference between war and jar?
    - Jar files are used to packaging and distributing standalone java applications while War files are used to
      packaging and distributing web application to a servlet container like tomcat

  14 . Explain Spring scopes?
    - Singleton: Creates a single instance of a bean per Spring IoC container
    - Prototype: Creates a new instance of a bean every time it's requested
    - Session: Creates a new instance of a bean for each HTTP session
    - Request: Creates a new instance of a bean for each HTTP request

- Spring boot

  0 . Why Spring Boot?
    - Rapid Application Development
    - Autoconfiguration reducing the need for manual setup and configuration
    - Embedded servers like tomcat or jetty
    - Native Cloud support using spring cloud
    - Rich ecosystem with extensive community support, libraries and plugins
    - Production ready endpoints for checking health, metrics and monitoring
    - Simplified unit and integration testing
    - Open source and based on Java

  1 . How SpringBoot works internally?
    - It leverages Spring's core features such as dependency injection and inversion of control (IoC) to manage
      application components
    - SpringBoot automatically configures your application based on its dependencies and the environment, reducing the
      need for manual configuration
    - It uses an embedded server like Tomcat, Jetty, or Undertow to simplify deployment. This means you can run your
      SpringBoot application as a standalone Java application
    - SpringBoot provides starter dependencies that bundle commonly used libraries, making it easier to set up and
      manage dependencies in your project
    - SpringBoot Actuator provides built-in endpoints to monitor and manage your application at runtime, offering
      insights into application health, metrics, and more
    - It offers a Command Line Interface (CLI) for rapid prototyping and development of SpringBoot applications,
      allowing you to quickly create, run, and test applications
    - Dev tools helps in rapid development by enabling features like automatic application restart, live reload, and
      remote debugging
    - SpringBoot supports various configuration formats like properties files, YAML files, environment variables, and
      command-line arguments

  2 . What are Spring boot starters?
    - Spring boot starter comprises templates which provide a Rapid Application Development
    - Spring boot starter contains a combination of all the relevant transitive dependencies
    - Spring boot starter solves the auto dependency resolution in a spring boot application
    - They provide a quick and easy way to include common dependencies for specific functionalities, such as web
      development, data access, security, and more
    - Spring boot resolves transitive dependencies internally
    - All available starters come under the org.springframework.boot group

  3 . What are the major starter dependencies of spring boot application?
    - spring-boot-starter-parent: Provides default configurations for our application, dependency management and plugin
      management
    - spring-boot-starter-web: Essential for developing web applications, providing embedded Tomcat server and Spring
      MVC
    - spring-boot-starter-security: Offers authentication, authorization, and other security features
    - spring-boot-starter-test: Facilitates testing with JUnit, Mockito, and other testing libraries
    - spring-boot-starter-actuator: Enables monitoring and managing the application through endpoints
    - spring-boot-starter-jdbc: Provides libraries for connecting the application with JDBC
    - spring-boot-starter-data-jpa: Simplifies working with databases using Java Persistence API
    - spring-boot-starter-data-aop: Provides Aspect-Oriented Programming with cross-cutting concerns

  4 . Can you disable particular auto-configuration in spring boot?
    - Yes
    - @EnableAutoConfiguration(exclude={DataSourceAutoConfiguration.class}) or @SpringBootApplication(
      exclude={DataSourceAutoConfiguration.class})

  5 . Explain below annotations?
    - @RestController: Marks a class as a controller where methods return data directly instead of relying on a view for
      presentation. Used in REST ful web services
    - @RequestMapping(value="/provider"): Maps HTTP requests to MVC or REST and specifies URL pattern that the
      controller should listen
    - @PathVariable: Extracts values from the URI path
    - @RequestParams: To extract query params from the URL
    - @ResponseEntity: Represents the entire HTTP response, including headers and body. It allows you to control the
      response status code, headers, and body content
    - @GetMapping: It maps HTTP GET requests onto specific handler methods in a controller
    - @ResponseBody: Indicates that the return value of a method should be bound to the web response body

  6 . Can we disable the default web server in the Spring Boot application?
    - Add below config to application.properties
        - spring.main.web-application-type=none

  7 . What is the difference between @Controller and @RestController annotations?
    - @Controller: It is used to mark classes as Spring MVC controllers. These classes handle web requests and usually
      return views
    - @RestController: It is a specialization of the @Controller annotation. It's used to create REST ful web services.
      It automatically converts Java objects into JSON or XML responses

  8 . What is the difference between @RequestMapping and @GetMapping annotations?
    - @RequestMapping can be used with GET,POST,PUT and many other request methods using the method attribute on the
      annotation
    - GetMapping is only an extension of RequestMapping, which helps you to improve clarity on requests

  9 . What is Singleton across per container and per jvm?
    - 1 singleton bean per Spring container
    - Multiple beans per JVM if we deploy multiple instances of the same application in the same server

  10 . Explain Spring Actuator and its advantages?
    - Spring Actuator is a feature in the Spring Boot framework that provides production-ready features to help monitor
      and manage your application
    - Actuator supports below endpoints
        - '/actuator/health'
        - '/actuator/metrics'
        - '/actuator/env'

  11 . What is spring boot dependency management?
    - Spring Boot dependency management is a feature that simplifies the management of dependencies in a Spring Boot
      application
    - Spring Boot automatically manages and resolves the versions based on compatibility requirements
    - This reduces the risk of version conflicts and simplifies the configuration process

  12 . What is the need for spring boot DevTools?
    - Set of tools that aims to make the process of developing an application easier
    - This module is automatically disabled in production
    - List of functionalities provided
        - Automatic restart
        - Live reload
        - Remote debugging
        - Dependency management

  13 . What is Spring initializer?
    - Is a web tool provided by Spring. With this tool you can create Spring boot projects just by providing project
      details

  14 . What are the differences between JPA and Hibernate?
    - JPA
        - Is a specification for object relational mapping in Java applications
        - Is a set of interfaces and annotations, allowing for multiple implementations
        - Can switch to another JPA implementation easily
    - Hibernate
        - Is a specific implementation of JPA
        - Require more code changes if migrating
        - Offers more features and performance tuning options compared to JPA

  15 . What do you understand by Spring Data?
    - Aims to simplify database access in java applications
    - It provides a consistent API for working with various data stores, including relational, NoSQL and cloud-based
      data services

  16 . What is the best way to expose custom application configuration with SpringBoot?
    - Using application.properties or application.yml
    - @ConfigurationProperties to bind custom properties directly to Java objects
    - Environmental variables
    - Spring Cloud Config
    - Profiles

  17 . What is the difference between @Autowired and @Inject?
    - @Inject is a standard annotation for dependency injection while @Autowired is a specific annotation in Spring for
      dependency injection
    - @Inject is from pure Java EE, while @Autowired is from Spring framework
    - We can achieve dependency injection in pure java using constructor injection, setter injection or method injection

  18 . What is the difference between @Component and @Bean?
    - @Component is used to auto-detect and autoconfigure beans using classpath scanning, while @Bean is used to
      explicitly declare a single bean instance manually
    - @Bean is method level but @Component is class level
    - The @Component annotation doesn't need to be used with the @Configuration annotation, whereas the @Bean needs to
      be within a class annotated with @Configuration

  19 . How many types of IOC containers are there in Spring?
    - BeanFactory: Serves as the core container for holding bean definitions, instantiating beans, and managing their
      lifecycle
    - ApplicationContext: ApplicationContext interface is built on top of the BeanFactory, and it provides additional
      functionality like Annotation support, Reactive programming

  20 . What is the use of @Qualifier annotation in Spring framework?
    - When we create more than one bean of the same type and want to wire only one of them with a property we can use
      the @Qualifier annotation
    - It helps resolve the ambiguity by specifying exactly which bean should be autowired into a particular dependency

  21 . What is @Primary annotation in Spring?
    - Indicates the primary bean to be used when multiple beans of the same type are present
    - Used to resolve ambiguity when auto-wiring beans by type
    - Spring will prioritize the bean annotated with @Qualifier over the one annotated with @Primary

  22 . What are the lifecycle methods in Spring?
    - init and destroy method which are executed by spring container

  23 . What are different ways of writing lifecycle methods in Spring?
    - XML Configuration
    - Implementing spring interfaces
        - InitializingBean
        - DisposableBean
    - Annotations:
        - @PostConstruct: The method annotated with @PostConstruct is invoked after the bean has been constructed and
          its dependencies have been injected
        - @PreDestroy: The method annotated with @PreDestroy is invoked before the bean is destroyed by the Spring
          container, typically during shutdown

  24 . What do you understand by validations in Spring MVC?
    - It is used to restrict the input provided by the user
    - Spring validations: @NotNull, @Pattern, @Email, @Size, @NotBlank
    - @Valid must be used at Method Parameter

  25 . Which annotations are used to define Global Exception Handler class?
    - @ControllerAdvice or @RestControllerAdvice
    - @ExceptionHandler

  26 . What is the main difference between Spring core and Spring MVC?
    - Spring Core provides the fundamental functionalities of the Spring Framework, such as dependency injection and
      inversion of control
    - Spring MVC is a part of the Spring Framework that provides a model-view-controller architecture for building web
      applications

  27 . What is ResponseEntity<T> in Spring REST?
    - It's a class representing the entire HTTP response including status code, headers, and body
    - Used to customize HTTP response in Spring REST controllers
    - Allows specifying status codes, headers, and response body type

  28 . What is ORM?
    - ORM stands for Object Relational Mapping
    - It's a programming technique to map objects from an object-oriented system to relational database tables
    - ORM helps developers work with databases using the programming language's object-oriented paradigm
    - It abstracts away the complexities of SQL queries, making database interactions more intuitive
    - ORM facilitates CRUD operations: Create, Read, Update, Delete, on database records through object manipulation

  29 . What is the Spring boot Data JPA repository?
    - Mainly there are 3 repositories
        - CrudRepository: Provides CRUD operations (Create, Read, Update, Delete) for the entity
        - PagingAndSortingRepository: Extends CrudRepository and adds pagination and sorting capabilities
        - JpaRepository: Extends PagingAndSortingRepository and adds JPA-specific methods like flushing the persistence
          context and deleting records in a batch

  30 . What are the predefined methods given by @Repository interfaces?
    - save(), saveAll(), findById(), findAll(), findAll(Sort), findAll(Pageable), count(), delete(), deleteAll(),
      deleteById()

  31 . What is @Query used for?
    - @Query annotation is used to write custom queries
    - By using this query we can write JPQL/HQL query which is written by the class name(DB table name) and variable
      name(Column name)

  32 . What is PlatformTransactionManager?
    - PlatformTransactionManager is an interface that extends TransactionManager
    - It coordinates the beginning, committing, or rolling back of transactions, ensuring data integrity and consistency
      in database operations

  33 . Difference between findById() and getOne()?
    - If data is not found in findById() will return null, means it return Optional<T> class
    - If data is not found in getOne() will throw an exception called EntityNotFoundException

  34 . What is the usage of Dialect?
    - It generates SQLs at runtime based on our operations
    - If we move from one Database to another database we need to update database dialect property in
      application.properties

  35 . What is the default FetchType in JPA?
    - LAZY: one-to-many, many-to-many
    - EAGER: one-to-one, many-to-one

  36 . How can we see generated SQLs at console files?
    - spring.jpa.show-sql=true(default is false)

  37 . What are some essential features of Spring Security?
    - Authentication: Provides mechanisms to authenticate users using various methods such as LDAP, JDBC, OAuth, etc
    - Authorization: Enables fine-grained access control to resources based on user roles and permissions.
    - Security Filters: Offers a set of filters for handling authentication, authorization, session management, and CSRF
      protection
    - Session Management: Supports session fixation protection, concurrent session control, and session timeout handling
    - Password Encoding: Built-in support for password hashing and salting to securely store user passwords
    - CSRF Protection: Helps prevent Cross-Site Request Forgery attacks by generating and validating unique tokens
    - Remember-Me Authentication: Allows users to authenticate with a persistent token, typically stored in a cookie,
      for automatic login
    - Method-Level Security: Provides annotations for securing individual methods within Spring components.

  38 . What do you mean by Basic Authentication?
    - We send a username and password using the HTTP header to enable us to access the resource
    - Username and password are encoded using base64 encoding in Basic Authentication
    - eg: Value = username:password -> Encoded = base64(Value) -> Authorization = Basic <Encoded>

  39 . Explain SecurityContext and SecurityContextHolder?
    - SecurityContext: SecurityContext is an interface in Spring Security that holds the details of the currently
      authenticated user, including their principal (username), authorities, and other security-related information
    - SecurityContextHolder: SecurityContextHolder is a class in Spring Security that provides access to the
      SecurityContext

  40 . Explain spring security OAuth2?
    - Spring Security OAuth2 is an extension of the Spring Security project that provides support for OAuth 2.0
      authentication and authorization
    - It helps secure Spring-based applications by providing mechanisms for authenticating users and authorizing access
      to resources using OAuth 2.0
    - The main components include Authorization Server, Resource Server, Client, and Tokens
    - Authorization server is responsible for issuing access tokens to clients after successfully authenticating and
      authorizing users
    - Resource server hosts resources that are protected by OAuth 2.0 and verifies access tokens to grant or deny access
      to those resources
    - The client is an application that requests access to protected resources on behalf of the resource owner
    - An access token is a credential that represents the user's authorization to access protected resources
    - It is issued by the Authorization Server after the user successfully authenticates and authorizes the client
      application
    - A refresh token is a long-lived credential that is used to obtain a new access token when the current one expires
    - When an access token expires, the client can use the refresh token to request a new access token without requiring
      the user to re-authenticate

  41 . What is method security and why do we need it?
    - The ROLE of the user is used to determine which user is authorized to access the resource
    - A security measure applied to a method prevents unauthorized users and only allows authentic users

  42 . What do you mean by hashing in spring security?
    - Hashing in Spring Security refers to the process of converting sensitive data, such as passwords, into
      irreversible scrambled strings using cryptographic algorithms

  43 . What is AuthenticationManager in Spring Security?
    - AuthenticationManager in Spring Security is responsible for authenticating a user's credentials
    - It validates the user's identity by checking the provided credentials against the stored credentials in the system
    - It acts as the central authentication point in the security framework

  44 . What do you mean by session management in Spring security?
    - Session management in Spring Security refers to the management of user sessions within a web application
    - It involves controlling the lifecycle of sessions, handling session creation, destruction, and tracking session
      attributes

  45 . Can we use REST POST endpoint to handle a REST GET behaviour?
    - Using a GET request to perform actions like creating, updating, or deleting resources is not considered a good
      practice because:
    - Idempotence: GET requests should be idempotent, meaning that making the same request multiple times should have
      the same effect as making it once. Performing actions like creating or modifying data through a GET request
      violates this principle.
    - Caching: GET requests are often cached by browsers and proxy servers, which means that they might be retrieved
      from cache rather than making a new request to the server. This can lead to unintended side effects if the action
      is performed multiple times without the server being aware.
    - Security: GET requests are typically logged by servers and intermediaries, potentially exposing sensitive data or
      actions in the URL parameters.

  46 . What are the difference between SpringBoot and Spring MVC?
    - SpringBoot
        - Spring Boot is a module of Spring for standalone application
        - It provides default configurations to build Spring-powered framework
        - There is no need to build configuration manually
        - There is no requirement for a deployment descriptor
        - It avoids boilerplate code and wraps dependencies together in a single unit
        - It reduces development time and increases productivity
        - Powerful batch processing is provided by Spring Boot
    - SpringMVC
        - Spring MVC is a model view controller-based web applications under the Spring framework
        - It provides ready to use features for building a web application
        - It requires build configuration manually
        - A Deployment descriptor is required
        - It specifies each dependency separately
        - It takes more time in development
        - Spring MVC do not provide powerful batch processing

  47 . SpringBoot oauth2 /oauth/token endpoint body example request and response?
- Request

~~~json
{
  "grant_type": "password",
  "client_id": "client_name",
  "auth_type": "auth_type",
  "secret": "Pass123@"
}
~~~

- Response

~~~json
{
  "access_token": "2YotnFZFEjr1zCsicMWpAA",
  "token_type": "Bearer",
  "expires_in": 3600,
  "scope": "openid email profile",
  "refresh_token": "eyJraWQiOiIxZTlnZGs3IiwiYWxnIjoiUl..."
}
~~~

- Hibernate

  1 . What is Hibernate?
    - Hibernate is one of the most popular Java frameworks that simplify the development of Java application to interact
      with the database
    - It is an ORM tool

  2 . What are the major advantages of Hibernate Framework?
    - Open sourced and lightweight
    - Performance is fast
    - Helps to generate independent queries
    - Provide facilities to create a table
    - Query statistics and database status

  3 . Advantages of using Hibernate over JDBC?
    - Eliminates a lot of boilerplate code
    - Supports inheritance and associations
    - HQL is more object-oriented and closer to java
    - Implicitly provides transaction management
    - It wraps exceptions and throw JDBCExceptions which are unchecked exceptions

  4 . What is an ORM tool?
    - A technique that maps the java object to a database table
    - An ORM tool helps in simplifying data creation, manipulation and access

  5 . Why use Hibernate Framework?
    - It overcomes the exception handling
    - Code portability is easily handled
    - Changing of the database costs a lot when working on JDBC
    - Strengthens the object level
    - Reduces the boilerplate code

  6 . What are the different functionalities supported by Hibernate?
    - ORM tool
    - Uses HQL
    - Supports auto DDL operations
    - Auto primary key generation support

  7 . What are the technologies that are supported by Hibernate?
    - Maven
    - Java J2EE
    - eclipse

  8 . What is HQL?
    - Hibernate Query Language
    - It is an object-oriented query language and is independent of the database

  9 . How to achieve mapping in Hibernate?
    - Association mappings are one of the key features of Hibernate
    - It supports the same associations as the relational database model
        - One-to-one
        - One-to-many
        - Many-to-many
        - Many-to-one

  10 . Mention some important annotations used in Hibernate mapping?
    - javax.persistence.GenerateValue
    - javax.persistence.Column
    - javax.persistence.Table
    - javax.persistence.Entity


- JPA

  1 . What is JPA?
    - Java Persistence API (JPA) is a specification for managing data persistence in Java applications
    - Used to simplify the process of writing code for data persistence by providing a high-level abstraction layer over
      the underlying data storage technology
    - JPA helps in mapping Java objects to relational database tables and allows developers to perform CRUD operations

  2 . What is ORM Framework and how is JPA related to that?
    - An Object-Relational Mapping (ORM) framework is a software tool that allows developers to map object-oriented
      programming language constructs to relational database constructs
    - It provides a layer of abstraction between the application code and the database, allowing developers to work with
      objects and classes rather than SQL queries

  3 . What are some benefits of using an ORM framework like JPA?
    - Increased Productivity: JPA provides a high level of abstraction that allows developers to focus on business logic
      instead of writing SQL queries, thus leads to faster development cycles and fewer errors
    - Portability: JPA abstracts away the details of the underlying database, which makes it possible to switch
      databases without changing the application code
    - Scalability: JPA provides a caching mechanism that can help improve application performance by reducing the number
      of database queries needed to access data. This can help an application scale better as the number of users and
      amount of data grows
    - Maintainability: JPA provides a clear separation between application logic and persistence logic. This makes it
      easier to maintain and modify an application over time

  4 . Can you tell the difference between JPA and Hibernate?
    - JPA provides a standard set of interfaces and annotations for ORM, while Hibernate is a concrete implementation of
      those interfaces and annotations.

  5 . What are entities in JPA? Explain the concept in detail?
    - An entity is a lightweight Java class that represents a persistent data object
    - Entities are used to map Java objects to database tables, where each entity corresponds to a row in the table
    - The most commonly used annotation for defining entities is @Entity, which marks a Java class as an entity
    - JPA also provides annotations for defining relationships between entities, such as @OneToOne, @OneToMany,
      @ManyToOne, and @ManyToMany

  6 . What is JPQL and how is it used in JPA?
    - JPQL stands for Java Persistence Query Language
    - It is a platform-independent object-oriented query language that is used to retrieve data from a relational
      database using Java Persistence API
    - JPQL is similar to SQL (Structured Query Language) in terms of syntax, but instead of operating on tables and
      columns, it operates on JPA entities and their corresponding attributes

  7 . What are the advantages of using JPA over JDBC?
    - Object-Relational Mapping: It offers an Object-Relational Mapping (ORM) framework that enables developers to map
      Java objects to database tables without having to create SQL queries
    - Portability: It is a standardized API that is independent of any specific database implementation. This means that
      applications written using JPA can be easily ported to different databases without having to rewrite the database
      access code
    - Increased Productivity: It offers a higher-level API that is simpler and easier to use than JDBC, thus reducing
      the amount of time that developers spend writing and debugging database access code, and allows them to focus on
      other aspects of the application
    - Improved Performance: It uses a caching mechanism that can enhance performance. This may lead to quicker response
      times and improved scalability
    - Transaction Management: It offers a transaction management system that simplifies the process of managing database
      transactions
    - Object-Oriented Features: It provides support for object-oriented features such as inheritance and polymorphism.
      This allows developers to work with Java objects instead of relational tables, which is easy to maintain

  8 . Difference between JPA Repository and CRUD Repository?
    - JPA Repository extends the functionality of the CRUD Repository by providing additional methods and the ability to
      define custom queries
    - However, if you only need basic CRUD functionality, then using CRUD Repository may be sufficient

  9 . What is a Named Query in JPA? How is it used? And what are the benefits of using this?
    - A named query is a pre-defined query that is given a name and can be used in multiple places in an application
    - It is defined in the entity class using the @NamedQuery annotation and can be used to retrieve entities based on
      specific criteria
    - Benefits are,
        - Re-usability: named queries can be defined once and used multiple times throughout the application
        - Performance: named queries are compiled and cached by the JPA provider, which can improve performance for
          frequently used queries
        - Maintenance: named queries can be easily modified or updated in a central location, rather than scattered
          throughout the codebase

  10 . What is the purpose of EntityManager in JPA?
    - The EntityManager in JPA is the primary interface through which an application interacts with the Persistence
      Context, which is responsible for managing the lifecycle of entity objects and their persistence in the database
    - It is responsible for,
    - Creating and removing entity objects
    - Retrieving entity objects from the database
    - Updating and persisting changes made to entity objects
    - Managing the association between entities
    - Managing the lifecycle of entity objects
    - Executing queries on the database using JPQL
    - Caching entity objects for improved performance

  11 . What is the purpose of the @JoinColumn annotation in JPA?
    - The @JoinColumn annotation in JPA is used to specify a join column for a relationship mapping between two entities
    - The @JoinColumn annotation can be applied to a field or property that is mapped as a foreign key column in the
      database

  12 . What is the purpose of the @Transactional annotation in JPA?
    - The @Transactional annotation in JPA is used to indicate that a method should be executed within a transaction
    - It is used to define the scope of a transaction, which determines when changes made to the database will be
      committed
    - It can be applied at the class or method level

  13 . Difference between JpaRepository.save() and JpaRepository.saveAndFlush() methods?
    - save()
        - It saves an entity to the database and returns the saved entity
        - It returns the saved entity
        - The changes made to the entity are not immediately persisted in the database. They are persisted when the
          current transaction is committed
        - This method is faster than saveAndFlush()
    - saveAndFlush()
        - It saves an entity to the database and immediately flushes the changes to the database
        - It returns the saved entity
        - The changes made to the entity are immediately persisted to the database, regardless of whether the current
          transaction is committed or not
        - This method is slower than save()

- SOLID Principals
    - Single Responsibility Principal
        - A Class should have one and only one responsibility
    - Open/Closed Principal
        - Open for extension and closed for modification
    - Liskov Substitute Principal
        - Subtypes must be substitutable for their base types
    - Interface Segregation Principal
        - The dependency of one class to another one should depend on the smallest possible interface
    - Dependency Inversion Principal
        - Depend upon abstractions, not upon concrete classes

- ACID
    - A:Atomicity
        - The entire transaction takes place at once or doesn't happen at all
        - eg: If T consists of T1 and T2 either T1 and T2 needs to complete or else T will be failed
    - C:Consistency
        - Correctness should be guaranteed
        - eg: Total before T and after T should be equal
    - I:Isolation
        - Transactions occur independently
        - eg: Changes occurring in 1 T should not be visible to other T until committed
    - D:Durability
        - Once the transaction is committed, the updates and modifications to the DB are stored in and written to disk,
          and they persist even if a system failure occurs

- Microservices

  1 . What is microservice architecture?
    - Architecture to develop complex applications
    - Built as a collection of small, independent services
    - Services communicate with each other through APIs
    - Modular and decoupled architecture

  2 . What are the benefits of using a microservice architecture?
    - Scalability
    - Resilience
    - Flexibility, faster development cycles
    - Easier maintenance due to modular independent nature

  3 . What is Spring Cloud, and what are its key features?
    - Spring Cloud is a framework built on top of SpringBoot
    - Used for development and deployment of microservices
    - Features:
        - Service discovery
        - Load balancing
        - Circuit breakers
        - API Gateway
        - Distributed tracing
        - Distributed configurations

  4 . What is service discovery?
    - The process of dynamically locating and communicating with services
    - Service discovery is achieved using Netflix Eureka
    - Allows services to register themselves and discover other services, enabling communication between microservices

  5 . Explain the role of API gateways in microservices?
    - Acts as a single entry point for client requests to microservices
    - Handles dynamic routing, load balancing
    - Support integration with Service Discovery and Authentication

  6 . What is circuit breaking and how is it implemented using Spring cloud?
    - It is a pattern that prevents cascading failures in microservices
    - Circuit breaking is implemented using Resilience4J library
    - Monitors the health of dependent services and, if failures occur, opens the circuit to stop sending requests

  7 . What is load balancing and how it is handled in microservices?
    - Distribution of client requests across multiple instances of a service
    - Spring cloud integrates with load balancers like Cloud Load balancer
    - Handles load distribution without manual configuration

  8 . What are the tools used to aggregate microservices log files?
    - ELK stack
    - Splunk
    - Fluentd

  9 . What is distributed tracing and how is it implemented in Spring Cloud?
    - It is a technique used to track and monitor requests as they flow through multiple microservices
    - It is implemented through integration with tracing system: Zipkin
    - Sleuth used for tracing information across microservices, transferred to Zipkin Server
    - Trace_id is same throughout a single request and span_id is different for every service it passes

  10 . What is the purpose of Spring Cloud Config?
    - It is centralized management of configuration properties for microservices
    - It uses configurations in a version controlled repository and provides a configuration server
    - Can retrieve their configuration information at runtime

  11 . What are the different approaches for inter service communication in microservices?
    - HTTP/ APIs
    - Asynchronous messaging: Kafka, RabbitMQ
    - Event driven

  12 . What is service orchestration and service choreography in microservices?
    - Service Orchestration is a centralized approach where a central component controls and coordinates the execution
      flow of microservices
    - Service Choreography is a decentralized approach where microservices collaborate with each other directly, without
      a central controller

  13 . What is the role of containers and container orchestration platforms?
    - It is lightweight and portable environment for packaging and deploying microservices
    - Consistency across different environments
    - They handle tasks like deployment, scaling, service discovery, load balancing and fault tolerance

- SQL
  1 . What is a database?
    - A database is an organized collection of logically related data

  2 . What is DBMS?
    - DBMS is a software for database management

  3 . Advantages of DBMS?
    - Data security
    - Data quality
    - Faster data accessibility
    - Data Backup
    - Reduced Data Redundancy

  4 . What are the differences between DBMS and RDBMS?
    - DBMS
        - Stores data in a flat file format
        - No relationship between its data
        - Cannot normalize data
        - Preferred for small datasets
    - RDBMS
        - Stores data in tables, consisting rows and columns
        - Stores data in multiple tables and there are relationship between the tables
        - Can normalize data
        - Preferred for larger datasets

  5 . What is query optimization?
    - Finds the best methods for implementing each query
    - Speeds up the process of fetching information from the database
    - Reduces the system resources required to run a query
    - Enhances the performance of a query
    - Use 'Explain Analyze' query plan

  6 . Disadvantages of Data Replication?
    - Data across multiple servers
    - Increases data redundancy

  7 . Advantages of Data Replication?
    - Disaster recovery
    - Improve data accessibility
    - Enhance server performance

  8 . What is normalization and what are the different types of normalization?
    - Organizing data in such a way that it reduces data redundancy
    - It is done by dividing the large table into multiple tables and establishing a relationship between them

  9 . Explain 1NF, 2NF and 3NF?
    - 1NF
        - Each cell in a table must contain only one value
        - No repeating columns or values
    - 2NF
        - Table should be in 1NF and all non-key columns of the tables must depend on the primary key
        - There should not be any partial dependency between its data
        - Occurs when there is a composite key
    - 3NF
        - Table should be in 2NF
        - There should be no transitive dependencies

  10 . What is De-Normalization?
    - Is a technique that is used to add redundant data to a table in order to optimize database access speed

  11 . What are the types of keys in a database?
    - Super key: If you can create a unique value by combining multiple columns or single column
    - Candidate key: Any single column which can uniquely identify value
    - Primary key: A key from candidate keys
    - Alternative key: All the keys except primary key from candidate keys
    - Foreign key
    - Composite key

  12 . Differences between unique key and primary key?
    - Unique Key
        - To uniquely identify a row, but can contain NULL values
        - There can be multiple unique keys
    - Primary Key
        - To uniquely identify a row, cannot contain NULL values
        - Can only contain one primary key or Composite primary key

  13 . Difference between Triggers and Stored Procedures?
    - Triggers
        - Invoked implicitly
        - Special type of stored procedures
    - Stored Procedures
        - Pre-written code
        - Invoked explicitly
        - Can accept inputs and also return a result after execution

  14 . What are indexes?
    - Indexing is a data structure technique created for the performance of a database
    - Indexes provide a quick lookup mechanism for finding specific records within a database table
    - While they improve read performance, they can slow down data modification operations like inserts, updates, and
      deletes
    - Clustered Index
        - Similar records are grouped together and indexes are created for these groups
        - Data is sorted in alphabetical order
        - One clustered index for a table
        - Index points to the block, not the record itself
    - Non Clustered Index
        - Index points to the location where the data is stored
        - There can be multiple Non-Clustered Indexes in the table

  15 . Wht do you understand by sub queries in SQL?
    - Sub query is simply defined as a query inside another query
    - A sub query must always be enclosed in parentheses

  16 . What are the differences between HAVING and WHERE clauses?
    - WHERE
        - Used to filter records in a database
        - Filters the data by individual rows
        - Cannot work with aggregate functions
        - Can use with select, update, delete
    - HAVING
        - Filters based on groups of data
        - Must use the GROUP BY clause
        - Can work with aggregate functions
        - Can only work with select statements

  17 . What are the differences between drop, truncate and delete commands?
    - Truncate
        - Delete all the rows of the table at once, but does not delete the table, DDL syntax
    - Delete
        - Delete existing records from a table, can delete single or multiple records, DML syntax
    - Drop
        - Drop existing records as well as the table, DDL syntax

  18 . What is partitioning?
    - Partitioning is the process of separating data into logical subsets(physical segments)

  19 . Which objects can be partitioned?
    - Tables and indexes can be partitioned
        - Table not partitioned, relevant index partitioned
        - Table partitioned, relevant index not partitioned
        - Table partitioned, relevant index partitioned

  20 . What are the advantages of partitioning?
    - Improved administration because many operations can be carried out on separate partitions
    - Partitions that are no longer required can simply be dropped
    - You can improve the performance of queries if only specific partitions have to be read
    - Partitioning is transparent for the application and does not require any change to SQL queries and DML statements

  21 . What problems can occur in connection with partitioning?
    - Queries that do not contain the partitioning criterion in the WHERE clause, must scan ALL partitions

  22 . How many types of partitioning exist?
    - Range Partitioning
        - Date range
    - List Partitioning
        - Based on a list value
    - Hash Partitioning
        - Hash algorithm
    - Combined Partitioning

  23 . What is vacuum?
    - Vacuuming is a crucial process in postgres that reclaims disk space and improves query performance by removing
      dead and outdated tuples(command: Vacuum FULL)
    - It performs 2 main tasks
        - Freeing up disk space
        - Updating statistics
    - It requires an exclusive lock on the table
    - The pg_stat_progress_vacuum view includes information such as the current table being vacuumed, the number of dead
      tuples found, the number of pages scanned, and the current state of the vacuum operation
    - Configuring vacuum depends on,
        - Amount of data it manages
        - Number of Delete/Updates

  24 . What is the purpose of autovacuum process in postgres?
    - The autovacuum process in postgres is responsible for automatically managing the database's physical storage and
      preventing excessive bloat caused by update and delete operations


- HTTP Status Codes
    - 1xx: Informational codes: Request received and process is continuing

    - 2xx: Successful codes: Successfully received, understood and accepted
        - 200: OK
        - 201: Created
        - 202: Accepted
        - 204: No Content

    - 3xx: Redirection codes: Further actions must be taken in order to complete
        - 301: Moved permanently
        - 302: Found, Temporarily moved
        - 304: Not modified

    - 4xx: Client Errors codes: Request contains incorrect syntax or cannot be fulfilled
        - 400: Bad request
        - 401: Unauthorized
        - 403: Forbidden
        - 404: Not found
        - 405: Method not allowed
        - 408: Request timeout
        - 415: Unsupported media type

    - 5xx: Server Errors codes: Server failed to fulfill the request
        - 500: Internal server error
        - 501: Not implemented
        - 502: Bad gateway
        - 503: Service unavailable
        - 504: Gateway timeout


- REST API

  1 . What are REST api methods?
    - GET: Retrieve data on the server(idempotent and safe)
    - POST: Sends data to the server for processing
    - PUT: Replace a resource identified with a given URL(idempotent but unsafe)
    - DELETE: Resource is deleted(idempotent but unsafe)
    - OPTION: Returns a list of HTTP methods that are supported
    - HEAD: Simply returns metadata about a resource on the server
    - TRACE: Diagnostic, debugging and troubleshooting

  2 . What is meant by idempotent and unsafe?
    - Idempotent means multiple invocations leave the server in the same state
    - Unsafe means that method change the state of a resource on the server

  3 . What are common API architecture styles?
    - SOAP - XML-based and best for enterprise applications
    - REST - Popular, easy-to-implement, HTTP methods, ideal for web services
    - GraphQL - Query language, request specific data, faster responses, clients can request exactly the data they need
    - gRPC(Google Remote Procedure Call) - Suitable for microservices architectures. It uses Protocol Buffers for data serialization
    - WebSocket - Real-time bidirectional data exchange between a client and a server
    - Webhook - Event-driven, HTTP callbacks, asynchronous
    - MQTT(Message Queuing Telemetry Transport) - A lightweight publish-subscribe messaging protocol designed for low-bandwidth, high-latency, or unreliable networks.
    - AMQP(Advanced Messaging Queuing Protocol) - Message oriented middleware reliable for message delivery, routing, and queuing, making it suitable for enterprise integration scenarios
    - SSE(Server Sent Events) - A server-push technology that allows a server to send updates to a client over an HTTP connection in a unidirectional manner

  4 . What are common software architecture patterns?
    - Event Driven: Components communicate through events, ideal for real-time processing.
    - Layered: Organizes the system into layers, each with a specific responsibility, promoting separation of concerns.
    - Monolithic: All functionalities are combined into a single application, suitable for simpler, smaller applications
    - Microservices: The System is divided into independent services, each responsible for a specific function, allowing for scalability and flexibility.
    - MVC: This approach separates the application into three interconnected components, separating internal representations of information from how information is presented and accepted
    - Master-slave: One component (master) controls one or more other components (slaves), commonly used in database replication.

- Kafka

  1 . What is the role of the offset?
    - The role is to identify each message in the partition uniquely
    - In partitions, messages are assigned a unique ID number called the offset

  2 . Can Kafka be used without ZooKeeper?
    - Any client request cannot be serviced if ZooKeeper is down

  3 . In Kafka, why are replications critical?
    - To make sure that the messages are not lost in case of application error or machine failure

  4 . What is a partitioning key?
    - The partitioning key indicates the destination partition of the message within the producer
    - A hashing based partitioner determines the partition ID when the key is given

  5 . What is the difference between kafka and rabbitmq?
    - Kafka
        - 1 million messages per second
        - Message retention up to 30 days
        - Payload size: 1MB limit
        - Massive data/ high throughput cases
        - Can assure the message retain the order in which they are sent
        - Consumers pull the data from brokers
        - Dumb broker/ Smart consumer
        - Scalable because of replication of brokers and partitions(minimum 3 brokers in the cluster)
        - Supports asynchronous
    - RabbitMQ
        - 4K-10K messages per second
        - Message retention acknowledgement based
        - Payload size: no constraints
        - Simple cases/ Lower throughput since each delivery message state is maintained
        - Cannot assure the order of messages
        - Pushing the messages to subscribers
        - Smart broker(responsibility of the producers to ensure delivery of messages) / Dumb consumer
        - No horizontal scalability
        - Supports both asynchronous and synchronous

  6 . What is a partition of a topic in Kafka Cluster?
    - Partition is a single piece of Kafka topic
    - More partitions allow excellent parallelism when reading from the topics
    - The number of partitions is configured based on per topic

  7 . How can you get precisely one messaging during data production?
    - To get precisely one messaging from data production, you have to follow two things:
        - Avoiding duplicates during data production
        - Avoiding duplicates during data consumption(de-duplication)

  8 . What is Zookeeper in Kafka?
    - It is a high performance and open source complete coordination service used for distributed applications adapted
      by Kafka

  9 . Name various components of Kafka?
    - Producer: Produces messages and can communicate to a specific topic
    - Consumer: One who consumes the published data and subscribes to different topics
    - Broker: Act as a channel between consumers and producers

  10 . Why is Kafka so popular?
    - Kafka builds real-time data pipelines responsible for data processing and transferring between different systems
      that need to use it

  11 . What is a consumer group?
    - When more than one consumer consumes a bunch of subscribed topics jointly, it forms a consumer group

  12 . How is a Kafka Server started?
    - To start a Kafka Server, the Zookeeper has to be powered up by using the following steps:
        - bin/zookeeper-server-start.sh config/zookeeper.properties
        - bin/kafka-server-start.sh config/server.properties

  13 . Discuss the architecture of Kafka?
    - A cluster in Kafka contains multiple brokers as the system is distributed
    - The topic in the system is divided into multiple partitions
    - Each broker stores one or multiple partitions so that consumers and producers can retrieve and publish messages
      simultaneously

  14 . What are the benefits of using Kafka?
    - Scalable: Data is streamlined over a cluster of machines and partitioned to enable large information
    - Fast: Kafka has brokers which can serve thousands of clients
    - Durable: Message is replicated in the cluster to prevent record loss. whenever the consumer gets up, all messages
      will be there
    - Distributed: Provides robustness and fault tolerance
    - Loose Coupling: Neither service knows about each other
    - Flexibility: The sender of a message has no idea who is going to consume it

  15 . How can the Kafka cluster be rebalanced?
    - If several nodes in a topic are already equal to the replication factor, adding disks will not help in
      re-balancing
    - Kafka-reassign-partitions command is recommended after adding new hosts

  16 . What is a broker in Kafka?
    - Is used to refer to a server in Kafka cluster

  17 . What is meant by SerDes?
    - SerDes (Serializer and Deserializer) materializes the data whenever necessary for any Kafka stream when SerDes is
      provided for all record and record values

  18 . What are the benefits of creating Kafka Cluster?
    - When we expand the cluster, the Kafka cluster has zero downtime
    - The cluster manages the replication and persistence of message data
    - The cluster also offers strong durability because of cluster centric design

  19 . Who is the producer in Kafka?
    - The producer is a client who publishes and sends the record
    - The producer sends data to the broker service
    - The producer applications write data to topics that are ready by consumer applications

  20 . What is fault tolerance?
    - There is a high probability of one of the nodes failing
    - Fault tolerance means that the system is protected and available even when nodes in the cluster fail

  21 . What is meant by partition offset?
    - The offset uniquely identifies a record within a partition
    - Topics can have multiple partition logs that allow consumers to read in parallel
    - Consumers can read messages from a specific as well as an offset print of their choice

  22 . Kafka Broker and Topic?
    - A Kafka broker is a server in the cluster, this will receive and send the data
    - Each Kafka broker is identified with an ID (integer)
    - Topics are logical channels or categories to which messages are published
    - Topics can be divided into partitions for scalability and parallelism
    - Each broker will have certain topic partitions
    - All the topic partitions data is Distributed across all brokers(load balanced)

  23 . Kafka Architecture
    - Cluster -> Brokers(1 Leader, followers) > Topics > Partitions > Offsets > Event/Message
    - Offset:Event/Message = 1:1
    - Replication is implemented at partition level
    - Every partition has one server acting as a leader and the rest of them as followers
    - Leader handles all reads and writes and followers replicate them
    - Producer publishes a message to leader and leader appends the message to its offset and increments the offset
    - Kafka cluster is a system that comprised of different brokers, topics and partitions
    - If the consumer is behind during message processing, it has the option to reset the offset it was reading from and
      read again
    - If you have only a single broker it does not give you the full benefit of replication in kafka
    - We can have infinite number of partitions with infinite offset values
    - To manage and coordinate kafka brokers, maintain metadata, leader election we need Zookeeper
    - Brokers are stateless, hence for maintaining the cluster state we can use zookeeper
    - No kafka server can run without a zookeeper server
    - We can decide which partition to send the message, but kafka decides the offset
    - Only 1 consumer can read from 1 partition for order maintenance
    - In the event of a leader or a broker failure, kafka ensures quick leader election and data replication from
      in-sync replicas(ISR)
    - The number of partitions in a topic determines the maximum parallelism of consumption

  24 . What is replication?
    - Kafka provides fault tolerance through data replication
    - Each partition in Kafka can have one or more replicas
    - Replicas are copies of the partition's data stored on different brokers
    - Replication ensures that if a broker fails, partitions can be served from replicas on other brokers

  25 . What is the use of consumer groups?
    - To allow multiple consumers to divide the work of consuming messages from multiple partitions
    - Each consumer in the group is assigned one or more partitions, ensuring that every partition is consumed by only
      one consumer within the group

  26 . What is replication-factor?
    - The number of copies of the data that will be maintained across different brokers
    - A higher replication factor ensures higher availability and fault tolerance

  27 . What are partitions?
    - This parameter defines the number of partitions into which the topic will be divided
    - More partitions can improve throughput and enable more parallelism in consuming the topic

  28 . Different ways consumers consume from topics?
    - Single consumer read data from one partition
        - Consumers in multiple consumer groups can also read from single partition when they have different group ids
        - They maintain different offset values
    - Single consumer read data from two partitions
        - When a consumer group subscribes to a topic, Kafka uses a partition assignment strategy to distribute the
          partitions among the consumers
        - If there are more partitions than consumers in the group, some consumers will be assigned more than one
          partition
    - Multiple consumers read data from one partition
        - Each consumer in the group is assigned a subset of the partitions to consume from, ensuring that each
          partition is consumed by only one consumer within the group
        - Multiple consumer groups can read from the same partition simultaneously
    - Single consumer read data from one partition with one replication
        - A replication factor of 1 means that there is only one copy of the data, stored on a single broker
        - If the broker holding the data fails, the data becomes unavailable until the broker is restored
        - Less overhead in terms of data replication

  29 . What is Kafka re-balancing?
    - Re-balancing is a process where the distribution of partition ownership among consumer group members is adjusted
    - This process ensures that each partition of a Kafka topic is assigned to a single consumer within a consumer group
    - Re-balancing can be triggered,
        - A new consumer joins the consumer group kafka needs to redistribute the partitions so that the new consumer
          can also start consuming data
        - When an existing consumer crashes and shut down, kafka needs to reassign the partitions that were previously
          assigned to this consumer to other remaining consumers
        - When topic partitions are added or removed
        - Any change to consumer groups configuration


- React

  1 . Differentiate between Real DOM and Virtual DOM?
    - Real DOM
        - It updates slow
        - Can directly update HTML
        - Creates a new DOM if element updates
        - DOM manipulation is very expensive
        - Too much of memory wastage
    - Virtual DOM
        - It updates faster
        - Can’t directly update HTML
        - Updates the JSX if element updates
        - DOM manipulation is very easy
        - No memory wastage

  2 . What is React?
    - React is a front-end JavaScript library developed by Facebook in 2011
    - It follows the component based approach which helps in building reusable UI components
    - It is used for developing complex and interactive web and mobile UI

  3 . What are the features of React?
    - It uses the virtual DOM instead of the real DOM
    - It follows uni-directional data flow or data binding
    - It uses SSR and CSR

  4 . List some of the major advantages of React?
    - It increases the application’s performance
    - Because of JSX, code’s readability increases
    - Using React, writing UI test cases become extremely easy

  5 . What are the limitations of React?
    - React is just a library, not a full-blown framework
    - Its library is very large and takes time to understand
    - Coding gets complex as it uses inline templating and JSX

  6 . How does virtual DOM works?
    - Whenever any underlying data changes, the entire UI is re-rendered in Virtual DOM representation
    - Then the difference between the previous DOM representation and the new one is calculated(virtual DOM and Real
      DOM)
    - Once the calculations are done, the real DOM will be updated with only the things that have actually changed

  7 . Why can’t browsers read JSX?
    - Browsers can only read JavaScript objects but JSX in not a regular JavaScript object.
    - To enable a browser to read JSX, first, we need to transform JSX file into a JavaScript object using JSX
      transformers like Babel and then pass it to the browser

  8 . How is React different from Angular?
    - React
        - Only the View of MVC
        - Uses virtual DOM
        - One-way data binding(from parent to children)
        - Created by facebook
        - Needs an additional set of tools for testing
        - Both supports CSR and SSR
    - Angular
        - Complete MVC
        - Uses real DOM
        - Two-way data binding
        - Created by Google
        - Complete tests solution within a single tool
        - Both supports CSR and SSR

  9 . What is the purpose of render() in React?
    - Each React component must have a render() mandatory.
    - It returns a single React element which is the representation of the native DOM component.

  10 . What is Props?
    - They are read-only components which must be kept pure and immutable
    - They are always passed down from the parent to the child components throughout the application
    - Needs to destruct props first

  11 . What is a state in React and how is it used?
    - States are the source of data and must be kept as simple as possible and it is mutable
    - Used to create dynamic and interactive components
    - Use the useEffect to initialize first

  12 . Differentiate between states and props? State | Props
    - Receive initial value from parent component Yes | Yes
    - Parent component can change value No | Yes
    - Set default values inside component Yes | Yes
    - Changes inside component Yes | No
    - Set initial value for child component Yes | Yes
    - Changes inside child components No | Yes

  13 . How can you update the state of a component?
    - State of a component can be updated using setState()

  14 . What are the different phases of React component’s lifecycle?
    - Mounting: This is the phase when the component is about to start its life journey and make its way to the DOM
    - Updating: Once the component gets added to the DOM, it can potentially update and re-render only when a prop or
      state change occurs
    - Unmounting: This is the final phase of a component’s life cycle in which the component is destroyed and removed
      from the DOM

  15 . Explain the lifecycle methods of React components?
    - componentWillMount()
    - componentDidMount()
    - componentWillReceiveProps()
    - shouldComponentUpdate()
    - componentWillUpdate()
    - componentDidUpdate()
    - componentWillUnmount()

  16 . What is an event in React?
    - Events are the triggered reactions to specific actions like mouse hover, mouse click, key press
    - Handling these events are similar to handling events in DOM elements

  17 . What are synthetic events in React?
    - Synthetic events are the objects which act as a cross-browser wrapper around the browser’s native event
    - They combine the behavior of different browsers into one API

  18 . What do you understand by refs in React?
    - Refs is the short for References in React
    - It is an attribute which helps to store a reference to a particular React element or component
    - They come in handy when we need DOM measurements or to add methods to the components

  19 . List some of the cases when you should use Refs?
    - When you need to manage focus, select text or media playback
    - To trigger imperative animations
    - Integrate with third-party DOM libraries

  20 . Difference between controlled and uncontrolled components?
    - Controlled
        - They do not maintain their own state
        - Data is controlled by the parent component
        - They take in the current values through props and then notify the changes via callbacks
    - Uncontrolled
        - They maintain their own state
        - Data is controlled by the DOM
        - Refs are used to get their current values

  21 . What are Higher Order Components(HOC)?
    - HOC are custom components which wrap another component within it
    - Allow developers to reuse code logic in their projects
    - Pure components
    - HOCs can be used to add shared features, like authentication and data retrieval, logging to various components

  22 . What are Pure Components?
    - Pure components are class components that extend React.PureComponent
    - Provide performance optimizations by preventing unnecessary re-renders when the data is same
    - Simplify the code
    - A “pure component” in React is a component that updates only when its properties or state have changed
    - In contrast, a “non-pure component” re-renders each time the parent component re-renders, regardless of whether
      its props or state have changed

  23 . What were the major problems with MVC framework?
    - DOM manipulation was very expensive
    - Applications were slow and inefficient
    - There was huge memory wastage

  24 . Explain Flux?
    - Flux is an architectural pattern which enforces the uni-directional data flow
    - It controls derived data and enables communication between multiple components using a central Store which has
      authority for all data

  25 . What is Redux?
    - Redux is a state container for JavaScript applications and is used for the entire applications state management

  26 . What are the three principles that Redux follows?
    - Single source of truth: The state of the entire application is stored in an object/ state tree within a single
      store
    - State is read only: The only way to change the state is to trigger an action, an action is a plain JS object
      describing the change
    - Changes are made with pure functions: Pure functions are those whose return value depends solely on the values of
      their arguments

  27 . List down the components of Redux?
    - Action – It’s an object that describes what happened
    - Reducer – It is a place to determine how the state will change
    - Store – State/ Object tree of the entire application is saved in the Store
    - View – Simply displays the data provided by the Store

  28 . How are Actions defined in Redux?
    - Actions in React must have a type property that indicates the type of ACTION being performed
    - Defined as String constants
    - Actions are created using the functions called Action Creators
        ~~~js
        function addTodo(text) {
          return {
            type: ADD_TODO,    
            text    
          }
        }
        ~~~
  29 . Explain the role of Reducers?
    - Reducers are pure functions which specify how the application’s state changes in response to an ACTION
    - Reducers work by taking in the previous state and action, and then it returns a new state

  30 . How is Redux different from Flux?
    - Flux
        - There are multiple stores
        - State is mutable
        - All the stores are disconnected and flat
        - The Store contains state and change logic
    - Redux
        - There is only one store
        - State is immutable
        - Single store with hierarchical reducers
        - Store and change logic are separate

  31 . What are the advantages of Redux?
    - Predictability of outcome
    - Maintainability
    - Server-side rendering
    - Developer tools
    - Community and ecosystem
    - Organization

  32 . What is React Router?
    - React Router is a powerful routing library built on top of React, which helps in adding new screens and flows to
      the application

  33 . Why is switch keyword used in React Router v4?
    - The ‘switch’ keyword is used when you want to display only a single route to be rendered amongst the several
      defined routes
    - The <switch> tag when in use matches the typed URL with the defined routes in sequential order
    - When the first match is found, it renders the specified route. Thereby bypassing the remaining routes

  34 . List down the advantages of React Router?
    - A Router can be visualized as a single root component (<BrowserRouter>) in which we enclose the specific child
      routes (<route>)
    - No need to manually set History value: In React Router v4, all we need to do is wrap our routes within
      the <BrowserRouter> component.

  35 . What is the purpose of the mapStateToProps function in Redux?
    - The mapStateToProps function in Redux is a way for a component to access the current state of the store and update
      its props accordingly
    - It does this by taking the current state of the store as an argument and returning an object that maps the state
      to the props of the component
    - This function is typically defined as a separate function outside the component and is passed as an argument to
      the connect function

  36 . Explain the difference between server-side rendering and client-side rendering in React?
    - SSR
        - Server-side rendering (SSR) is when the initial render of a React application is done on the server
        - The server generates the HTML for the initial state of the application and sends it to the browser
        - Benefits of SSR
            - Improved performance for search engines and users on slow connections
            - Faster time-to-first-byte
    - CSR
        - Client-side rendering (CSR) is when the React application is rendered entirely in the browser, using
          JavaScript
        - The browser requests the JavaScript bundle from the server and then renders the components on the client side
        - Benefits of CSR
            - Faster Load times for users on fast connections
            - More responsive UI

  37 . How do you handle data persistence in a React application?
    - Local storage: This allows you to store key-value pairs in the browser’s local storage, which can be retrieved
      even after the user closes the browser or restarts their device.
    - Cookies: Cookies are small pieces of data that are stored in the user’s browser and can be accessed by the website
      on subsequent visits.
    - Server-side storage: You can also store data on a remote server using an API or a database such as MySQL,
      Postgresql etc
    - Redux: State management libraries like Redux can be used to manage and persist application state across different
      components and sessions

  38 . What is the difference between a stateless component and a stateful component in React?
    - A stateless component, also known as a “dumb” or “presentational” component, is a component that does not maintain
      its own internal state
    - It receives data and callbacks through props (short for properties) and only renders the UI based on those props
    - A stateful component, also known as a “smart” or “container” component, is a component that maintains its own
      internal state
    - It can handle internal state updates and side effects, and may also manage the state of other child components

  39 . How do you handle optimization in a large React application?
    - Use the React Developer Tools to identify and fix performance bottlenecks
    - Use PureComponent and memo instead of Components
    - Use the useEffect hook to handle side effects
    - Use the useMemo hook to memoize expensive calculations
    - Lazy loading
    - Optimize the loading time of your application by using techniques like code minification, compression, and caching

  40 . What is the purpose of the combineReducers function in Redux?
    - The combineReducers function in Redux is used to combine multiple individual reducers into a single root reducer
    - This root reducer is then passed to the createStore function to create the Redux store

  41 . How do you handle testing in a React application?
    - React Testing Library is a great tool for testing React components
    - It’s a set of helpers that let you test React components without relying on their implementation details

  42 . What is the difference between a functional component and a class component in React?
    - In React, a functional component is a plain JavaScript function that takes in props and returns a React element
    - A class component is a JavaScript class that extends React.Component and has a render method that returns a React
      element

  43 . Explain the concept of a Context in React?
    - In React, context is a way to share data that is considered “global” for a component tree
    - It allows you to pass data through the component tree without having to pass props down manually at every level
    - A component that needs to access the context data can consume it by using the useContext hook

  44 . What is the difference between state and props in React?
    - State
        - State is mutable
        - State can be changed by the component
        - State is initialized and managed by the component
    - Props
        - Props are immutable
        - Props are read only
        - Props are passed from parent to child component

  45 . Explain the concept of a Hook in React?
    - Hooks are a new feature in React that allows us to add state and other React features to functional components
    - Hooks are named functions that start with the word use and allow us to reuse stateful logic across components
      without having to write a class component

  46 . How do you handle localization in a React application?
    - Handling localization in a React application typically involves creating translated versions of your text content
      and displaying the appropriate version based on the user’s preferred language
    - One way to handle localization in a React application is to use a library such as react-i18next
    - This library provides a set of tools for internationalization and localization, including the ability to define
      translation keys and their corresponding translations, as well as providing a way to switch between languages at
      runtime

  47 . Explain the concept of a Custom Hook in React?
    - A Custom Hook in React is a JavaScript function that lets you extract state logic and behavior out of a component,
      and reuse it across multiple components
    - Custom Hooks allow you to abstract away state and behavior that is common across your application into a reusable
      piece of code

  48 . How do you handle accessibility in a React application?
    - Handling accessibility in a React application involves making sure that your application can be used by as many
      people as possible, including those with disabilities
    - This can be achieved through various techniques, including:
        - Semantic HTML: Use semantic HTML elements, such as \<button\>, \<nav\>, and \<header\>, to clearly define the
          structure and purpose of your content
        - Accessible Props: Use accessible props, such as aria-label, role, and tabIndex, to provide additional
          information to assistive technologies, such as screen readers
        - Keyboard Navigation: Ensure that all functionality can be accessed using a keyboard, and that keyboard focus
          is managed correctly
        - Color Contrast: Make sure that the contrast between the text and the background is high enough to be readable
          by people with color blindness or low vision.
        - Alternative Text: Provide alternative text for images, videos, and other non-text elements to ensure that
          information is accessible to screen reader users.
        - Screen Reader Testing: Test your application with screen readers and other assistive technologies to identify
          and fix any accessibility issues.

  49 . What is the difference between a reducer and an action in Redux?
    - Action is a plain JavaScript object that describes the change that should be made to the state of the application
    - It has a type property that defines the type of action being performed, and a payload property
    - A reducer is a pure function that takes the current state of the application and an action, and returns the next
      state of the application

  50 . How do you handle data validation in a React application?
    - PropTypes
    - Custom validation functions
    - Third party libraries

  51 . Explain the concept of a Thunk in Redux?
    - A Thunk in Redux is a function that returns another function instead of a plain action object
    - It’s used to perform asynchronous operations and dispatch multiple actions
    - Thunks allow you to write action creators that return a function instead of an action

  52 . How do you handle security in a React application?
    - Input validation: Validate all user inputs on the client and server side to prevent any malicious data from being
      processed
    - Authenticating and authorizing users: Use a secure authentication mechanism such as JSON Web Tokens (JWT) to
      ensure that only authorized users can access sensitive data
    - Storing sensitive data securely: Do not store sensitive information such as passwords and credit card numbers in
      local storage, use encrypted storage instead
    - Implementing HTTPS
    - Keeping dependencies up-to-date
    - Regular security audits

  53 . Explain the concept of a Provider in React-Redux?
    - The “Provider” in React-Redux is a higher-order component that wraps your React application and provides it with
      the ability to access the Redux store
    - It allows you to pass the store down to your components using context, without having to manually pass it down as
      props through every level of the component tree

  54 . How do you handle code splitting in a React application?
    - Dynamic Imports: Dynamic imports allow you to load a component lazily only when it is needed
    - Webpack Bundle Analyzer: This is a tool that provides a visual representation of the code and its size. You can
      use this tool to identify the large chunks of code that can be split into smaller chunks and loaded lazily

  55 . Explain the concept of a Sagas in Redux?
    - A Saga in Redux is a way to manage side effects in a Redux application
    - It is implemented as a middleware using generator functions in JavaScript and runs in the background, separate
      from the main thread of your application

  56 . How do you handle code optimization in a large React application?
    - Code splitting
    - Lazy loading
    - Use of a bundler such as Webpack
    - Use of caching
    - Use of efficient algorithms and data structures
    - Regular performance monitoring and profiling
    - Use of optimization techniques such as memoization

  57 . Explain the concept of a Middleware in Redux?
    - Middleware is a software component that sits between the store and the action dispatching process to add
      additional functionality, such as logging, crash reporting, handling asynchronous actions
    - It allows you to extend the store’s behavior without modifying the store itself

  58 . What is the difference between a React class and Functional component?
    - React Class
        - JavaScript classes that extend the React.Component class, have a render method, and can have additional
          lifecycle methods and state
    - Functional Component
        - Plain JavaScript functions that return the component’s JSX markup, and that they can use state and other React
          features with hooks

  59 . Explain the concept of a Memoization in React?
    - Memoization is a technique used to optimize the performance of a component by avoiding unnecessary re-renders
    - It involves caching the results of a component’s render so that if the inputs (props) to the component do not
      change, the cached result can be reused, instead of re-computing the result

  60 . How do you connect a React component to a Redux store?
    - To connect a React component to a Redux store, you use the connect function from the react-redux library
    - The connect function connects the component to the Redux store, allowing it to access the state and dispatch
      actions

  61 . Can you differentiate between mapStateToProps and mapDispatchToProps?
    - mapStateToProps connects parts of the Redux state to a React component's props, while mapDispatchToProps connects
      Redux actions to a React component's props.

- CSS and SCSS

  1 . Why SCSS is preferred over CSS?
    - Variables: SCSS allows you to define variables which can be reused throughout your stylesheets
    - Nesting: SCSS allows for nesting of CSS rules, which can make your stylesheets more organized and easier to read
    - Mixins: SCSS supports mixins, which are reusable blocks of styles
    - Functions: SCSS allows for the creation of functions, enabling more complex calculations and transformations
    - Extensions: SCSS provides additional features and syntax that CSS does not have, such as the @extend directive,
      which allows one selector to inherit styles from another.

~~~scss
// Define variables
$primary-color: #3498db;
$secondary-color: #2ecc71;

// Use variables
.btn-primary {
  background-color: $primary-color;
  color: white;
}
----------------------------------
// Nesting example
.navbar {
background-color: #333;
  ul {
    list-style: none;
    padding: 0;
  }
}
----------------------------------
// Define a mixin
@mixin border-radius($radius) {
  -webkit-border-radius: $radius;
  -moz-border-radius: $radius;
  border-radius: $radius;
}

// Use the mixin
.btn {
  @include border-radius(5px);
}
----------------------------------
// Define a function
@function em($px, $base) {
  @return ($px / $base) * 1em;
}

// Use the function
h1 {
  font-size: em(24px, 16px); // Assuming a base font size of 16px
}
----------------------------------
// Extending
%text-style {
  font-family: Arial, sans-serif;
  font-size: 14px;
  color: #333;
}

// Use the placeholder selector with @extend
.custom-text {
  @extend %text-style;
  font-weight: bold;
}
~~~

- Javascript