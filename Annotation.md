##Java Annotation

1, Annotation is first added to Java 5.  
2, Java annotations are typically used for the following purposes:  
    Compiler instructions  
    Build-time instructions  
    Runtime instructions    
3, **Build-in** annotations  
  Java comes with three built-in annotations which are used to give the Java compiler instructions. These annotations are:   
  * Deprecated  
  * Override  
  * SuppressWarnings    
Each of these annotations are explained in the following sections.  
4, Creating Your Own Annotation
It is possible to create your own (custom) Java annotations.   
Annotations are defined in their own file, just like a Java class or interface.   
Here is custom Java annotation example:
```
@interface MyAnnotation {

    String   value();

    String   name();
    int      age();
    String[] newNames();

}
```
5, **@Retention**
You can specify for your custom annotation if it should be available at runtime, for inspection via reflection.   
You do so by annotating your annotation definition with the **@Retention** annotation. Here is how that is done:
``` 
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;

@Retention(RetentionPolicy.RUNTIME)

@interface MyAnnotation {

    String   value() default "";

}
```  
Notice the **@Retention** annotation added above the `MyAnnotation` definition:

`@Retention(RetentionPolicy.RUNTIME)`  
This is what signals to the Java **compiler** and **JVM** that the annotation should be available via reflection at runtime.  
Accessing annotations at runtime is covered in [Java Reflection and Annotations](http://tutorials.jenkov.com/java-reflection/annotations.html) tutorial,   
which is part of Java Reflection Tutorial.

The RetentionPolicy class contains two more values you can use:  

**RetentionPolicy.CLASS** means that the annotation is stored in the `.class` file, but not available at runtime.   
This is the default retention policy, if you do not specify any retention policy at all.

**RetentionPolicy.SOURCE** means that the annotation is only available in the source code, 
and not in the `.class` files and not a runtime. If you create your own annotations for use with build tools that scan the code, 
you can use this *retention* policy. That way the `.class` files are not polluted unnecessarily.

6, **@Target**
You can specify which Java elements your custom annotation can be used to annotate.   
You do so by annotating your annotation definition with the **@Target** annotation.   
Here is a **@Target** Java annotation example:
```
import java.lang.annotation.ElementType;
import java.lang.annotation.Target;

@Target({ElementType.METHOD})
public @interface MyAnnotation {

    String   value();
}
```  
The ElementType class contains the following possible targets:  
* ElementType.ANNOTATION_TYPE
* ElementType.CONSTRUCTOR
* ElementType.FIELD
* ElementType.LOCAL_VARIABLE
* ElementType.METHOD
* ElementType.PACKAGE
* ElementType.PARAMETER
* ElementType.TYPE  

Most of these are self explaining, but a few are not. Therefore I will explain the targets which are not obvious.

The **ANNOTATION_TYPE** target means Java annotation definitions.   
Thus, the annotation can only be used to annotate other annotations. Like the @Target and @Retention annotations.  
The TYPE target means any type. A type is either a class, interface, enum or annotation.  


##Reference 
1, [Java Annotations by Jakob Jenkov] (http://tutorials.jenkov.com/java/annotations.html) 
2, source code for [java.lang.annotation.ElementType](http://grepcode.com/file/repository.grepcode.com/java/root/jdk/openjdk/6-b27/java/lang/annotation/ElementType.java#ElementType%5B%5D).
