**Q15.** What is Internal Iteration in Java SE 8?
Before Java 8, We don’t Internal Iteration concept. Java 8 has introduced a new feature known as “Internal Iteration”. Before Java 8, Java Language has only External Iteration to iterate elements of an Aggregated Object like Collections, Arrays etc.  
Internal Iteration means “Iterating an Aggregated Object elements one by one internally by Java API”. Instead of Java Application do iteration externally, We ask Java API to do this job internally.
Internal Iteration Example: 
```
import java.util.*;
public class InternalIterator {
  public static void main(String args[]){
  List<String> namesList=Arrays.asList("Kathy", "Ping", "Yuan");
    namesList.forEach(name -> System.out.println(name));  //Internal Iteration
  }
}
```

**Q16.** Differences between External Iteration and Internal Iteration?  

| NO.	| EXTERNAL ITERATION	| INTERNAL ITERATION |
| --- | ---| --- |
| 1.	| Available before Java 8 too.	| It is introduced in Java SE 8 |
| 2.	| Iterating an Aggregated Object elements externally.	| Iterating an Aggregated Object elements internally (background). |
| 3.	| Iterate elements by using for-each loop and Iterators like Enumeration, Iterator, ListIterator.	| Iterate elements by using Java API like “forEach” method. |
| 4.	| Iterating elements in Sequential and In-Order only.	| Not required to iterate elements in Sequential order. |
| 5.	| It follows OOP approach that is Imperative Style.	| It follows Functional Programming approach that is Declarative Style. |
| 6.	| It does NOT separate responsibilities properly that is, it defines both “What is to be done” and “How it is to be done”.	| It defines only “What is to be done”. No need to worry about “How it is to be done”. Java API takes care about “How to do”. | 
| 7.	| Less Readable Code.	| More Readable code. |

**Q17.** What are the major drawbacks of External Iteration?  
External Iteration has the following drawbacks:  
* We need to write code in Imperative Style.  
* There is no clear separation of Responsibilities. Tightly-Coupling between “What is to be done” and “How it is to be done” code.
* Less Readable Code.  
* More Verbose and Boilerplate code.  
* We have to iterate elements in Sequential order only.  
* It does not support Concurrency and Parallelism properly.  

**Q18.** What are the major advantages of Internal Iteration over External Iteration?  
Compare to External Iteration, Internal Iteration has the following advantages:   
* As it follows Functional Programming style, we can write Declarative Code.  
* More Readable and concise code.
* Avoids writing Verbose and Boilerplate code
* No need to iterate elements in Sequential order.
* It supports Concurrency and Parallelism properly.
* We can write Parallel code to improve application performance.
* Clear separation of Responsibilities. Loosely-Coupling between “What is to be done” and “How it is to be done” code.
* We need to write code only about “What is to be done” and Java API takes care about “How it is to be done” code.

**Q19.** What is the major drawback of Internal Iteration over External Iteration?
In Internal Iteration, as Java API takes care about Iterating elements internally, we do NOT have control over Iteration.  

**Q20.** What is the major advantage of External Iteration over Internal Iteration?
In External Iteration, as Java API does NOT take care about Iterating elements, we have much control over Iteration.  

**Q21.** When do we need to use Internal Iteration? When do we need to use External Iteration?

* When we need more control over Iteration, we can use External Iteration.
* When we do NOT need more control over Iteration, we can use Internal Iteration.
* When we need to develop Highly Concurrency and Parallel applications and we , we should use Internal Iteration.

**Q22.** Differences between Intermediate Operations and Terminal Operations of Java 8’s Stream API?  

| NO. |	STREAM INTERMEDIATE OPERATIONS	| STREAM TERMINAL OPERATIONS |  
| --- | --- | --- |
| 1.	| Stream Intermediate operations are not evaluated until we chain it with Stream Terminal Operation.	| Stream Terminal Operations are evaluated on it’s own. No need other operations help. |
| 2.	| The output of Intermediate Operations is another Stream.	| The output of Terminal Operations is Not a Stream. Something else other than a Stream. |
| 3.	| Intermediate Operations are evaluated Lazily.	| Terminal Operations are evaluated Eagerly. | 
| 4.	| We can chain any number of Stream Intermediate Operations.	| We can NOT chain Stream Terminal Operations. |
| 5.	| We can use any number of Stream Intermediate Operations per Statement.	| We can use only one Stream Terminal Operation per Statement. |

**Q23.** Is it possible to provide method implementations in Java Interfaces? If possible, how do we provide them?
In Java 7 or earlier, It is **not** possible to provide method implementations in Interfaces. Java 8 on-wards, it is possible.  
In Java SE 8, We can provide method implementations in Interfaces by using the following two new concepts:  
* Default Methods
* Static Methods

**Q24.** What is a Default Method? Why do we need Default methods in Java 8 Interfaces?
A Default Method is a method which is implemented in an interface with “default” keyword. It’s new featured introduced in Java SE 8.
Default methods enable us to add new functionalities to interfaces without breaking the classes that implements that interface.   

We need Default Methods because of the following reasons:

It allow us to provide method’s implementation in Interfaces.
To add new Functionality to Interface without breaking the Classes which implement that Interface.
To provide elegant Backwards Compatibility Feature.
To ease of extend the existing Functionality.
To ease of Maintain the existing Functionality.

**Q25.** What is a Static Method? Why do we need Static methods in Java 8 Interfaces?
A Static Method is an Utility method or Helper method, which is associated to a class (or interface). It is not associated to any object.  
We need Static Methods because of the following reasons:   
We can keep Helper or Utility methods specific to an interface in the same interface rather than in a separate Utility class.
We do not need separate Utility Classes like Collections, Arrays etc to keep Utility methods.  
Clear separation of Responsibilities. That is we do not need one Utility class to keep all Utility methods of Collection API like Collections etc.  
Easy to extend the API.  
Easy to Maintain the API.    

**Q26.** Differences between Functional Programming and Object-Oriented Programming?

| No. | FUNCTIONAL PROGRAMMING	| OOP |
| --- | --- | --- |
| 1. | Does not exist State	Exists State | Uses Immutable data	Uses Mutable data |
| 2. | It follows Declarative Programming Model	| It follows Imperative Programming Model. | 
| 3. | Stateless Programming Model	| Stateful Programming Model |
| 4. | Main Fcous on: “What you are doing”	| Main focus on “How you are doing” | 
| 5. | Good for Parallel (Concurrency) Programming	| Poor for Parallel (Concurrency) Programming | 
| 6. | Good for BigData processing and analysis	NOT  | Good for BigData processing and analysis | 
| 7. | Supports pure Encapsulation	| It breaks Encapsulation concept. | 
| 8. | Functions with No-Side Effects	| Methods with Side Effects | 
| 9. | Functions are first-class citizens	| Objects are first-class citizens |
| 10. | Primary Manipulation Unit is “Function”	| Primary Manipulation Unit is Objects(Instances of Classes) | 
| 11. | Flow Controls: Function calls, Function Calls with Recursion	| Flow Controls: Loops, Conditional Statements | 
| 11. | It uses “Recursion” concept to iterate Collection Data.	| It uses “Loop” concept to iterate Collection Data. For example:-For-each loop in Java | 
| 12. | Order of execution is less importance.	|  Order of execution is must and very important. | 
| 13. | Supports both “Abstraction over Data” and “Abstraction over Behavior”.	| Supports only “Abstraction over Data”. | 
| 14. | We use FP when we have few Things with more operations.	| We use OOP when we have few Operations with more Things. For example: Things are classes and Operations are Methods in Java. | 

**Q27.** Explain issues of Old Java Date API?   
What are the advantages of Java 8’s Date and Time API over Old Date API and Joda Time API?    
Java’s OLD Java Date API means Date API available before Java SE 8 that is Date, Calendar, SimpleDateFormat etc.  
Java’s Old Date API has the following Issues or Drawbacks compare to Java 8’s Date and Time API and Joda Time API.  
* Most of the API is deprecated.  
* Less Readability.  
* java.util.Date is **Mutable** and **not Thread-Safe**.  
* java.text.SimpleDateFormat is not Thread-Safe.  
* Less Performance.  

Java SE 8’s Date and Time API has the following Advantages compare to Java’s OLD Date API.  

Very simple to use.  
Human Readable Syntax that is More Readability.  
All API is Thread-Safe.  
Better Performance.

**Q28.** Why do we need new Date and Time API in Java SE 8?  
Explain how Java SE 8 Data and Time API solves issues of Old Java Date API?  
We need Java 8’s Date and Time API to develop Highly Performance, Thread-Safe and Highly Scalable Java Applications.  
Java 8’s Date and Time API solves all Java’s Old Date API issues by following Immutability and Thread-Safety principles.  

**Q29.** What are the Differences between Java’s OLD Java Date API and Java 8’s Date and Time API?   


**Q30.** What is Multiple Inheritance? How Java 8 supports Multiple Inheritance?
Multiple Inheritance means a class can inherit or extend characteristics and features from more than one parent class.

In Java 7 or Earlier, Multiple Inheritance is not possible because Java follows “A class should extend one and only one class or abstract class” Rule. However, it’s possible to provide Multiple Implementation Inheritance using Interface because Java follows “A class can extend any number of Interfaces” Rule.

However, Java 8 supports “Implementing Methods in Interfaces” by introducing new features: Default methods in Interface. Because of this feature, Java 8 supports Multiple Inheritance with some limitations.

**Q31.** What is Diamond Inheritance Problem? How Java 8 Solves this problem?



## References
1. [journaldev](http://www.journaldev.com/10081/javase8-interview-questions-part2). 
