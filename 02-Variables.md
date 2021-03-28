# Variables

* Is the basic unit of storage in a Java program.
* All variables have an scope, which defines their visibility and lifetime.
* A variable is defined by the combination of an identifier, a type and a optional initializer.



## Variable Names

There are 4 rules to name a variable.

+ They must begin with a word, the symbol $ or _
+ They could include numbers but not begin with them
+ Since Java 9 a simple _ can not be a variable name
+ Can not use the same name of a **keyword**

The Java keywords are the next:

![image-20210327200955256](D:\Personal\Cursos\JAVA\02-Variables.assets\image-20210327200955256.png)

Include **true**, **false** and **null**

### Variable name styling

+ **Camel case**

  Examples: *getName*, *setDirection*, calculateRent

+ **Snake case**

  Examples: *get_name*, set_direction, calculate_rent



## Declaring Variables

In Java, all variables must be declared before they can be used. The basic form of a variable declaration is shown here:

> type *identifier* [ = value ]

**type**: is one of Java's atomic types or the name of a class or interface.

**identifier**: is the name of the variable.

```java
int a, b, c; 				// declares three ints
int d = 3, e, f = 5			// declares three ints, initializing d and f
double pi = 3.14159			// declares and initializing an approximation of pi

Car myCar = new Car();		// declares and class instance

// This fragment is wrong!
count = 100;				// cannot use count before it is declared!
int count;
```



## Dynamic Initialization

Java allows variables to be initialized dynamically, using any expression valid at the time the variable is declared.

```java
double a = 3.0, b = 4.0;			// declares and initializing two doubles
double c = Math.sqrt(a*a+b*b);		// c is dynamically initialized
```



## Default Initialization Value

![image-20210327193631410](D:\Personal\Cursos\JAVA\02-Variables.assets\image-20210327193631410.png)



## Var to declare local variables

Java has var keyword to declare local variables, which allow you to declare a variable without their type, for example:

```java
// Before
String str = "Java";

// With var
var str = "Java"; // infers String

// Other examples:
var list = new ArrayList<String>(); // infers ArrayList<String>
var stream = list.stream(); // infers Stream<String>s
```

**Var** is only for local variables consider the next examples:

```java
// Valid
public void whatTypeAmI() {
    var name = "Hello";
    var size = 7;
}

// Not Valid
public class VarKeywordFailExample {
    var tricky = "Hello"; // Does not compile
}
```

Once the **var** is initializing his type can not change, for example:

```java
public void reassignment() {
    var number = 7;
    number = 4;
    number = "five"; // Does not compile
    
    var apples = (short) 10;
    apples = (byte) 5;
    apples = 1_000_000; // Does not compile
}
```

The follow var initializing also are invalid.

```java
public void invalidInitializing() {
    int a, var b = 3; // Does not compile
    var n = null; // Does not compile
}
```

### Var - var

**Var** is not a java keyword, but **var** it is for. For these reason is forbidden use **var** as class, interface or enum name.

```java
package var;

// Valid
public class Var {
    public void var() {
        var var = "var";
    }
    
    public void Var() {
        Var var = new Var();
    }
}

// Not valid
public class var { // Does not compile
    public var() {
    }
}
```

### Var rules

+ A **var** can be used as a local variable inside a *constructor*, *method* or *initializing block*.

+ Can not be used as *parameter*, *instance variable* or *class variable*.

+ They always must be initialized on the same line where it is declared.

+ His value can change but not his type.

+ A **var** can not been initialized with **null** value.

+ A **var** is not allowed in multiple variable declarations.

+ **Var** is not a java keyword, but **var** it is for. For these reason is forbidden use **var** as class, interface or enum name.

  

## The Scope and Lifetime of Variables

Java allows variables to be declared inside any block, a block is begun with an opening curly brace and ended by a closing curly brace.

```java
{ // opening block
    int anyValue = 23;
} // ending block
```

A block defines a  ***scope***. Thus, each time you start a new block, you are creating a new scope.

A ***scope*** determines what objects are visible to other parts of your program. It also determines the lifetime of those objects.

![image-20210301204401011](D:\Personal\Cursos\JAVA\Variables.assets\image-20210301204401011.png)



Here is another important point to remember: variables are created when their scope is entered and, destroyed when their scope is left. This means that a variable will not hold its value once it has gone out of scope. Also, a variable declared within a block will lose its value when the block is left.

![image-20210301205150629](D:\Personal\Cursos\JAVA\Variables.assets\image-20210301205150629.png)



## Type Conversion and Casting

If you have previous programming experience, then you already know that it is fairly common to assign a value of one type to a variable of another type. If the two types are compatible, then Java will perform the conversion automatically.

For example:

* Assign an **int** value to a **long** variable
* Assign **short** value to a **int** or **long** value

However, not all types are compatible. For instance, there is no automatic conversion between incompatible types. To do so, you must use a cast, which performs an explicit conversion between incompatible types.

### Java's Automatic Conversions

Is valid if:

* The two types are compatible.
* The destination type is larger than the source type.

When these two conditions are met, a *widening conversion* take place. For example:

+ The **int** type is always large enough to hold all valid **byte** values, so no explicit cast statement is required.

For widening conversions, the numeric types, including integer and floating point types, are compatibles with each other. However, there are no automatic conversions from the numeric types to **char** or **boolean**. Also, **char** and boolean are not compatible with each other.