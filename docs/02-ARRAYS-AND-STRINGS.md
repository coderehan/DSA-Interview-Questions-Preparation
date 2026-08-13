# 🟢 Arrays & Strings — DSA Questions

> Click **📤 Output** under each program to reveal the sample output.

---

## 1. Find duplicates in array

```kotlin
fun main() {

    val arr = intArrayOf(1, 2, 3, 2, 4, 1, 5)

    val seen = HashSet<Int>()       // To store elements we've already visited
    val duplicates = HashSet<Int>() // To store duplicate elements found

    // Take each element from arr one by one and store it in num
    for (num in arr) {
        // If already seen before, it's a duplicate
        if (!seen.add(num)) {
            duplicates.add(num)
        }
    }

    println("Duplicates found: $duplicates")
}
```
<details>
<summary>📤 Output</summary>

```
Duplicates found: [2, 1]
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(n)

---

## 2. Reverse a string

```kotlin
fun main() {

    println("Enter a string:")
    val input = readLine()!!

    // reversed() built-in function reverses character order
    val reversed = input.reversed()

    println("Reversed string: $reversed")
}
```
<details>
<summary>📤 Output</summary>

```
Enter a string:
Kotlin
Reversed string: niltoK
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(n)

---

## 3. Check palindrome

```kotlin
fun main() {

    println("Enter a string:")
    val input = readLine()!!

    // Compare original string with its reverse
    val isPalindrome = input == input.reversed()

    if (isPalindrome) {
        println("$input is a Palindrome")
    } else {
        println("$input is NOT a Palindrome")
    }
}
```
<details>
<summary>📤 Output</summary>

```
Enter a string:
madam
madam is a Palindrome
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(n)

---

## 4. Two sum problem

```kotlin
fun main() {

    val nums = intArrayOf(2, 7, 11, 15)
    val target = 9

    // Map to store value -> index of elements we've already visited
    val map = HashMap<Int, Int>()

    for (i in nums.indices) {
        val complement = target - nums[i]   // Number needed to reach target

        // If complement already exists in map, we found our pair
        if (map.containsKey(complement)) {
            println("Indices: [${map[complement]}, $i]")
            return
        }

        // Store current number with its index
        map[nums[i]] = i
    }

    println("No pair found")
}
```
<details>
<summary>📤 Output</summary>

```
Indices: [0, 1]
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(n)

---

## 5. Find maximum element

```kotlin
fun main() {

    val arr = intArrayOf(4, 9, 1, 7, 3)

    // Assume first element is max initially
    var max = arr[0]

    // Traverse rest of the array
    for (i in 1 until arr.size) {
        if (arr[i] > max) {
            max = arr[i]   // Update max when a bigger element is found
        }
    }

    println("Maximum element = $max")
}
```
<details>
<summary>📤 Output</summary>

```
Maximum element = 9
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(1)

---
