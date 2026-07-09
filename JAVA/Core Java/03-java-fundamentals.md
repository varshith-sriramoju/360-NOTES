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
100  â†’  int type
100L or 100l  â†’  long type
```

### Floating Point Suffix

**Note:**
- In java, by default every floating number is double type
- To represent a floating number as float type we use a letter f or F as a suffix.

```
2.5  â†’  double type
2.5f or 2.5F  â†’   float type
```

**Important Note:** Java is strict or strong type checking language.

```java
int a = 2.5;   //c.e (compile error)
System.out.println(a);
```

### Floating Literals

1. `float a = 4.5;` â†’ c.e (compile error)
2. `float a = 4.5f;` â†’ valid
3. `double a = 4.5;` â†’ valid
4. `double a = 4.5f;` â†’ valid
5. `double a = 10;` â†’ 10.0
6. `double a = 15e3;` â†’ 15000.0
7. `float a = 5e2;` â†’ c.e (in java, exponential result is double type)
8. `double a = 2E3;` â†’ 2000.0

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

