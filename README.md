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
    - A marker interface is an empty interface. eg: Serializable, Cloneable
    
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
    
    16 . 
    
- Spring


- Springboot


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