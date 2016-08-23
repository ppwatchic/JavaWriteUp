Had a problem about static import. and spent a little time to figure out what. 

```
import static java.lang.System.out;     // correct
import static java.lang.System.out.*;   // wrong
import static java.lang.System.*;       // correct
```

**fields** and **methods** are two ingredients of a java class.  
For import static, we can import all static fields and methods from the class. So the syntax is like: 
```
import static [java class name].*; 
```

Or if we just want to import a specific field or method, it goes like this: 
`[java class name].field_name; ` or `[java class name].method_name;`

So in the above code snippet, `out` is the field of `java.lang.System class`. 

