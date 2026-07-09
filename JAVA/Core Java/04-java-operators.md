## Operators
![My project screenshot](../images/operators-part-1.png)
![My project screenshot](../images/operators-part-2.png)

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

**Example:** 2 * 5 + 7 â†’ 10 + 7 â†’ 17

**Associativity of Operators:**
- Associativity is the order in which an operator is evaluated
- Associativity can be left to right or right to left.

**Examples:**
```java
int a = 10;   //right to left

8 / 2 * 5 â†’ 4 * 5 â†’ 20   // left to right
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
   a = a + b;  â†’ a += b;
   a = a * b;  â†’ a *= b;
   a = a - b;  â†’ a -= b;
   a = a / b;  â†’ a /= b;
   a = a % b;  â†’ a %= b;
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

- 0 â†’ binary digit or bit
- 1 â†’ binary digit or bit

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
