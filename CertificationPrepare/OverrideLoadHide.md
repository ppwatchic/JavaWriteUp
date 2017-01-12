## Final method in a super class
Note: A final method in a super class can not be hiden, override from a subclass.   
There will be a compilation error if do so as shown in the code snippet:   
```
class Super {
  public final int getNext(int i) {
    return i++;
  }
}

class Sub extends Super {
  public int getNext(int i) { // Error, can only fix by remove final from Super class
    return i++;
  }
}
```
