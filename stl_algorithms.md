# STL Algorithms.md

> **Goal**
>
> Learn the most useful STL algorithms required for DSA and LeetCode.
>
> These algorithms work on STL containers like `vector`, `deque`, `set`, etc., so instead of implementing common algorithms yourself, you simply call them.

---

# Table of Contents

1. What are STL Algorithms?
2. Iterators
3. sort()
4. reverse()
5. find()
6. count()
7. binary_search()
8. lower_bound()
9. upper_bound()
10. min() & max()
11. min_element() & max_element()
12. swap()
13. fill()
14. accumulate()
15. Common Iterator Functions
16. Complexity Table
17. Java ↔ C++ Comparison
18. Summary

---

# What are STL Algorithms?

Think of STL algorithms as ready-made implementations of common algorithms.

Instead of writing:

- Quick Sort
- Binary Search
- Reverse
- Find
- Count

yourself...

C++ already provides them.

This keeps your code shorter, cleaner and less error-prone.

---

# Iterators

Before learning STL algorithms, you need to know one thing.

Almost every STL algorithm works using **iterators**.

Example:

```cpp
vector<int> nums = {5,2,9,1};
```

Beginning:

```cpp
nums.begin()
```

End:

```cpp
nums.end()
```

Notice

`end()`

does **NOT** point to the last element.

It points **one position after** the last element.

Exactly like Java's

```java
list.size()
```

where the last valid index is

```java
size() - 1
```

---

# sort()

Probably the most used STL algorithm.

Instead of implementing Quick Sort or Merge Sort...

```cpp
sort(nums.begin(), nums.end());
```

Example

```cpp
vector<int> nums = {5,2,9,1};

sort(nums.begin(), nums.end());
```

Result

```
1 2 5 9
```

Complexity

```
O(n log n)
```

---

## Descending Order

```cpp
sort(nums.begin(), nums.end(), greater<int>());
```

Result

```
9 5 2 1
```

---

## Java Comparison

Java

```java
Collections.sort(list);
```

or

```java
Arrays.sort(array);
```

---

# reverse()

```cpp
reverse(nums.begin(), nums.end());
```

Example

```
1 2 3 4
```

↓

```
4 3 2 1
```

Complexity

```
O(n)
```

---

# find()

Searches for an element.

```cpp
auto it = find(nums.begin(), nums.end(), 10);
```

If found

```
it
```

points to the element.

Otherwise

```cpp
it == nums.end()
```

Example

```cpp
if(it != nums.end())
{
    cout << "Found";
}
```

Complexity

```
O(n)
```

---

## Java Comparison

```java
list.contains(x)
```

or

manual loop.

---

# count()

Counts occurrences.

```cpp
count(nums.begin(), nums.end(), 5);
```

Example

```
1 5 5 7
```

↓

returns

```
2
```

Complexity

```
O(n)
```

---

# binary_search()

Checks whether an element exists.

**Requires sorted data.**

```cpp
binary_search(nums.begin(), nums.end(), 10);
```

Returns

```
true
```

or

```
false
```

Complexity

```
O(log n)
```

---

## Java Comparison

```java
Collections.binarySearch(...)
```

---

# lower_bound()

One of the most useful algorithms.

Returns the first position

```
>= value
```

Example

```
1 2 2 2 5 7
```

Searching

```
2
```

Returns

```
first 2
```

Searching

```
3
```

Returns

```
5
```

because

```
5
```

is the first number greater than or equal to 3.

Complexity

```
O(log n)
```

Requires sorted data.

---

# upper_bound()

Returns first position

```
> value
```

Example

```
1 2 2 2 5
```

Searching

```
2
```

Returns

```
5
```

because 5 is the first number strictly greater than 2.

Complexity

```
O(log n)
```

---

# min()

```cpp
min(a,b)
```

Example

```cpp
min(4,9)
```

↓

```
4
```

---

# max()

```cpp
max(a,b)
```

Example

```cpp
max(4,9)
```

↓

```
9
```

---

# min_element()

Returns iterator pointing to smallest element.

```cpp
auto it = min_element(nums.begin(), nums.end());
```

Actual value

```cpp
*it
```

---

# max_element()

Exactly the same.

```cpp
auto it = max_element(nums.begin(), nums.end());
```

---

# swap()

```cpp
swap(a,b);
```

Instead of

```cpp
temp = a;
a = b;
b = temp;
```

---

# fill()

Assigns one value everywhere.

```cpp
fill(nums.begin(), nums.end(), 0);
```

Result

```
0 0 0 0 0
```

---

# accumulate()

Computes sum.

Need

```cpp
#include <numeric>
```

Example

```cpp
int sum = accumulate(nums.begin(), nums.end(), 0);
```

Equivalent to

```java
int sum = 0;

for(int x : nums)
{
    sum += x;
}
```

---

# Common Iterator Functions

Beginning

```cpp
begin()
```

End

```cpp
end()
```

Size

```cpp
size()
```

Empty?

```cpp
empty()
```

---

# Complexity Table

| Algorithm | Complexity |
|-----------|------------|
| sort | O(n log n) |
| reverse | O(n) |
| find | O(n) |
| count | O(n) |
| binary_search | O(log n) |
| lower_bound | O(log n) |
| upper_bound | O(log n) |
| min | O(1) |
| max | O(1) |
| min_element | O(n) |
| max_element | O(n) |
| swap | O(1) |
| fill | O(n) |
| accumulate | O(n) |

---

# Java ↔ C++ Comparison

| Java | C++ |
|------|------|
| Arrays.sort() | sort() |
| Collections.sort() | sort() |
| Collections.reverse() | reverse() |
| Collections.binarySearch() | binary_search() |
| Collections.min() | min_element() |
| Collections.max() | max_element() |
| Math.min() | min() |
| Math.max() | max() |

---

# Which Algorithms Should I Master?

For DSA, these are enough initially.

⭐⭐⭐⭐⭐

- sort()
- reverse()
- find()

⭐⭐⭐⭐

- binary_search()
- lower_bound()
- upper_bound()

⭐⭐⭐

- count()
- accumulate()
- fill()

Everything else can be learned as needed.

---

# Summary

You do **not** get extra marks for implementing Quick Sort or Binary Search yourself if the problem allows STL.

Good programmers know when to use the library.

The real skill is recognizing:

- Which algorithm fits the problem?
- What is its complexity?
- Does the input satisfy the algorithm's requirements (e.g., sorted data)?

Focus on those questions rather than memorizing every function.
