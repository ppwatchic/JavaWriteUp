## Topics 
* Util class
* Primitive/Wrapping class
* Exceptions
* IO/NIO
* Interface and Abstract class
* Nested class
* Modifiers
* Initialization order

## Util class
1. Locale  
There are 4 ways to create a Locale object. 
Code snippet: 
```
	Locale loc = new Locale("en", "US");	// constructor
	Locale loc2 = Locale.forLanguageTag("en-US");	// factory method
	Locale loc3 = new Locale.Builder().setLanguage("en").build();	// Builder
	Locale loc4 = Locale.ENGLISH;	// Locale constants
```
2. Arrays.sort(Object[] a): Sorts the specified array of objects into ascending order, according to the natural ordering of its elements. All elements in the array must implement the Comparable interface. Furthermore, all elements in the array must be mutually comparable (that is, e1.compareTo(e2) must not throw a ClassCastException for any elements e1 and e2 in the array).
The above code snippet will throw a `java.lang.ClassCastException`: 
```Java
	Object[] myObjects = {
				new Integer(12),
				new String("foo"),
				new Integer(5), 
				new Boolean(true)
		};
	Arrays.sort(myObjects);
```
3. NavigableSet is an interface. We cannot `new NavigableSet<>()`. 


## Primitive/Wrapping class
### Integer
Integer is immutable object. 
Code snippet: 
```
		Integer x = 100;
		Integer y = x;
		x++;    // a new Integer object is constructed 
		System.out.println(x==101);	// true
		System.out.println(x==y);	// false
		System.out.println(y);	// 100
```

### String 
1. split() method. 
Code snippet: 
```
    String str= "She sells sea shells.";
    System.out.println(Arrays.toString(str.split("\\s")));	// space
    String inputString = "a1b2c3";
    System.out.println(Arrays.toString(inputString.split("\\d")));	// digit
    System.out.println(Arrays.toString(inputString.split("\\d", 2)));	// digit
```

## Exceptions
### Catch order matters
when catching exceptions you want to always catch the most specific first and then the most generic. 
The wrong way below: 
```
	catch(Exception e) {
		System.out.println("Exception");
	} catch(ArithmeticException ae) {	// We should move this exception before Exception.
		System.out.println("A Exception");
	}
```

## Nested class
The Java programming language allows you to define a class within another class. Such a class is called a nested class and is illustrated here:
```
class OuterClass {
    ...
    class NestedClass {
        ...
    }
}
```
Terminology: Nested classes are divided into two categories: **static** and **non-static**. Nested classes that are declared static are called static nested classes. Non-static nested classes are called inner classes.
```
class OuterClass {
    ...
    static class StaticNestedClass {
        ...
    }
    class InnerClass {
        ...
    }
}
```
A nested class is a member of its enclosing class. Non-static nested classes (inner classes) have access to other members of the enclosing class, even if they are declared private. Static nested classes **DO NOT** have access to other members of the enclosing class. As a member of the OuterClass, a nested class can be declared private, public, protected, or package private. (Recall that outer classes can only be declared public or package private.)

To create an object for the static nested class, use this syntax:
```
OuterClass.StaticNestedClass nestedObject =
     new OuterClass.StaticNestedClass();
```


### Interface
1. How to access interface constant variable?
Code snippet: 
```
interface DoSomeStuff {
	public static final int STUFF = 3;
	
	void doStuff(int t);
}

public class TestDeclare {

	public static void main(String[] args) {
		int x = 5;
		new TestDeclare().doStuff(x++);
	}
	
	void doStuff(int s) {
		s += DoSomeStuff.STUFF+ ++s;
		System.out.println("s " + s);
	}

}
```

### Abstract class
1. NumberFormat is an abstract class. It has no public constrcutor; instead use factory method to create an object of this class.   
Code snippet: 
```
	NumberFormat nf = NumberFormat.getInstance(Locale.ITALY);
	String s = nf.format(123.45);
	System.out.println(s);
```

## Exceptions
1. ParseException
Code snippet: 
```
	NumberFormat numf = NumberFormat.getInstance(Locale.US);
	Number N;
	String ns = "123.4567";
	numf.setMaximumFractionDigits(2);
		
	try {
		N = nf.parse(ns);
		System.out.println(N);
	} catch(ParseException ne) {
		System.out.println("Exception");
	}
```

## ION/NIO
### [Console](https://docs.oracle.com/javase/7/docs/api/java/io/Console.html)
1. `System.console()` may return `null`. 
2. `Java.io.Console` is sinced Java 1.6. 

### Java.io.File
1. `isDirectory()` to check if the file is a directory. 
2. `delete()` Deletes the file or directory denoted by this abstract pathname.
3. `listFiles()` Returns an array of abstract pathnames denoting the files in the directory denoted by this abstract pathname.
4. `list()` Returns an array of strings naming the files and directories in the directory denoted by this abstract pathname.

### Java.io.file.Files
1. It can set or get file attributes. 

### Java.io.file.FileStore
Storage for files. A FileStore represents a storage pool, device, partition, volume, concrete file system or other implementation specific means of file storage. The FileStore for where a file is stored is obtained by invoking the getFileStore method, or all file stores can be enumerated by invoking the getFileStores method.

## Initialization Order
The correct order of initialisation is:  
1. Static variable initialisers and static initialisation blocks, in textual order, if the class hasn't been previously initialised.
2. The super() call in the constructor, whether explicit or implicit.
3. Instance variable initialisers and instance initialisation blocks, in textual order.
4. Remaining body of constructor after super().

