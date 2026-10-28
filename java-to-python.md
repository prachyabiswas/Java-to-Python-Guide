# Java → Python: A Code Equivalence Guide

A side-by-side reference for developers who already know Java and are learning Python — every concept shown as working Java code next to its Python equivalent, with actual output.

## Table of Contents

1. [Variables and Data Types](#1-variables-and-data-types)
2. [Printing Variables](#2-printing-variables)
3. [Checking Types](#3-checking-types)
4. [Basic Arithmetic Operations](#4-basic-arithmetic-operations)
5. [Concatenation](#5-concatenation)
6. [Strings](#6-strings)
7. [User Input](#7-user-input)
8. [Conditional Statements](#8-conditional-statements)
9. [Python Built-in Data Types](#9-python-built-in-data-types)
10. [Loops](#10-loops)
11. [Functions / Methods](#11-functions--methods)
12. [NumPy (Java Arrays → Python Arrays)](#12-numpy-java-arrays--python-arrays)

---

## 1. Variables and Data Types

**Java** is statically typed — you must declare a data type when declaring a variable.

```java
public class DeclaringVariable{
    public static void main(String[] args){
        int a = 123;
        float b = 1.23f;
        double c = 1.23;
        String d = "Hello World!";
        boolean e = true;
        boolean f = false;
    }
}
```

**Python** is dynamically typed — no need to write a data type when declaring a variable.

```python
a = 123          #integer
b = 1.23         #float
c = 1 + 2j       #complex
d = "Hello World" #string
e = True         #boolean true
f = False        #boolean false
```

---

## 2. Printing Variables

**Java**

```java
public class PrintingVariable{
    public static void main(String[] args){
        System.out.println(a);
        System.out.println(b);
        System.out.println(c);
        System.out.println(d);
        System.out.println(e);
        System.out.println(f);
    }
}
```
```
# Output
123
1.23
1.23
Hello World
true
false
```

**Python**

```python
print(a)
print(b)
print(c)      #Bracket for complex number
print(d)
print(e)
print(f)
```
```
# Output
123
1.23
(1+2j)
Hello World
True
False
```

---

## 3. Checking Types

**Java** — you cannot check primitive types at runtime because Java is statically typed. For non-primitive data types, use `instanceof`.

```java
public class CheckType{
    public static void main(String[] args){
        Object a = 123;
        System.out.println(a instanceof Integer);
    }
}
```
```
# Output
true
```

**Python**

```python
c = 1 + 2j
type(c)
```
```
# Output
complex
```

---

## 4. Basic Arithmetic Operations

For floor division, both numbers should be of `int` datatype (Java).

**Java**

```java
public class PrintingVariable{
    public static void main(String[] args){
        System.out.println(5 + 2);
        System.out.println(5 - 2);
        System.out.println(5 * 2);
        System.out.println(5.0 / 2);
        System.out.println(5 / 2);
        System.out.println(5 % 2);
        System.out.println(Math.pow(2,4));
    }
}
```
```
# Output
7
3
10
2.5
2
1
16
```

**Python**

```python
print (5 + 2)
print (5 - 2)
print (5 * 2)
print (5 / 2)
print (5 // 2)
print (5 % 2)
print (2 ** 4)
```
```
# Output
7
3
10
2.5
2
1
16
```

---

## 5. Concatenation

**Java**

```java
public class Contatination{
    public static void main(String[] args){
        int a = 123;
        int b = 456;
        System.out.println("The current value of a is "+ a);
        System.out.println("The current value of a is " + a + " and b is" + b);
    }
}
```
```
# Output
The current value of a is 123
The current value of a is 123 and b is 456
```

**Python**

```python
a = 123
b = 456

# Concatenated using comma
print ("The current value of a is", a)
print ("The current value of a is", a, "and b is", b)

# Concatenated using +
print ("The current value of a is " + a)   # Note: needs str(a) in real Python
print ("The current value of a is " + a + " and b is " + b)
```
```
# Output
The current value of a is 123
The current value of a is 123 and b is 456
The current value of a is 123
The current value of a is 123 and b is 456
```

> **Gotcha:** unlike Java, Python's `+` operator cannot silently mix `str` and `int` — you need `str(a)` to concatenate a number with `+`. The comma form in `print()` avoids this entirely.

---

## 6. Strings

### String Concatenation

**Java**
```java
public class StrContatination{
    public static void main(String[] args){
        String a = "Welcome to ";
        String b = "CSE330 Lab.";
        System.out.println(a + b);
    }
}
```
```
# Output
Welcome to CSE330 Lab.
```

**Python**
```python
a = "Welcome to "
b = "CSE330 Lab."
z = a + b
print(z)
```
```
# Output
Welcome to CSE330 Lab.
```

### String Indexing

Space counts as a character in both languages.

**Java**
```java
// Accessing String with character position number.
public class StrIndexing{
    public static void main(String[] args){
        String a = "Welcome to ";
        String b = "CSE330 Lab.";
        System.out.println(a.charAt(0));
        System.out.println(b.charAt(5));
    }
}
```
```
# Output
W
0
```

**Python**
```python
a = "Welcome to "
b = "CSE330 Lab."
print (a[0])
print (b[5])
```
```
# Output
W
0
```

### Length of the String

**Java**
```java
public class StrLength{
    public static void main(String[] args) {
        String a = "Welcome to ";
        String b = "CSE330 Lab.";
        String z = a + b;
        System.out.println(z.length());
    }
}
```
```
#Output
22
```

**Python**
```python
a = "Welcome to "
b = "CSE330 Lab."
z = a + b
print(len(z))
```
```
#Output
22
```

### Accessing Last Character

**Java**
```java
public class LastChar{
    public static void main(String[] args) {
        String a = "Welcome to ";
        String b = "CSE330 Lab.";
        System.out.println(b.charAt(b.length() - 1));
    }
}
```
```
#Output
.
```

**Python**
```python
a = "Welcome to "
b = "CSE330 Lab."
print(b[len(b)-1])
print(b[-1])      # Pythonic shortcut: negative indexing
```
```
#Output
.
.
```

### String Slicing

**Java** has no built-in slicing — use `substring()` or loop manually.

```java
public class StrSlice {
    public static void main(String[] args) {
        String s = "Welcome to CSE330 Lab.";

        // s[0:6] → substring starting from 0 to 6 (excluding)
        System.out.println(s.substring(0, 6));

        // s[6:] → substring starting from 6 to End
        System.out.println(s.substring(6));

        // s[-4:] → last 4 characters
        System.out.println(s.substring(s.length() - 4));
    }
}
```
```
#Output
Welcom
e to CSE330 Lab.
Lab.
```

**Python** has native slicing syntax `s[start:stop]`:

```python
s = "Welcome to CSE330 Lab."

print(s[:6])    # from 0 to 6 (excluding)
print(s[6:])    # from 6 to end
print(s[-4:])   # last 4 characters
```
```
#Output
Welcom
e to CSE330 Lab.
Lab.
```

---

## 7. User Input

**Java**
```java
import java.util.Scanner;

public class UserInput {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter username: ");
        String username = sc.nextLine();
        System.out.println("Username is: " + username);
        System.out.println(username + username + username);

        System.out.print("Enter number: ");
        int num = sc.nextInt();
        System.out.println(num * 2);
    }
}
```
```
#Output
Enter username:coder
Username is: coder
codercodercoder
Enter number:4
8
```

**Python**
```python
username = input("Enter username:")
print("Username is: " + username)
print(username*3)                     # Pythonic shortcut for repetition

num = int(input("Enter number:"))     # input() always returns a string — must cast
print (num * 2)
```
```
#Output
Enter username:coder
Username is: coder
codercodercoder
Enter number:4
8
```

> **Gotcha:** Python's `input()` always returns a `str`. You must explicitly convert with `int()` / `float()` before doing arithmetic — Java's `Scanner.nextInt()` does this for you.

---

## 8. Conditional Statements

### if / else

**Java**
```java
public class CondStat {
    public static void main(String[] args) {
        int x = 5;
        int y = 6;
        if (x > y) {
            System.out.println("Maximum is x");
        } else {
            System.out.println("Maximum is y");
        }
    }
}
```
```
#Output
Maximum is y
```

**Python** — no braces, no parentheses required; indentation defines the block.
```python
x = 5
y = 6
if x > y:
    print("Maximum is x")
else:
    print("Maximum is y")
```
```
#Output
Maximum is y
```

### elif

**Java**
```java
int x = 5, y = 5;
if (x > y) {
    System.out.println("Maximum is x");
} else if (x == y) {
    System.out.println("x and y are equal");
} else {
    System.out.println("Maximum is y");
}
```
```
#Output
x and y are equal
```

**Python**
```python
x = 5
y = 5
if x > y:
    print("Maximum is x")
elif x == y:
    print("x and y are equal")
else:
    print("Maximum is y")
```
```
#Output
x and y are equal
```

### and / or

Both conditions must be `True` for `and`; either one being `True` is enough for `or`.

**Java**
```java
int a = 200, b = 10, c = 500;
if (a > b && c > a) {
    System.out.println("Both conditions are True");
} else {
    System.out.println("Negative!!");
}
// Output: Both conditions are True

if (a > b || a > c) {
    System.out.println("At least one of the conditions is True");
} else {
    System.out.println("Negative!!");
}
// Output: At least one of the conditions is True
```

**Python**
```python
a = 200
b = 10
c = 500
if a > b and c > a:
    print("Both conditions are True")
else:
    print("Negative!!")
# Output: Both conditions are True

if a > b or a > c:
    print("At least one of the conditions is True")
else:
    print("Negative!!")
# Output: At least one of the conditions is True
```

### Nested if

**Java**
```java
int x = 50;
if (x > 10) {
    System.out.println("Above ten!");
    if (x > 20) {
        System.out.println("and also above 20!");
    } else {
        System.out.println("but not above 20!");
    }
} else {
    System.out.println("Not even above ten!");
}
```

**Python**
```python
x = 50
if x > 10:
    print("Above ten!")
    if x > 20:
        print("and also above 20!")
    else:
        print("but not above 20!")
else:
    print("Not even above ten!")
```
```
#Output (both)
Above ten!
and also above 20!
```

### pass

**Java** doesn't need a `pass` keyword — an empty block is simply an empty `{}` or no `else` at all.
```java
int a = 10, b = 20;
if (b > a) {
    // do nothing (equivalent to pass)
} else {
    System.out.println("hello");
}
```

**Python** requires a placeholder statement if a block is intentionally left empty — this is `pass`.
```python
a = 10
b = 20
if b > a:
    pass
#else:
#   print("hello")
```

---

## 9. Python Built-in Data Types

Java doesn't have direct equivalents for Python's `list`, `tuple`, `set`, and `dict` — the closest is arrays and (for maps) `HashMap`, but Python's built-ins are more flexible and built into the language core.

### List

- Similar to a Java/C array, but not the same.
- Can store any type of data in a single list.
- Doesn't have a fixed size like an array.
- Requires more memory to track each element's data type.

```python
#Initializing
list = [1, 2, 3, 4, 5]
print(list)
# Output: [1, 2, 3, 4, 5]

mixed_list = [1, 2.5, "hello", [1, 2, 3]]
print(mixed_list[3])
# Output: [1, 2, 3]

#List Methods
print(len(list))          # 5
print(4 in list)          # True   (search)

list[2] = "New"           # update value
print(list)                # [1, 2, 'New', 4, 5]

list.append("World")      # add new element
print(list)                # [1, 2, 'New', 4, 5, 'World']

list.remove("New")        # remove by value
print(list)                # [1, 2, 4, 5, 'World']

list.pop(1)                # remove by index
print(list)                # [1, 4, 5, 'World']

list2 = [16, 55]
joined_list = list + list2
print(joined_list)         # [1, 4, 5, 'World', 16, 55]
```

#### List Slicing

```python
my_list = ['a', 'b', 'c', 'e', 'f', 'd']

print(my_list[3])        # e
print(my_list[1:3])      # ['b', 'c']
print(my_list[:3])       # ['a', 'b', 'c']
print(my_list[3:])       # ['e', 'f', 'd']
print(my_list[-3:])      # ['e', 'f', 'd']
print(my_list[0:4:2])    # ['a', 'c']   (step +2 every time)
print(my_list[:])        # all elements
print(my_list[::2])      # ['a', 'c', 'f']
print(my_list[::-1])     # ['d', 'f', 'e', 'c', 'b', 'a']  (reversed)

# Print last 4 elements in reverse
my_list2 = ['a', 'b', 'c', 'd', 'e', 'f']
print(my_list2[-1:-5:-1])  # ['f', 'e', 'd', 'c']

# Print 2nd to 5th element in reverse order
print(my_list2[4:0:-1])    # ['e', 'd', 'c', 'b']
```

### Tuple

- **Immutable** — items cannot be modified once set.
- Collection of elements of multiple data types.
- Commonly used to store a fixed sequence of related data (and as dictionary keys, database rows, etc.).

```python
tuple = (1, 2, 3, 4, 5)
tuple[0]            # 1

tuple[1] = "hello"   # TypeError: 'tuple' object does not support item assignment
```

### Set

- Unordered — no indexing.
- No duplicates allowed.
- Items themselves are immutable, though the set can grow/shrink.

```python
set = {"apple", "banana", "cherry", "banana"}
print(set)
# Output: {'apple', 'cherry', 'banana'}   (duplicate "banana" dropped)

set.add("orange")
print(set)
# {'apple', 'cherry', 'orange', 'banana'}

set.remove("banana")
print(set)
# {'apple', 'cherry', 'orange'}
```

### Dictionary

- Values are stored as key : value pairs.
- Unordered, mutable.
- Keys must be unique and of an immutable type (strings, numbers, tuples).

```python
drivers = {
    16: "Charles",
    1: "Max",
    55: "Carlos",
    "Extra": "Liam"
}
print(drivers)
# {16: 'Charles', 1: 'Max', 55: 'Carlos', 'Extra': 'Liam'}

print(drivers["Extra"])        # accessing: Liam

drivers["Extra"] = "Ollie"     # updating
print(drivers)

drivers.update({81: "Oscar"})  # adding a new pair
print(drivers)

drivers.pop("Extra")           # removing a key
print(drivers)
```

---

## 10. Loops

### While Loop

**Java**
```java
public class WhileLoop{
    public static void main(String[] args) {
        int i = 0;
        while (i < 10) {
            System.out.println(i);
            i = i + 1;
        }
    }
}
```

**Python**
```python
i = 0
while i < 10:
    print(i)
    i = i + 1
```
```
# Output (both): 0 1 2 3 4 5 6 7 8 9
```

### For Loop

**Java**
```java
public class ForLoop{
    public static void main(String[] args) {
        for (int i = 0; i < 10; i += 2) {
            System.out.println(i);
        }
    }
}
```

**Python**
```python
for i in range(0, 10, 2):
    print(i)
```
```
# Output (both): 0 2 4 6 8
```

### Iterating Over a List

**Java**
```java
String[] list = {"a","b","c","d","e"};
for(int i = 0; i < list.length; i++){
    System.out.println(list[i]);
}
for(int i = 0; i < list.length; i++){
    System.out.println("Index = "+i+", Value = "+list[i]);
}
```

**Python**
```python
list = ['a', 'b', 'c', 'd', 'e']

for i in list:
    print(i)

for i in range(len(list)):
    print("Index =", i, "Value =", list[i])
```

### Break Statement

**Java**
```java
String[] fruits = {"apple", "banana", "cherry"};
for(int i = 0; i < fruits.length; i++){
    System.out.println(fruits[i]);
    if(fruits[i].equals("banana")){
        break;
    }
}
```

**Python**
```python
fruits = ["apple", "banana", "cherry"]
for x in fruits:
    print(x)
    if x == "banana":
        break
```
```
# Output (both): apple  banana
```

### Continue Statement

**Java**
```java
String[] fruits = {"apple", "banana", "cherry"};
for(int i = 0; i < fruits.length; i++){
    if(fruits[i].equals("banana")){
        continue;
    }
    System.out.println(fruits[i]);
}
```

**Python**
```python
fruits = ["apple", "banana", "cherry"]
for i in fruits:
    if i == "banana":
        continue
    print(i)
```
```
# Output (both): apple  cherry
```

### Nested Loop

**Java**
```java
int[] num_arr = {1,2,3};
String[] alphabet_arr = {"a","b","c"};
for(int i = 0; i < num_arr.length; i++){
    System.out.println(num_arr[i]);
    for(int j = 0; j < alphabet_arr.length; j++){
        System.out.println(alphabet_arr[j]);
    }
}
```

**Python**
```python
num_list = [1, 2, 3]
alphabet_list = ['a', 'b', 'c']

for number in num_list:
    print(number)
    for letter in alphabet_list:
        print(letter)
```
```
# Output (both): 1 a b c 2 a b c 3 a b c
```

---

## 11. Functions / Methods

Java cannot give a parameter a default value, but supports method overloading (same name, different parameter lists). Python supports default parameter values and keyword arguments directly.

**Java**
```java
public class JavaMethod{
    public static void hello_method(){
        System.out.println("Hello");
    }
    public static void name_method(String fname, String lname){
        System.out.println(fname+" "+lname);
    }
    public static int sum_numbers(int num1, int num2){
        return num1 + num2;
    }
    public static int increment(int number) {
        return increment(number, 1);  // overload calling overload — default value
    }
    public static int increment(int number, int by) {
        return number + 2 * by;
    }

    public static void main(String[] args){
        hello_method();
        name_method("Cristiano", "Ronaldo");
        int x = sum_numbers(2, 3);
        System.out.println(x);
        System.out.println(increment(2,5));
        System.out.println(increment(2));
    }
}
```
```
# Output
Hello
Cristiano Ronaldo
5
4
12
```

**Python**
```python
def hello_function():
    print("Hello")

def name_function(fname, lname):
    print(fname, " ", lname)

def sum_numbers(number1, number2):
    result = number1 + number2
    return result

def increment(number, by=1):      # default value, no overloading needed
    return number + 2*by

hello_function()
name_function("Cristiano", "Ronaldo")
x = sum_numbers(2, 3)
print(x)
print(increment(2))
print(increment(2, 5))
# Keyword arguments
print(increment(by=1, number=2))
```
```
# Output
Hello
Cristiano   Ronaldo
5
4
12
5
```

---

## 12. NumPy (Java Arrays → Python Arrays)

NumPy is a Python library for working with arrays (short for "Numerical Python"). It provides an array object up to 50x faster than a plain Python list, with a lot of supporting functions — the closest Python equivalent to Java's native arrays, but far more powerful.

> `import numpy as np` at the top of every example below.

### Creating an Array

**Java**
```java
import java.util.Arrays;
public class JavaArr{
    public static void main(String[] args){
        String[] arr = {"1", "2", "3", "2.45", "hello"};
        System.out.println(Arrays.toString(arr));
        System.out.println("Arr Length: " + arr.length);
    }
}
```
```
# Output
[1, 2, 3, 2.45, hello]
Arr Length: 5
```

**Python** — Java arrays can only hold one data type, so mixed values get silently converted to `String`. NumPy does something similar: mixing types upcasts everything to a common type (here, all to strings), and you lose the ability to do numeric calculations on it.
```python
import numpy as np

arr = np.array([1, 2, 3, 2.45, "hello"])
print(arr)
print(type(arr))
print("Arr Length:", len(arr))
print(arr.shape)
```
```
# Output
['1' '2' '3' '2.45' 'hello']
<class 'numpy.ndarray'>
5
(5,)
```

### Append

**Java** — arrays are fixed-size, so appending means manually creating a bigger array and copying everything over.
```java
int[] x = {1,2,3,4,5};
int[] y = new int[x.length+1];
for(int i = 0; i < x.length; i++){
    y[i] = x[i];
}
y[y.length-1] = 70;
System.out.println(Arrays.toString(y));  // [1,2,3,4,5,70]
System.out.println(Arrays.toString(x));  // [1,2,3,4,5]  (original unchanged)
```

**Python**
```python
x = np.array([1, 2, 3, 4, 5])
y = np.append(x, [70])
print(y)        # [ 1  2  3  4  5 70]
print(x)        # [1 2 3 4 5]   — no change to the original array
```

### Delete

**Java**
```java
int[] x = {1, 2, 3, 4, 5};
int deleteValue = 3;
int[] y = new int[x.length - 1];
int index = 0;
for (int i = 0; i < x.length; i++) {
    if (x[i] != deleteValue) {
        y[index] = x[i];
        index++;
    }
}
System.out.println(Arrays.toString(y));  // [1, 2, 4, 5]
```

**Python**
```python
x = np.array([1, 2, 3, 4, 5])
y = np.delete(x, 3)    # delete using index (not value!)
print(x)                # [1, 2, 3, 4, 5]
print(y)                # [1, 2, 4, 5]
```

### Sorting

**Java** has no reverse-sort built in — sort ascending, then manually reverse.
```java
int[] numbers = {5, 2, 8, 1, 9};
Arrays.sort(numbers);   // Ascending

int[] revArr = new int[numbers.length];
int s = 0;
for(int i=numbers.length-1; i>=0; i--){
    revArr[s++]=numbers[i];
}
System.out.println(Arrays.toString(numbers)); // [1, 2, 5, 8, 9]
System.out.println(Arrays.toString(revArr));  // [9, 8, 5, 2, 1]
```

**Python**
```python
x = np.array([7, 8, 3, 10, 5])
sorted_x = np.sort(x)
print(sorted_x)          # Ascending: [3, 5, 7, 8, 10]
print(sorted_x[::-1])    # Descending: reverse the ascending-sorted array
```

### 2-D Array

**Java**
```java
int[][] arr_2d = {
    {1, 2, 3, 7, 55},
    {4, 5, 6, 99, 10}
};
System.out.println(Arrays.deepToString(arr_2d));
// [[1, 2, 3, 7, 55], [4, 5, 6, 99, 10]]
```

**Python**
```python
arr_2d = np.array([[1, 2, 3, 7, 55],
                    [4, 5, 6, 99, 10]])
print(arr_2d)
# [[ 1  2  3  7 55]
#  [ 4  5  6 99 10]]
```

### Shape & Dimension of a Matrix

**Java** — all 2D arrays are explicitly 2-dimensional by construction; rows/cols are computed manually.
```java
int[][] arr_2d = {{1,2,3,4,5}, {6,7,8,9,10}};
int rows = arr_2d.length;
int cols = arr_2d[0].length;
int ndim = 2;
System.out.println("Number of rows: " + rows);          // 2
System.out.println("Shape: (" + rows + ", " + cols + ")"); // (2, 5)
System.out.println("Number of dimensions: " + ndim);     // 2
```

**Python**
```python
print(len(arr_2d))        # 2
print(arr_2d.shape)       # (2, 5)   — (row, column)
print(arr_2d.ndim)        # 2        — number of dimensions
```

### Indexing (1-D)

**Java**
```java
int[] numbers = {5, 2, 8, 1, 9};
System.out.println(numbers[0]);                 // 5 (first element)
System.out.println(numbers[numbers.length-1]);  // 9 (last element)
```

**Python**
```python
arr = np.array([5, 2, 8, 1, 9])
print(arr[0])    # 5
print(arr[-1])   # 9  — negative indexing straight from the language
```

### 2-D Indexing

**Java**
```java
int[][] arr = {{1,2,3,4,5}, {6,7,8,9,10}};
System.out.println("4th element on 2nd row: " + arr[1][3]);  // 9
```

**Python**
```python
arr = np.array([[1,2,3,4,5], [6,7,8,9,10]])
print('4th element on 2nd row:', arr[1, 3])   # 9
```

### Slicing a 2-D Array

**Java** has no 2D slicing syntax — use `Arrays.copyOfRange()` row by row.
```java
int[][] arr = {{1,2,3,4,5}, {6,7,8,9,10}};
// From the second row, slice index 1 to 4 (not included)
int[] slice1 = Arrays.copyOfRange(arr[1], 1, 4);
System.out.println(Arrays.toString(slice1));   // [7, 8, 9]

// From both rows, slice index 1 to 4 (not included)
int[][] slice2 = new int[2][3];
for (int i = 0; i < 2; i++) {
    slice2[i] = Arrays.copyOfRange(arr[i], 1, 4);
}
System.out.println(Arrays.deepToString(slice2));  // [[2, 3, 4], [7, 8, 9]]
```

**Python**
```python
arr = np.array([[1, 2, 3, 4, 5],
                 [6, 7, 8, 9, 10]])

print(arr[1, 1:4])     # from the second row: [7 8 9]
print(arr[0:2, 1:4])   # from both rows: [[2 3 4] [7 8 9]]
```

### Taking the Last Column and Row

**Java**
```java
int[][] arr = {{1,2,3,4,5}, {6,7,8,9,10}};

int[] column0 = new int[arr.length];
for (int i = 0; i < arr.length; i++) {
    column0[i] = arr[i][0];
}
System.out.println(Arrays.toString(column0));  // [1, 6]

int[] row0 = new int[arr[0].length];
for (int j = 0; j < arr[0].length; j++) {
    row0[j] = arr[0][j];
}
System.out.println(Arrays.toString(row0));      // [1, 2, 3, 4, 5]
```

**Python**
```python
print(arr[:, 0])    # column: [1 6]
print(arr[0, :])    # row:    [1 2 3 4 5]
```

### Zero Matrix

**Java**
```java
// Create a 4×2 2D array filled with zeros
int[][] y = new int[4][2];
System.out.println(Arrays.deepToString(y));
// [[0, 0], [0, 0], [0, 0], [0, 0]]
```

**Python**
```python
y = np.zeros((4,2))     # row, column
print(y)
# [[0. 0.]
#  [0. 0.]
#  [0. 0.]
#  [0. 0.]]
```

### Summation & Product of All Elements

**Java**
```java
int[] a = {3, 4, 5};
int sumA = 0, prodA = 1;
for (int i = 0; i < a.length; i++) {
    sumA += a[i];
    prodA *= a[i];
}
System.out.println("Sum of a: " + sumA);       // 12
System.out.println("Product of a: " + prodA);  // 60
```

**Python**
```python
a = np.array([3, 4, 5])
print(np.sum(a))     # 12
print(np.prod(a))    # 60
```

### Column & Row Wise Operation

**Java**
```java
int[][] b = {{1,2,3}, {4,5,6}};
int sumB = 0;
for (int i = 0; i < b.length; i++)
    for (int j = 0; j < b[i].length; j++)
        sumB += b[i][j];
System.out.println("Sum of b: " + sumB);  // 21

int[] colSum = new int[b[0].length];
for (int j = 0; j < b[0].length; j++)
    for (int i = 0; i < b.length; i++)
        colSum[j] += b[i][j];
System.out.println("Column-wise sum: " + Arrays.toString(colSum));  // [5, 7, 9]

int[] rowSum = new int[b.length];
for (int i = 0; i < b.length; i++)
    for (int j = 0; j < b[i].length; j++)
        rowSum[i] += b[i][j];
System.out.println("Row-wise sum: " + Arrays.toString(rowSum));  // [6, 15]
```

**Python**
```python
b = np.array([[1,2,3],
              [4,5,6]])

print(np.sum(b))            # 21        — total
print(np.sum(b, axis=0))    # [5 7 9]   — column-wise
print(np.sum(b, axis=1))    # [6 15]    — row-wise
```

### Iterating Row by Row / Element by Element

**Java**
```java
int[][] arr = {{1,2,3}, {4,5,6}};
for (int i = 0; i < arr.length; i++) {
    for (int j = 0; j < arr[i].length; j++) {
        System.out.print(arr[i][j] + " ");
    }
    System.out.println();
}
```

**Python**
```python
arr = np.array([[1, 2, 3],
                 [4, 5, 6]])

for x in arr:          # iterate row by row
    print(x)
# [1 2 3]
# [4 5 6]

for x in arr:           # iterate element by element
    for y in x:
        print(y)
# 1 2 3 4 5 6
```

### Linspace — Evenly Spaced Numbers

**Java** has no built-in linspace — build it manually.
```java
double start = 0, end = 100;
int n = 4;
double[] x = new double[n];
double step = (end - start) / (n - 1);
for (int i = 0; i < n; i++) {
    x[i] = start + i * step;
}
// Output: 0.0  33.333333333333336  66.66666666666667  100.0
```

**Python**
```python
x = np.linspace(0, 100, 4)   # start, end, how many numbers
print(x)
# [  0.          33.33333333  66.66666667 100.        ]
```

---

*Reference compiled while transitioning from Java to Python for data science / ML work.*
