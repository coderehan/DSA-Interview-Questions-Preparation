# 💼 FAQ Interview Questions — DSA

> Click **📤 Output** under each program to reveal the sample output.

---

## 1. Find the second smallest element in array (without sort)

```kotlin
fun main() {

    val arr = intArrayOf(5, 2, 8, 1, 9, 1)

    var smallest = Int.MAX_VALUE
    var secondSmallest = Int.MAX_VALUE

    for (num in arr) {
        if (num < smallest) {
            // Current smallest becomes second smallest before updating
            secondSmallest = smallest
            smallest = num
        } else if (num < secondSmallest && num != smallest) {
            // Update second smallest if num is smaller but not equal to smallest
            secondSmallest = num
        }
    }

    println("Second smallest element = $secondSmallest")
}
```
<details>
<summary>📤 Output</summary>

```
Second smallest element = 2
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(1)

---

## 2. Move all zeros to the end

**Input:** `[0,1,0,3,12]` → **Output:** `[1,3,12,0,0]`

```kotlin
fun main() {

    val arr = intArrayOf(0, 1, 0, 3, 12)

    var insertPos = 0   // Position where next non-zero element should go

    // Move all non-zero elements to the front, preserving order
    for (i in arr.indices) {
        if (arr[i] != 0) {
            arr[insertPos] = arr[i]
            insertPos++
        }
    }

    // Fill the remaining positions with zeros
    while (insertPos < arr.size) {
        arr[insertPos] = 0
        insertPos++
    }

    println("Result: ${arr.joinToString(",", "[", "]")}")
}
```
<details>
<summary>📤 Output</summary>

```
Result: [1,3,12,0,0]
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(1)

---

## 3. Rotate array by k steps

**Input:** `[1,2,3,4,5]`, k = 2 → **Output:** `[4,5,1,2,3]`

```kotlin
fun main() {

    val arr = intArrayOf(1, 2, 3, 4, 5)
    val k = 2

    val n = arr.size
    val steps = k % n   // Handle cases where k > array size

    // Take the last 'steps' elements and place them in front,
    // followed by the remaining elements
    val rotated = arr.takeLast(steps) + arr.dropLast(steps)

    println("Result: ${rotated.joinToString(",", "[", "]")}")
}
```
<details>
<summary>📤 Output</summary>

```
Result: [4,5,1,2,3]
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(n)

---

## 4. Check if two strings are anagrams

**Example:** "listen" and "silent"

```kotlin
fun main() {

    println("Enter first string:")
    val str1 = readLine()!!

    println("Enter second string:")
    val str2 = readLine()!!

    // Two strings are anagrams if their sorted characters match
    val isAnagram = str1.toCharArray().sorted() == str2.toCharArray().sorted()

    println("Are anagrams: $isAnagram")
}
```
<details>
<summary>📤 Output</summary>

```
Enter first string:
listen
Enter second string:
silent
Are anagrams: true
```
</details>

⏱ Time Complexity: O(n log n) 🗂 Space Complexity: O(n)

---

## 5. First non-repeating character in string

**Input:** "aabbcdd" → **Output:** c

```kotlin
fun main() {

    println("Enter a string:")
    val input = readLine()!!

    // Count frequency of every character
    val frequency = LinkedHashMap<Char, Int>()
    for (ch in input) {
        frequency[ch] = frequency.getOrDefault(ch, 0) + 1
    }

    // First character with frequency 1 is the answer
    val result = input.firstOrNull { frequency[it] == 1 }

    println("First non-repeating character: ${result ?: "None"}")
}
```
<details>
<summary>📤 Output</summary>

```
Enter a string:
aabbcdd
First non-repeating character: c
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(n)

---

## 6. Remove duplicates from string

**Input:** "programming" → **Output:** "progamin"

```kotlin
fun main() {

    println("Enter a string:")
    val input = readLine()!!

    // LinkedHashSet keeps insertion order while removing duplicates
    val seen = LinkedHashSet<Char>()
    for (ch in input) {
        seen.add(ch)
    }

    val result = seen.joinToString("")
    println("Result: $result")
}
```
<details>
<summary>📤 Output</summary>

```
Enter a string:
programming
Result: progamin
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(n)

---

## 7. Find intersection of two arrays

**Input:** `[1,2,2,1]`, `[2,2]` → **Output:** `[2]`

```kotlin
fun main() {

    val arr1 = intArrayOf(1, 2, 2, 1)
    val arr2 = intArrayOf(2, 2)

    // Convert both arrays to sets to get unique elements
    val set1 = arr1.toHashSet()
    val set2 = arr2.toHashSet()

    // retainAll keeps only elements present in both sets
    set1.retainAll(set2)

    println("Intersection: ${set1.joinToString(",", "[", "]")}")
}
```
<details>
<summary>📤 Output</summary>

```
Intersection: [2]
```
</details>

⏱ Time Complexity: O(n + m) 🗂 Space Complexity: O(n + m)

---

## 8. Longest consecutive sequence

**Input:** `[100,4,200,1,3,2]` → **Output:** 4 (sequence: 1,2,3,4)

```kotlin
fun main() {

    val arr = intArrayOf(100, 4, 200, 1, 3, 2)
    val numSet = arr.toHashSet()

    var longestStreak = 0

    for (num in numSet) {
        // Only start counting from the beginning of a sequence
        // (i.e. num - 1 is not present in the set)
        if (!numSet.contains(num - 1)) {
            var currentNum = num
            var currentStreak = 1

            // Keep extending the streak while the next number exists
            while (numSet.contains(currentNum + 1)) {
                currentNum++
                currentStreak++
            }

            longestStreak = maxOf(longestStreak, currentStreak)
        }
    }

    println("Longest consecutive sequence length = $longestStreak")
}
```
<details>
<summary>📤 Output</summary>

```
Longest consecutive sequence length = 4
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(n)

---

## 9. Kadane's Algorithm (Maximum Subarray Sum)

```kotlin
fun main() {

    val arr = intArrayOf(-2, 1, -3, 4, -1, 2, 1, -5, 4)

    var maxSoFar = arr[0]     // Best sum found so far
    var maxEndingHere = arr[0] // Best sum ending at current index

    for (i in 1 until arr.size) {
        // Either extend the previous subarray or start a new one at arr[i]
        maxEndingHere = maxOf(arr[i], maxEndingHere + arr[i])

        // Update overall maximum
        maxSoFar = maxOf(maxSoFar, maxEndingHere)
    }

    println("Maximum subarray sum = $maxSoFar")
}
```
<details>
<summary>📤 Output</summary>

```
Maximum subarray sum = 6
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(1)

---

## 10. Find missing number from 1 to n

```kotlin
fun main() {

    val arr = intArrayOf(1, 2, 4, 5, 6)   // Missing number: 3
    val n = arr.size + 1

    // Expected sum of numbers 1 to n
    val expectedSum = n * (n + 1) / 2

    // Actual sum of the given array
    val actualSum = arr.sum()

    // Difference is the missing number
    val missing = expectedSum - actualSum

    println("Missing number = $missing")
}
```
<details>
<summary>📤 Output</summary>

```
Missing number = 3
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(1)

---

## 11. Check if linked list has cycle

```kotlin
class Node(val value: Int) {
    var next: Node? = null
}

fun hasCycle(head: Node?): Boolean {
    // Floyd's Cycle Detection (Tortoise & Hare)
    var slow = head
    var fast = head

    while (fast != null && fast.next != null) {
        slow = slow!!.next
        fast = fast.next!!.next

        // If slow and fast ever meet, a cycle exists
        if (slow === fast) return true
    }

    return false
}

fun main() {
    // Build list: 1 -> 2 -> 3 -> (back to 2, cycle!)
    val head = Node(1)
    val second = Node(2)
    val third = Node(3)

    head.next = second
    second.next = third
    third.next = second   // Creates a cycle

    println("Has cycle: ${hasCycle(head)}")
}
```
<details>
<summary>📤 Output</summary>

```
Has cycle: true
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(1)

---

## 12. Buy and sell stock max profit

```kotlin
fun main() {

    val prices = intArrayOf(7, 1, 5, 3, 6, 4)

    var minPrice = Int.MAX_VALUE   // Lowest price seen so far
    var maxProfit = 0

    for (price in prices) {
        if (price < minPrice) {
            // Found a cheaper day to buy
            minPrice = price
        } else if (price - minPrice > maxProfit) {
            // Selling today gives a better profit than before
            maxProfit = price - minPrice
        }
    }

    println("Maximum profit = $maxProfit")
}
```
<details>
<summary>📤 Output</summary>

```
Maximum profit = 5
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(1)

---

# ✍️ String-Based Important Questions

---

## 13. Longest substring without repeating characters

```kotlin
fun main() {

    println("Enter a string:")
    val s = readLine()!!

    val seen = HashMap<Char, Int>()   // Character -> last seen index
    var maxLength = 0
    var start = 0   // Start of current window

    for (end in s.indices) {
        val ch = s[end]

        // If character was seen inside the current window, shrink window
        if (seen.containsKey(ch) && seen[ch]!! >= start) {
            start = seen[ch]!! + 1
        }

        seen[ch] = end   // Update last seen index
        maxLength = maxOf(maxLength, end - start + 1)
    }

    println("Longest substring without repeating characters = $maxLength")
}
```
<details>
<summary>📤 Output</summary>

```
Enter a string:
abcabcbb
Longest substring without repeating characters = 3
```
</details>

⏱ Time Complexity: O(n) — sliding window 🗂 Space Complexity: O(min(n, charset size))

---

## 14. Reverse words in a sentence

```kotlin
fun main() {

    println("Enter a sentence:")
    val sentence = readLine()!!

    // Split by whitespace, reverse the order of words, join back
    val reversed = sentence.trim().split("\\s+".toRegex()).reversed().joinToString(" ")

    println("Reversed sentence: $reversed")
}
```
<details>
<summary>📤 Output</summary>

```
Enter a sentence:
Kotlin is fun to learn
Reversed sentence: learn to fun is Kotlin
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(n)

---

## 15. Count vowels and consonants

```kotlin
fun main() {

    println("Enter a string:")
    val input = readLine()!!

    var vowelCount = 0
    var consonantCount = 0

    val vowels = "aeiouAEIOU"

    for (ch in input) {
        if (ch.isLetter()) {
            // Check whether the letter is a vowel or a consonant
            if (vowels.contains(ch)) {
                vowelCount++
            } else {
                consonantCount++
            }
        }
    }

    println("Vowels = $vowelCount, Consonants = $consonantCount")
}
```
<details>
<summary>📤 Output</summary>

```
Enter a string:
Hello World
Vowels = 3, Consonants = 7
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(1)

---

## 16. String compression

**Input:** "aaabb" → **Output:** "a3b2"

```kotlin
fun main() {

    println("Enter a string:")
    val input = readLine()!!

    val result = StringBuilder()
    var count = 1

    var i = 0
    while (i < input.length) {
        // Count how many times the current character repeats consecutively
        if (i + 1 < input.length && input[i] == input[i + 1]) {
            count++
        } else {
            // Append character followed by its count, then reset
            result.append(input[i])
            result.append(count)
            count = 1
        }
        i++
    }

    println("Compressed string: $result")
}
```
<details>
<summary>📤 Output</summary>

```
Enter a string:
aaabb
Compressed string: a3b2
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(n)

---
