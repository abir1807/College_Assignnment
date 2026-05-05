# 📘 Assignment 1 – 

---

# 🔹 Problem 1: Cyclic Substring Maximum Sum

## 📝 Problem Statement

You are given a string **S** consisting of lowercase English alphabets. Each character has a value equal to its position in the alphabet:

```
a = 1, b = 2, ..., z = 26
```

You are allowed to:

* Choose any **cyclic substring** (substring can wrap from end to beginning)

### 🎯 Objective

Find the **maximum possible sum** of character values such that:

* No character appears more than once in the substring

---

## 📥 Input Format

* A single string **S**

## 📤 Output Format

* Print a single integer representing the maximum sum

---

## ⚙️ Constraints

* `1 ≤ |S| ≤ 10^5`

---

## 📌 Example

**Input:**

```
abca
```

**Output:**

```
6
```

**Explanation:**
Valid cyclic substrings:

* `abc` → 1 + 2 + 3 = 6
* `bca` → 2 + 3 + 1 = 6
* `cab` → 3 + 1 + 2 = 6

Maximum = **6**

---

## 💡 Approach

### 🔍 Key Observations

* Substring must be **continuous**
* Cyclic behavior can be handled by **doubling the string**
* Duplicate characters are not allowed

### ⚙️ Strategy

1. Convert string into cyclic form:

   ```
   S → S + S
   ```
2. Use **Sliding Window (Two Pointers)**
3. Use a **HashSet** to maintain unique characters
4. Expand window when no duplicates
5. Shrink window when duplicate appears
6. Ensure window size ≤ original string length
7. Track maximum sum

---

## ⏱ Complexity

* **Time:** `O(N)`
* **Space:** `O(1)` (max 26 characters)

---

# 🔹 Problem 2: Array Transformation Cost Minimization

## 📝 Problem Statement

You are given an integer array **A** of size **N**.

You can perform the following operation any number of times:

```
A[i] → A[i] + K  OR  A[i] - K
```

---

### 🎯 Objective

* Transform the array such that **all elements become equal**
* Return:

  * Minimum number of operations
  * OR `-1` if not possible

---

## 📥 Input Format

* First line: Integer **N**
* Second line: **N space-separated integers**
* Third line: Integer **K**

---

## 📤 Output Format

* Print minimum number of operations or `-1`

---

## ⚙️ Constraints

* `1 ≤ N ≤ 10^5`
* `1 ≤ A[i], K ≤ 10^9`

---

## 📌 Example

**Input:**

```
5
2 4 6 8 10
2
```

**Output:**

```
6
```

**Explanation:**
Convert all elements to 6:

* 2 → 6 (2 steps)
* 4 → 6 (1 step)
* 6 → 6 (0 steps)
* 8 → 6 (1 step)
* 10 → 6 (2 steps)

Total operations = **6**

---

## 💡 Approach

### 🔍 Key Observations

* Each element changes in steps of **K**
* All elements must satisfy:

  ```
  A[i] % K is same for all i
  ```

---

### ⚙️ Strategy

1. **Feasibility Check**

   ```
   If (A[i] - A[0]) % K != 0 → return -1
   ```

2. **Normalize the Array**

   ```
   B[i] = A[i] / K
   ```

3. **Find Optimal Target**

   * Choose **median** of B

4. **Compute Operations**

   ```
   Total = Σ |B[i] - median|
   ```

---

## ⏱ Complexity

* **Time:** `O(N log N)`
* **Space:** `O(N)`

---

# 📊 Summary

| Problem                                | Technique                |
| -------------------------------------- | ------------------------ |
| Cyclic Substring Maximum Sum           | Sliding Window + HashSet |
| Array Transformation Cost Minimization | Greedy + Median          |

---

# 🚀 Key Takeaways

* Convert cyclic problems using **string doubling**
* Use **Sliding Window** for substring constraints
* Prefer **Set over Map** for uniqueness problems
* Median minimizes total absolute difference
* Reduce problems to known algorithmic patterns

---
