## String Concatenation Operator +

- If atleast one value or one operand is string type then plus symbol acts as string concatenation operator.
- String + anything is string or anything + string is string.
- The result of string concatenation is string.

**Examples:**
```
"hello" + 10 = hello10
100 + "welcome" = 100welcome
"data" + "base" = database
```

---

## Java Naming Conventions

Java naming conventions are the rules given by sun microsystems for writing the class name, interface name, method name, variable name, package name, keyword name and constant variable name.

### 1. Class and Interface Names

**Examples:** String, Runnable, StringBuffer, PreparedStatement, InputStreamReader, DatabaseMetaData, ByteArrayOutputStream

### 2. Method Names

**Examples:** read(), equals(), close(), readLine(), startsWith(), equalsIgnoreCase(), compareToIgnoreCase()

### 3. Variable Names

**Examples:** age, city, firstName, phoneNumber, dateOfBirth

### 4. Constant Variable Names

**Examples:** MONTH, YEAR, MAX_PRIORITY, NORM_PRIORITY, DAY_OF_MONTH

### 5. Package Names

**Examples:** java.lang, java.util, java.util.concurrent, javax.servlet.http

### 6. Keywords

**Examples:** if, else, for, do, while, break, continue, return, int, float, char

---

## Keywords (Reserved Words)

- Java has grammar, the grammar of java is represented by some words which are reserved or fixed in java for some purpose
- Every word is having some meaning attach with it which is known to java compiler
- Such words are called as keywords.
- In java, 49 keywords are there.

**Examples:** class, interface, package, import, extends, implements, public, if, private, break, final, static, abstract, void, try, this, super, else, do, for, int, byte, float, boolean

**Note:**
- null, true, false are literals or constant and literals or constants are not keywords.

---

## Identifiers

- Any name in java is called as identifier.

**Examples:** class name, interface name, method name, variable name, package name, array name, object name

### Rules for Identifiers

1. Can contain: a to z, A to Z, 0 to 9, _, $
2. An identifier cannot start with a digit
3. An identifier can start with alphabet or underscore or dollar
4. No length limit
5. Keywords cannot be used as identifiers
6. Identifiers are case sensitive
7. Literals or constants like null, true and false cannot be used as identifiers
8. Predefined class names and interface names can be used as identifiers, it is valid but not recommended to use

**Valid Examples:**
1. value123
2. xyz$234
3. _abc987
4. $123abc
5. System (valid but not recommended)

**Invalid Examples:**
1. 7xyz (starts with digit)
2. abc#123 (contains invalid character)
3. for (keyword)
4. true (literal)

---

## Literals (Constants)
![My project screenshot](./images/constants.png)


**What is a literal?**
- A fixed value which can be assigned to a variable is called as literal or constant.

**Example:**
```java
int a = 10;  // 10 is a literal or constant
```

### Types of Literals

1. **Numeric literals**
   - Integer literals
     - Decimal literals
     - Octal literals
     - Hexadecimal literals
     - Binary literals
   - Floating literals

2. **Non-numeric literals**
   - Character literals
   - String literals

3. **Boolean literals**

### Decimal Literals

- **Base:** 10
- **Range:** 0 to 9
- **Prefix:** no prefix

**Examples:**
```
1. int num = 3;
2. int num = 5;
3. int num = 9;
4. int num = 10;
5. int num = 123;
6. int num = 1000;
7. int num = 12345;
```

### Octal Literals

- **Base:** 8
- **Range:** 0 to 7
- **Prefix:** 0

**Examples:**
```
1. int num = 04;
2. int num = 07;
3. int num = 010;
4. int num = 0543;
5. int num = 07162;
6. int num = 038;    //invalid
```

### Hexadecimal Literals

- **Base:** 16
- **Range:** 0 to 15 (0 to 9 a b c d e f)
- **Prefix:** 0x or 0X

**Examples:**
```
1. int num = 0x10;
2. int num = 0x4f;
3. int num = 0xab3d;
4. int num = 0x7D3CF;
```

### Binary Literals

- **Base:** 2
- **Range:** 0 and 1
- **Prefix:** 0b or 0B

**Examples:**
```
1. int num = 0b10;
2. int num = 0b101;
3. int num = 0b1010;
4. int num = 0B1100;
```

### Integer Type Suffix

**Note:**
- In java, by default every integer number is int type
- To represent an integer number as long type we use l or L letter as a suffix.

```
100  →  int type
100L or 100l  →  long type
```

### Floating Point Suffix

**Note:**
- In java, by default every floating number is double type
- To represent a floating number as float type we use a letter f or F as a suffix.

```
2.5  →  double type
2.5f or 2.5F  →   float type
```

**Important Note:** Java is strict or strong type checking language.

```java
int a = 2.5;   //c.e (compile error)
System.out.println(a);
```

### Floating Literals

1. `float a = 4.5;` → c.e (compile error)
2. `float a = 4.5f;` → valid
3. `double a = 4.5;` → valid
4. `double a = 4.5f;` → valid
5. `double a = 10;` → 10.0
6. `double a = 15e3;` → 15000.0
7. `float a = 5e2;` → c.e (in java, exponential result is double type)
8. `double a = 2E3;` → 2000.0

### Character Literals

- A single alphabet or a single digit or a single special character or a single white space character which is enclosed (written) within single quotes is called as character literal.

**Examples:**
```java
1. char ch = 'a';
2. char ch = '5';
3. char ch = '$';
4. char ch = ' ';
5. char ch = 'ab';  //c.e
6. char ch = '10';  //c.e
7. char ch = '@#';  //c.e
8. char ch = 97;    //a
```

**Unicode Character Literal:**
- In java, to represent unicode value sun microsystems has provided a unicode character literal as '\uxxxx' here each x is any hexadecimal value.

```java
9. char ch = '\u0061';  //a
```

### Escape Sequences

| Escape | Meaning |
|--------|---------|
| \n | new line |
| \t | tabspace |
| \r | carriage return |
| \b | backspace |
| \a | alarm |
| \" | " |
| \\ | \ |
| \' | ' |

**Note:** In java, all the escape sequences can be used as character literals.

```java
10. char ch = '\n';
11. char ch = '\t';
12. char ch = '\b';
13. char ch = '\x';   //c.e
```

### String Literals

- A group of characters which are enclosed (written) within double quotes is called as string literal.

**Examples:**
```java
1. String str = "hyderabad";
2. String str = "welcome";
3. String str = "abc123$#@";
```

### Boolean Literals

- In java, true and false are called as boolean literals.

**Examples:**
```java
1. boolean b = true;
2. boolean b = false;
3. boolean b = 1;       //c.e
4. boolean b = "true";  //c.e
5. boolean b = False;   //c.e
```

**Note:** Boolean literals that is true and false are case sensitive.

---

## Variables

**What is a variable?**

- A variable is a name or an identifier which is given to the memory location internally.
- Variables are used in the program to store data and by using variables we access the data in the program to perform operations.
- A variable is a container which is used to hold some data.
- Variables are place holders in the program.
- Variables are varying in nature which means any time any place in the program we can change or modify the value of the variable.

### Declaration of Variable

- Writing the name of the variable and datatype of the variable is called as declaration of variable.

**Syntax:** `datatype variableName = <initialization>;`

**Note:** Here initialization is optional

**Examples:**
```java
1. int num;
2. float value;
3. char ch;
4. long fact;
5. double area;
```

### Initialization of Variable

- Assigning or storing value to the variable is called as initialization of variable.

**Examples:**
```java
int num = 10;  (or)   int num;
                      num = 10;

float b = 2.5f; (or)  float b;
                      b = 2.5f;

char ch = 'a';  (or)  char ch;
                      ch = 'a';
```

---

## Datatypes

**What are datatypes?**

- Datatypes are keywords and datatypes are used to specify two things:
  1. Type of data
  2. Size of data
- Datatypes are used to specify the type of data a variable should hold.
- Datatypes are used to specify what size of memory should be allocated for the data.

### Types of Datatypes

1. **Primitive datatypes**
   - These datatypes allow a variable to store single value.
   - Examples: byte, short, int, long, char, float, double, boolean

2. **Userdefined datatypes**
   - These datatypes allow a variable to store multiple values which can be homogeneous or heterogeneous.
   - Examples: any class or class name

### Primitive Datatypes Classification

Primitive datatypes are divided into 4 types:

1. **Integer datatypes:** byte, short, int, long
2. **Floating datatypes:** float, double
3. **Character datatype:** char
4. **Boolean datatype:** boolean

### Integer Datatypes

#### 1. byte (smallest size integer datatype in java)

- **Size:** 1 byte
- **Range:** -2^7 to 2^7 - 1 (-128 to 127)

**Examples:**
```java
byte b = 10;
byte b = 127;
byte b = 128;     //c.e
byte b = 2.5;     //c.e
byte b = true;    //c.e
byte b = "hello"; //c.e
```

#### 2. short

- **Size:** 2 bytes
- **Range:** -2^15 to 2^15 - 1 (-32768 to 32767)

**Examples:**
```java
short s = 10;
short s = 128;
short s = 32767;
short s = 32768;  //c.e
```

#### 3. int

- **Size:** 4 bytes
- **Range:** -2^31 to 2^31 - 1

**Examples:**
```java
int i = 10;
int i = 128;
int i = 32768;
int i = 453820;
```

#### 4. long (highest size integer datatype in java)

- **Size:** 8 bytes
- **Range:** -2^63 to 2^63 - 1

**Examples:**
```java
long a = 10;
long a = 100L;
long a = 43829;
long a = 827435;
```

### Floating Datatypes

#### 1. float

- **Size:** 4 bytes
- **Range:** 3.4e-38 to 3.4e38

**Examples:**
```java
float a = 2.5;      //c.e
float a = 2.5f;     // valid
float a = 10;       //10.0
float a = true;     //c.e
float a = "hello";  //c.e
```

#### 2. double

- **Size:** 8 bytes
- **Range:** 1.7e-308 to 1.7e308

**Examples:**
```java
double a = 2.5;
double a = 2.5f;
double a = 10;    //10.0
double a = true;  //c.e
double a = "hello";  //c.e
```

**Notes:**
- Float is 32 bit floating point datatype and double is 64 bit floating point datatype.
- Float uses 6 digits of precision where as double uses 14 digits of precision.

### Character Datatype

#### 1. char

- **Size:** 2 bytes
- **Range:** 0 to 65535

**Examples:**
```java
char ch = 'a';
char ch = 97;        //a
char ch = '$';
char ch = '5';
char ch = 'ab';      //c.e
char ch = '10';      //c.e
char ch = '\u0061';  //a
```

### Boolean Datatype

#### 1. boolean

- **Size:** 1 bit
- **Range:** true and false

**Examples:**
```java
boolean b = true;
boolean b = false;
boolean b = 1;   //c.e
boolean b = 0;   //c.e
boolean b = "true";   //c.e
boolean b = True;   //c.e
```

### void

- Void means empty or no value
- Void is a keyword and it can be used as return type of the method.
- If the return of the method is void such method never returns any value.

---

## Operators
![My project screenshot](./images/operators-part-1.png)
![My project screenshot](./images/operators-part-2.png)

**What is an operator?**

- An operator is a symbol which is used to perform some operations on operands or variables.

**Example:** a + b

### Operator Categories

In java, operators are divided into 3 categories:

1. **Unary operators** - use one operand
   - Examples: ++, --, !, ~, -, +, typecast

2. **Binary operators** - use two operands
   - Examples: +, -, *, /, %, <, >, >=, <=, ==, !=, &, |, ^, <<, >>, >>>

3. **Ternary operators** - use three operands
   - Examples: ?: (conditional operator)

### Precedence and Associativity

**Precedence of Operators:**
- In java, for every operator a number is given which is called as precedence
- Using the precedence we decide which operator should be given first preference or priority.

**Example:** 2 * 5 + 7 → 10 + 7 → 17

**Associativity of Operators:**
- Associativity is the order in which an operator is evaluated
- Associativity can be left to right or right to left.

**Examples:**
```java
int a = 10;   //right to left

8 / 2 * 5 → 4 * 5 → 20   // left to right
```

**Summary:**
- Precedence means priority
- Associativity means order

### new Operator

- new operator is used to create object to the class.
- If we create object to the class then memory will allocated for the members of the class and we can access the members of the class.

**Syntax:** `ClassName objectName = new ClassName();`

**Example:**
```java
class Employee
{
   int id = 1;
   String name = "ravi";
   double salary = 1000.0;

   public void work() {
      System.out.println("working");
   }
}
```

**Notes:**
- If we create a class then memory will not be allocated for the members of the class because a class is a blueprint.
- If memory is not allocated for the members of the class then we cannot access the members of the class.
- We can access the members of the class if memory is allocated for the members of the class.
- Memory will be allocated for the members of the class when we create object to the class
- To create object to the class we use new operator in java.

### Member Operator (.)

- The dot symbol (.) is called as member operator.
- Member operator is used to access or refer to the members of the class or object.

**Uses:**

i. **Access instance variables:**
   - Syntax: `objectName.instanceVariableName;`

ii. **Access instance methods:**
   - Syntax: `objectName.instanceMethodName();`

iii. **Access static variables:**
   - Syntax: `ClassName.staticVariableName;` (recommended) or `objectName.staticVariableName;`

iv. **Access static methods:**
   - Syntax: `ClassName.staticMethodName();` (recommended) or `objectName.staticMethodName();`

v. **Access sub package:**
   - Syntax: `package-name.sub-package-name1.sub-package-name2;`

vi. **Access class inside package:**
   - Syntax: `package-name.sub-package-name.ClassName;`

### Parenthesis ()

- It is the highest precedence operator in java.
- Using parenthesis we can control the precedence of operators.

**Examples:**
```java
int n;

1. n = 7 * (4 + 5);   //63

2. n = (7 - 3) * (4 + 2);   //24
```

### Assignment Operator =

- Assignment operator is used to assign or store a value to the variable.
- The associativity of assignment operator is right to left.

**Three ways to use assignment operator:**

i. **Simple assignment**
   ```java
   int a = 10;
   ```

ii. **Chain assignment**
   ```java
   int a, b, c;
   a = b = c = 10;
   ```

iii. **Compound assignment**
   ```java
   a = a + b;  → a += b;
   a = a * b;  → a *= b;
   a = a - b;  → a -= b;
   a = a / b;  → a /= b;
   a = a % b;  → a %= b;
   ```

**Compound Assignment Operators:** `+=  -=  *=  /=  %=  &=  ^=  |=  <<=  >>=  >>>=`

---

## (Continuing in next section due to length...)

### Increment and Decrement Operators

**Operators:** `++` (increment), `--` (decrement)

**Notes:**
- Both increment and decrement operators are unary operators.
- Increment operator increments the value of the variable by 1 directly in the memory location.
- Decrement operator decrements the value of the variable by 1 directly in the memory location.

**Types:**
- `++x` (pre-increment)
- `x++` (post-increment)
- `--x` (pre-decrement)
- `x--` (post-decrement)

**Examples:**
```java
int x = 3, y = 7;

1. y = ++x;       //x = 4, y = 4

2. y = x++;       //x = 4, y = 3

3. y = --x;       //x = 2, y = 2

4. y = x--;       //x = 2, y = 3

5. int x = 5;
   System.out.println(++x);   //6, x = 6

6. int x = 5;
   System.out.println(x++);   //5, x = 6

7. int x = 5;
   ++x;
   System.out.println(x);     //6

8. int x = 5;
   x++;
   System.out.println(x);     //6

9. float a = 2.5f;
   ++a;
   System.out.println(a);     //3.5

10. char ch = 'a';
    ch++;
    System.out.println(ch);   //b

11. boolean b = false;
    ++b;                      //c.e: bad operand type

12. String str = "hello";
    ++str;                    //c.e: bad operand type

13. int x = 5;
    x = ++x + x + x++ + x--;
    System.out.println(x);   //25
## Binary Language

**Binary** means two numbers that is 0 and 1

- 0 → binary digit or bit
- 1 → binary digit or bit

**What is binary language?**
- The language which uses only 0's and 1's is called as binary language or machine language.
- Only machine understands binary language.

**Topics:**
1. Decimal to binary conversion
2. Binary to decimal conversion
3. BCD code
4. LSB and MSB
5. 1's complement
6. 2's complement
7. Binary addition
8. Negative decimal to binary conversion
9. Negative binary to decimal conversion

---
![My project screenshot](./images/conversions.png)
![My project screenshot](./images/decl-&-exe-sections.PNG)


## Bitwise Operators

- These operators work on binary language.

**Operators:**
- `&` - bitwise and
- `|` - bitwise or
- `^` - bitwise xor
- `~` - bitwise complement
- `<<` - bitwise left shift
- `>>` - bitwise right shift
- `>>>` - bitwise zero fill right shift

**Notes:**
- Bitwise complement operator is unary operator and remaining all are binary operators.
- `&`, `|`, `^` can be applied only on integer type and boolean type.

### Truth Table

| a | b | a & b | a \| b | a ^ b |
|---|---|-------|--------|-------|
| 1 | 0 |   0   |   1    |   1   |
| 0 | 1 |   0   |   1    |   1   |
| 1 | 1 |   1   |   1    |   0   |
| 0 | 0 |   0   |   0    |   0   |

### Bitwise AND, OR, XOR Examples

```java
boolean b1 = true, b2 = false;

1. System.out.println(b1 & b2);   //false

2. System.out.println(b1 | b2);   //true

3. System.out.println(b1 ^ b2);   //true

int a = 10, b = 6;

4. System.out.println(a & b);   //2
    1010
    0110 &
   ------
    0010 = 2

5. System.out.println(a | b);   //14
    1010
    0110 |
   ------
    1110 = 14

6. System.out.println(a ^ b);   //12
    1010
    0110 ^
   ------
    1100 = 12
```

### Bitwise Complement ~

- It is a unary operator and it is applied on integer type only.
- Bitwise complement changes 0's to 1's and 1's to 0's internally.

**Example:**
```java
int a = 5;
System.out.println(~a);   //-6

0000 0101
apply ~a
1111 1010 = -6
```

**Formula:** -(n+1)

### Bitwise Left Shift Operator <<

- It is a binary operator and it is applied only on integer type.
- It shifts the bits from left side.

**Example:**
```java
int a = 10;
System.out.println(a << 1);   //20

0000 1010
 a << 1
_000 1010  (all bits shift left)
0001 0100 = 20
```

### Bitwise Right Shift Operator >>

- It is a binary operator and it is applied only on integer type.
- It shifts the bits from right side.

**Example:**
```java
int a = 10;
System.out.println(a >> 1);   //5

0000 1010
 a >> 1
0000 101_  (all bits shift right)
_000 0101
0000 0101 = 5
```

### Bitwise Zero Fill Right Shift Operator >>>

- Bitwise zero fill right shift operator is same as bitwise right shift operator except one difference
- In case of bitwise right shift operator if the number is positive then msb is filled with 0 so result will positive and if the number is negative then msb is filled with 1 so result will be negative
- In case of bitwise zero fill right shift operator if the number is positive or negative always msb is filled with 0 only so always the result will be positive.

---

## Short Circuit Operators

- `&&` and `||` are called as short circuit operators in java.

**Operators:**
- `&&` - logical and
- `||` - logical or

### Differences between Bitwise and Short Circuit Operators

| &, \| | &&, \|\| |
|--------|----------|
| Can be applied on boolean and integer types | Can be applied only on boolean type |
| Second expression evaluation is always mandatory in case of bitwise operators | Second expression evaluation is not always mandatory sometimes it is optional |
| | i. in case of && if first expression is false then only second expression evaluation is optional and if first expression is true then second expression evaluation is mandatory. |
| | ii. in case of \|\| if first expression is true then only second expression evaluation is optional and if first expression is false then second expression evaluation is mandatory. |

**Note:** It is always recommended to use short circuit operators over bitwise operators because short circuit operators improve performance.

---

## Boolean Complement Operator !

- It is a unary operator and it can be applied only on boolean type.
- It will change true to false and false to true.

**Examples:**
```java
1. boolean b = true;
   System.out.println(!b);  //false

2. boolean b = false;
   System.out.println(!b);  //true

3. System.out.println(!(2<5));   //false

4. System.out.println(!(5>3 && 7<4));   //true
```

---

```