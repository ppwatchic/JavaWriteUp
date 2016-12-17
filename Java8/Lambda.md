## What is Lambda? 
Lambdas are used to create function objects.  
With them, we can specify methods inside other methods—and even pass methods as arguments to other methods. 
Classes like Function, Supplier, Consumer, accept lambdas with specific shapes.  

List 1. Function 
```
import java.util.function.*;

public class FuncExample {
  public static void main(String[] args) {

	  // Create a Function from lambda expression.
	  // ... It returns power 2 of the argument.
	  Function<Integer, Integer> func = x -> x*x;

	  // Apply the function to an argument of 10.
	  int result = func.apply(10);
	  System.out.println(result);
  }
}
```

## What is Predicate Lambda? 
The term predicate is used in computer science to mean a boolean-returning method.  
A Predicate object receives one value and returns true or false.  
```
import java.util.ArrayList;

public class Program {
    public static void main(String[] args) {

	// Create ArrayList and add four String elements.
	ArrayList<String> list = new ArrayList<>();
	list.add("cat");
	list.add("dog");
	list.add("cheetah");
	list.add("deer");

	// Remove elements that start with c.
	list.removeIf(element -> element.startsWith("c"));
	System.out.println(list.toString());
    }
}
```
