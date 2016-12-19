## Diamond Operator
JDK 7 onwards, we can code like this with the diamond operator <>:  
```
Map<String, List<String>> map = new HashMap<>();
```

## String in Switch statement
In JDK 7, we can use a String object as the selector for switch-case statement. 

## Automatic Resource Management  
Before JDK 7, we need to use a `finally` block to ensure that a resource is closed regardless of whether the try statement   
completes normally or abruptly. For example, while reading files and streams, we need to close them in a finally block, which 
results a lot of boiler plate and messy code. 

## Fork Join Framework 

## Underscore in Numeric literals 

## Catching Multiple Exception Type in Single Catch Block 
If there is more than one exception in a try-catch block, we can use "|" to separate them. 
```
try {
...
} catch (ClassNotFoundException | SQLException ex) {
  ex.printStackTrace();
}
```
> Note: Alternatives in a multi-catch statement cannot be related by sub classing. For example, this will throw compile time error: 
`catch(FileNotFoundException | IOException ex) {...}`. 

## Java NIO 2.0 
1. Introduce Path class which allows to represent any path in OS. 
2. New File API is also capable of searching for files using wild cards. 
3. NIO stands for non-blocking IO. 

## G1 Garbage Collector


