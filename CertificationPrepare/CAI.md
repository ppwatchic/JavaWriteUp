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




