[TOC]



```java
/***
 * ┌───┐   ┌───┬───┬───┬───┐ ┌───┬───┬───┬───┐ ┌───┬───┬───┬───┐ ┌───┬───┬───┐
 * │Esc│   │ F1│ F2│ F3│ F4│ │ F5│ F6│ F7│ F8│ │ F9│F10│F11│F12│ │P/S│S L│P/B│  ┌┐    ┌┐    ┌┐
 * └───┘   └───┴───┴───┴───┘ └───┴───┴───┴───┘ └───┴───┴───┴───┘ └───┴───┴───┘  └┘    └┘    └┘
 * ┌───┬───┬───┬───┬───┬───┬───┬───┬───┬───┬───┬───┬───┬───────┐ ┌───┬───┬───┐ ┌───┬───┬───┬───┐
 * │~ `│! 1│@ 2│# 3│$ 4│% 5│^ 6│& 7│* 8│( 9│) 0│_ -│+ =│ BacSp │ │Ins│Hom│PUp│ │N L│ / │ * │ - │
 * ├───┴─┬─┴─┬─┴─┬─┴─┬─┴─┬─┴─┬─┴─┬─┴─┬─┴─┬─┴─┬─┴─┬─┴─┬─┴─┬─────┤ ├───┼───┼───┤ ├───┼───┼───┼───┤
 * │ Tab │ Q │ W │ E │ R │ T │ Y │ U │ I │ O │ P │{ [│} ]│ | \ │ │Del│End│PDn│ │ 7 │ 8 │ 9 │   │
 * ├─────┴┬──┴┬──┴┬──┴┬──┴┬──┴┬──┴┬──┴┬──┴┬──┴┬──┴┬──┴┬──┴─────┤ └───┴───┴───┘ ├───┼───┼───┤ + │
 * │ Caps │ A │ S │ D │ F │ G │ H │ J │ K │ L │: ;│" '│ Enter  │               │ 4 │ 5 │ 6 │   │
 * ├──────┴─┬─┴─┬─┴─┬─┴─┬─┴─┬─┴─┬─┴─┬─┴─┬─┴─┬─┴─┬─┴─┬─┴────────┤     ┌───┐     ├───┼───┼───┼───┤
 * │ Shift  │ Z │ X │ C │ V │ B │ N │ M │< ,│> .│? /│  Shift   │     │ ↑ │     │ 1 │ 2 │ 3 │   │
 * ├─────┬──┴─┬─┴──┬┴───┴───┴───┴───┴───┴──┬┴───┼───┴┬────┬────┤ ┌───┼───┼───┐ ├───┴───┼───┤ E││
 * │ Ctrl│    │Alt │         Space         │ Alt│    │    │Ctrl│ │ ← │ ↓ │ → │ │   0   │ . │←─┘│
 * └─────┴────┴────┴───────────────────────┴────┴────┴────┴────┘ └───┴───┴───┘ └───────┴───┴───┘
 */
————————————————
https://blog.csdn.net/ydk888888/article/details/81563608
```



# JavaSE basic

```java
public class Hello{							// class
    public static void main(String[] args){	  // method
        System.out.print("Hello world!")
    }
}
```

```shell
# compile
javac Hello.java
# run
java Hello
```

- Java is sensible to uppercase and lowercase
- File name should be identical to class name
- Java is a mix of Compiled Language and Interpreted Language

## IDEA 

```shell
psvm # public static void main(String[] args)
sout # System.out.println();
Ctrl + D # Copy the corrent line and paste to the next line
```

---

# Java grammar

## Java comment

```java
// Single line comment

/*
Block comment
*/

/**
 * JavaDoc
 * @Description
 * @Author
 */
```

## Identifiers

```java
```

- All identifiers should begin with a letter (A to Z or a to z), currency character ($) or an underscore (_).
- A key word (class,catch,try,do...) cannot be used as an identifier.
- Identifiers are case sensitive.
- Examples of legal identifiers: age, $salary, _value, __1_value.
- Examples of illegal identifiers: 123abc, -salary.

## Data types

> There are two data types available in Java −
>
> - Primitive Data Types (lower case)
>   - byte, short, int, long (8 bytes) 
>
>     ```java
>     int num1 = 10;
>     int num2 = 0b10; // binary '0b'
>     int num3 = 010;	 // octonary '0'
>     int num4 = 0x10; // hexadecimal '0x'
>     ```
>
>     > Add `L` after `long`
>     >
>     > ```java
>     > long num = 30L;
>     > ```
>
>   - float, double (8 bytes)
>
>     > Add `F` after `float`
>     >
>     > ```java
>     > float num = 50.1F;
>     > ```
>     >
>     > **Never compare float or double**
>     >
>     > > Use BigDecimal (ex: in banking systems)
>     >
>     > ``` java
>     > float f = 0.1f;
>     > double d = 1.0/10;
>     > // f==d is False
>     > 
>     > float d1 = 123123123123123f;
>     > float d2 = d1 + 1;
>     > // d1==d2 is True
>     > ```
>
>   - char (2 bytes)
>
>   - boolean
>
>     ```java
>     boolean flag = true;
>     if (flag==true){}
>     // is the same as 
>     if (flag){} //less is more
>     ```
>   
> - Reference/Object Data Types
>
>   ```java
>   String s = 'Hello';
>   ```
>
>   

### forced data type conversion

```java
char c1 = 'a';
int i1 = (int)c1; // Will output the encoding for 'a' => 97

// Overflow problem
int i2 = 128;
byte b = (byte)i; // b => -128

int i3 = (int)23.7; // i3 => 23 without rounding up
```

> Write Unicode
>
> ```java
> char c2 = '\u0061'; // is the same as c2 = 'a'
> ```

### literals

> A literal is a source code representation of a fixed value. They are represented directly in the code without any computation.

special escape sequences

| Notation |        Character represented         |
| :------: | :----------------------------------: |
|    \n    |            Newline (0x0a)            |
|    \r    |        Carriage return (0x0d)        |
|    \f    |           Formfeed (0x0c)            |
|    \b    |           Backspace (0x08)           |
|    \s    |             Space (0x20)             |
|    \t    |                 tab                  |
|    \"    |             Double quote             |
|    \'    |             Single quote             |
|    \\    |              backslash               |
|   \ddd   |        Octal character (ddd)         |
|  \uxxxx  | Hexadecimal UNICODE character (xxxx) |

### Handling overflow with big numbers

```java
// New in JDK7 seperate number with '_'
int money = 10_000_000;
int years = 20;
int total = money * years; // -1474836480 Overflow

// lift data types by automatic conversion
int total2 = money * ((long)years);
```

## Declaration variables

- Class variables

  > A static class variable can be directly used within methods without `new class`

- Instance variables

- Local variables

> Static initialization block (https://docs.oracle.com/javase/tutorial/java/javaOO/initial.html)
>
> ```java
> static{
>     // whatever code is needed for initialization goes here
> }
> ```

> Default value for a boolean is `false`

## Operators

### Arithmetic operators

> Data types change
>
> ```java
> long a = 123123123123L;
> int b = 123;
> short c = 10;
> byte d = 8;
> 
> /*
> a+b+c+d => Long (same case for d)
> b+c+d => Int
> c+d => Int Data type will be lifted 
> */
> 
> //
> a+=b;// a = a+b
> 
> // Adding a String ******
> System.out.println(""+a+b);// 1020
> System.out.println(a+b+"");// 30
> ```

### Math class

> ex :
>
> ```java
> double pow = Math.pow(3.2); // pow => 9
> ```

### Logical operators

> Short-circuit
>
> > The `&&` and `||` operators "short-circuit", meaning they don't evaluate the right-hand side if it isn't necessary.
> >
> > The `&` and `|` operators, when used as logical operators, always evaluate both sides.
> >
> > There is only one case of short-circuiting for each operator, and they are:
> >
> > - `false && ...` - it is not necessary to know what the right-hand side is because the result can only be `false` regardless of the value there
> > - `true || ...` - it is not necessary to know what the right-hand side is because the result can only be `true` regardless of the value there
> >
> > ```java
> > int c = 5;
> > boolean d = (c<4)&&(c++<4);
> > //d = false, c=5 , c++ is not being excuted because of short-circuit
> > ```

### Bitwise operators

> a = 0011 1100
>
> b = 0000 1101
>
> \-----------------
>
> a&b = 0000 1100
>
> a|b = 0011 1101
>
> a^b = 0011 0001
>
> ~a = 1100 0010

> the shortest way to calculate 2 * 8 :
>
> ```java
> int out = 2<<3;
> // << can be seen as *2
> // >> can be seen as /2
> ```

### Conditional operators

> Conditional operator is also known as the **ternary operator**. This operator consists of three operands and is used to evaluate Boolean expressions. The goal of the operator is to decide, which value should be assigned to the variable.

```java
// x ? y :z
// if x==True, result is y, otherwise z
int score = 80;
String type = score < 60 ? "failed" : "passed";
// type => passed
```

## JavaDoc

> Generate API documents with JavaDoc

```java
/**
 * @author XXX
 * @version 1.0
 * @since
 * @param
 * @return
 * @throws
 */
```

> Change encoding for JavaDoc
>
> ```shell
> ~/: javadoc -encoding UTF-8 -charset UTF-8 XXX.java
> ```

## Process control

### Scanner

> java.util.Scanner

```java
//basic usage of Scanner

Scanner scanner = new Scanner(System.in);

//Using hasNext() to verify if imput is present
if (scanner.hasNext()){
    String str = scanner.next(); //next() will stop at a blank character
    String str = scanner.nextLine(); //nextLine() (must change if condition to hasNextLine())
}

//IO Stream must be closed after
Scanner.close();
```

> Use Stirng.equals() to judge if two Strings are the same

```java
if (scanner.hasNextInt()){
    i = scanner.nextInt();
}
```

- hasNextInt()
- hasNextFloat()
- ...

### switch case

> Without break, all the lines in the following cases will be executed until the next break (Case Penetration)

- NOTE: See the source code in .class file (reverse compile) when switch case is dealing with String. (using hash)

### for

> 100.for => for (int i - 0; i < 100; i++)

> for (int i=0,j=10; i<11; i++,j--)

### Enhanced for loop

> for tuples and arrays

```java
int[] numbers = {10,20,30};

for (int x:numbers){
    //expressions
}
```

```java
// Labe

int count = 0;

outer:for (int i=101;i<150;i++){
    for (int j=2; j<i/2;j++){
        if (i % j == 0){
            continue outer;
        }
    }
}
```



## Method



### Varargs

> Varargs must be the last parametre, only one varargs is allowed in each methos

```java
public void test(int... i){
    System.out.print(i[0]);
}
```



### Recursion

> Recursin funtions must begin with a exitable header

```java
public static int f(int n){
    if (n==1){
        return 1;
    }else{
        return n*f(n-1)
    }
}
```



## Tuple

> Two ways to declair a tuple
>
> - `dataType[] arrayRefVar;` <-- use this
>
> - `dataType arrayRefVar[];` <-- C/C++ style

> Set a length to Tuple
>
> - `arrayRefVar = new dataTyple[10];`
>
> Get the length:
>
> - `arrayRefVar.length`

> A faster way to setup tuple
>
> - `dataTyple[] arrayRefVar = new dataType[arraySize]`
> - `int[] a = {1,2,3,4,5}`
> - `Class[] class = {new Class(), new Class()}`

> Using `arrayRefVar.for` to generate a for-each loop
>
> Using `arrayRefVar.length.fori` to generate a for loop

### Array Class





# Object oriented



## OO Basic

> Methods + Varibles = Object
>
> Organize the code in the way of classes, and encapsulate the data in the way of objects.
>
> - Encapsulate
> - inherit
> - polymorphize

```java
public class Student{
    
    String name;
    int age;
    
    public void study(){
        return this.name+" study"
    }
}
```

> Constructor must have the same name as the class and must not have a return type not even void
>
> - the new XXX() phrase is actually calling the constructor
> - Alt + Insert (in IDEA) to create a constructor

```java
//in .java file write
public class Person{
}

//in .class file it will be
public class Person{
    public Person(){
        // this is a constructor
    }
}
```



### Encapsulation

> In encapsulation, the variables of a class will be hidden from other classes, and can be accessed only through the methods of their current class. Therefore, it is also known as **data hiding**.
>
> To achieve encapsulation in Java −
>
> - Declare the variables of a class as private.
> - Provide public setter and getter methods to modify and view the variables values.

### Inheritance

> The class which inherits the properties of other is known as subclass (derived class, child class) and the class whose properties are inherited is known as superclass (base class, parent class).
>
> - in Java all Class will inherit Object Class by default

```java
class Super{
    
}

class Sub extends Super{
    
}
```

> child class can't inherit private property

> Ctrl + H to open Hierarchy
