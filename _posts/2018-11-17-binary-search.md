---
layout: post
title: Binary Search
date: 2018-11-17 15:09:00
description: Explanation of binary search algorithm 
tags: dsa code
categories: computer-science
---
Binary search is used to locate an element in an array efficiently than the linear search. To use a binary search, the array must be sorted in non-decreasing order. If A[1…n] is the sorted array, then the binary search returns an index i at which the element(say x) is found. If the element is not in the array then, it returns a possible index where the element might be inserted. Here, we wish to find the index i such that 1 < i < n + 1 and A[i - 1] < x < A[i].

At first, let’s see how do we locate an element in an array using linear or sequential approach.

LINEAR-SEARCH (A[1…n], x)
```
for i = 1 to n
    if A[i] > x
        return i
return n + 1
```

From the above algorithm, we can see clearly that the algorithm takes the time in θ(n) in the worst case where n is the number of elements. Now, let’s see how binary search algorithm will improve this running time. Basically, a binary search algorithm works like this. First, we compare the element x with the middle element of the array. As the array is sorted, if x is greater than the middle element of the array, then we do not have to search x in the left portion of the array. Otherwise, we search for x in the left portion of the array and do not have to search in the right portion of the array. The figure below will illustrate this.

Suppose we are searching for the number 9 in the sorted array:

<figure align="center">
  <img alt="Loading" src="https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEi92JZtZ_KRTtp3CnRxBb7RkK1pntDRPRXXBCJhYjmW9FtvABUMlcNLJb2f1YhxSYrn20PsaMW3drAjOsnquiYJ-6l7FJ3TKBA6x4EMcNXbzJoyzNombHjdOkl9UHU9GKKO8R00vNH4vcwtLzYGJY5-mgY1RpiTB1FQRhdBST-JJusi7UvA37c2SYSr/s320/binary_search.png"/>
  <figcaption align="center">Binary search for x = 12 in T[1...11] [Source: <a href="https://www.amazon.com/Fundamentals-Algorithmics-Gilles-Brassard/dp/0133350681">Fundamental of Algorithmics</a>]</figcaption>
</figure>

In the pseudocode below, we first check whether x lies within the range A[1] to A[n]. If it does not, we will return n + 1 and avoid the unnecessary recursive calls.

BINARY-SEARCH(A[1…n], x)
```
if n = 0 or x > A[n]
    return n + 1
else
    return BINARY-RECURSIVE(A[1…n], x)
```
BINARY-RECURSIVE(A[i…j], x)
```
if i == j
    return i
k = (i + j) / 2
if x < A[k]
    return BINARY-RECURSIVE(A[1…k], x)
else
    return BINARY-RECURSIVE(A[k + 1 … n], x)
```

**Analysis:**  
Let, T(n) be the time required for a call on BINARY-RECURSIVE(A[i…j], x) where n = j – i + 1 is the number of elements. The time required for BINARY-SEARCH(A[1..n], x) is also T(n) with a small additive constant for conditional checking. For the recursive call we can use T(n) = T(n/2) + g(n) when n is even and g(n) = θ(1) = θ(n<sup>0</sup>) =  θ(n<sup>log<sub>2</sub>1</sup>) because the algorithm takes a constant amount of time besides recursive calls. Even when n is odd, master theorem can be used and by using master theorem, T(n) = θ(n<sup>log<sub>2</sub>1</sup> log n) = θ(log n). So, binary search has logarithmic time complexity.

I think it is worth mentioning that the above algorithm can be implemented iteratively rather than recursively. The running time will be same in both cases. The only difference is that recursion needs some additional spaces because of function calls.

Originally Posted On:  
[My blog series](https://nisheshawale.blogspot.com/2018/11/binary-search.html)

Reference:  
[Fundamentals of Algorithmics](https://www.amazon.com/Fundamentals-Algorithmics-Gilles-Brassard/dp/0133350681)

