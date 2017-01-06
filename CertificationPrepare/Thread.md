## What is the output?
```
public class Bees {
  public static void main(String[] args) {
    try {
      new Bees().go();
    } catch (Exception e) {
      System.out.println("thrown to main");
    }
  }
  synchronized void go() throws InterruptedException {
    Thread t1 = new Thread();
    t1.start();
    System.out.print("1 ");
    t1.wait(5000);
    System.out.print("2 ");
  }
}
```
The output will be "1 thrown to main". 
Reason: main and t1 will compete the lock for go() method and then there is exception. 
