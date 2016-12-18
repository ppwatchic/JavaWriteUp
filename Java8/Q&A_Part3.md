**Q1.** Can Null reference call its static method without causing compile time/runtime error?  
**A1.** Yes. For the below code snippet
```
package lambdaExpression;

import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

class AWithStatic {
	public static void test() {
		System.out.println("in test.");		
	}
}

public class InternalIte {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		List<AWithStatic> list = new ArrayList<AWithStatic>(Arrays.asList(null,null));
		System.out.println(list.size());
		list.forEach(m->m.test());
	}

}
```
We can have output: 
```
2
in test.
in test.
```
`m.test()` is treated as `AWithStatic.test()`. Thus there is no `NullPointerException()`. 



