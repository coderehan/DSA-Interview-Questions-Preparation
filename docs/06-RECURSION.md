# 🔁 Recursion — DSA Questions

> Click **📤 Output** under each program to reveal the sample output.

---

## 1. Fibonacci

```kotlin
fun fibonacci(n: Int): Int {
    // Base case: first two Fibonacci numbers are 0 and 1
    if (n <= 1) return n

    // Recursive case: sum of the previous two Fibonacci numbers
    return fibonacci(n - 1) + fibonacci(n - 2)
}

fun main() {
    println("Enter number of terms:")
    val n = readLine()!!.toInt()

    print("Fibonacci Series: ")
    for (i in 0 until n) {
        print("${fibonacci(i)} ")
    }
}
```
<details>
<summary>📤 Output</summary>

```
Enter number of terms:
6
Fibonacci Series: 0 1 1 2 3 5 
```
</details>

⏱ Time Complexity: O(2ⁿ) — can be optimized with memoization to O(n) 🗂 Space Complexity: O(n) — recursion stack

---

## 2. Factorial

```kotlin
fun factorial(n: Int): Long {
    // Base case
    if (n == 0) return 1L

    // Recursive call
    return n * factorial(n - 1)
}

fun main() {
    println("Enter a number:")
    val n = readLine()!!.toInt()

    println("Factorial of $n = ${factorial(n)}")
}
```
<details>
<summary>📤 Output</summary>

```
Enter a number:
5
Factorial of 5 = 120
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(n) — recursion stack

---

## 3. Binary search

```kotlin
fun binarySearch(arr: IntArray, target: Int, low: Int, high: Int): Int {

    // Base case: search range exhausted, element not found
    if (low > high) return -1

    val mid = (low + high) / 2   // Middle index

    return when {
        arr[mid] == target -> mid                              // Found it
        arr[mid] < target -> binarySearch(arr, target, mid + 1, high)  // Search right half
        else -> binarySearch(arr, target, low, mid - 1)                // Search left half
    }
}

fun main() {
    val arr = intArrayOf(2, 5, 8, 12, 16, 23, 38, 45)

    println("Enter target to search:")
    val target = readLine()!!.toInt()

    val index = binarySearch(arr, target, 0, arr.size - 1)

    if (index != -1) {
        println("Element found at index $index")
    } else {
        println("Element not found")
    }
}
```
<details>
<summary>📤 Output</summary>

```
Enter target to search:
23
Element found at index 5
```
</details>

⏱ Time Complexity: O(log n) 🗂 Space Complexity: O(log n) — recursion stack

---

## 4. Sum of digits

```kotlin
fun sumOfDigits(n: Int): Int {
    // Base case: no digits left
    if (n == 0) return 0

    // Add last digit and recurse on the remaining number
    return n % 10 + sumOfDigits(n / 10)
}

fun main() {
    println("Enter a number:")
    val n = readLine()!!.toInt()

    println("Sum of digits = ${sumOfDigits(n)}")
}
```
<details>
<summary>📤 Output</summary>

```
Enter a number:
12345
Sum of digits = 15
```
</details>

⏱ Time Complexity: O(d) — d = number of digits 🗂 Space Complexity: O(d) — recursion stack

---
