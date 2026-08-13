# 📚 Stack & Queue — DSA Questions

> Click **📤 Output** under each program to reveal the sample output.

---

## 1. Valid parentheses

```kotlin
fun isValid(s: String): Boolean {

    val stack = ArrayDeque<Char>()   // Stack to keep track of opening brackets

    // Map each closing bracket to its matching opening bracket
    val pairs = mapOf(')' to '(', ']' to '[', '}' to '{')

    for (ch in s) {
        if (ch == '(' || ch == '[' || ch == '{') {
            stack.addLast(ch)   // Push opening bracket
        } else {
            // If stack is empty or top doesn't match, it's invalid
            if (stack.isEmpty() || stack.removeLast() != pairs[ch]) {
                return false
            }
        }
    }

    // Valid only if all brackets were matched and closed
    return stack.isEmpty()
}

fun main() {
    println("Enter a string of brackets:")
    val input = readLine()!!

    println("Is valid: ${isValid(input)}")
}
```
<details>
<summary>📤 Output</summary>

```
Enter a string of brackets:
{[()]}
Is valid: true
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(n)

---

## 2. Implement stack using queue

```kotlin
class StackUsingQueue {

    // A single queue is enough to simulate a stack
    private val queue: ArrayDeque<Int> = ArrayDeque()

    fun push(x: Int) {
        queue.addLast(x)   // Add new element at the back

        // Rotate the queue so the new element moves to the front
        // This makes the most recently pushed element come out first (LIFO)
        for (i in 1 until queue.size) {
            queue.addLast(queue.removeFirst())
        }
    }

    fun pop(): Int {
        return queue.removeFirst()   // Front always holds the last-pushed item
    }

    fun top(): Int {
        return queue.first()
    }

    fun isEmpty(): Boolean {
        return queue.isEmpty()
    }
}

fun main() {
    val stack = StackUsingQueue()

    stack.push(1)
    stack.push(2)
    stack.push(3)

    println("Top element = ${stack.top()}")
    println("Popped = ${stack.pop()}")
    println("Top after pop = ${stack.top()}")
}
```
<details>
<summary>📤 Output</summary>

```
Top element = 3
Popped = 3
Top after pop = 2
```
</details>

⏱ Time Complexity: O(n) per push, O(1) per pop 🗂 Space Complexity: O(n)

---

## 3. Next greater element

```kotlin
fun nextGreaterElement(arr: IntArray): IntArray {

    val result = IntArray(arr.size) { -1 }   // Default -1 if no greater element exists
    val stack = ArrayDeque<Int>()             // Stores indices, not values

    for (i in arr.indices) {
        // While current element is greater than the element at stack's top index,
        // we've found the "next greater element" for that index
        while (stack.isNotEmpty() && arr[i] > arr[stack.last()]) {
            val index = stack.removeLast()
            result[index] = arr[i]
        }
        stack.addLast(i)   // Push current index, waiting for its greater element
    }

    return result
}

fun main() {
    val arr = intArrayOf(4, 5, 2, 25)

    val result = nextGreaterElement(arr)
    println("Next Greater Elements: ${result.joinToString()}")
}
```
<details>
<summary>📤 Output</summary>

```
Next Greater Elements: 5, 25, 25, -1
```
</details>

⏱ Time Complexity: O(n) — each element is pushed/popped at most once 🗂 Space Complexity: O(n)

---
