## What is the output from the following code snippet?
```
public class MyA {
	static int count = 0;
	// Class statement 
	static {
		count++;
	}
	
	// Object statement 
	{
		count++;
	}
	
	public void printCount() {
		System.out.println(count);
	}
	
	public static void main(String[] args) {
		MyA ma1 = new MyA();
		ma1.printCount();
		MyA ma2 = new MyA();
		ma2.printCount();
		
	}

}
```
**A.** It would be 2 and 3. 
Because the static {count++} code block belongs to class statement, and {count} is object-wise statement. 

