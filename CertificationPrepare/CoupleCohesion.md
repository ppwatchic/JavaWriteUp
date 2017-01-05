## Cohesion
Cohesion refers to what the class (or module) will do.
Low cohesion would mean that the class does a great variety of actions and is not focused on what it should do. 
High cohesion would then mean that the class is focused on what it should be doing, i.e. 
only methods relating to the intention of the class.

Example of Low Cohesion:
```
-------------------
| Staff           |
-------------------
| checkEmail()    |
| sendEmail()     |
| emailValidate() |
| PrintLetter()   |
-------------------
```
Example of High Cohesion:
```
----------------------------
| Staff                   |
----------------------------
| -salary                 |
| -emailAddr              |
----------------------------
| setSalary(newSalary)    |
| getSalary()             |
| setEmailAddr(newEmail)  |
| getEmailAddr()          |
----------------------------
```
As for coupling, it refers to how related are two classes / modules and how dependent they are on each other. 
Being low coupling would mean that changing something major in one class should not affect the other. 
High coupling would make your code difficult to make changes as well as to maintain it, as classes are coupled closely together, 
making a change could mean an entire system revamp.

All good software design will go for **high cohesion** and **low coupling**.
