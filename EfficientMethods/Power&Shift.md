1, Math.pow(base, power) is comparative slow, if we can do it in shift operation. 
For example, for `Math.pow(2, 13)` and `2<<(13-1)`, the former takes: 22200ns; the later one: almost cost 0; 
The reason stems from: 
* Math.pow() operates on **double** data type, which can be expected slower than int data type;
* Math.pow() is basically **multiply** operations, one multiplication takes more than 4 clock cycle; while shift only takes one clock cycle. 
