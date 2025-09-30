# Big-O-notation

# Algorithm Analysis

## 1. What is Algorithm Analysis?

Algorithm analysis is the process of determining the efficiency of an algorithm in terms of:

- **Time Complexity**: How long an algorithm takes to run as a function of input size `n`.
- **Space Complexity**: How much memory an algorithm uses as a function of input size `n`.

It helps us predict performance and compare algorithms without actually running them.

---

## 2. Why Use Big O Notation?

Big O notation provides an **upper bound** on the growth of an algorithm’s running time (or space) relative to the input size.

- It focuses on **asymptotic behavior**, meaning how the algorithm behaves as `n` becomes very large.
- Big O **ignores constants and less significant terms** because they become negligible for large `n`.

---

## 3. Common Big O Notations

| Complexity | Name        | Example                        | Notes                                      |
|------------|------------|--------------------------------|--------------------------------------------|
| `O(1)`    | Constant    | Accessing an array element     | Time doesn’t depend on input size         |
| `O(log n)`| Logarithmic | Binary search                  | Very efficient for large inputs           |
| `O(n)`    | Linear      | Traversing an array            | Time grows proportionally with input      |
| `O(n log n)` | Linearithmic | Merge Sort, Quick Sort (average) | Slightly worse than linear but efficient |
| `O(n²)`   | Quadratic   | Bubble Sort, Selection Sort    | Becomes slow for large inputs             |
| `O(n³)`   | Cubic       | Triple nested loops            | Rarely practical for big inputs           |
| `O(2^n)`  | Exponential | Recursive Fibonacci            | Extremely slow for large `n`              |
| `O(n!)`   | Factorial   | Travelling Salesman (brute-force) | Only feasible for very small `n`         |

## 4. Steps to Analyze an Algorithm

1. **Identify basic operations**: Determine the operations that dominate the algorithm (loops, recursive calls, etc.).  
2. **Count the number of times the operation runs**: Express it as a function of `n` (input size).  
3. **Express as Big O**: Keep only the fastest-growing term and drop constants.  

### Examples

**Example 1: Linear Search**  
for (int i = 0; i < n; i++) {
    if (arr[i] == key) return i;
}

**Example 2: Nested Loop**
for (int i = 0; i < n; i++) {
    for (int j = 0; j < n; j++) {
        // some constant operation
    }
}

**Example 3: Binary Search**
int low = 0, high = n-1;
while (low <= high) {
    int mid = (low + high)/2;
    if (arr[mid] == key) return mid;
    else if (arr[mid] < key) low = mid+1;
    else high = mid-1;
}



## 5. Rules for Big O Simplification

- **Drop constants**: `O(2n)` → `O(n)`  
- **Keep dominant term**: `O(n² + n)` → `O(n²)`  
- **Multiply for nested loops**: `O(n ⋅ m)` (for loops inside loops)  
- **Add for sequential operations**: `O(n) + O(m)` → `O(n + m)`  

---

## 6. Space Complexity

- **Auxiliary space**: Extra memory used by the algorithm (e.g., recursion stack, temporary arrays).  
- **Example**: Merge Sort uses `O(n)` space due to temporary arrays.  

---

## 7. Why Big O is Important

- Predicts performance for large inputs.  
- Helps choose better algorithms.  
- Allows comparing efficiency without implementation.

- ## Conclusion

Algorithm analysis using Big O notation is a fundamental tool in computer science to evaluate the efficiency of algorithms in terms of **time** and **space**. It helps us:

- Predict how an algorithm will scale with increasing input size.  
- Compare multiple algorithms to choose the most efficient for a problem.  
- Focus on the dominant operations, ignoring minor contributions that are negligible for large inputs.  

Big O notation provides a **clear, standardized, and language-independent** way to describe performance, making it easier to write optimized and reliable code. Understanding it is essential for:

- Designing efficient algorithms  
- Improving software performance  
- Succeeding in competitive programming or technical interviews

