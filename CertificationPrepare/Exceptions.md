## Can constructor throw exceptions?  
Yes. 

## What is the problem with the code snippet? 
```
import java.io.IOException;
class AirPlane {
public AirPlane() throws IOException, RuntimeException {
System.out.println(&quot;AirPlane&quot;);
}
}
class AirJet extends AirPlane { } // line 7
```  
Error: For line 7, default constructor cannot handle IOException throw by implicite super constructor. 

## Uncaught exceptions
Java programming language does not require methods to catch or to specify unchecked exceptions (**RuntimeException**, **Error**, and their subclasses),

## \<Init> in stack trace
```
Exception in thread "main" java.lang.RuntimeException
	at exceptions.Father.<init>(Tester.java:6)
```
Question: What is \<init>?  
Answer:  
> At the level of the Java Virtual Machine, every constructor written in the Java programming language (JLS §8.8) appears as an instance initialization method that has the special name <init>. This name is supplied by a compiler. Because the name is not a valid identifier, it cannot be used directly in a program written in the Java programming language.  

## Class Throwable 
Class Throwable is the super class of `Error`, and `Exception`. 
[The Throwable class](http://docs.oracle.com/javase/7/docs/api/java/lang/Throwable.html) is the superclass of all errors and exceptions in the Java language. Only objects that are instances of this class (or one of its subclasses) are thrown by the Java Virtual Machine or can be thrown by the Java throw statement. Similarly, only this class or one of its subclasses can be the argument type in a catch clause. For the purposes of compile-time checking of exceptions, Throwable and any subclass of Throwable that is not also a subclass of either RuntimeException or Error are regarded as checked exceptions.
