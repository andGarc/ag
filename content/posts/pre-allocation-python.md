+++
title = 'Optimize Python Code Using Pre-Allocation'
date = 2023-08-26T18:41:22-05:00
draft = false
tags = ['python']
description = 'Pre-Allocation example in python'
+++

**Note:** you'll really only notice a performance improvement when working with large data. Always make sure to look at Big-O first and fixt those issues first. 

## What is Pre-Allocation

Pre-allocation in Python typically refers to allocating memory or space for data structures such as lists, arrays, or other collections before adding elements to them. This concept is particularly relevant in situations where the size of the data structure is known in advance, or when performance optimization is desired.

## Example 
We are creating an empty list, iterating 30 million times using a for loop, and appending an element to the list at every iteration.

```python
# Dynamic Storage
start = time.time()
my_list = []
for num in range(30_000_000):
    my_list.append(num)
end = time.time()
print(f"Seconds: {end-start}")
```

We can use pre-allocation to optimize the code above.
We can create a list containing 30 million elements, with each element initially set to 0. Then we'll change the values of that list at each index as we go throught the loop. 

```python
# Pre-allocation
start = time.time()
my_list = [0]*30_000_000
for num in range(30_000_000):
    my_list[num] = num
end = time.time()
print(f"Seconds: {end-start}")
```

## Summary
Preallocation can be beneficial in scenarios where you know the size of the data structure in advance and want to avoid unnecessary memory reallocations, which can improve performance and memory efficiency. However, it's important to note that Python's lists automatically resize themselves as needed, so preallocation is not always necessary and may not always lead to significant performance improvements. It's often a matter of optimizing specific performance-critical sections of code.
