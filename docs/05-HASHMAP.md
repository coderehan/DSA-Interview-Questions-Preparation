# 🗺️ HashMap — DSA Questions

> Click **📤 Output** under each program to reveal the sample output.

---

## 1. Two sum using HashMap

```kotlin
fun main() {

    val nums = intArrayOf(3, 2, 4)
    val target = 6

    // Map stores value -> its index, for O(1) lookups
    val map = HashMap<Int, Int>()

    for (i in nums.indices) {
        val complement = target - nums[i]

        // Check if the number we need is already in the map
        if (map.containsKey(complement)) {
            println("Indices: [${map[complement]}, $i]")
            return
        }

        map[nums[i]] = i   // Store current number with its index
    }

    println("No pair found")
}
```
<details>
<summary>📤 Output</summary>

```
Indices: [1, 2]
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(n)

---

## 2. First non-repeating character

```kotlin
fun main() {

    println("Enter a string:")
    val input = readLine()!!

    // Map to store frequency of each character
    val frequency = LinkedHashMap<Char, Int>()

    // Count occurrences of every character
    for (ch in input) {
        frequency[ch] = frequency.getOrDefault(ch, 0) + 1
    }

    // Find first character whose count is exactly 1
    var result: Char? = null
    for (ch in input) {
        if (frequency[ch] == 1) {
            result = ch
            break
        }
    }

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

## 3. Group anagrams

```kotlin
fun main() {

    val words = arrayOf("eat", "tea", "tan", "ate", "nat", "bat")

    // Map: sorted version of word -> list of original words matching it
    val groups = HashMap<String, MutableList<String>>()

    for (word in words) {
        // Anagrams share the same sorted character sequence
        val key = word.toCharArray().sorted().joinToString("")

        // Add word to the group matching its sorted key
        groups.getOrPut(key) { mutableListOf() }.add(word)
    }

    println("Grouped anagrams:")
    for (group in groups.values) {
        println(group)
    }
}
```
<details>
<summary>📤 Output</summary>

```
Grouped anagrams:
[eat, tea, ate]
[tan, nat]
[bat]
```
</details>

⏱ Time Complexity: O(n · k log k) — n words, k = avg word length 🗂 Space Complexity: O(n · k)

---

## 4. Count word frequency

```kotlin
fun main() {

    println("Enter a sentence:")
    val sentence = readLine()!!

    // Split sentence into words by whitespace
    val words = sentence.split(" ")

    // Map to store how many times each word appears
    val frequency = HashMap<String, Int>()

    for (word in words) {
        frequency[word] = frequency.getOrDefault(word, 0) + 1
    }

    println("Word Frequencies:")
    for ((word, count) in frequency) {
        println("$word -> $count")
    }
}
```
<details>
<summary>📤 Output</summary>

```
Enter a sentence:
the cat sat on the mat the cat ran
Word Frequencies:
the -> 3
cat -> 2
sat -> 1
on -> 1
mat -> 1
ran -> 1
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(n)

---
