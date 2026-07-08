# Java ↔ C++ Cheat Sheet.md

> **Goal**
>
> A quick reference for Java developers solving DSA in C++.
>
> This file is **not** meant for learning concepts. It is meant to answer:
>
> > "What's the C++ equivalent of this Java thing?"
>
> Use this whenever you forget C++ syntax during LeetCode or competitive programming.

---

# Variables

| Java | C++ |
|------|------|
| int | int |
| long | long / long long |
| double | double |
| float | float |
| char | char |
| boolean | bool |
| String | string |
| final | const |
| var | auto |

---

# Input & Output

| Java | C++ |
|------|------|
| Scanner | cin |
| System.out.print() | cout |
| System.out.println() | cout << '\n' |
| System.err.println() | cerr |

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

Preferred for DSA

```cpp
vector<int> nums = {1,2,3};
```

---

# Collections

| Java | C++ |
|------|------|
| ArrayList | vector |
| LinkedList | list |
| ArrayDeque | deque |
| Stack | stack |
| Queue | queue |
| PriorityQueue | priority_queue |
| HashSet | unordered_set |
| TreeSet | set |
| HashMap | unordered_map |
| TreeMap | map |

---

# Adding Elements

| Java | C++ |
|------|------|
| add() | push_back() |
| push() | push() |
| put() | map[key] = value |
| offer() | push() |

---

# Removing Elements

| Java | C++ |
|------|------|
| remove() | erase() |
| remove(index) | erase(iterator) |
| pop() | pop() |
| clear() | clear() |

---

# Access

| Java | C++ |
|------|------|
| list.get(i) | vector[i] |
| map.get(key) | map[key] |
| list.size() | size() |
| isEmpty() | empty() |
| contains() | find() |

---

# Loops

Java

```java
for(int i=0;i<n;i++)
```

↓

C++

```cpp
for(int i=0;i<n;i++)
```

Exactly the same.

---

Enhanced for-loop

Java

```java
for(int num : nums)
```

↓

C++

```cpp
for(int num : nums)
```

Exactly the same.

---

# Sorting

Java

```java
Collections.sort(list);

Arrays.sort(array);
```

↓

C++

```cpp
sort(nums.begin(), nums.end());
```

Descending

```cpp
sort(nums.begin(), nums.end(), greater<int>());
```

---

# Reverse

Java

```java
Collections.reverse(list);
```

↓

C++

```cpp
reverse(nums.begin(), nums.end());
```

---

# Binary Search

Java

```java
Collections.binarySearch(...)
```

↓

C++

```cpp
binary_search(...)
```

---

# Minimum & Maximum

Java

```java
Math.min(a,b)

Math.max(a,b)
```

↓

C++

```cpp
min(a,b)

max(a,b)
```

---

# String Length

Java

```java
name.length()
```

↓

C++

```cpp
name.length()

or

name.size()
```

---

# String Concatenation

Java

```java
a + b
```

↓

C++

```cpp
a + b
```

Exactly the same.

---

# HashMap

Java

```java
Map<Integer,Integer> map = new HashMap<>();
```

↓

C++

```cpp
unordered_map<int,int> map;
```

---

Insert

Java

```java
map.put(5,10);
```

↓

C++

```cpp
map[5] = 10;
```

---

Retrieve

Java

```java
map.get(5);
```

↓

C++

```cpp
map[5];
```

---

# HashSet

Java

```java
Set<Integer> set = new HashSet<>();
```

↓

C++

```cpp
unordered_set<int> set;
```

---

Insert

Java

```java
set.add(5);
```

↓

C++

```cpp
set.insert(5);
```

---

# Queue

Java

```java
Queue<Integer> q = new LinkedList<>();
```

↓

C++

```cpp
queue<int> q;
```

---

Add

Java

```java
offer()

add()
```

↓

C++

```cpp
push()
```

---

Front

Java

```java
peek()
```

↓

C++

```cpp
front()
```

---

Remove

Java

```java
poll()
```

↓

C++

```cpp
pop()
```

---

# Stack

Java

```java
Stack<Integer> stack = new Stack<>();
```

↓

C++

```cpp
stack<int> s;
```

---

Push

```cpp
push()
```

Top

```cpp
top()
```

Pop

```cpp
pop()
```

---

# Priority Queue

Java

```java
PriorityQueue<Integer> pq;
```

↓

C++

```cpp
priority_queue<int> pq;
```

Default

```
Max Heap
```

---

# Function Parameters

Java

```java
void solve(List<Integer> nums)
```

↓

C++

```cpp
void solve(const vector<int>& nums)
```

Need modification?

↓

```cpp
void solve(vector<int>& nums)
```

---

# Type Inference

Java

```java
var name = "Nitin";
```

↓

C++

```cpp
auto name = "Nitin";
```

---

# Constants

Java

```java
final int SIZE = 100;
```

↓

C++

```cpp
const int SIZE = 100;
```

---

# Imports

Java

```java
import java.util.*;
```

↓

C++

```cpp
#include <bits/stdc++.h>
```

For competitive programming.

---

# Main Function

Java

```java
public static void main(String[] args)
```

↓

C++

```cpp
int main()
{

}
```

---

# Common Headers

| Purpose | Header |
|----------|--------|
| Input / Output | `<iostream>` |
| Strings | `<string>` |
| Vector | `<vector>` |
| Queue | `<queue>` |
| Stack | `<stack>` |
| HashMap | `<unordered_map>` |
| HashSet | `<unordered_set>` |
| Algorithms | `<algorithm>` |
| Math | `<cmath>` |
| Everything (Competitive Programming) | `<bits/stdc++.h>` |

---

# Common Complexity

| Container | Complexity |
|-----------|------------|
| vector push_back | O(1) amortized |
| unordered_map lookup | O(1) average |
| unordered_set lookup | O(1) average |
| map lookup | O(log n) |
| set lookup | O(log n) |
| priority_queue push | O(log n) |
| sort | O(n log n) |

---

# Mental Translation

When solving DSA:

```
ArrayList

↓

vector
```

```
HashMap

↓

unordered_map
```

```
HashSet

↓

unordered_set
```

```
Collections.sort()

↓

sort()
```

```
PriorityQueue

↓

priority_queue
```

```
Scanner

↓

cin
```

```
System.out.println()

↓

cout
```

```
var

↓

auto
```

```
final

↓

const
```

---

# DSA Starter Pack

If you know these C++ tools, you can solve the majority of beginner and intermediate DSA problems.

Containers

- vector
- unordered_map
- unordered_set
- queue
- stack
- priority_queue

Algorithms

- sort()
- reverse()
- binary_search()
- lower_bound()
- upper_bound()
- find()

Language Features

- auto
- const
- &
- range-based for loop

---

# Final Advice

Don't try to become a C++ expert.

Become a Java developer who is comfortable expressing algorithms in modern C++.

Whenever you're unsure about syntax, open this file.

Whenever you're unsure about *which* container or algorithm to use, open the corresponding documentation.

That's enough to become productive without getting lost in the enormous world of C++.
