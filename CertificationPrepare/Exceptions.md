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

## Division by 0
1. For `int` type, There will be an exception when it is divided by 0. 
2. For `float` or `double` types in Java, like pretty much any other language out there (and pretty much any hardware FP unit), implement the **IEEE 754** standard for floating point math, which mandates division by zero to return a special **infinity** value. Throwing an exception would actually violate that standard.  
```
		int i = -4;
		try {
		i /= 0;
		} catch (ArithmeticException e) {
			System.out.println("Exception");
		} finally {
			System.out.println("Int type division by 0: " + i);
		}
		
		double d  = -4.0;
		try {
		d /= 0;
		} catch (ArithmeticException e) {
			System.out.println("Exception");
		} finally {
			System.out.println("Double type division by 0: " + d);
		}
```

## Throws clause 
1. Questions: Will compiler complain if two exceptions (super-class and sub-class relationship) throws at a method?  
Will it matter for the order of the exceptions?  
Does it ok if we throw same exceptions twice?  
```

class Base {
	void getNext() throws IllegalArgumentException{
		
	}
}

public class OverRidePrac extends Base {
	
	@Override
	//void getNext() throws RuntimeException, IllegalArgumentException{	// OK? Yes
	//void getNext() throws IllegalArgumentException, RuntimeException{	// OK? Yes
	void getNext() throws IllegalArgumentException, IllegalArgumentException{	// OK? Yes
		throw new IllegalArgumentException();
	}

	public static void main(String[] args) {
		try {
			new OverRidePrac().getNext();
		} catch (RuntimeException re) {
			System.out.println("RE" );
		}
	}
}
```



