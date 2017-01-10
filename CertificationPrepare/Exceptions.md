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
Answer: >At the level of the Java Virtual Machine, every constructor written in the Java programming language (JLS §8.8) appears as an instance initialization method that has the special name <init>. This name is supplied by a compiler. Because the name is not a valid identifier, it cannot be used directly in a program written in the Java programming language.
