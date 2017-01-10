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
Question: What is <init>?  
