## Arrays.asList()
1. what is the output of the below code snippet:  
```
import java.util.*;

public class Test {
  public static void main(String[] args) {
    String[] arr = { "Java", "Collections", "." };
    List<String> list = (List<String>) Arrays.asList(arr); // line 1
    arr[2] = "Arrays"; // line 2
    for (String word : list) {
      System.out.print(word);
    }
    
    // Insert Here 
    // list.remove(0); // Compile Ok? Runtime Ok?
    // (ArrayList)list;
  }
}
```  
Output: `JavaCollectionsArrays`.  
2. Will `list.remove(0)` in the above code snippet both compile and run with no exception?  
*No, No, No.* It compiles Ok. However there will be an `UnsupportedOperationException` during runtime.  
`list` is the an object of `java.util.Arrays.ArrayList`, not `java.util.ArrayList`.  
You will get an cast error if we try to `List<String> nlist = (ArrayList<String>)list;`. 



