# Java Data Types

It is important to state at the outset that Java is a strongly typed language.
Indeed, part of Java’s safety and robustness comes from this fact. Let’s see
what this means:

* Every variable and expression has a type and every type is strictly defined.
* All Assignments, whether explicit or via parameter passing in method calls, are checked for type compatibility.
* There are no automatic coercions or conversions of conflicting types as in some languages.
* The Java compiler checks all expressions and parameters to ensure that the types are compatible.
* Any type mismatches are errors that must be corrected before the compiler will finish compiling the class.

## The primitive Types

Java defines eights *primitive types* of data **byte, short, int, long, char, float, double** and **boolean**.

These can be put in four data types groups.

* **Integers:** This group includes **byte, short, int** and **long** which are for whole-valued signed numbers.
* **Floating-point numbers:** This group includes **float** and **double** which represent numbers with fractional or decimal precision.
* **Characters:** This group include **char** which represents symbols in a character set, like letters and numbers.
* **Boolean:** Only the **boolean** is consider into this group, which is a especial type for *true* or *false* values.

![image-20210227220431327](D:\Personal\Cursos\JAVA\01-Java Data Types.assets\image-20210227220431327.png)

### Integers

![image-20210227220702308](D:\Personal\Cursos\JAVA\01-Java Data Types.assets\image-20210227220702308.png)



### Floating-Point Types

![image-20210227221226215](D:\Personal\Cursos\JAVA\01-Java Data Types.assets\image-20210227221226215.png)



### Characters

In Java, the data type used to store characters is char. A key point to understand is that Java uses Unicode to represent characters. Unicode defines a fully international character set that can represent all of the characters found in all human languages. It is a unification of dozens of character sets, such as Latin, Greek, Arabic, Cyrillic, Hebrew, Katakana, Hangul, and many more. At
the time of Java’s creation, Unicode required 16 bits. Thus, in Java char is a 16-bit type. The range of a char is 0 to 65,536. There are no negative chars. The standard set of characters known as ASCII still ranges from 0 to 127 as always, and the extended 8-bit character set, ISO-Latin-1, ranges from 0 to 255. Since Java is designed to allow programs to be written for worldwide use, it makes sense that it would use Unicode to represent characters. Of course, the use of Unicode is somewhat inefficient for languages such as English, German, Spanish, or French, whose characters can easily be contained within 8 bits. But such is the price that must be paid for global portability.



### Boolean

Java has a primitive type, called boolean, for logical values. It can have only one of two possible values, true or false. This is the type returned by all relational operators, as in the case of a < b. boolean is also the type required by the conditional expressions that govern the control statements such as if and for.



## Integer Literals

Integers are probably the most commonly used type in the typical program. Any whole number is a integer literal. Examples are 1, 2, 3 and 50. These are all decimal  values, meaning they are describing a *base 10* number.

In Java two other bases can be used are ***octal*** (base 8) and ***hexadecimal*** (base 16)

* **Octal** values are denotated in Java by a leading zero

  ```java
  int octalValue1 = 07;
  int octalValue2 = 07345;
  ```

  Thus the value **09** produces an error from the compiler, because 9 is outside of octal's (0-7)

  ```java
  int invalidOctalValue = 09; // produces an compiler error
  ```

  

* **hexadecimal** which matches cleanly with modulo 8 word sizes, such as 8, 16, 32, and 64 bits. You signify a hexadecimal constant with a leading zero-x, (0x or 0X). The range of a hexadecimal digit is 0 to 15, so A through F (or a through f ) are substituted for 10 through 15.

  ```java
  int hexadecimalValue1 = 0x6AD9876;
  int hexadecimalValue2 = 0X6AD9876;
  ```

  

* Integer literals create an int value. Is possible assign an integer literal to other integer types such as **byte** or **long** without causing a mismatch error. However, to specify a **long** literal, you will need to explicitly tell the compiler that the literal value is of type **long** appending an uppercase or lowercase ***L***

  ```java
  long hexadecimalValue1 = 0x7ffffffffffffffL;
  ```

  You can also specify integer literals using binary. To do so, prefix the value with **0b** or **0B**. For example.

  ```java
  int binaryValue = 0b1010;
  ```

* An integer can also be assigned to a char as long as it is within range.

* Another use of integer literals

  ```java
  int x = 123_456_789;
  int x = 0b1101_0101_0001_1010;
  ```



## Floating-Point Literals

```java
double num = 9_423_497_862.0;
double num = 9_423_497.1_0_9;
```



## Character Literals

* All of the visible ASCII characters can be directly entered inside the quotes, such as 'a', 'z', and '@'.

  ```java
  char anyChar = 'a';
  char arroba = '@';
  ```

* For octal notation, use the backslash followed by the three-digit number. For example, '\141' is the letter 'a'.

  ```java
  char anyChar = '\141'; // is letter 'a'
  ```

* For hexadecimal, you enter a backslash-u ( \u), then exactly four hexadecimal digits. For example, ' \u0061' is the ISO-Latin-1 'a'

  ```java
  char anyChar = '\u0061'; // is letter 'a'
  ```

  

  ![image-20210227230232662](D:\Personal\Cursos\JAVA\01-Java Data Types.assets\image-20210227230232662.png)



## String Literals

String literals in Java are specified like they are in most other languages—by enclosing a sequence of characters between a pair of double quotes. Examples:

```java
String anyString = "Hello World";
String anyOtherString = "two\nlines";
String anyAnotherString = "\"This is in quotes\"";
```

