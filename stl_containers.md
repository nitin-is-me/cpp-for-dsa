# STL Containers.md

> **Goal**
>
> Learn the STL containers required for solving DSA and LeetCode problems.
>
> This document assumes you already know Java, so every container is compared against its Java equivalent.

---

# Table of Contents

1. What is STL?
2. Why STL Exists
3. Sequence Containers
    - vector
    - deque
4. Container Adapters
    - stack
    - queue
    - priority_queue
5. Associative Containers
    - set
    - map
6. Unordered Associative Containers
    - unordered_set
    - unordered_map
7. pair
8. Which Container Should I Use?
9. Complexity Table
10. Java ↔ C++ Cheat Sheet

---

# What is STL?

STL stands for **Standard Template Library**.

Think of it as C++'s built-in toolbox.

Instead of implementing data structures yourself, C++ provides highly optimized implementations.

Java has something similar:

```
Java Collections Framework
```

Examples:

```
ArrayList
HashMap
HashSet
PriorityQueue
Queue
Stack
```

C++ provides similar containers through STL.

---

# Why STL Exists

Imagine implementing every data structure yourself.

Need a dynamic array?

↓

Write hundreds of lines.

Need a hash table?

↓

Write hundreds more.

Need a heap?

↓

Again...

Instead, STL already provides them.

You focus on solving the problem.

---

# vector

## Java Equivalent

```java
ArrayList<Integer>
```

## C++

```cpp
vector<int> nums;
```

---

## What is it?

A dynamic array.

It automatically resizes as elements are added.

This is probably the **most commonly used STL container**.

---

## Common Operations

```cpp
nums.push_back(10);

nums.pop_back();

nums.size();

nums.empty();

nums.clear();

nums.front();

nums.back();

nums[3];
```

---

## Time Complexity

| Operation | Complexity |
|-----------|------------|
| Access | O(1) |
| Push Back | O(1) amortized |
| Pop Back | O(1) |
| Insert Middle | O(n) |
| Delete Middle | O(n) |

---

## Example

```cpp
vector<int> nums;

nums.push_back(5);
nums.push_back(10);

for(int num : nums)
{
    cout << num << " ";
}
```

Output

```
5 10
```

---

## Java Comparison

Java

```java
ArrayList<Integer> nums = new ArrayList<>();

nums.add(5);
```

C++

```cpp
vector<int> nums;

nums.push_back(5);
```

---

# deque

## Java Equivalent

```java
ArrayDeque
```

---

## What is it?

Double Ended Queue.

Can insert and remove from both ends efficiently.

---

## Operations

```cpp
push_front()

push_back()

pop_front()

pop_back()

front()

back()
```

---

## Complexity

Everything above

```
O(1)
```

---

# stack

## Java Equivalent

```java
Stack<Integer>
```

or

```java
Deque<Integer>
```

---

## What is it?

LIFO

Last In First Out

Think:

```
Books
```

---

## Operations

```cpp
stack<int> s;

s.push(10);

s.pop();

s.top();

s.empty();
```

---

## Complexity

Everything

```
O(1)
```

---

# queue

## Java Equivalent

```java
Queue<Integer>
```

---

## What is it?

FIFO

First In First Out

Think

```
People standing in a line.
```

---

## Operations

```cpp
queue<int> q;

q.push(5);

q.pop();

q.front();

q.back();
```

---

## Complexity

Everything

```
O(1)
```

---

# priority_queue

## Java Equivalent

```java
PriorityQueue<Integer>
```

---

## What is it?

A Heap.

By default

```
Max Heap
```

Largest element always stays on top.

---

## Operations

```cpp
priority_queue<int> pq;

pq.push(30);

pq.push(10);

pq.push(50);

pq.top();
```

Returns

```
50
```

---

## Complexity

| Operation | Complexity |
|-----------|------------|
| Insert | O(log n) |
| Remove Top | O(log n) |
| Top | O(1) |

---

# set

## Java Equivalent

```java
TreeSet<Integer>
```

---

## What is it?

Stores only unique values.

Automatically keeps them sorted.

Implemented using a balanced tree.

---

## Operations

```cpp
set<int> s;

s.insert(5);

s.erase(5);

s.find(5);

s.count(5);
```

---

## Complexity

Everything

```
O(log n)
```

---

# unordered_set

## Java Equivalent

```java
HashSet<Integer>
```

---

## What is it?

Hash Table.

Stores unique values.

Not sorted.

---

## Complexity

Average

```
O(1)
```

Worst

```
O(n)
```

---

# map

## Java Equivalent

```java
TreeMap<K,V>
```

---

## What is it?

Stores

```
key → value
```

Automatically sorted by key.

Balanced Tree.

---

## Example

```cpp
map<string,int> age;

age["Nitin"] = 20;
```

---

## Complexity

Everything

```
O(log n)
```

---

# unordered_map

## Java Equivalent

```java
HashMap<K,V>
```

---

## What is it?

Hash Table.

Probably the second most used container after vector.

---

## Example

```cpp
unordered_map<string,int> age;

age["Nitin"] = 20;
```

---

## Complexity

Average

```
O(1)
```

Worst

```
O(n)
```

---

# pair

## Java Equivalent

No exact equivalent.

Closest:

```
Map.Entry
```

or

a tiny custom class.

---

## Example

```cpp
pair<int,string> student;

student.first = 1;

student.second = "Nitin";
```

---

## Why useful?

Frequently used in

- Graphs

- BFS

- DFS

- Coordinates

---

# Which Container Should I Use?

Need...

Dynamic Array

↓

```
vector
```

Need...

Hash Table

↓

```
unordered_map
```

Need...

Unique Values

↓

```
unordered_set
```

Need...

Sorted Keys

↓

```
map
```

Need...

Sorted Unique Values

↓

```
set
```

Need...

LIFO

↓

```
stack
```

Need...

FIFO

↓

```
queue
```

Need...

Largest / Smallest Element Quickly

↓

```
priority_queue
```

Need...

Insert From Both Ends

↓

```
deque
```

---

# Complexity Table

| Container | Java Equivalent | Lookup | Insert | Delete |
|-----------|-----------------|---------|---------|---------|
| vector | ArrayList | O(1) index | O(1) back | O(1) back |
| deque | ArrayDeque | O(1) | O(1) | O(1) |
| stack | Stack | O(1) | O(1) | O(1) |
| queue | Queue | O(1) | O(1) | O(1) |
| priority_queue | PriorityQueue | O(1) top | O(log n) | O(log n) |
| set | TreeSet | O(log n) | O(log n) | O(log n) |
| unordered_set | HashSet | O(1) avg | O(1) avg | O(1) avg |
| map | TreeMap | O(log n) | O(log n) | O(log n) |
| unordered_map | HashMap | O(1) avg | O(1) avg | O(1) avg |

---

# Java ↔ C++ Cheat Sheet

| Java | C++ |
|------|------|
| ArrayList | vector |
| ArrayDeque | deque |
| Stack | stack |
| Queue | queue |
| PriorityQueue | priority_queue |
| HashSet | unordered_set |
| TreeSet | set |
| HashMap | unordered_map |
| TreeMap | map |

---

# Which STL Containers Should I Master?

For DSA and LeetCode, mastering these is enough:

- vector

- unordered_map

- unordered_set

- queue

- stack

- priority_queue

Everything else can be learned when needed.

---

# Summary

Don't try to memorize the entire STL.

Instead, become comfortable answering one question:

> **"Which container best fits this problem?"**

Once you can answer that, the syntax becomes much easier to remember.
