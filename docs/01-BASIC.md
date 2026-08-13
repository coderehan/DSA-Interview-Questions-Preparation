# 🟢 Basic Kotlin Programs

> 30 fundamental Kotlin programs — click **📤 Output** under each program to reveal the sample output.

---

## 1. To print a number entered by the user

```kotlin
fun main() {
    // Ask user to enter a number
    println("Enter a number:")

    // readLine() reads input as String, so convert it to Int
    val number = readLine()!!.toInt()

    // Print the entered number
    println("You entered: $number")
}
```
<details>
<summary>📤 Output</summary>

```
Enter a number:
25
You entered: 25
```
</details>

⏱ Time Complexity: O(1) 🗂 Space Complexity: O(1)

---

## 2. To add two numbers (take inputs from the user)

```kotlin
fun main() {
    // Ask for first number
    println("Enter first number:")
    val num1 = readLine()!!.toInt()

    // Ask for second number
    println("Enter second number:")
    val num2 = readLine()!!.toInt()

    // Add both numbers
    val sum = num1 + num2

    // Print result
    println("Sum = $sum")
}
```
<details>
<summary>📤 Output</summary>

```
Enter first number:
5
Enter second number:
7
Sum = 12
```
</details>

⏱ Time Complexity: O(1) 🗂 Space Complexity: O(1)

---

## 3. To multiply two floating numbers (take input from the user)

```kotlin
fun main() {
    // Ask for first floating number
    println("Enter first decimal number:")
    val num1 = readLine()!!.toDouble()

    // Ask for second floating number
    println("Enter second decimal number:")
    val num2 = readLine()!!.toDouble()

    // Multiply both numbers
    val product = num1 * num2

    // Print result
    println("Product = $product")
}
```
<details>
<summary>📤 Output</summary>

```
Enter first decimal number:
2.5
Enter second decimal number:
4.0
Product = 10.0
```
</details>

⏱ Time Complexity: O(1) 🗂 Space Complexity: O(1)

---

## 4. To find ASCII value of a character (Character should be entered the user)

```kotlin
fun main() {
    // Ask user to enter a character
    println("Enter a character:")

    // Read input and take first character
    val ch = readLine()!![0]

    // Convert character to its ASCII value using .code
    val asciiValue = ch.code

    // Print ASCII value
    println("ASCII value of $ch is $asciiValue")
}
```
<details>
<summary>📤 Output</summary>

```
Enter a character:
A
ASCII value of A is 65
```
</details>

⏱ Time Complexity: O(1) 🗂 Space Complexity: O(1)

---

## 5. To compute quotient and remainder (dividend & divisor should be entered by user)

```kotlin
fun main() {
    // Ask for dividend
    println("Enter dividend:")
    val dividend = readLine()!!.toInt()

    // Ask for divisor
    println("Enter divisor:")
    val divisor = readLine()!!.toInt()

    // Calculate quotient using division operator
    val quotient = dividend / divisor

    // Calculate remainder using modulus operator
    val remainder = dividend % divisor

    // Print results
    println("Quotient = $quotient")
    println("Remainder = $remainder")
}
```
<details>
<summary>📤 Output</summary>

```
Enter dividend:
17
Enter divisor:
5
Quotient = 3
Remainder = 2
```
</details>

⏱ Time Complexity: O(1) 🗂 Space Complexity: O(1)

---

## 6. To swap two numbers (take inputs from the user)

```kotlin
fun main() {
    // Ask user for first number
    println("Enter first number:")
    var num1 = readLine()!!.toInt()

    // Ask user for second number
    println("Enter second number:")
    var num2 = readLine()!!.toInt()

    // Print numbers before swapping
    println("Before Swapping: num1 = $num1, num2 = $num2")

    // Use a temporary variable to swap
    val temp = num1      // Store num1 in temp
    num1 = num2          // Assign num2 to num1
    num2 = temp          // Assign temp (old num1) to num2

    // Print numbers after swapping
    println("After Swapping: num1 = $num1, num2 = $num2")
}
```
<details>
<summary>📤 Output</summary>

```
Enter first number:
3
Enter second number:
9
Before Swapping: num1 = 3, num2 = 9
After Swapping: num1 = 9, num2 = 3
```
</details>

⏱ Time Complexity: O(1) 🗂 Space Complexity: O(1)

---

## 7. To check whether a number is odd or even (take input from the user)

```kotlin
fun main() {
    // Ask user to enter a number
    println("Enter a number:")
    val number = readLine()!!.toInt()

    // Check using modulus operator
    if (number % 2 == 0) {
        println("$number is Even")
    } else {
        println("$number is Odd")
    }
}
```
<details>
<summary>📤 Output</summary>

```
Enter a number:
7
7 is Odd
```
</details>

⏱ Time Complexity: O(1) 🗂 Space Complexity: O(1)

---

## 8. To find the frequency of the character in a string (take input from the user)

```kotlin
fun main() {
    // Ask user to enter a string
    println("Enter a string:")
    val input = readLine()!!

    // Ask user to enter a character
    println("Enter a character to find frequency:")
    val ch = readLine()!![0]

    var count = 0   // Variable to store frequency

    // Loop through each character in string
    for (c in input) {
        if (c == ch) {   // Check if character matches
            count++
        }
    }

    // Print frequency
    println("Frequency of '$ch' = $count")
}
```
<details>
<summary>📤 Output</summary>

```
Enter a string:
programming
Enter a character to find frequency:
g
Frequency of 'g' = 2
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(1)

---

## 9. To remove all whitespaces from the string (take input from the user)

```kotlin
fun main() {
    // Ask user to enter a string
    println("Enter a string:")
    val input = readLine()!!

    // Replace all spaces with empty string
    val result = input.replace(" ", "")

    // Print result
    println("String after removing whitespaces:")
    println(result)
}
```
<details>
<summary>📤 Output</summary>

```
Enter a string:
Hello World Kotlin
String after removing whitespaces:
HelloWorldKotlin
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(n)

---

## 10. To round a number in decimal places (take input from the user)

```kotlin
import kotlin.math.round

fun main() {
    // Ask user to enter a decimal number
    println("Enter a decimal number:")
    val number = readLine()!!.toDouble()

    // Ask user how many decimal places to round
    println("Enter number of decimal places:")
    val places = readLine()!!.toInt()

    // Calculate rounding factor (10^places)
    val factor = Math.pow(10.0, places.toDouble())

    // Round the number
    val rounded = round(number * factor) / factor

    // Print result
    println("Rounded value = $rounded")
}
```
<details>
<summary>📤 Output</summary>

```
Enter a decimal number:
3.14159
Enter number of decimal places:
2
Rounded value = 3.14
```
</details>

⏱ Time Complexity: O(1) 🗂 Space Complexity: O(1)

---

## 11. To check whether an alphabet is vowel or consonant (take inputs from the user)

```kotlin
fun main() {
    // Ask user to enter a character
    println("Enter an alphabet:")
    val ch = readLine()!![0]

    // Convert character to lowercase for easier comparison
    val lowercaseChar = ch.lowercaseChar()

    // Check if character is a vowel
    if (lowercaseChar == 'a' || lowercaseChar == 'e' ||
        lowercaseChar == 'i' || lowercaseChar == 'o' ||
        lowercaseChar == 'u') {

        println("$ch is a Vowel")
    } else {
        println("$ch is a Consonant")
    }
}
```
<details>
<summary>📤 Output</summary>

```
Enter an alphabet:
E
E is a Vowel
```
</details>

⏱ Time Complexity: O(1) 🗂 Space Complexity: O(1)

---

## 12. To find the largest among three numbers (take inputs from the user)

```kotlin
fun main() {
    // Take three numbers as input
    println("Enter first number:")
    val num1 = readLine()!!.toInt()

    println("Enter second number:")
    val num2 = readLine()!!.toInt()

    println("Enter third number:")
    val num3 = readLine()!!.toInt()

    // Assume num1 is largest initially
    var largest = num1

    // Compare with num2
    if (num2 > largest) {
        largest = num2
    }

    // Compare with num3
    if (num3 > largest) {
        largest = num3
    }

    // Print largest number
    println("Largest number is $largest")
}
```
<details>
<summary>📤 Output</summary>

```
Enter first number:
4
Enter second number:
9
Enter third number:
6
Largest number is 9
```
</details>

⏱ Time Complexity: O(1) 🗂 Space Complexity: O(1)

---

## 13. To check a leap year (take input from the user)

> 👉 Rule: Year divisible by 4 AND not divisible by 100, OR divisible by 400.

```kotlin
fun main() {
    // Ask user to enter year
    println("Enter a year:")
    val year = readLine()!!.toInt()

    // Check leap year condition
    if ((year % 4 == 0 && year % 100 != 0) || (year % 400 == 0)) {
        println("$year is a Leap Year")
    } else {
        println("$year is NOT a Leap Year")
    }
}
```
<details>
<summary>📤 Output</summary>

```
Enter a year:
2024
2024 is a Leap Year
```
</details>

⏱ Time Complexity: O(1) 🗂 Space Complexity: O(1)

---

## 14. To check whether a number is positive or negative (take input from the user)

```kotlin
fun main() {
    // Ask user to enter a number
    println("Enter a number:")
    val number = readLine()!!.toInt()

    // Check condition
    if (number > 0) {
        println("$number is Positive")
    } else if (number < 0) {
        println("$number is Negative")
    } else {
        println("Number is Zero")
    }
}
```
<details>
<summary>📤 Output</summary>

```
Enter a number:
-8
-8 is Negative
```
</details>

⏱ Time Complexity: O(1) 🗂 Space Complexity: O(1)

---

## 15. To check whether a character is alphabet or not (take input from the user)

```kotlin
fun main() {
    // Ask user to enter a character
    println("Enter a character:")
    val ch = readLine()!![0]

    // Check if character lies between a-z or A-Z
    if ((ch in 'a'..'z') || (ch in 'A'..'Z')) {
        println("$ch is an Alphabet")
    } else {
        println("$ch is NOT an Alphabet")
    }
}
```
<details>
<summary>📤 Output</summary>

```
Enter a character:
7
7 is NOT an Alphabet
```
</details>

⏱ Time Complexity: O(1) 🗂 Space Complexity: O(1)

---

## 16. To calculate the sum of natural numbers (take inputs from the user)

**Approach 1 — using a loop**

```kotlin
fun main() {
    // Ask user to enter a number
    println("Enter a positive number:")
    val n = readLine()!!.toInt()

    var sum = 0   // Variable to store sum

    // Loop from 1 to n
    for (i in 1..n) {
        sum += i   // Add each number to sum
    }

    // Print result
    println("Sum of first $n natural numbers = $sum")
}
```
<details>
<summary>📤 Output</summary>

```
Enter a positive number:
5
Sum of first 5 natural numbers = 15
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(1)

**Approach 2 — using the direct formula `n(n+1)/2`**

```kotlin
fun main() {
    println("Enter a positive number:")
    val n = readLine()!!.toInt()

    // Formula avoids looping entirely
    val sum = n * (n + 1) / 2
    println("Sum of first $n natural numbers = $sum")
}
```
<details>
<summary>📤 Output</summary>

```
Enter a positive number:
1000000
Sum of first 1000000 natural numbers = 500000500000
```
</details>

> 🎯 **Interview tip:** The formula `n(n+1)/2` runs in **O(1)**, while the loop takes **O(n)** — for large `n` the formula is far more optimized.

⏱ Time Complexity: O(1) 🗂 Space Complexity: O(1)

---

## 17. To find the factorial of a number (take inputs from the user)

> 👉 Factorial of n = n × (n-1) × (n-2) × ... × 1

```kotlin
fun main() {
    // Ask user to enter a number
    println("Enter a number:")
    val n = readLine()!!.toInt()

    var factorial = 1L  // Use Long to handle larger numbers

    // Loop from 1 to n
    for (i in 1..n) {
        factorial *= i   // Multiply each number
    }

    // Print result
    println("Factorial of $n = $factorial")
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

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(1)

---

## 18. To display fibonacci series (take inputs from the user)

> 👉 Fibonacci series: 0, 1, 1, 2, 3, 5, 8, 13, ...

```kotlin
fun main() {
    // Ask user how many terms to print
    println("Enter number of terms:")
    val n = readLine()!!.toInt()

    var first = 0
    var second = 1

    println("Fibonacci Series:")

    for (i in 1..n) {

        print("$first ")

        // Calculate next term
        val next = first + second

        // Update values
        first = second
        second = next
    }
}
```
<details>
<summary>📤 Output</summary>

```
Enter number of terms:
6
Fibonacci Series:
0 1 1 2 3 5 
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(1)

---

## 19. To find GCD of two numbers (take inputs from the user)

> 👉 Using the Euclidean Algorithm

```kotlin
fun main() {
    // Ask user to enter two numbers
    println("Enter first number:")
    var a = readLine()!!.toInt()

    println("Enter second number:")
    var b = readLine()!!.toInt()

    // Euclidean Algorithm
    while (b != 0) {
        val temp = b
        b = a % b
        a = temp
    }

    // 'a' contains GCD
    println("GCD = $a")
}
```
<details>
<summary>📤 Output</summary>

```
Enter first number:
36
Enter second number:
60
GCD = 12
```
</details>

⏱ Time Complexity: O(log(min(a,b))) 🗂 Space Complexity: O(1)

---

## 20. To find LCM of two numbers (take inputs from the user)

> 👉 Formula: LCM(a, b) = (a × b) / GCD(a, b)

```kotlin
fun main() {
    // Take two numbers
    println("Enter first number:")
    val num1 = readLine()!!.toInt()

    println("Enter second number:")
    val num2 = readLine()!!.toInt()

    var a = num1
    var b = num2

    // Find GCD first
    while (b != 0) {
        val temp = b
        b = a % b
        a = temp
    }

    val gcd = a

    // Calculate LCM
    val lcm = (num1 * num2) / gcd

    println("LCM = $lcm")
}
```
<details>
<summary>📤 Output</summary>

```
Enter first number:
4
Enter second number:
6
LCM = 12
```
</details>

⏱ Time Complexity: O(log(min(a,b))) 🗂 Space Complexity: O(1)

---

## 21. To display characters from A to Z using loop

```kotlin
fun main() {
    // Loop from 'A' to 'Z'
    for (ch in 'A'..'Z') {

        // Print each character
        print("$ch ")
    }
}
```
<details>
<summary>📤 Output</summary>

```
A B C D E F G H I J K L M N O P Q R S T U V W X Y Z 
```
</details>

⏱ Time Complexity: O(1) (always 26 iterations — constant) 🗂 Space Complexity: O(1)

---

## 22. To reverse a number (take input from the user)

> Example: Input → 1234, Output → 4321

```kotlin
fun main() {
    // Ask user to enter a number
    println("Enter a number:")
    var number = readLine()!!.toInt()

    var reversed = 0   // Variable to store reversed number

    // Loop until number becomes 0
    while (number != 0) {

        val digit = number % 10   // Get last digit
        reversed = reversed * 10 + digit  // Build reversed number
        number /= 10   // Remove last digit
    }

    println("Reversed number = $reversed")
}
```
<details>
<summary>📤 Output</summary>

```
Enter a number:
1234
Reversed number = 4321
```
</details>

⏱ Time Complexity: O(d) — d = number of digits 🗂 Space Complexity: O(1)

---

## 23. To calculate the power of a number (take input from the user)

> Example: 2^3 = 8

```kotlin
fun main() {
    // Ask user for base
    println("Enter base:")
    val base = readLine()!!.toInt()

    // Ask user for exponent
    println("Enter exponent:")
    val exponent = readLine()!!.toInt()

    var result = 1

    // Multiply base exponent times
    for (i in 1..exponent) {
        result *= base
    }

    println("$base raised to $exponent = $result")
}
```
<details>
<summary>📤 Output</summary>

```
Enter base:
2
Enter exponent:
3
2 raised to 3 = 8
```
</details>

⏱ Time Complexity: O(n) — n = exponent 🗂 Space Complexity: O(1)

---

## 24. To check whether a number is palindrome or not (take input from the user)

> 👉 A palindrome reads the same forward and backward. Example: 121 → Palindrome

```kotlin
fun main() {
    // Ask user to enter number
    println("Enter a number:")
    var number = readLine()!!.toInt()

    val original = number   // Store original number
    var reversed = 0

    // Reverse the number
    while (number != 0) {

        val digit = number % 10
        reversed = reversed * 10 + digit
        number /= 10
    }

    // Compare original and reversed
    if (original == reversed) {
        println("$original is a Palindrome")
    } else {
        println("$original is NOT a Palindrome")
    }
}
```
<details>
<summary>📤 Output</summary>

```
Enter a number:
121
121 is a Palindrome
```
</details>

⏱ Time Complexity: O(d) 🗂 Space Complexity: O(1)

---

## 25. To check whether a number is prime or not (take inputs from the user)

> 👉 A prime number is divisible only by 1 and itself

```kotlin
fun main() {
    // Ask user to enter number
    println("Enter a number:")
    val number = readLine()!!.toInt()

    var isPrime = true

    // 0 and 1 are not prime
    if (number <= 1) {
        isPrime = false
    } else {

        // Check divisibility from 2 to number/2
        for (i in 2..number / 2) {

            if (number % i == 0) {
                isPrime = false
                break
            }
        }
    }

    // Print result
    if (isPrime) {
        println("$number is a Prime number")
    } else {
        println("$number is NOT a Prime number")
    }
}
```
<details>
<summary>📤 Output</summary>

```
Enter a number:
17
17 is a Prime number
```
</details>

⏱ Time Complexity: O(n) — can be optimized to O(√n) 🗂 Space Complexity: O(1)

---

## 26. To check armstrong number (take input from the user)

> 👉 A number is Armstrong if the sum of (each digit ^ total digits) = the original number.
> Example: 153 = 1³ + 5³ + 3³ = 153 ✅

```kotlin
fun main() {
    // Ask user to enter number
    println("Enter a number:")
    var number = readLine()!!.toInt()

    val original = number
    var result = 0

    // Count number of digits
    val digits = original.toString().length

    // Loop through each digit
    while (number != 0) {

        val digit = number % 10

        // Raise digit to power of number of digits
        result += Math.pow(digit.toDouble(), digits.toDouble()).toInt()

        number /= 10
    }

    // Check if Armstrong
    if (original == result) {
        println("$original is an Armstrong number")
    } else {
        println("$original is NOT an Armstrong number")
    }
}
```
<details>
<summary>📤 Output</summary>

```
Enter a number:
153
153 is an Armstrong number
```
</details>

⏱ Time Complexity: O(d) 🗂 Space Complexity: O(1)

---

## 27. To make a simple calculator using switch case (take inputs from the user)

```kotlin
fun main() {

    println("Enter first number:")
    val num1 = readLine()!!.toDouble()

    println("Enter operator (+, -, *, /):")
    val operator = readLine()!!

    println("Enter second number:")
    val num2 = readLine()!!.toDouble()

    var result: Double? = null

    // 'when' works like switch
    result = when (operator) {
        "+" -> num1 + num2
        "-" -> num1 - num2
        "*" -> num1 * num2
        "/" -> num1 / num2
        else -> {
            println("Invalid Operator")
            null
        }
    }

    // Print result if valid
    if (result != null) {
        println("Result = $result")
    }
}
```
<details>
<summary>📤 Output</summary>

```
Enter first number:
10
Enter operator (+, -, *, /):
*
Enter second number:
5
Result = 50.0
```
</details>

⏱ Time Complexity: O(1) 🗂 Space Complexity: O(1)

---

## 28. To find the largest element in the array (take inputs from the user)

```kotlin
fun main() {

    println("Enter size of array:")
    val size = readLine()!!.toInt()

    val arr = IntArray(size)

    // Take array elements
    println("Enter elements:")
    for (i in 0 until size) {
        arr[i] = readLine()!!.toInt()
    }

    var largest = arr[0]

    // Traverse array
    for (i in 1 until size) {
        if (arr[i] > largest) {
            largest = arr[i]
        }
    }

    println("Largest element = $largest")
}
```
<details>
<summary>📤 Output</summary>

```
Enter size of array:
4
Enter elements:
3
9
1
7
Largest element = 9
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(n)

---

## 29. To find sum of natural numbers using recursion (take inputs from the user)

```kotlin
fun sum(n: Int): Int {

    // Base case
    if (n == 0)
        return 0

    // Recursive call
    return n + sum(n - 1)
}

fun main() {

    println("Enter a number:")
    val n = readLine()!!.toInt()

    val result = sum(n)

    println("Sum of first $n natural numbers = $result")
}
```
<details>
<summary>📤 Output</summary>

```
Enter a number:
5
Sum of first 5 natural numbers = 15
```
</details>

⏱ Time Complexity: O(n) 🗂 Space Complexity: O(n) — recursive call stack

---

## 30. To reverse a sentence using recursion (take inputs from the user)

```kotlin
fun reverseString(str: String) {

    // Base case
    if (str.isEmpty())
        return

    // Recursive call with substring from index 1
    reverseString(str.substring(1))

    // Print first character after recursion unwinds
    print(str[0])
}

fun main() {

    println("Enter a sentence:")
    val input = readLine()!!

    println("Reversed sentence:")
    reverseString(input)
}
```
<details>
<summary>📤 Output</summary>

```
Enter a sentence:
Hello Kotlin
Reversed sentence:
niltoK olleH
```
</details>

⏱ Time Complexity: O(n²) — substring creates a new string each call 🗂 Space Complexity: O(n) — recursive call stack

---
