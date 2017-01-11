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

## java.lang.NullPointerException
```
Class NullPointerException

	java.lang.Object
		java.lang.Throwable
			java.lang.Exception
			java.lang.RuntimeException
```  
java.lang.NullPointerException is an unchecked exception. 
> The unchecked exception classes (§11.1.1) are exempted from compile-time checking.  

## Method signature
1. Methods that throw unchecked exceptions in Java must delcare it in the method signature
2. Is it ok to declare exceptions in a method signature while the method body doesn't throw any exception?  
Yes.  There will be no compile errer for the below code snippet. 
```
void method() throws Exception {
	return; 
}

// Or the following format is OK
void method1() throws IOException {
	try {
		throw new IOException();
	} catch {
		System.out.println("in method1()");
	}
}
```

## Finally block
Question: Will finally block always being executed? 
Answer: It depends. If the thread itself dies, then there is no way to execute finally block. Otherwise it will be executed anyway.  
Code snippet that it is not executed:  
```
	System.out.print("1");
	try {
		System.out.print("2");
		System.exit(0);	    // thread itself exit 
	} finally {
		System.out.print("3"); // won't print 3 in the output 
	}
```  
Follow-up question: What is `System.exit(0)` ?  
Answer: `exit(int stautsCode)` Terminates the currently running Java virtual machine by initiating its shutdown sequence. This method never returns normally. The argument serves as a status code; 0 means exit normally; >0 means something you expected go wrong (like file output stream exception); <0 means unexpected error (like hardware error). 

