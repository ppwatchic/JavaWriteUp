**Interface:**

In general, an interface exposes a contract without exposing the underlying implementation details.  
In Object Oriented Programming, interfaces define abstract types that expose behavior, but contain no logic. 
Implementation is defined by the class or type that implements the interface.

@interface : (denotes an Annotation type)

Take the below example Which has a lot of comments.
```
public class Generation3List extends Generation2List {

   // Author: John Doe
   // Date: 3/17/2002
   // Current revision: 6
   // Last modified: 4/12/2004
   // By: Jane Doe
   // Reviewers: Alice, Bill, Cindy

   // class code goes here
}
```
Instead of this , u can use like this[declaration]
```
 @interface ClassPreamble {
   String author();
   String date();
   int currentRevision() default 1;
   String lastModified() default "N/A";
   String lastModifiedBy() default "N/A";
   // Note use of array
   String[] reviewers();
}
```
this can be used as:
```
@ClassPreamble (
   author = "John Doe",
   date = "3/17/2002",
   currentRevision = 6,
   lastModified = "4/12/2004",
   lastModifiedBy = "Jane Doe",
   // Note array notation
   reviewers = {"Alice", "Bob", "Cindy"}
)
public class Generation3List extends Generation2List {

// class code goes here

}
```
PS: Many annotations replace comments in code.

## References
1. [Oracle Docs](http://docs.oracle.com/javase/tutorial/java/annotations/declaring.html).
2. [Stack Overflow](http://stackoverflow.com/questions/918393/whats-the-difference-between-interface-and-interface-in-java).
