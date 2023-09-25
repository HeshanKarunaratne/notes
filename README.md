# Interview Preparation

- Core Java

    1 . Why Java is not 100% Object oriented?
    - Because of Primitive data types eg: boolean, byte, char, int, float, double, long, short
    - We can use wrapper classes to wrap primitive data types into an object
    
    2 . Why pointers are not used in java
    - They are unsafe, increases the complexity of the program, JVM is responsible for memory allocation thus pointers are not needed in java

    3 . What is JIT compiler in Java?
    - Convert byte codes into machine codes and to improve performance in java application
    
    4 . Why String is immutable in java?
    - String literals are kept inside String pool and it requires Strings to be immutable. If there is a String in the pool it will get referenced otherwise a new String object will be created and will get a reference
    
    5 . What is a marker interface?
    - A marker interface is an empty interface. eg: Serializable, Cloneable(To get an exact duplicate object)
    - By implementing a marker interface classes will get additional behaviour at compile time
    - You can create your own marker interface, but need to do some customizations to the JVM
    
    6 . Can you override a private or static method in Java?
    - Cannot override a private or static methods in java
    - We cannot override a private method in sub class because it is not accessible there
    - For static methods if we create a similar method with same return type and same method arguments in child class then it will hide the superclass method, also known as method hiding

    7 . Does finally always execute in Java?
    - This will not execute in System.exit() or in System crash
    
    8 . What methods does the Object class have?
    - clone(), equals(), finalize(), hashCode(), toString(), getClass()
    
    9 . How to make a class Immutable?
    - Declare the class as final
    - Make all fields private and final
    - Dont provide setter methods for variables
    - Initialize all the fields via a constructor

    10 . Boxing and unBoxing
    - Boxing is the process of converting a primitive datatype into an object wrapper datatype
    - Unboxing is the process of converting a value from an object wrapper type back to the native primitive value

    11 . What is JDK, JRE and JVM
    - JDK > JRE > JVM
    - JDK: Contains JRE and other development tools
    - JRE: Runtime Environment for the bytecode to execute
    - JVM: Convert bytecode to machine code using a platform independent virtual machine
    - Java Program ---Java compiler--> Java ByteCode ---JVM---> Machine Code
    
    12 . Why main() method is public static?
    - So that the JVM can directly invoke it without instantiating class object
    
    13 . What are mutable and immutable String objects?
    - String is immutable while StringBuilder and StringBuffer are mutable
    
    14 . Difference between == and equals() method in Java?
    - equals() used for content comparison while == checks same objects points to the same memory location
    
    15 . Difference between StringBuilder and StringBuffer?
    - StringBuilder is not thread safe while StringBuffer is thread safe
    - StringBuffer is slower compared to StringBuilder 
    
    16 . Difference between List and Set
    - List allow duplicates, Set doesn't allow duplicates
    - List maintains insertion order, Set doesn't maintain insertion order
    - List allows any number of null values, Set can have only a single null value at most
    
    17 . Difference between ArrayList and LinkedList
    - ArrayList internally uses a dynamic array to store elements, LinkedList internally uses a doubly linked list to store elements
    - Manipulation of ArrayList is slow, while LinkedList is faster
    - ArrayList consumes less memory, while LinkedList consumes more memory since it stores references to previous and next elements
    - ArrayList implements List interface only, LinkedList implements List and Deque interfaces
    
    18 . Difference between Collections and Streams
    - Collections are used to store and group the data while streams are used to perform filtering,matching,mapping operations
    - Can add or remove elements from Collections but cannot do that in Streams
    - Collections need to be iterated externally(for loops) but Streams are iterated internally(for-each())
    
    19 . What are the new features in Java 8?
    - Lambda Expressions
    - Method References
        1. What ware different kind of method references?
            - Reference to a static method
            - Reference to an instance method of a particular object
            - Reference to an instance method of an arbitrary object of a particular type
            - Reference to a constructor
           
    - Optional
        1. What are the advantages of Optionals?
            - Null checks are not required
            - No more NullPointerException at run time
            - Clean neat APIs
            
    - Functional Interfaces
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
    - 
    
    22 . Why do we need OOP?
    - It helps us to think in terms of Real world objects
    - Pillars of OOP?
        1. Abstraction: Show only what is necessary, hiding the complexity
            - Abstract methods do not have an implementation, it only have method signatures
            - If a class have abstract method then the class needs to be declared abstract
            - An abstract class does not necessarily have an abstract method
            - Cannot be instantiated but abstract classes can have constructors: constructor can only be called during constructor chaining
            - Can have static methods and final methods
            - Abstract class implements interfaces but it does not need to implement all methods
            - Abstract classes cannot be final because making an abstract class final will stop the abstract class from being extended

        2. Polymorphism: Objects act differently under different conditions
            - There are 2 types of polymorphism
                1. Static polymorphism(Overloading)
                2. Dynamic polymorphism(Overriding)
        
        3. Inheritance: Parent Child relationship
            - All the methods are declared with the empty body and are public and abstract by default
            - All the fields public, static and final by default
            - Interface is used for full abstraction
            - A class implements interface and implements all abstract methods
            
        4. Encapsulation: Hiding the data
    
    23 . What is a class and an object?
    - A class is a blueprint of an object
    - An object is an instance of a class
    
    24 . Is-A relationship and Has-A relationship?
    - Whenever one class inherits another class it is called an Is-A relationship(extend)
    - Whenever an instance of one class has a reference to an instance of another class or same class it is known as Has-A relationship
    
    25 . What is method overriding and overloading?
    - Overloading is same method name with different signatures
    - Overriding is same method name with same signature, need to have parent child relationship and any method in parent class can be overridden in child class
    
    26 . Static(Compile) vs Dynamic(Runtime) Polymorphism?
    - Static Polymorphism is implemented by Method Overloading
    - Dynamic Polymorphism is implemented by Method Overriding
    
    27 . What is an Abstract Class
    - Abstract class is a Partially defined Parent class
    - We cannot create constructors for Abstract classes
    
    28 . What is an Interface?
    - Interface is a contract
    - We cant write logic in interface
    - All the methods are public in an interface
    - Multiple Inheritance helps to add new methods without affecting the old interfaces
    
    29 . what are static blocks and static initalizers in Java?
    - Static blocks or static initializers are used to initalize static fields in java.
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
        4. Parameters must be different when we do overloading
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
    
    34 . Explain about instanceof operator in java?
    - \<reference expression> instanceof \<destination type>: will return true if reference is an instance of destination type
    - There will be a compile time check, so that if its not a subtype then compile time error will be shown
    
    35 . Can we define package statement after import statement in java?
    - We can’t define package statement after import statement in java. package statement must be the first statement in source file. We can have comments before the package statement
    
    36 . What are identifiers in java?
    - Identifiers are names in java
    - Identifiers must start with letter,Underscore or dollar($) sign
    - Identifiers can’t start with numbers
    - Case sensitive
    - From second letter we can have numbers
    - We cant use reserved words for identifiers
    
    37 . What access modifiers can be used for class ?
    - public and default: Can access in same class, same package subclass, same package non subclass, different package subclass, different package non subclass
    
    38 . Explain what access modifiers can be used for methods?
    - All access modifiers
        - private: Only in same class
        - protected: Can access in same class, same package subclass, same package non subclass, different package subclass only
        - default: Can access in same class, same package subclass, same package non subclass only
        - public: Can access in same class, same package subclass, same package non subclass, different package subclass, different package non subclass
    
    39 . What is an error in Java?
    - Error is the subclass of Throwable class in java
    - Exceptions which cannot be recovered are called as errors in java
    
    40 . Can we have try block without catch block?
    - Each try block requires atleast one catch block or finally block
    
    41 . What is checked and unchecked Exception in Java?
    - Checked Exception(Compile time exception)
        1. All the subclasses of Throwable except RuntimeException and its subclasses are checked Exception
        2. Checked Exception should be thrown with keyword throws or provided try catch block else program would not compile
        3. Examples
            - IOException
            - SQIException
            - FileNotFoundException
            - ClassNotFoundException
            - InvocationTargetException
    - Unchecked Exception
        1. All subclasses of RuntimeException are called unchecked Exception
        2. Program compiles even if we do not catch the exception or throws the exception
        3. Examples
            - ArithmeticException
            - IndexOutOfBoundsException
            - NullPointerException
            - NumberFormatException
            - UnsupportedOperationException
    
    42 . Explain the importance of finally over return statement?
    - 'finally' block is more important than return statement when both are present in a program. For example if there is any return statement present inside try or catch block , and finally block is also present first finally statement will be executed and then return statement will be considered
    - 'finally' will not work in JVM shutdowns
    
    43 . Explain when ClassNotFoundException will be raised ?
    - When JVM tries to load a class by its string name, and couldn’t able to find the class classNotFoundException will be thrown
       
    44 . Explain when NoClassDefFoundError will be raised ?
    - JVM tries to load the class but no definition for that class is found. The class may exist at compile time but unable to find at runtime
    
    45 . Explain about main thread in java?
    - Main thread is the first thread that starts immediately after a program is started
    - Main thread is important because,
        1. All the child threads are spawn from main thread
        2. It is responsible for executing the main method of the class specified when launching the program
           
    46 . Explain the life cycle of thread?
    - New: When the instance of thread is created it will be in New state
    - Runnable: When the start method is invoked or after coming back from blocked/sleeping/waiting state
    - Running: If thread scheduler allocates cpu time, then the thread will be in running state
    - Waiting/Blocked/Sleeping: The thread waits to acquire lock of an object, waits for another thread to complete
    - Dead: A thread is in dead state when thread’s run method execution is complete
    
    47 . In how many ways we can do synchronization in java?
    - Synchronized methods
    - Synchronized blocks
    
    48 . When do we use synchronized methods in java?
    - If multiple threads tries to access a method where method can manipulate the state of object , in such scenario we can declare a method as synchronized
    
    49 . Can we use synchronized block for primitives?
    - Synchronized blocks are applicable only for objects if we try to use synchronized blocks for primitives we get compile time error
    
    50 . What are daemon threads in java?
    - Daemon threads are threads which run in background. These are service threads and works for the benefit of other threads. Garbage collector is one of the good example for daemon threads
    
    51 . What are nested classes in java?
    - Class declared with in another class is defined as nested class
        1. Static nested class
        1. Non static nested class
    
    52 . What are inner classes or non static nested classes in java?
    - Nested classes without any static keyword declaration in class definition are defined as non static nested classes. Generally non static nested classes are referred as inner classes
    - There are 4 types of Inner classes
        1. Local Inner Class
        2. Member Inner Class
        3. Static Nested Inner Class
        4. Anonymous Inner Class
    
    53 . Will the compiler creates a default constructor if I have a parameterized constructor in the class?
    - No compiler won’t create default constructor if there is parameterized constructor in the class. 
    - For example if I have a class with no constructors, then compiler will create default constructor
    
    54 . Can Static methods access instance variables in java?
    - No. Instance variables can’t be accessed in static methods. When we try to access instance variable in static method we get compilation error
   
    55 . How many times finalize method will be invoked ? who invokes finalize() method in java?
    - Finalize () method will be called only once on object. Before the object gets garbage collected garbage collector will call finalize() method to free the resources. 
    - Finalize() method will be called only when object is eligible for garbage collection
   
    56 . Explain about transient variables in java?
    - To save the state of an object to persistent state we use serialization. If we want a field or variable in the object not to be saved, then we declare that variable or field as transient
   
    57 . Can we define static methods inside interface?
    -  Only instance methods are permitted in interfaces.only public and abstract modifiers are permitted for interface methods
    
    58 . Define interface in java?
    -  Interface is collection of abstract methods and constants. An interface is also defined as pure or 100 percent abstract class.Interfaces are implicitly abstract whether we define abstract access modifier or not.
   
    59 . Explain restrictions on using enum?
    - Enums cannot extend any other class or enum
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
   
    63 . Explain about fail fast iterators in java
    - When iterator iterates over collection, collection should not be modified except by that iterator
   
    64 . What is serialization in java?
    - Serialization is the process of converting an object in to bytes, so that it can be transmitted over the network,or stored in a flat file and can be recreated later. 
    - Serialized object is an object represented as sequence of bytes that includes objects data, object type, and the types of data stored in the object.
   
    65 . How to make object serializable in java?
    - Our class must implement serializable interface. If our object contains other objects those class must also implement serializable interface.
    - We use ObjectOutputStream which extends OutputStream used to write objects to a stream.
    - We use ObjectInputStream which extends InputStream used to read objects from stream.
   
    66 . If we don’t want some of the fields not to serialize How to do that?
    - If we don’t want to serialize some fields during serialization we declare those variables as transient
     
- Spring
    
    1 . Explain Dependency Inversion and Inversion Of Control concepts in Spring?
    - Inversion Of Control(IoC):
        1. Is a design principle where the control of object(beans) creation and management is shifted from the application itself to an external container or framework(Spring IoC container is responsible)
        2. The container manages the lifecycle of these beans and handles their dependencies, ensuring that the right dependencies are injected into the right places.
        3. Overall architecture becomes more flexible and maintainable
    - Dependency Injection(DI):
        1. Dependency Injection is a specific implementation of the IoC principle
        2. It is a technique used to inject the dependencies of a class into the class itslef
        
    2 . What are the common design patterns used in Spring applications?
    - Singleton pattern: There is only one instance of a particular bean per Spring container. This ensures that beans are shared across the application reducing resource usage
    - Prototype pattern: New instance per request
    - Factory pattern: Spring IoC container acts as a factory that creates and manages bean instances based on their configurations
    - DI pattern: Spring IoC container performs DI by injecting dependencies into classes either through constructor injection, setter injection or method injection using annotations
    - Template Method pattern: Template classes provide a consistent approach to perform repetitive tasks such as database access(JdbcTemplate), transaction management(TransactionTemplate) and email sending(JavaMailSender)
    
    3 . Explain the difference between constructor and setter injection?
    - In constructor injection, the required dependencies are passed to the class via its constructor at the time of object creation, the class is responsible for initializing its instance variables with the provided dependencies.
    - In setter injection, the dependencies are provided through setter methods of the class. The class exposes setter methods for each dependency it requires, and the Spring container uses these methods to inject the required dependencies after creating the object.
    - Use constructor injection for mandatory dependencies, immutability, safety and readability.
    - Use setter injection for optional dependencies, flexibility to change dependencies, circular dependencies.
    
    4 . What is a Spring Bean?
    - Any java object that is managed by Spring is called Spring Bean
    
    5 . @Value can help loading the values from?
    - Environment properties, VM arguments, properties file
    
    6 . What are the places @PropertySource extract values from?
    - Classpath
    - Another properties file from another project

    7 . How the singleton beans are initialized?
    - Eagerly initialized
    
    8 . Is @Bean a stereotype annotation?
    - No, If its stereotype it has a specific role
    
    9 . Can you define private Beans using @Bean annotation inside a Configuration file that are annotated with @Configuration?
    - No
    
    10 . What are the places where @Profile annotation can be used?
    - @Bean, @Component, @Configuration, @Repository
    
- Springboot

    1 . How SpringBoot works internally?
    - Entry point of springboot application is a class which contains @SpringBootApplication annotation and has the main method
    - SpringBoot scan all the components included in the project by using @ComponentScan annotation
    - Using @EnableAutoConfiguration annotation the springboot application configures the springboot application automatically
    
    2 . What are Spring boot starters?
    - Springboot starter comprises of templates which provide a Rapid Application Development, spring boot starter contains a combination of all the relevant transitive dependencies
    - Springboot starter solves the auto dependency resolution in a spring boot application
    - Springboot resolves transitive dependencies internally
    
    3 . What are the major starter dependencies of springboot application?
    - spring-boot-starter-parent: Provides default configurations for our application and a complete dependency tree to quickly build our springboot project
    - spring-boot-starter-web: Uses Spring MVC, REST, tomcat as a default embedded server, and pulls in all dependencies related to web development
    - spring-boot-starter-security: Automatically secures all HTTP endpoints with basic authentication
    - spring-boot-starter-test: Primary dependency required for tests
    - spring-boot-starter-actuator: Helps monitor application via HTTP endpoints, several endpoints are available out of the box
    - spring-boot-starter-jdbc: Provides libraries for connecting the application with JDBC
    - spring-boot-starter-data-jpa: Provides access to different kinds of persistence stores
    - spring-boot-starter-data-aop: Provides Aspect-Oriented Programming with cross cutting concerns
    
    4 . Can you disable particular auto-configuration in springboot?
    - Yes
    - @EnableAutoConfiguration(exclude={DataSourceAutoConfiguration.class}) or @SpringBootApplication(exclude={DataSourceAutoConfiguration.class})

    5 . Explain below annotations?
    - @RestController: Class level annotation, so that spring container will consider as RestEndpoint
    - @RequestMapping(value="/provider"): Define the REST url
    - @PathVariable: To extract variable value
    - @RequestParams: To extract query params 
    - @ResponseEntity: To convert domain object into the response format 
    - @GetMapping: To make endpoint compatible for GET requests 
    - @ResponseBody: To generate the response message 
    
    6 . Can we disable the default web server in the Springboot application?
    - Add below config to application.properties
        - spring.main.web-application-type=none
    
    7 . What is SpringBoot and why use springboot in your project?
    - SpringBoot is a spring module for RAD(Rapid Application Development) with extra support of auto configuration, embedded application servers, auto dependency resolution, management endpoints, spring boot CLI
    
    8 . What is the difference between @Controller and @RestController annotations?
    - @Controller maps the model object to a view or template and makes it human readable but @RestController simply returns the object and data as JSON or XML
    
    9 . What is the difference between @RequestMapping and @GetMapping annotations?
    - @RequestMapping can be used with GET,POST,PUT and many other request methods using the method attribute on the annotation
    - GetMapping is only an extension of RequestMapping, which helps you to improve clarity on requests
    
    10 . Why should you use Spring Boot?
    - Stability: Changes are backward compatible
    - Based on JVM: Spring is Java based
    - Connectivity: Can connect to any database
    - Cloud Native: Ready for cloud out of the box
    - Flexibility: 
    - Open Source: Easy to setup and configure
    
    11 . What are the differences between Spring and Springboot?
    - Spring
        - Spring is a web application framework based on java
        - Provides tools and libraries to create customized web application
    - SpringBoot
        - A module of Spring
        - Used to create a Spring application project which can just run/execute
    
    12 . Advantages of Springboot?
    - Provides auto configuration to load a set of default configuration for a quick start of the application
    - Comes with embedded tomcat to avoid the usage of WAR files
    - Provides CLI tools to develop and test applications
    - Provides Spring boot starters to ensure dependency management
    - Consists of APIs for monitoring and managing applications in dev and prod
    - Integrates with Spring JDBC, JPA, Data, Security by avoiding boilerplate code

    13 . What are springboot starters?
    - Springboot starters are a set of dependency management providers which can be used in the application to enable dependencies
    - These starters make development easy and rapid
    - All available starters come under the org.springframework.boot group

    14 . Explain Spring Actuator and its advantages?
    - Provides a very easy way to access production ready rest points and fetch all kinds of information from the web
    
    15 . What is spring boot dependency management?
    - Is used to manage dependencies and configuration automatically without you specifying the version for any of that dependencies
    
    16 . What is the need for spring boot DevTools?
    - Set of tools that aims to make the process of developing an application easier
    - This module is automatically disabled in production
    
    17 . What is Spring initializer?
    - Is a web tool provided by Spring. With this tool you can create Spring boot projects 8just by providing project details
    
    18 . 


- SOLID Principals
    - Single Responsibility Principal
        - A Class should have one and only one responsibility
    - Open/Closed Principal
        - Open for extension and closed for modification
    - Liscov Substitute Principal
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
        - Once the transaction is committed, the updates and modifications to the DB are stored in and written to disk and they persist even if a system failure occurs

- Microservices



- SQL