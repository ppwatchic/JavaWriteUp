## How to set entry point for a jar file?
**A.** If you have an application bundled in a JAR file, you need some way to indicate which class within the JAR file 
is your application's entry point. You provide this information with the Main-Class header in the manifest, 
which has the general form:
`Main-Class: classname`
The value classname is the name of the class that is your application's entry point.  
**Recall** that the entry point is a class having a method with signature `public static void main(String[] args)`.  

After you have set the Main-Class header in the manifest, you then run the JAR file using the following form of the java command:
`java -jar JAR-name` The main method of the class specified in the Main-Class header is executed.  
Example is [here](https://docs.oracle.com/javase/tutorial/deployment/jar/appman.html).

## How to execute a class with parameter in command line?  
