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

**Q2.** What would be the correct output in the below code? 
```
package init;

class A {
	A() {
		System.out.println("A");
	}
	
	// inner classes are tied to an enclosing instance of their outer class unless declared static,
	class B {
		B() {
			System.out.println("B");
		}
	}
}

public class InitOrder extends A.B{
	InitOrder() {
		System.out.println("C");
	}
	
	
	public static void main(String[] args) {
		new InitOrder();
	}
}
```
**A2.** Compile time error because if inner class B is not static, class InitOrder can not extends it. 