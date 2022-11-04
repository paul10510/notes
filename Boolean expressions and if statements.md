## Boolean Expressions

### Boolean
- a boolean is a set of data that either evaluates to true or false

```
boolean a;
boolean b = true;
boolean c = false;
```

- Java has comparison operators called relational operators to evaluate true and false from data
- Arithmetic expression values can be compared using relational operators (i.e., <, >, <=, >=).

Relational Operator | Description | Description
--|--|--
a < b | a less than b | Equates to true if a is less than b, false otherwise.
a <= b | a less than or equal to b| Equates to true if a is less than or equal to b, false otherwise.
a > b | a greater than b | Equates to true if a is greater than b, false otherwise.
a >= b  | a greater than or equal to b | Equates to true if a is greater than or equal to b, false otherwise.  
a == b  | a equals b | Equates to true if a has the same value as b.  
a != b  | a does not equal b | Equates to true if a does not have the same value as b, false otherwise.

- when evaluating for equality you must use two equal signs.one equal sign is for assigning data and two s for evaluating it
- The not operator ! used to test for inequality

```
boolean a = true;
boolean b = !a; // not a, so b is assigned the value of false
```

- `boolean` is a primitive data type
- primitive values and reference values can be compared using relational operators.

## If Statements and Control Flow

### Program Flow

- One way selection (only an if statement) will only execute what is in the if statement under certain conditions
- The code in the body of the if statement, often referred to as the if clause, will be executed only when the Boolean condition is true.

#### if clauses

```java
public class IfDivideByZero 
{
  public static void main(String[] args) 
  {
    int a = 6;
    int b = 2;
    int c = 2;
    
    if (b != 0 ) 
    {
      System.out.println("a / b = " + (a / b));
    }

    b = 0;
    
    if (b != 0)
    { //Remove this line. 
      System.out.println("a / b = " + (a / b));
    } //Remove this line. 
    
  }
}
```

- If an if clause has one statement (like a boolean) you do not need the curly braces. If the If colause has two or more you will need the curly braces
- while not having the curly braces on a one statement if clause works, most programmers use the curly braces anyway to avoid confusion
- ***Indentation and Spacing** Java is not dependent on the indentation. Therefore the indentation does not matter when it comes to whether the code will compile, the only use for it is making the code mre readable*

#### Strings to ints

- `Integer()` and `Double()` have static methods to convert from string to int which can be helpful when taking user input

```
int i = Integer.parseInt(String str);
double d = Double.parseDouble(String str);
```

```java
import java.util.Scanner;

public class IfDivideByZeroWithInput
{
  public static void main(String[] args) 
  {
    double a;
    int b;
    String str;
    
    // Create a scanner to get user input.
    Scanner sc = new Scanner(System.in);
    
    System.out.print("Enter an double value for a: ");
    str = sc.nextLine();
    
    a = Double.parseDouble(str);
    
    System.out.print("Enter an integer value for b: ");
    str = sc.nextLine();
    
    b = Integer.parseInt(str);

    if (b != 0)
      System.out.println("a / b = " + (a / b));

  }
}
```

## If / Else statements

### Two Way Statements

- Two way slection statements (if else) will execute when the statement evaluates to true or false. 
- one segment will be executed when theb statement is true and the other when it is false

#### Nested if

- Nested if statements are when you put one if statement inside another if/esle statement

```
if (condition1) 
{
    if (condition2)
    {
        Statements;
    }
}
else
{
    if (condition3)
    {
        Statements;
    }
}
```

## Else / If Statements

### Multi-way section

- When you have multiple conditions that can evaluate to true or false, but only one will run

```
if (condition){
	Statement;
}
else if (condition){
	Statement;
}
else if (condition){
	Statement;
}
else{
	Statement;
}
```

- you can have as many else if statements as needed

## Compound Boolean Expressions

### Coumpound statements

- Simple expressions like `(a > b)` can be combined with other simple expressions to create compound boolean expressions
- to combine you can use the operators `!` (not), `|` (or), and `&&` (and)

```
((x >= 1) && (x <= 10)
```

Logical Operator | Description | Boolean Value
--|--|--
!a | not a | Evaluates to true if a is false; in other words, NOT is the opposite of a.
a && b | a and b | Evaluates to true when both a and b are true.
a \| \| b | a or b | Evaluates to true when either a or b is true.

-   (a > b) && (b > c)   evaluates to true if both a > b and b > c
-   (a > b) || (b > c) evaluates to true if either a > b or b > c
-   !(a > b) evaluates to true if a is not > b, in other words, if a <= b

#### Short Circuted evaluation
- when you only need the first part of the boolean expression to evaluate whether or not it is true of false Java will not execute the second expression

## Equivelant Boolean Expressions

### De Morgan's Laws

De Morgan’s laws are:
-   **not (a and b)** is the same as **(not a) or (not b)**
-   **not (a or b)** is the same as **(not a) and (not b)**

using the distributive property of mathematics:
-   Law 1: **not (a and b)** is the same as **(not a) or (not b)** 
	- Starting with **not (a and b)**, distribute the **not** and switch the logical operator to get **(not a) or (not b)**. In Java, this can be written as: `!(a && b) == (!a || !b)`
    
-   Law 2: **not (a or b)** is the same as **(not a) and (not b) 
	- **Again, distribute the not** and switch the logical operator to get **(not a) and (not b)** . In Java:  `!(a || b) == (!a && !b)`

Conditional Operator | De Morgan’s Law | De Morgan’s Law Applied
--|--|--
< | **not** < | >=
\> | **not** > | <=
== | **not** == | !=
\<= | **not <=** | \> 
\>= | **not** >= | <
!= | **not** not equal | ==

## Comparing Objects

### Object Equals

#### Comparing null objects

- Reference variables can be compared with null, using == or != to determine if the variable actually references an object.

#### Object Equality
- The == operator can be used to test whether whether two variables reference the same operator
```
String s1 = new String("HELLO");
String s2 = s1;
```

- if you compared s1 and s2 in the above example the return would be true because both objects reference the same location in memory, s1

```
String s1 = new String("HELLO");
String s2 = new String("HELLO");
```

- if you were to compare the above s1 and s2 variables the return would be false because they do not reference the same location in memory despite having the same value
-  to compare the values of the objects you must use then `equals()` method
```
s1.equals(s2);
```

```java
public class TestString
{ 
  public static void main(String[] args) 
  { 
    String s1 = new String("HELLO"); 
    String s2 = new String("HELLO"); 
    System.out.println("s1 == s2: " + (s1 == s2)); 
    System.out.println("s1.equals(s2): " + s1.equals(s2)); 
  } 
} 
```

#### Aliasing

```java
public class ShapeEquals
{
  public static void main(String[] args) 
  {
    Shape shape1 = new Shape();
    shape1.setShape("Triangle", 3);
  
    Shape shape2 = new Shape();
    shape2.setShape("Square", 4);
  
    Shape shape3 = shape1;
    shape3.setShape("Hexagon", 6);
    
    System.out.println(shape1.getShape());
  }
}
```

- You can have two variables set to the same area in memory. This makes it so that when you change any variable connected to that slot in memory, all the variables change

#### The Equals Method
- classes can define thier own equals method
- must provide an equals method to define how to compare the values of two of thier objects