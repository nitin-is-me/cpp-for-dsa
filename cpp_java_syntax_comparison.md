# C++ Syntax Compared to Java

> **Goal**
>
> This document is **not** intended to teach the entirety of C++.
>
> It exists to help a Java developer become comfortable solving DSA and LeetCode problems in **modern C++**.
>
> Think of this as:
>
> **"How would I write Java code in C++?"**

---

# Table of Contents

1. Hello World
2. Variables
3. Primitive Types
4. Constants
5. Input & Output
6. Functions
7. References
8. Pointers
9. Arrays
10. Strings
11. Loops
12. Conditionals
13. switch
14. Namespaces
15. auto
16. Range-based for loop
17. Structs vs Classes
18. Memory Management
19. Useful Notes

---

# Hello World

## Java

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
```

## C++

```cpp
#include <iostream>

int main()
{
    std::cout << "Hello World\n";
}
```

### Notes

- `iostream` provides input/output.
- `std::cout` prints to the console.
- `main()` returns an integer.
- Returning `0` is optional in modern C++.

---

# Variables

## Java

```java
int age = 20;
double salary = 50000.5;
char grade = 'A';
boolean student = true;
```

## C++

```cpp
int age = 20;
double salary = 50000.5;
char grade = 'A';
bool student = true;
```

### Differences

Java:

```java
boolean
```

C++:

```cpp
bool
```

---

# Primitive Types

| Java | C++ |
|------|------|
| byte | char / std::int8_t |
| short | short |
| int | int |
| long | long |
| float | float |
| double | double |
| char | char |
| boolean | bool |

For DSA, you'll mostly use:

- int
- long long
- double
- char
- bool

---

# Constants

## Java

```java
final int SIZE = 10;
```

## C++

```cpp
const int SIZE = 10;
```

Modern C++ also has:

```cpp
constexpr int SIZE = 10;
```

You won't need `constexpr` for most DSA problems.

---

# Input & Output

## Java

```java
Scanner sc = new Scanner(System.in);

int n = sc.nextInt();

System.out.println(n);
```

## C++

```cpp
#include <iostream>

int n;

std::cin >> n;

std::cout << n << '\n';
```

### Notes

`cin`

↓

reads input

`cout`

↓

prints output

---

# Functions

## Java

```java
static int square(int x)
{
    return x * x;
}
```

## C++

```cpp
int square(int x)
{
    return x * x;
}
```

No `static` needed.

---

# References

One of the biggest differences from Java.

Java:

```java
void print(List<Integer> nums)
```

C++:

```cpp
void print(vector<int>& nums)
```

Notice the `&`.

This means:

> Pass by reference.

Advantages:

- No copying.
- Faster.
- Modifies original object.

If you don't want modifications:

```cpp
void print(const vector<int>& nums)
```

You'll see this **everywhere** in C++.

---

# Pointers

You already know pointers from C.

Nothing fundamentally changes.

```cpp
int x = 10;

int* p = &x;
```

Modern C++ prefers references whenever possible.

---

# Arrays

## Java

```java
int[] nums = {1,2,3};
```

## C++

```cpp
int nums[] = {1,2,3};
```

However...

For DSA you'll almost always use:

```cpp
vector<int>
```

instead of raw arrays.

---

# Strings

## Java

```java
String name = "Nitin";
```

## C++

```cpp
string name = "Nitin";
```

Remember to include:

```cpp
#include <string>
```

or

```cpp
#include <bits/stdc++.h>
```

---

# Loops

## for

Java

```java
for(int i=0;i<10;i++)
```

C++

```cpp
for(int i=0;i<10;i++)
```

Exactly the same.

---

## while

Java

```java
while(condition)
```

C++

```cpp
while(condition)
```

Exactly the same.

---

# Conditionals

Identical.

```cpp
if(...)
{

}
else
{

}
```

---

# switch

Also identical.

```cpp
switch(value)
{

}
```

---

# Namespaces

You'll constantly see:

```cpp
std::
```

Examples:

```cpp
std::cout

std::cin

std::vector

std::string

std::unordered_map
```

Many competitive programmers simply write:

```cpp
using namespace std;
```

Then:

```cpp
vector<int> nums;

cout << nums.size();
```

Instead of:

```cpp
std::vector<int>

std::cout
```

---

# auto

One of C++'s nicest features.

Instead of

```cpp
unordered_map<int,int>::iterator it = map.begin();
```

you write

```cpp
auto it = map.begin();
```

The compiler figures out the type.

Think of it as:

> "Infer the type."

Similar to Java:

```java
var
```

introduced in Java 10.

---

# Range-based for loop

Java

```java
for(int num : nums)
```

C++

```cpp
for(int num : nums)
```

Exactly the same syntax.

You'll use this constantly.

---

# Structs vs Classes

In C:

```c
struct Student
{

};
```

C++:

```cpp
struct Student
{

};
```

Difference:

Members are public by default.

Classes are private by default.

For DSA you'll rarely care.

---

# Memory Management

Old C++:

```cpp
new

delete
```

Modern C++:

Prefer STL containers.

Instead of:

```cpp
new int[100];
```

Use:

```cpp
vector<int> nums;
```

Instead of:

```cpp
char*
```

Use:

```cpp
string
```

Instead of manually managing memory...

Let STL do it.

---

# Useful Notes

## Semicolons

Still required.

---

## Comments

Single line

```cpp
//
```

Multi-line

```cpp
/*
...
*/
```

---

## Header Files

Java:

```java
import java.util.*;
```

C++:

```cpp
#include <vector>
#include <unordered_map>
```

Competitive programmers usually use:

```cpp
#include <bits/stdc++.h>
```

This includes almost everything.

Not part of the official C++ standard, but available on most competitive programming platforms.

---

# Mental Mapping

| Java | C++ |
|------|------|
| Scanner | cin |
| System.out | cout |
| String | string |
| Array | array / vector |
| ArrayList | vector |
| HashMap | unordered_map |
| HashSet | unordered_set |
| TreeMap | map |
| TreeSet | set |
| Queue | queue |
| Stack | stack |
| PriorityQueue | priority_queue |
| var | auto |

---

# Summary

When coming from Java, C++ should not feel like an entirely new language.

Instead, think of it as:

- Java syntax + C power + an amazing Standard Template Library (STL).

For DSA, the biggest transition is not the language itself.

It is learning the STL.
