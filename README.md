# Merge Sorted Array

## 📌 Problem Description

Given two sorted integer arrays `A` and `B`, merge `B` into `A` as one sorted array. Array `A` has enough space to accommodate all elements of `B`.

## 💡 Approach

Use the **Two-Pointer Technique** to merge both arrays from right to left.

* `i` points to the last valid element of `A`.
* `j` points to the last element of `B`.
* `idx` points to the last position of the merged array.
* Compare elements and place the larger element at `A[idx]`.
* Copy any remaining elements from `B` into `A`.

## ⚙️ Workflow

1. Initialize `idx = m + n - 1`, `i = m - 1`, and `j = n - 1`.
2. Compare `A[i]` and `B[j]`.
3. Place the larger element at `A[idx]`.
4. Decrease the corresponding pointer and `idx`.
5. Repeat until either array has no remaining elements.
6. Copy any remaining elements from `B` into `A`.
7. The array `A` now contains all elements in sorted order.

## 🔄 Flowchart

```mermaid
flowchart TD
    A([Start]) --> B[Initialize i = m-1, j = n-1, idx = m+n-1]
    B --> C{i >= 0 AND j >= 0?}
    C -- Yes --> D{A[i] >= B[j]?}
    D -- Yes --> E[A[idx] = A[i]]
    D -- No --> F[A[idx] = B[j]]
    E --> G[Decrease i and idx]
    F --> H[Decrease j and idx]
    G --> C
    H --> C
    C -- No --> I{j >= 0?}
    I -- Yes --> J[A[idx] = B[j]]
    J --> K[Decrease j and idx]
    K --> I
    I -- No --> L([End: A contains merged sorted array])
```

## ⏱️ Complexity Analysis

* **Time Complexity:** `O(m + n)` — Each element is processed at most once.
* **Space Complexity:** `O(1)` — The merging is performed in place.

## 🛠️ Technologies Used

* Language: C++
* Concept: Two Pointers
* Algorithm: In-place Array Merging

## 🎯 Key Learning

This problem demonstrates how two sorted arrays can be merged efficiently without using additional array space.
