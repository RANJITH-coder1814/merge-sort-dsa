# 🔀 Merge Sort (C++)

This repository contains an implementation of the **Merge Sort algorithm** using C++. It is a classic **Divide and Conquer** sorting technique.

---

## 🚀 Problem Statement

Given an array of integers `nums`, sort the array in **non-decreasing order** using the **Merge Sort algorithm**.

---

## 🧠 Approach

Merge Sort works in three steps:

1. **Divide** the array into two halves
2. **Recursively sort** both halves
3. **Merge** the sorted halves

---

## ⚙️ Algorithm

* Find the middle index
* Recursively sort left and right halves
* Merge both halves using a temporary array

---

## 💻 Code (C++)

```cpp
class Solution {
public:

    void merge(vector<int>& nums, int lb, int mid, int ub) {
        vector<int> temp;

        int i = lb;
        int j = mid + 1;

        while (i <= mid && j <= ub) {
            if (nums[i] <= nums[j]) {
                temp.push_back(nums[i++]);
            } else {
                temp.push_back(nums[j++]);
            }
        }

        while (i <= mid) {
            temp.push_back(nums[i++]);
        }

        while (j <= ub) {
            temp.push_back(nums[j++]);
        }

        for (int k = lb; k <= ub; k++) {
            nums[k] = temp[k - lb];
        }
    }

    void solve(vector<int>& nums, int lb, int ub) {
        if (lb >= ub) return;

        int mid = (lb + ub) / 2;

        solve(nums, lb, mid);
        solve(nums, mid + 1, ub);

        merge(nums, lb, mid, ub);
    }

    vector<int> mergeSort(vector<int>& nums) {
        solve(nums, 0, nums.size() - 1);
        return nums;
    }
};
```

---

## ⏱️ Time Complexity

| Case         | Complexity |
| ------------ | ---------- |
| Best Case    | O(n log n) |
| Average Case | O(n log n) |
| Worst Case   | O(n log n) |

---

## 💾 Space Complexity

* **O(n)** → Temporary array used during merging

---

## 📌 Key Points

* Stable sorting algorithm
* Works well for large datasets
* Not an in-place algorithm

---

## 🧪 Example

**Input:**

```
nums = [7, 4, 1, 5, 3]
```

**Output:**

```
[1, 3, 4, 5, 7]
```

---

## 📚 Topics Covered

* Divide and Conquer
* Recursion
* Sorting Algorithms

---

## ⭐ If you found this helpful, give it a star!
