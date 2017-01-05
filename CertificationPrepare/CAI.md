## CAI
C: class  
A: abstract class  
I: Interface  

## Interface
1. Question: Can interface implements interface?  
Answer: No. Interface can only extends interface(s). 

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




