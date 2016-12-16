**Q1.** Java SE 8 New Features?  
**A1.** 
* Lambda Expressions  
* Functional Interfaces  
* Stream API  
* Date and Time API  
* Interface Default Methods and Static Methods  
* Spliterator  
* Method and Constructor References  
* Collections API Enhancements  
* Concurrency Utils Enhancements  
* Fork/Join Framework Enhancements  
* Internal Iteration  
* Parallel Array and Parallel Collection Operations  
* [Optional](http://www.oracle.com/technetwork/articles/java/java8-optional-2175753.html)  
* Type Annotations and Repeatable Annotations  
* Method Parameter Reflection    
* Base64 Encoding and Decoding  
* IO and NIO2 Enhancements  
* Nashorn JavaScript Engine  
* javac Enhancements  
* JVM Changes  
* Java 8 Compact Profiles: compact1,compact2,compact3  
* JDBC 4.2  
* JAXP 1.6  
* Java DB 10.10  
* Networking  
* Security Changes  

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
Let's explain it in the table.  

| No. | Collection API | Stream API |
| ---- | ---- | ---- |
| 1.	| It’s available since Java 1.2 | It is introduced in Java SE8 |
| 2.	| It is used to store Data(A set of Objects).	| It is used to compute data(Computation on a set of Objects). |
| 3.	| We can use both Spliterator and Iterator to iterate elements.	| We can use both Spliterator and Iterator to iterate elements. |
| 4.	| It is used to store limited number of Elements.	 | It is used to store either Limited or Infinite Number of Elements.|
| 5.	| Typically, it uses Internal Iteration concept to iterate Elements.	| It uses External Iteration to iterate Elements.|
| 6.	| Collection Object is constructed Eagerly.	| Stream Object is constructed Lazily.| 
| 7.	| We add elements to Collection object only after it is computed completely.	| We can add elements to Stream Object without any prior computation. That means Stream objects are computed on-demand.|
| 8.	| We can iterate and consume elements from a Collection Object at any number of times.	|We can iterate and consume elements from a Stream Object only once.|


**Q12.** What is Spliterator in Java SE 8?   
Differences between Iterator and Spliterator in Java SE 8?  
Spliterator stands for Splitable Iterator. It is newly introduced by Oracle Corporation as part Java SE 8.
Like Iterator and ListIterator, It is also one of the Iterator interface.  

| NO. |	SPLITERATOR	| ITERATOR |
| --- | --- | --- |
| 1.	| It is introduced in Java SE 8.	| It is available since Java 1.2.|
| 2.	| Splitable Iterator	| Non-Splitable Iterator |
| 3.	| It is used in Stream API.	| It is used for Collection API. | 
| 4.	| It uses Internal Iteration concept to iterate Streams.	| It uses External Iteration concept to iterate Collections. |
| 5.	| We can use Spliterator to iterate Streams in Parallel and Sequential order.	| We can use Spliterator to iterate Collections only in Sequential order.|
| 6.	| We can get Spliterator by calling spliterator() method on Stream Object.	| We can get Iterator by calling iterator() method on Collection Object. |
| 7.	| Important Method: tryAdvance()	| Important Methods: next(), hasNext() |

