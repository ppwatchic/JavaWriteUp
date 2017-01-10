## CAI
C: class  
A: abstract class  
I: Interface  

## Interface
1. Question: Can interface implements interface?  
Answer: No. Interface can only extends interface(s).   
2. Question: Can abstract class implements interface?  
Answer: Yes.   
Follow-up questions: Does the abstract class have to implement the method(s) of the interface?  
Answer: Not necessary. Example as below:  
 ```
 // Interface 
 public interface Convertable {
 	int convertToInt();	// with an implicitly public modifier 
	char convertToChar();
	float convertToFloat();
 }

// Another file 
abstract class AbstrClass implements Convertable {
	public abstract void abstrc(); // abstract modifier for the method is A-MUST. 
	
	public abstract int convertToInt();	// Error if we missed the abstract modifier 
	public abstract char convertToChar();	// Error if we missed the public modifier 
	// It is ok if abstract class didn't implement some method(s) in the interface. 
}
 ```  
3. All interface methods are implicitly public if not specified. And all classes that implement this interface can not reduce the visibility level of this method.  



## [Override and Hiding](https://coderanch.com/wiki/659959/Overriding-Hiding) 
The following code snippet:  
```
class Foo {
    public static void method() {
        System.out.println("in Foo");
    }
}
 
class Bar extends Foo {
    public static void method() {
        System.out.println("in Bar");
    }
}
```
is an example of a static method **hiding** another static method.  
The difference: Briefly, when you override a method, you still get the benefits of run-time polymorphism, and when you hide, you don't. 

## Abstract class and synchronized key word
The following code DOESN'T work:  
```
abstract class AbstractA {
	final void f() {}
	abstract synchronized void g(); // Compiler Error Here
    static abstract void testMethod();  // Compiler Error Here 
	static void h(){}
	public static void main(String[] args) {
		AbstractA obj;
	}
}
```
And here are some [explanation](http://stackoverflow.com/questions/12805698/why-cant-an-abstract-method-be-synchronized): 
Whether or not a method is synchronized is an **implementation** detail of the method. Synchronization isn't specified anywhere as a declarative contract - it's not like you can synchronize in interfaces, either.

static method will never be overriden, its implementation is final. Abstract method which has no implement functionality, will have to implement in a subclass. The two modifiere contracts with each other. 




