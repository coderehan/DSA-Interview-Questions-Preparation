# 🔗 Linked List — DSA Questions

> Click **📤 Output** under each program to reveal the sample output.

---

## 1. Reverse a linked list

```kotlin
// Node class represents a single element of the linked list
class Node(val value: Int) {
    var next: Node? = null
}

fun reverseList(head: Node?): Node? {
    var prev: Node? = null   // Will become the new head
    var current = head

    // Traverse the list, flipping each 'next' pointer as we go
    while (current != null) {
        val nextNode = current.next  // Save next node before overwriting
        current.next = prev          // Reverse the pointer
        prev = current                // Move prev forward
        current = nextNode            // Move current forward
    }

    return prev   // prev is now the new head of the reversed list
}

fun printList(head: Node?) {
    var current = head
    while (current != null) {
        print("${current.value} -> ")
        current = current.next
    }
    println("null")
}

fun main() {
    // Build list: 1 -> 2 -> 3 -> 4 -> null
    val head = Node(1)
    head.next = Node(2)
    head.next!!.next = Node(3)
    head.next!!.next!!.next = Node(4)

    println("Original list:")
    printList(head)

    val reversedHead = reverseList(head)

    println("Reversed list:")
    printList(reversedHead)
}
```
<details>
<summary>📤 Output</summary>

```
Original list:
1 -> 2 -> 3 -> 4 -> null
Reversed list:
4 -> 3 -> 2 -> 1 -> null
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(1)

---

## 2. Find middle element

```kotlin
class Node(val value: Int) {
    var next: Node? = null
}

fun findMiddle(head: Node?): Node? {
    // Slow pointer moves 1 step, fast pointer moves 2 steps
    var slow = head
    var fast = head

    // When fast reaches the end, slow will be at the middle
    while (fast != null && fast.next != null) {
        slow = slow!!.next
        fast = fast.next!!.next
    }

    return slow
}

fun main() {
    // Build list: 1 -> 2 -> 3 -> 4 -> 5 -> null
    val head = Node(1)
    head.next = Node(2)
    head.next!!.next = Node(3)
    head.next!!.next!!.next = Node(4)
    head.next!!.next!!.next!!.next = Node(5)

    val middle = findMiddle(head)
    println("Middle element = ${middle?.value}")
}
```
<details>
<summary>📤 Output</summary>

```
Middle element = 3
```
</details>

⏱ Time Complexity: O(n) — Slow/Fast pointer technique 🗂 Space Complexity: O(1)

---

## 3. Detect cycle

```kotlin
class Node(val value: Int) {
    var next: Node? = null
}

fun hasCycle(head: Node?): Boolean {
    // Floyd's Cycle Detection (Tortoise & Hare)
    var slow = head
    var fast = head

    while (fast != null && fast.next != null) {
        slow = slow!!.next        // Moves 1 step
        fast = fast.next!!.next   // Moves 2 steps

        // If they ever meet, there's a cycle
        if (slow === fast) {
            return true
        }
    }

    return false   // fast reached null -> no cycle
}

fun main() {
    // Build list: 1 -> 2 -> 3 -> 4 -> (back to 2, cycle!)
    val head = Node(1)
    val second = Node(2)
    val third = Node(3)
    val fourth = Node(4)

    head.next = second
    second.next = third
    third.next = fourth
    fourth.next = second   // Creates a cycle

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

## 4. Merge two sorted lists

```kotlin
class Node(val value: Int) {
    var next: Node? = null
}

fun mergeSortedLists(l1: Node?, l2: Node?): Node? {
    // Dummy node simplifies handling of the head
    val dummy = Node(-1)
    var tail = dummy

    var first = l1
    var second = l2

    // Pick the smaller value at each step and attach it
    while (first != null && second != null) {
        if (first.value <= second.value) {
            tail.next = first
            first = first.next
        } else {
            tail.next = second
            second = second.next
        }
        tail = tail.next!!
    }

    // Attach whichever list still has remaining nodes
    tail.next = first ?: second

    return dummy.next   // Skip the dummy node
}

fun printList(head: Node?) {
    var current = head
    while (current != null) {
        print("${current.value} -> ")
        current = current.next
    }
    println("null")
}

fun main() {
    // List 1: 1 -> 3 -> 5
    val l1 = Node(1)
    l1.next = Node(3)
    l1.next!!.next = Node(5)

    // List 2: 2 -> 4 -> 6
    val l2 = Node(2)
    l2.next = Node(4)
    l2.next!!.next = Node(6)

    val merged = mergeSortedLists(l1, l2)
    println("Merged list:")
    printList(merged)
}
```
<details>
<summary>📤 Output</summary>

```
Merged list:
1 -> 2 -> 3 -> 4 -> 5 -> 6 -> null
```
</details>

⏱ Time Complexity: O(n + m) 🗂 Space Complexity: O(1)

---
