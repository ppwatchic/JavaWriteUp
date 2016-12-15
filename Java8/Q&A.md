**Q1.** Java SE 8 New Features?
Lambda Expressions  
Functional Interfaces  
Stream API  
Date and Time API  
Interface Default Methods and Static Methods  
Spliterator  
Method and Constructor References  
Collections API Enhancements  
Concurrency Utils Enhancements  
Fork/Join Framework Enhancements  
Internal Iteration  
Parallel Array and Parallel Collection Operations  
Optional  
Type Annotations and Repeatable Annotations  
Method Parameter Reflection    
Base64 Encoding and Decoding  
IO and NIO2 Enhancements  
Nashorn JavaScript Engine  
javac Enhancements  
JVM Changes  
Java 8 Compact Profiles: compact1,compact2,compact3  
JDBC 4.2  
JAXP 1.6  
Java DB 10.10  
Networking  
Security Changes  

**Q2.** Advantages of Java SE 8 New Features?
More Concise and Readable code  
More Reusable code  
More Testable and Maintainable Code  
Highly Concurrent and Highly Scalable Code  
Write Parallel Code  
Write Database Like Operations  
Better Performance Applications  
More Productive code  

**Q3.** What is Lambda Expression?
They provide a clear and concise way to represent one method interface using an expression.
Lambda Expression is a block of code without a name. 

**Q4.** What are the three parts of a Lambda Expression? What is the type of Lambda Expression?
Input parameter(s), An arrow (->) and expression body which generates the result. 
The Type of a Lambda Expression is a **Functional Interface**.

```
()->System.out.println("Impingping").
```
This Lambda Expression does not have parameters and does return any results.   
So it’s type is “java.lang.Runnable” Functional Interface.

**Q5.** What is a Functional Interface? What is SAM Interface?
A functional interface is an interface with exactly one abstract method. 
Functional Interface is also know as SAM Interface because it contains only one abstract method.

**Q6.** Is it possible to define our own Functional Interface?   
Yes, it is possible to define our own Functional Interfaces. We use Java SE 8’s @FunctionalInterface annotation to mark an interface as Functional Interface.

**Q7.** What is @FunctionalInterface? What are the rules to define a Functional Interface?  
It is an annotation.   
We need to follow these rules to define a Functional Interface:  
* Define an interface with one and only one abstract method.
* We cannot define more than one abstract method.
* Use @FunctionalInterface annotation in interface definition.
* We can define any number of other methods like Default methods, Static methods.
* If we override java.lang.Object class’s method as an abstract method, which does not count as an abstract method.

**Q8.** Is @FunctionalInterface annotation mandatory to define a Functional Interface?  
It is not mandatory to define a Functional Interface with @FunctionalInterface annotation. If we don’t want, We can omit this annotation. However, if we use it in Functional Interface definition, Java Compiler forces to use one and only one abstract method inside that interface.

**Q9.** What is the use of @FunctionalInterface annotation? Why do we need Functional Interfaces in Java?  
The type of a Java SE 8’s Lambda Expression is a Functional Interface. Whereever we use Lambda Expressions that means we are using Functional Interfaces.

**Q10.** When do we go for Java 8 Stream API? Why do we need to use Java 8 Stream API in our projects?  
* When we want perform Database like Operations. For instance, we want perform groupby operation, orderby operation etc.  
* When want to Perform operations Lazily.  
* When we want to write Functional Style programming.  
* When we want to perform Parallel Operations.  
* When want to use Internal Iteration.  
* When we want to perform Pipelining operations.  
* When we want to achieve better performance.  

**Q11.** Explain Differences between Collection API and Stream API?  
| No. | Collection API | Stream API |
| --- | --- | --- |
| 1.	| It’s available since Java | It is introduced in Java SE8 |
| 2.	| It is used to store Data(A set of Objects).	| It is used to compute data(Computation on a set of Objects). |
3.	We can use both Spliterator and Iterator to iterate elements.	We can use both Spliterator and Iterator to iterate elements.
4.	It is used to store limited number of Elements.	It is used to store either Limited or Infinite Number of Elements.
5.	Typically, it uses Internal Iteration concept to iterate Elements.	It uses External Iteration to iterate Elements.
6.	Collection Object is constructed Eagerly.	Stream Object is constructed Lazily.
7.	We add elements to Collection object only after it is computed completely.	We can add elements to Stream Object without any prior computation. That means Stream objects are computed on-demand.
8.	We can iterate and consume elements from a Collection Object at any number of times.	We can iterate and consume elements from a Stream Object only once.


**Q12.** What is Spliterator in Java SE 8?   
Differences between Iterator and Spliterator in Java SE 8?

**Q13.** What is Optional in Java 8?  
What is the use of Optional?  
Advantages of Java 8 Optional?

**Q14.** What is Type Inference? 
Is Type Inference available in older versions like Java 7 and Before 7 or it is available only in Java SE 8?

**Q15.** What is Internal Iteration in Java SE 8?

**Q16.** Differences between External Iteration and Internal Iteration?

**Q17.** What are the major drawbacks of External Iteration?

**Q18.** What are the major advantages of Internal Iteration over External Iteration?

**Q19.** What is the major drawback of Internal Iteration over External Iteration?

**Q20.** What is the major advantage of External Iteration over Internal Iteration?

**Q21.** When do we need to use Internal Iteration? When do we need to use External Iteration?

**Q22.** Differences between Intermediate Operations and Terminal Operations of Java 8’s Stream API?

**Q23.** Is it possible to provide method implementations in Java Interfaces? If possible, how do we provide them?

**Q24.** What is a Default Method? Why do we need Default methods in Java 8 Interfaces?

**Q25.** What is a Static Method? Why do we need Static methods in Java 8 Interfaces?

**Q26.** Differences between Functional Programming and Object-Oriented Programming?

**Q27.** Explain issues of Old Java Date API?   
What are the advantages of Java 8’s Date and Time API over Old Date API and Joda Time API?  

**Q28.** Why do we need new Date and Time API in Java SE 8?  
Explain how Java SE 8 Data and Time API solves issues of Old Java Date API?


**Q29.** What are the Differences between Java’s OLD Java Date API and Java 8’s Date and Time API?  

**Q30.** What is Multiple Inheritance? How Java 8 supports Multiple Inheritance?


**Q31.** What is Diamond Inheritance Problem? How Java 8 Solves this problem?
