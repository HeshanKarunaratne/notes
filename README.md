# Interview Preparation

- Core Java

    1 . Why Java is not 100% Object oriented?
    - Because of Primitive data types which are not objects eg: boolean, byte, char, int, float, double, long, short
    - We can use wrapper classes to wrap primitive data types into an object
    - Java allows the creation of static methods which are not tied to specific instance of a class
    - Lack of multiple inheritance which is a characteristic of some OOP languages
    
    2 . Why pointers are not used in java?
    - They are unsafe, increases the complexity of the program, JVM is responsible for memory allocation thus pointers are not needed in java

    3 . What is JIT compiler in Java?
    - Just In Time compiler which is a component of JVM that dynamically compiles byte codes into machine codes and to improve performance in java application
    
    4 . Why String is immutable in java?
    - Thread safe
    - Immutability allows strings to be cached and reused, improving performance
    - Immutable strings prevent unintended changes, enhancing security
    - String literals are kept inside String pool, and it requires Strings to be immutable. If there is a String in the pool it will get referenced otherwise a new String object will be created and will get a reference
    
    5 . What is a marker interface?
    - A marker interface is an empty interface. eg: Serializable, Cloneable(To get an exact duplicate object)
    - By implementing a marker interface classes will get additional behaviour at compile time
    - You can create your own marker interface, but need to do some customizations to the JVM
    
    6 . Can you override a private or static method in Java?
    - Cannot override a private or static methods in java
    - We cannot override a private method in subclass because it is not accessible there
    - For static methods if we create a similar method with same return type and same method arguments in child class then it will hide the superclass method, also known as method hiding

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
    - JDK: Java Development Kit which includes JRE, tools for compiling, debugging and running the java programs, along with libraries and documentation
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
    - Lists are typically implemented using arrays or linked lists, while sets are implemented using hash table and trees
    - Lists are generally more efficient for access by index, while sets are optimized for membership testing and uniqueness

    17 . Difference between ArrayList and LinkedList
    - ArrayList internally uses a dynamic array to store elements, LinkedList internally uses a doubly linked list to store elements
    - Manipulation of ArrayList is slow, while LinkedList is faster
    - ArrayList consumes less memory, while LinkedList consumes more memory since it stores references to previous and next elements
    - ArrayList implements List interface only, LinkedList implements List and Deque interfaces
    - ArrayList provides fast access to elements by index, while in LinkedList accessing elements by index is slower
    
    18 . Difference between Collections and Streams
    - Collections are concrete data structures like lists, sets and maps, while Streams are not data structures
    - Collections are used to store and group the data while streams are used to perform filtering,matching,mapping operations(aggregate operations)
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
        1. Abstraction: Show only what is necessary, hiding the complexity. It helps in reducing programming complexity and effort by providing simplified view of objects
            - Abstract methods do not have an implementation, it only has method signatures
            - If a class have abstract method then the class needs to be declared abstract
            - An abstract class does not necessarily have an abstract method
            - Cannot be instantiated but abstract classes can have constructors: constructor can only be called during constructor chaining
            - Can have static methods and final methods
            - Abstract class implements interfaces, but it does not need to implement all methods
            - Abstract classes cannot be final because making an abstract class final will stop the abstract class from being extended

        2. Polymorphism: Objects of different classes treated as objects of a common superclass, it enables methods to do different things based on the object that they are acting upon
            - There are 2 types of polymorphism
                1. Static polymorphism(Overloading)
                2. Dynamic polymorphism(Overriding)
        
        3. Inheritance: Where a class(child) inherits properties and behaviours from another class(parent)
            - It's implemented using the extends
            - Inheritance establishes an "IS-A" relationship between classes

        4. Encapsulation: Is bundling of data and methods inside a single unit or class
            - To hide the internal state of an object and only allow access through public methods
            - Use private access modifier for fields to restrict direct access, and public methods to manipulate or access the fields
            - Getters and setters are typical encapsulation techniques used to control access to object fields
    
    23 . What is a class and an object?
    - A class is a blueprint of an object, it defines the attributes and behaviours that objects of that type will have
    - An object is an instance of a class with its own unique set of attributes and behaviours
    
    24 . Is-A relationship and Has-A relationship?
    - Whenever one class inherits another class it is called an Is-A relationship(extends)
    - Whenever an instance of one class has a reference to an instance of another class or same class it is known as Has-A relationship
    
    25 . What is method overriding and overloading?
    - Overloading is same method name with different signatures, return types can be same or different
    - Overriding is same method name with same signature, need to have parent child relationship and any method in parent class can be overridden in child class
    
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
    - If we want to call one constructor from other we use this() method. Based on the number of parameters we pass appropriate this() method is called
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
    - In any programming language source code is compiled in to executable code. When javac compiles a java program it generates an executable file called .class file.
    - .class file contains byte codes. Byte codes are interpreted only by JVM
    - We can execute this byte code in any platform and this makes Java platform independent
    
    33 . Difference between this() and super() in java ?
    - this() is used to access one constructor from another with in the same class while super() is used to access superclass constructor. Either this() or super() exists it must be the first statement in the constructor.
    
    34 . Explain about instanceOf operator in java?
    - \<reference expression> instanceOf \<destination type>: will return true if reference is an instance of destination type
    - There will be a compile time check, so that if it's not a subtype then compile time error will be shown
    
    35 . Can we define package statement after import statement in java?
    - We can’t define package statement after import statement in java. package statement must be the first statement in source file.
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
        - protected: Can access in same class, same package subclass, same package non subclass, different package subclass only
        - default: Can access in same class, same package subclass, same package non subclass only
        - public: Can access in same class, same package subclass, same package non subclass, different package subclass, different package non subclass
    
    39 . What is an error in Java?
    - Error is the subclass of Throwable class in java
    - Exceptions which cannot be recovered are called as errors in java
    - They cannot be handled by the application code, and they are not meant to be caught or handled using exception handling mechanisms like try-catch blocks
    - They are caused by problems outside the control of the application, such as system failures or resource exhaustion
    - ex: OutOfMemoryError, StackOverflowError
    
    40 . Can we have try block without catch block?
    - Each try block requires at-least one catch block or finally block
    
    41 . What is checked and unchecked Exception in Java?
    - Checked Exception(Compile time exception)
        1. All the subclasses of Throwable except RuntimeException and its subclasses are checked Exception
        2. Checked Exception should be thrown with keyword throws or provided try catch block else program would not compile
        3. Examples
            - FileNotFoundException: Occurs when a file specified cannot be found by a FileInputStream or a RandomAccessFile
            - IOException: A broad exception indicating an I/O problem, such as the failure of reading from or writing to a file
            - SQLException: Indicates a problem accessing a database through JDBC
            - ClassNotFoundException: Occurs when the specified class is not found by the ClassLoader
            - InvocationTargetException
    - Unchecked Exception
        1. All subclasses of RuntimeException are called unchecked Exception
        2. Program compiles even if we do not catch the exception or throws the exception
        3. Examples
            - ArithmeticException: Performing arithmetic operations that result in an error, like dividing by zero
            - IndexOutOfBoundsException: Thrown when attempting to access an array element at an index that is outside the bounds of the array
            - NullPointerException: Occurs when you try to access or manipulate an object reference that has a null value
            - NumberFormatException: Arises when attempting to convert a string to a numeric type, but the string does not contain a valid numeric value
            - UnsupportedOperationException
    
    42 . Explain the importance of finally over return statement?
    - 'finally' block is more important than return statement when both are present in a program
    - For resource cleanup
    - Guaranteed execution
    - Centralized cleanup code in one place
    - 'finally' will not work in JVM shutdowns
    
    43 . Explain when ClassNotFoundException will be raised ?
    -  Occurs when the JVM tries to load a class dynamically at runtime using Class.forName() or ClassLoader.loadClass(), but the specified class cannot be found in the classpath
    - This can occur due to a missing jar or classpath issue
    - This is a checked exception which occurs at runtime
       
    44 . Explain when NoClassDefFoundError will be raised ?
    - JVM tries to load the class but no definition for that class is found. The class may exist at compile time but unable to find at runtime
    
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
    - Use synchronized methods in Java when you need to ensure thread safety by allowing only one thread to access the method at a time
    - Synchronized methods are used to prevent concurrent access to critical sections of code, ensuring data consistency in multithreaded environments
    
    49 . Can we use synchronized block for primitives?
    - Synchronized blocks are applicable only for objects
    
    50 . What are daemon threads in java?
    - Daemon threads are threads which run in background. These are service threads and works for the benefit of other threads. 
    - Garbage collector is one of the good example for daemon threads
    
    51 . What are nested classes in java?
    - Class declared with in another class is defined as nested class
        1. Static nested class
        2. Non-static nested class
    
    52 . What are inner classes or non-static nested classes in java?
    - Nested classes without any static keyword declaration in class definition are defined as non-static nested classes. Generally non-static nested classes are referred as inner classes
    - There are 4 types of Inner classes
        1. Local Inner Class: A class defined within a method of another class. It can access all members of the enclosing class and local variables of the enclosing method
        2. Member Inner Class: A class defined at the member level of another class. It has access to all members of the enclosing class, including private members
        3. Static Nested Inner Class: A static nested class defined within another class. It cannot access non-static members of the outer class directly
        4. Anonymous Inner Class: A class defined without a name. It's typically used for instantiating interfaces or extending classes
    
    53 . Will the compiler creates a default constructor if I have a parameterized constructor in the class?
    - No compiler won’t create default constructor if there is parameterized constructor in the class. 
    - For example if I have a class with no constructors, then compiler will create default constructor
    
    54 . Can Static methods access instance variables in java?
    - No. Instance variables can’t be accessed in static methods. When we try to access instance variable in static method we get compilation error
   
    55 . How many times finalize method will be invoked ? who invokes finalize() method in java?
    - Finalize() method will be called only when object is eligible for garbage collection
   
    56 . Explain about transient variables in java?
    - To save the state of an object to persistent state we use serialization. If we want a field or variable in the object not to be saved, then we declare that variable or field as transient
   
    57 . Can we define static methods inside interface?
    -  Yes we can define static methods in interfaces but cannot override it
    
    58 . Define interface in java?
    -  Interface is collection of abstract methods and constants. An interface is also defined as pure or 100 percent abstract class.Interfaces are implicitly abstract whether we define abstract access modifier or not.
   
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
      - Immediately throw a ConcurrentModificationException if the underlying collection is modified structurally while iterating
    - Fail safe
      - Fail-safe iterators work on the cloned copy of the underlying collection, ensuring that modifications to the collection don't affect ongoing iterations
      - These iterators do not throw exceptions if the collection is modified during iteration
   
    64 . What is serialization in java?
    - Serialization is the process of converting an object in to bytes, so that it can be transmitted over the network,or stored in a flat file and can be recreated later. 
    - Serialized object is an object represented as sequence of bytes that includes objects data, object type, and the types of data stored in the object.
   
    65 . How to make object serializable in java?
    - Our class must implement serializable interface. If our object contains other objects those class must also implement serializable interface.
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
    - As operations complete, the count is decremented using the countDown() method. When the count reaches zero, waiting threads are released

    71 . What is CyclicBarrier?
    - Allows fixed number of threads that must wait for each other to reach a common point before continuing execution
  
    72 . What are the types of inheritance in Java?
    - Single level: Only one class is derived from the parent class
    - Multi level: One class inherits the features from a parent class and the newly created subclass becomes the base class for another new class 
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


- Spring
    
    1 . Explain Inversion Of Control, Dependency Inversion, Dependency Injection concepts in Spring?
    - Inversion Of Control(IoC):
        1. Control of object(beans) creation and management is shifted from the application itself to an external container or framework(Spring IoC container is responsible)
        2. The container manages the lifecycle of these beans and handles their dependencies, ensuring that the right dependencies are injected into the right places
        3. Overall architecture becomes more flexible and maintainable
        4. This allows for greater flexibility, easier testing and decoupling of components
    - Dependency Inversion(DI):
        1. High-level modules should not depend on low-level modules. Both should depend on abstractions
        2. This is achieved through interfaces or abstract classes, allowing for loose coupling between components
    - Dependency Injection:
        1. A design pattern used to implement dependency inversion, where dependencies are injected into a class rather than being created or managed by the class itself
        
    2 . What are the common design patterns used in Spring applications?
    - Singleton pattern: There is only one instance of a particular bean per Spring container. This ensures that beans are shared across the application reducing resource usage
    - DI pattern: Spring IoC container performs DI by injecting dependencies into classes either through constructor injection, setter injection or method injection using annotations
    - Prototype pattern: New instance per request
    - Factory pattern: Spring IoC container acts as a factory that creates and manages bean instances based on their configurations
    - Template Method pattern: Template classes provide a consistent approach to perform repetitive tasks such as database access(JdbcTemplate), transaction management(TransactionTemplate) and email sending(JavaMailSender)
    
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
    - Component scanning is an automatic detection and instantiation of Spring beans based on classpath scanning and predefined rules
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
    - Initialization of singleton beans involves instantiation, property injection, and any required initialization methods
    - Once initialized, singleton beans are cached for subsequent requests, improving performance by avoiding repeated creation
    
    8 . Is @Bean a stereotype annotation?
    - No, If its stereotype it has a specific role
    - @Component, @Repository, @Service, and @Controller @value are stereotype annotations
    
    9 . Can you define private Beans using @Bean annotation inside a Configuration file that are annotated with @Configuration?
    - No
    
    10 . What are the places where @Profile annotation can be used?
    - Use @Profile on @Component, @Service, @Repository, or @Configuration to specify when a bean should be created based on the active profiles
    - Include or exclude components based on active profiles by annotating your configuration class with @ComponentScan and providing profile names
    - Use along with @ConditionalOnBean, @ConditionalOnClass to conditionally create beans or configure components based on profiles

    11 . Differences between Spring and Spring Boot?
    - Spring
      - Widely used Java EE framework for building web applications
      - Requires manual configuration for various components like data sources, security and logging
      - Requires more configuration and setup time
      - Provides a wide range of modules for different functionalities like spring MVC, spring data and spring security
    - Spring Boot
      - Widely used to developing microservices and standalone applications
      - Provides autoconfiguration for most common application needs
      - Rapid Application Development reducing boilerplate code
      - Simplifies application development by bundling necessary dependencies and providing starter modules for common tasks

    12 . What is auto wiring?
    - The process of injecting dependencies into a spring bean without explicitly configuring them

    13 . What is the difference between war and jar?
    - Jar files are used to packaging and distributing standalone java applications while War files are used to packaging and distributing web application to a servlet container like tomcat

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
    - It leverages Spring's core features such as dependency injection and inversion of control (IoC) to manage application components
    - SpringBoot automatically configures your application based on its dependencies and the environment, reducing the need for manual configuration
    - It uses an embedded server like Tomcat, Jetty, or Undertow to simplify deployment. This means you can run your SpringBoot application as a standalone Java application
    - SpringBoot provides starter dependencies that bundle commonly used libraries, making it easier to set up and manage dependencies in your project
    - SpringBoot Actuator provides built-in endpoints to monitor and manage your application at runtime, offering insights into application health, metrics, and more
    - It offers a Command Line Interface (CLI) for rapid prototyping and development of SpringBoot applications, allowing you to quickly create, run, and test applications
    - Dev tools helps in rapid development by enabling features like automatic application restart, live reload, and remote debugging
    - SpringBoot supports various configuration formats like properties files, YAML files, environment variables, and command-line arguments
    
    2 . What are Spring boot starters?
    - Spring boot starter comprises templates which provide a Rapid Application Development
    - Spring boot starter contains a combination of all the relevant transitive dependencies
    - Spring boot starter solves the auto dependency resolution in a spring boot application
    - They provide a quick and easy way to include common dependencies for specific functionalities, such as web development, data access, security, and more
    - Spring boot resolves transitive dependencies internally
    - All available starters come under the org.springframework.boot group
    
    3 . What are the major starter dependencies of spring boot application?
    - spring-boot-starter-parent: Provides default configurations for our application, dependency management and plugin management
    - spring-boot-starter-web: Essential for developing web applications, providing embedded Tomcat server and Spring MVC
    - spring-boot-starter-security: Offers authentication, authorization, and other security features
    - spring-boot-starter-test: Facilitates testing with JUnit, Mockito, and other testing libraries
    - spring-boot-starter-actuator: Enables monitoring and managing the application through endpoints
    - spring-boot-starter-jdbc: Provides libraries for connecting the application with JDBC
    - spring-boot-starter-data-jpa: Simplifies working with databases using Java Persistence API
    - spring-boot-starter-data-aop: Provides Aspect-Oriented Programming with cross-cutting concerns
    
    4 . Can you disable particular auto-configuration in spring boot?
    - Yes
    - @EnableAutoConfiguration(exclude={DataSourceAutoConfiguration.class}) or @SpringBootApplication(exclude={DataSourceAutoConfiguration.class})

    5 . Explain below annotations?
    - @RestController: Marks a class as a controller where methods return data directly instead of relying on a view for presentation. Used in REST ful web services
    - @RequestMapping(value="/provider"): Maps HTTP requests to MVC or REST and specifies URL pattern that the controller should listen
    - @PathVariable: Extracts values from the URI path
    - @RequestParams: To extract query params from the URL
    - @ResponseEntity: Represents the entire HTTP response, including headers and body. It allows you to control the response status code, headers, and body content
    - @GetMapping: It maps HTTP GET requests onto specific handler methods in a controller
    - @ResponseBody: Indicates that the return value of a method should be bound to the web response body
    
    6 . Can we disable the default web server in the Spring Boot application?
    - Add below config to application.properties
        - spring.main.web-application-type=none

    7 . What is the difference between @Controller and @RestController annotations?
    - @Controller: It is used to mark classes as Spring MVC controllers. These classes handle web requests and usually return views
    - @RestController: It is a specialization of the @Controller annotation. It's used to create REST ful web services. It automatically converts Java objects into JSON or XML responses
    
    8 . What is the difference between @RequestMapping and @GetMapping annotations?
    - @RequestMapping can be used with GET,POST,PUT and many other request methods using the method attribute on the annotation
    - GetMapping is only an extension of RequestMapping, which helps you to improve clarity on requests

    9 . What is Singleton across per container and per jvm?
    - 1 singleton bean per Spring container
    - Multiple beans per JVM if we deploy multiple instances of the same application in the same server

    10 . Explain Spring Actuator and its advantages?
    - Spring Actuator is a feature in the Spring Boot framework that provides production-ready features to help monitor and manage your application
    - Actuator supports below endpoints
      - '/actuator/health'
      - '/actuator/metrics'
      - '/actuator/env'
    
    11 . What is spring boot dependency management?
    - Spring Boot dependency management is a feature that simplifies the management of dependencies in a Spring Boot application
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
    - Is a web tool provided by Spring. With this tool you can create Spring boot projects just by providing project details
    
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
    - It provides a consistent API for working with various data stores, including relational, NoSQL and cloud-based data services
    
    16 . What is the best way to expose custom application configuration with SpringBoot?
    - Using application.properties or application.yml
    - @ConfigurationProperties to bind custom properties directly to Java objects
    - Environmental variables
    - Spring Cloud Config
    - Profiles
    
    17 . What is the difference between @Autowired and @Inject?
    - @Inject is a standard annotation for dependency injection while @Autowired is a specific annotation in Spring for dependency injection
    - @Inject is from pure Java EE, while @Autowired is from Spring framework
    - We can achieve dependency injection in pure java using constructor injection, setter injection or method injection
    
    18 . What is the difference between @Component and @Bean?
    - @Component is used to auto-detect and autoconfigure beans using classpath scanning, while @Bean is used to explicitly declare a single bean instance manually
    - @Bean is method level but @Component is class level
    - The @Component annotation doesn't need to be used with the @Configuration annotation, whereas the @Bean needs to be within a class annotated with @Configuration
    
    19 . How many types of IOC containers are there in Spring?
    - BeanFactory: Serves as the core container for holding bean definitions, instantiating beans, and managing their lifecycle
    - ApplicationContext: ApplicationContext interface is built on top of the BeanFactory, and it provides additional functionality like Annotation support, Reactive programming
    
    20 . What is the use of @Qualifier annotation in Spring framework?
    - When we create more than one bean of the same type and want to wire only one of them with a property we can use the @Qualifier annotation
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
      - @PostConstruct: The method annotated with @PostConstruct is invoked after the bean has been constructed and its dependencies have been injected
      - @PreDestroy: The method annotated with @PreDestroy is invoked before the bean is destroyed by the Spring container, typically during shutdown
    
    24 . What do you understand by validations in Spring MVC?
    - It is used to restrict the input provided by the user
    - Spring validations: @NotNull, @Pattern, @Email, @Size, @NotBlank
    - @Valid must be used at Method Parameter

    25 . Which annotations are used to define Global Exception Handler class?
    - @ControllerAdvice or @RestControllerAdvice
    - @ExceptionHandler
    
    26 . What is the main difference between Spring core and Spring MVC?
    - Spring Core provides the fundamental functionalities of the Spring Framework, such as dependency injection and inversion of control
    - Spring MVC is a part of the Spring Framework that provides a model-view-controller architecture for building web applications

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
        - JpaRepository: Extends PagingAndSortingRepository and adds JPA-specific methods like flushing the persistence context and deleting records in a batch

    30 . What are the predefined methods given by @Repository interfaces?
    - save(), saveAll(), findById(), findAll(), findAll(Sort), findAll(Pageable), count(), delete(), deleteAll(), deleteById()
    
    31 . What is @Query used for?
    - @Query annotation is used to write custom queries
    - By using this query we can write JPQL/HQL query which is written by the class name(DB table name) and variable name(Column name)
    
    32 . What is PlatformTransactionManager?
    - PlatformTransactionManager is an interface that extends TransactionManager
    - It coordinates the beginning, committing, or rolling back of transactions, ensuring data integrity and consistency in database operations
    
    33 . Difference between findById() and getOne()?
    - If data is not found in findById() will return null, means it return Optional<T> class
    - If data is not found in getOne() will throw an exception called EntityNotFoundException
    
    34 . What is the usage of Dialect?
    - It generates SQLs at runtime based on our operations
    - If we move from one Database to another database we need to update database dialect property in application.properties
    
    35 . What is the default FetchType in JPA?
    - LAZY: one-to-many, many-to-many
    - EAGER: one-to-one, many-to-one
    
    36 . How can we see generated SQLs at console files?
    - spring.jpa.show-sql=true(default is false)

    37 . What are some essential features of Spring Security?
    - Authentication: Provides mechanisms to authenticate users using various methods such as LDAP, JDBC, OAuth, etc
    - Authorization: Enables fine-grained access control to resources based on user roles and permissions.
    - Security Filters: Offers a set of filters for handling authentication, authorization, session management, and CSRF protection
    - Session Management: Supports session fixation protection, concurrent session control, and session timeout handling
    - Password Encoding: Built-in support for password hashing and salting to securely store user passwords
    - CSRF Protection: Helps prevent Cross-Site Request Forgery attacks by generating and validating unique tokens
    - Remember-Me Authentication: Allows users to authenticate with a persistent token, typically stored in a cookie, for automatic login
    - Method-Level Security: Provides annotations for securing individual methods within Spring components.
    
    38 . What do you mean by Basic Authentication?
    - We send a username and password using the HTTP header to enable us to access the resource
    - Username and password are encoded using base64 encoding in Basic Authentication
    - eg: Value = username:password -> Encoded = base64(Value) -> Authorization = Basic <Encoded>
    
    39 . Explain SecurityContext and SecurityContextHolder?
    - SecurityContext: SecurityContext is an interface in Spring Security that holds the details of the currently authenticated user, including their principal (username), authorities, and other security-related information
    - SecurityContextHolder: SecurityContextHolder is a class in Spring Security that provides access to the SecurityContext
    
    40 . Explain spring security OAuth2?
    - Spring Security OAuth2 is an extension of the Spring Security project that provides support for OAuth 2.0 authentication and authorization
    - It helps secure Spring-based applications by providing mechanisms for authenticating users and authorizing access to resources using OAuth 2.0
    - The main components include Authorization Server, Resource Server, Client, and Tokens
    - Authorization server is responsible for issuing access tokens to clients after successfully authenticating and authorizing users
    - Resource server hosts resources that are protected by OAuth 2.0 and verifies access tokens to grant or deny access to those resources
    - The client is an application that requests access to protected resources on behalf of the resource owner
    - An access token is a credential that represents the user's authorization to access protected resources
    - It is issued by the Authorization Server after the user successfully authenticates and authorizes the client application
    - A refresh token is a long-lived credential that is used to obtain a new access token when the current one expires
    - When an access token expires, the client can use the refresh token to request a new access token without requiring the user to re-authenticate
    
    41 . What is method security and why do we need it?
    - The ROLE of the user is used to determine which user is authorized to access the resource
    - A security measure applied to a method prevents unauthorized users and only allows authentic users
    
    42 . What do you mean by hashing in spring security?
    - Hashing in Spring Security refers to the process of converting sensitive data, such as passwords, into irreversible scrambled strings using cryptographic algorithms
    
    43 . What is AuthenticationManager in Spring Security?
    - AuthenticationManager in Spring Security is responsible for authenticating a user's credentials
    - It validates the user's identity by checking the provided credentials against the stored credentials in the system
    - It acts as the central authentication point in the security framework

    44 . What do you mean by session management in Spring security?
    - Session management in Spring Security refers to the management of user sessions within a web application
    - It involves controlling the lifecycle of sessions, handling session creation, destruction, and tracking session attributes

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
        - Once the transaction is committed, the updates and modifications to the DB are stored in and written to disk, and they persist even if a system failure occurs

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

    10 . What is the purpose of Spring Cloud Config?
    - It is centralized management of configuration properties for microservices
    - It uses configurations in a version controlled repository and provides a configuration server
    - Can retrieve their configuration information at runtime
    
    11 . What are the different approaches for inter service communication in microservices?
    - HTTP/ APIs
    - Asynchronous messaging: Kafka, RabbitMQ
    - Event driven
    
    12 . What is service orchestration and service choreography in microservices?
    - Service Orchestration is a centralized approach where a central component controls and coordinates the execution flow of microservices
    - Service Choreography is a decentralized approach where microservices collaborate with each other directly, without a central controller
    
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
    
    6 . Disadvantages of Data Replication?
    - Data across multiple servers
    - Increases data redundancy

    7 . Advantages of Data Replication?
    - Disaster recovery
    - Improve data accessibility
    - Enhance server performance

    8 . What is normalization and what are the different types of normalization?
    - Organizing data in such a way that it reduces data redundancy
    - Is done by dividing the large table into multiple tables and establishing a relationship between them

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
    - Candidate key
    - Primary key
    - Secondary key
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
    - While they improve read performance, they can slow down data modification operations like inserts, updates, and deletes
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
      - Drop existing records as well as the table, DDL syntax 8