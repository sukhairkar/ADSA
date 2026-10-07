# Experiment 01: Implementation of Merge Sort

## Aim
To implement the Merge Sort algorithm using the divide-and-conquer strategy to sort a given array of integers in non-decreasing order.

## Requirements
- Java JDK 8 or later
- Command Prompt, PowerShell, VS Code, IntelliJ IDEA, or any Java-compatible IDE

## How to Compile
```bash
javac MergeSortExp.java
```

## How to Run
```bash
java MergeSortExp.java
```

## Algorithm
1. Divide the array into two halves by calculating the midpoint: $\text{mid} = \text{left} + (\text{right} - \text{left}) / 2$.
2. Recursively apply Merge Sort to the left half: $\text{sort}(\text{arr}, \text{left}, \text{mid})$.
3. Recursively apply Merge Sort to the right half: $\text{sort}(\text{arr}, \text{mid} + 1, \text{right})$.
4. Merge the two sorted subarrays back into the original array:
   - Create auxiliary arrays for left and right subarrays.
   - Compare elements from both subarrays and place the smaller element into the merged array.
   - Copy any remaining elements from either subarray.
5. Repeat until the entire array is sorted.

## Example

**Input:**
```plaintext
Enter number of elements: 5
Enter array elements:
38 27 43 3 9
```

**Output:**
```plaintext
Sorted array: 3 9 27 38 43 
```

## Complexity
- **Time Complexity:**
  - **Best Case:** $O(n \log n)$
  - **Average Case:** $O(n \log n)$
  - **Worst Case:** $O(n \log n)$
- **Space Complexity:** $O(n)$ auxiliary space for temporary merge buffers

## Conclusion
The experiment successfully implements Merge Sort in Java. The program accepts an unsorted array, applies the divide-and-conquer paradigm, and produces a sorted sequence. This experiment demonstrates the stability and logarithmic time efficiency of divide-and-conquer algorithms in computational sorting.
