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
The output will be "1 thrown to main".  There will be actually an `IllegalMonitorStateException` in Java. 
Reason: go() method didn't own the monitor of t1. 

## Monitor
Each object in Java is associated with a monitor, which a thread can lock or unlock. Only one thread at a time may hold a lock on a monitor. 

## Synchronized method 
To make a method synchronized, simply add the synchronized keyword to its declaration. 

## Constructors cannot be synchronized



