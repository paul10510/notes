# Notes 11.1.22

- Test will be on classes and objects

## Constructors, objects, instance variables, and classes

```java
public class Student { //class
    private String name; //instance variable
    private int stuId; //instance variable

    public Student(){} //default constructor

    public Student(String nm, int id){ //constructor
        name = nm; //passthrough value to instance variable
        stuId = id; //passthrough value to instance variable
    }

    public void changeId(int newId){ //method
        System.out.println("My new ID is: " + newId); //spaghet code
        stuId = newId;
    }

    public static void main(String[] args){
        Student s1 = new Student("Mary", 223169); //declares new Student object using the Student constructor with parameters

        Student s2 = new Student(); //creates a new Student object using the default Student constructor

        s1.changeId(246675); //calls the changeId() method and passes a new parameter to s1.stuId
    }
}
```

### Constructors

- A constructor is used to invoke or call on a class to execute the code in it.
- You can use a constructor with parameters to create an object that has parameters
- If you have a constructor with parameters, but still want to call a default object you must declare a default constructor within that class

### Objects

- Objects can have nested values like in the student example where s1 has the nested value of `name` which you can call with `s1.name` This would return `Mary `
- You can use objects to call methods that are a part of that class, for example `s1.changeId()` which calls the `changeId()` method that ois part of the `Student` class

### Instance variables

- Instance variables are where the nested values that are part of an object are stored. 

### Classes

- A class is a formal design defining all attributes and behaviors of an object.
- A class can contain methods that manipulate that class or other data.

## String Methods

```java
public class stuff{
    public static void main(String[] args){
        String myString = "hello";

        int myStringLength = myString.length(); //returns the length of the myString varable and passes it to the value of the myStringLength variable

        int myStringH = myString.indexOf("h"); //returns the index of the letter "h" in myString and passes it to the value of myStringH variable therefore myStringH = 0

        String newString1 = "Hello my name is Paul.";

        String newString2 = newString1.subString(0, 6); //takes all of the characters from index 0 up to but not including index 6 and stores them in the value of the variable newString2

    }
}
```
- String methods ar the built in Java methods that manipulate Strings. 
- The main String methods on this test will be `indexOf()`, `subString()`, and `length()`.

### indexOf()
- The `indexOf()` method takes in a `String` parameter and will return the first instance of that strings index.

## Math Methods

```java
public class stuff{
    public static void main(String[] args){
        int min = 1;
        int max = 4;

        int randomNumber = (int) (Math.random() * (max - min) + min); //returns a random umber bewteen 1 and 4 and stores that value in randomNumber

        int sqrtOf4 = Math.sqrt(4); //returns the square root of 4 and stores it in a variable

        int fourSquared = Math.pow(4, 2); //returns the value of the first passed through variable to the power of the second passed through variable into the value of the variable fourSquared
    }
}
```

- Math methods are the built in Java methods that can manipulate Integers and doubles
- The main Math methods on this test will be the `Math.random()` method, the `Math.sqrt()` mrthod, and the `Math.pow` method

### Math.random()

- chooses a random number between 0 and 1. You can apply algorithms to this method to get random numbers between any values.
- to get a random number between 0 and `int max` you can do `Math.random() * max`
- to get a number between `int min` and `int max` you can do `Math.random() * (max - min) + min`

### Math.sqrt()

- returns the square root of whatever integer or double parameter you pass to it

### Math.pow()

- returns the value of the first parameter you pass to the power of the second passed parameter.
- For example: `Math.pow(3, 3)` would return 27
