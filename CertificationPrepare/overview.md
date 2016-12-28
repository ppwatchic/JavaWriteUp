## Topics 
* Util class
* Primitive/Wrapping class
* Exceptions
* IO/NIO
* Interface and Abstract class
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

###
