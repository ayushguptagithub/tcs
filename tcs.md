Sure! Here's the **Markdown (`.md`) file** with the question and both Java and Python solutions. You can **copy and paste** this directly into your file.

---

### **Markdown File (`painting_cost.md`)**

```md
# Estimate the Cost of Painting a Property

## Problem Statement
We want to estimate the cost of painting a property.  

- The **interior wall painting** cost is **Rs.18 per sq.ft.**  
- The **exterior wall painting** cost is **Rs.12 per sq.ft.**  
- The program should take the following inputs:
  1. Number of interior walls  
  2. Number of exterior walls  
  3. Surface area of each interior wall (in square feet)  
  4. Surface area of each exterior wall (in square feet)  
- If the user enters **zero (0)** as the number of walls, **skip** taking input for the surface areas.
- The program should then calculate and display the **total cost** of painting the property.

### **Example Input/Output**
#### **Input**
```

6
3
12.3
15.2
12.3
15.2
12.3
15.2
10.10
10.10
10.00

```
#### **Output**
```

Total estimated Cost : 1847.4 INR

```

---

## **Java Implementation**
```java
import java.util.Scanner;

public class PaintingCostEstimator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
  
        // Constants for cost per square foot
        final double INTERIOR_COST = 18.0;
        final double EXTERIOR_COST = 12.0;
  
        // Taking input for number of walls
        int numInteriorWalls = scanner.nextInt();
        int numExteriorWalls = scanner.nextInt();
  
        double totalInteriorArea = 0.0, totalExteriorArea = 0.0;
  
        // Taking input for interior wall areas
        for (int i = 0; i < numInteriorWalls; i++) {
            totalInteriorArea += scanner.nextDouble();
        }
  
        // Taking input for exterior wall areas
        for (int i = 0; i < numExteriorWalls; i++) {
            totalExteriorArea += scanner.nextDouble();
        }
  
        // Calculate total cost
        double totalCost = (totalInteriorArea * INTERIOR_COST) + (totalExteriorArea * EXTERIOR_COST);
  
        // Display result
        System.out.printf("Total estimated Cost : %.1f INR\n", totalCost);
  
        scanner.close();
    }
}
```

---

## **Python Implementation**

```python
# Constants for cost per square foot
INTERIOR_COST = 18.0
EXTERIOR_COST = 12.0

# Taking input for number of walls
num_interior_walls = int(input())
num_exterior_walls = int(input())

total_interior_area = 0.0
total_exterior_area = 0.0

# Taking input for interior wall areas
for _ in range(num_interior_walls):
    total_interior_area += float(input())

# Taking input for exterior wall areas
for _ in range(num_exterior_walls):
    total_exterior_area += float(input())

# Calculate total cost
total_cost = (total_interior_area * INTERIOR_COST) + (total_exterior_area * EXTERIOR_COST)

# Display result
print(f"Total estimated Cost : {total_cost:.1f} INR")
```

---

### **How to Run**

#### **Java**

1. Copy and save the Java code in a file named `PaintingCostEstimator.java`.
2. Compile and run using:
   ```sh
   javac PaintingCostEstimator.java
   java PaintingCostEstimator
   ```
3. Provide input as per the format.

#### **Python**

1. Copy and save the Python code in a file named `painting_cost.py`.
2. Run using:
   ```sh
   python painting_cost.py
   ```
3. Provide input as per the format.

### **Markdown File (`string_game.md`)**

```md
# Jack and Jill's String Game

## Problem Statement
Jack and Jill are playing a string game.  
Jack has given Jill **two strings**: `A` and `B`.  
Jill has to derive a **new string C** from `A` by **removing all characters** from `A` that are present in `B`.  

### **Input Format**
- The first line contains string `A`.  
- The second line contains string `B`.  

### **Output Format**
- Print the resulting string `C` after removing characters of `B` from `A`.

---

### **Example 1**
#### **Input**
```

tiger
ti

```
#### **Output**
```

ger

```
#### **Explanation**
- Removing `"t"` and `"i"` from `"tiger"` results in `"ger"`.

---

### **Example 2**
#### **Input**
```

processed
esd

```
#### **Output**
```

proc

```
#### **Explanation**
- Removing `"e"`, `"s"`, and `"d"` from `"processed"` results in `"proc"`.

---

## **Java Implementation (Using Normal `for` Loop)**
```java
import java.util.Scanner;

public class StringGame {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String A = sc.nextLine();
        String B = sc.nextLine();
        sc.close();
  
        StringBuilder result = new StringBuilder();
  
        // Iterate through each character of A using a normal for loop
        for (int i = 0; i < A.length(); i++) {
            char ch = A.charAt(i);
            boolean found = false;
      
            // Check if the character exists in B
            for (int j = 0; j < B.length(); j++) {
                if (ch == B.charAt(j)) {
                    found = true;
                    break;
                }
            }
      
            // If character is not in B, add to result
            if (!found) {
                result.append(ch);
            }
        }
  
        System.out.println(result.toString());
    }
}
```

---

## **Python Implementation (Without Built-in Replace)**

```python
A = input()
B = input()

result = ""

# Check each character of A, if not in B, add to result
for i in range(len(A)):
    found = False
    for j in range(len(B)):
        if A[i] == B[j]:
            found = True
            break
    if not found:
        result += A[i]

print(result)
```

---

### **How to Run**

#### **Java**

1. Save the Java code in a file named `StringGame.java`.
2. Compile and run using:
   ```sh
   javac StringGame.java
   java StringGame
   ```
3. Provide input as per the format.

#### **Python**

1. Save the Python code in a file named `string_game.py`.
2. Run using:
   ```sh
   python string_game.py
   ```
3. Provide input as per the format.

### **Markdown File (`strong_number.md`)**

```md
# Strong Number Check

## Problem Statement
Write a program to check whether the given number is **strong** or not.

### **Definition**
A number is said to be **strong** if the **sum of the factorial of its digits** is equal to the original number.

### **Example**
#### **Input 1**
```

145

```
#### **Output 1**
```

Yes

```
#### **Explanation**
- 1! + 4! + 5! = 1 + 24 + 120 = 145  
- Since the sum equals the original number, **145 is a strong number**.

---

#### **Input 2**
```

123

```
#### **Output 2**
```

No

```
#### **Explanation**
- 1! + 2! + 3! = 1 + 2 + 6 = 9  
- Since 9 is **not equal** to 123, **123 is not a strong number**.

---

## **Java Implementation (Without Built-in Factorial Function)**
```java
import java.util.Scanner;

public class StrongNumber {
    // Function to compute factorial
    public static int factorial(int num) {
        int fact = 1;
        for (int i = 1; i <= num; i++) {
            fact *= i;
        }
        return fact;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        sc.close();
  
        int original = n;
        int sum = 0;

        while (n > 0) {
            int digit = n % 10; // Extract last digit
            sum += factorial(digit); // Compute factorial and add to sum
            n /= 10; // Remove last digit
        }

        if (sum == original) {
            System.out.println("Yes");
        } else {
            System.out.println("No");
        }
    }
}
```

---

## **Python Implementation (Without Built-in Factorial Function)**

```python
def factorial(num):
    fact = 1
    for i in range(1, num + 1):
        fact *= i
    return fact

n = int(input())
original = n
sum_of_factorials = 0

while n > 0:
    digit = n % 10  # Extract last digit
    sum_of_factorials += factorial(digit)  # Compute factorial and add to sum
    n //= 10  # Remove last digit

if sum_of_factorials == original:
    print("Yes")
else:
    print("No")
```

---

### **How to Run**

#### **Java**

1. Save the Java code in a file named `StrongNumber.java`.
2. Compile and run using:
   ```sh
   javac StrongNumber.java
   java StrongNumber
   ```
3. Provide input as per the format.

#### **Python**

1. Save the Python code in a file named `strong_number.py`.
2. Run using:
   ```sh
   python strong_number.py
   ```
3. Provide input as per the format.

### **Markdown File (`game_rewards.md`)**

```md
# Maximizing Reward Points in Alice's Game

## Problem Statement
Alice has introduced a new **online game** with `N` levels (1 to `N`).  
Each day, Alice will **launch one level**, but the order is **random** and not necessarily increasing.  
- A level **cannot be launched twice**.  
- Players can only play **higher levels** than the ones they have completed.  
- A player **earns one reward point** for each level they complete.  

You, being the best gamer, want to **maximize your reward points** by playing as many levels as possible.  
Your goal is to determine **the maximum reward points you can earn** based on the launch order.

---

## **Input Format**
1. The first line contains an integer `N` (total levels).
2. The second line contains `N` space-separated integers, representing the **order in which levels are launched**.

---

## **Output Format**
- Print **maximum reward points** the player can earn.

---

## **Example 1**
#### **Input**
```

5
2 1 3 4 5

```
#### **Output**
```

4

```
#### **Explanation**
- Levels launched in order: **[2, 1, 3, 4, 5]**
- The player **waits until level 1 is launched**, then plays **levels 1, 3, 4, and 5**.
- **Maximum levels completed: 4**
- **Total reward points = 4**

---

## **Approach**
- Track the **highest level completed** so far.
- Try playing only the **next increasing level** in order.

---

## **Java Implementation (Using Simple Loop)**
```java
import java.util.Scanner;

public class GameRewards {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int N = sc.nextInt();  // Total levels
        int[] levels = new int[N];
  
        for (int i = 0; i < N; i++) {
            levels[i] = sc.nextInt();  // Reading the launch order
        }
  
        sc.close();

        int maxRewards = 0;
        int lastPlayed = 0; // Last highest level played
  
        for (int i = 0; i < N; i++) {
            if (levels[i] == lastPlayed + 1) {  // Play only if it's the next required level
                maxRewards++;
                lastPlayed = levels[i];
            }
        }

        System.out.println(maxRewards);
    }
}
```

---

## **Python Implementation (Without Built-in Methods)**

```python
N = int(input())  # Number of levels
levels = []  

# Read input without using built-in methods like map()
for i in range(N):
    levels.append(int(input()))  # Reading each level separately

max_rewards = 0
last_played = 0  # Last highest level played

for i in range(N):
    if levels[i] == last_played + 1:  # Play only if it's the next required level
        max_rewards += 1
        last_played = levels[i]

print(max_rewards)
```

---

### **How to Run**

#### **Java**

1. Save the Java code in a file named `GameRewards.java`.
2. Compile and run using:
   ```sh
   javac GameRewards.java
   java GameRewards
   ```
3. Provide input as per the format.

#### **Python**

1. Save the Python code in a file named `game_rewards.py`.
2. Run using:
   ```sh
   python game_rewards.py
   ```
3. Provide input as per the format.

### **Markdown File (`zero_padding.md`)**

```md
# To Zero or Not Zero

## **Problem Statement**
Given two positive integers **m** and **n** (`m < n; 0 < m < 999; 1 < n <= 999`), print numbers from **m to n** while ensuring that each number has **leading zeros** to match the width of `n`.

---

## **Input Format**
- Two space-separated integers **m** and **n**.

---

## **Output Format**
- Print numbers from **m to n**, ensuring they all have the **same width as `n`** by adding **leading zeros** where necessary.

---

## **Example 1**
#### **Input**
```

5 10

```
#### **Output**
```

05 06 07 08 09 10

```

---

## **Example 2**
#### **Input**
```

9 100

```
#### **Output**
```

009 010 011 012 ... 099 100

```

---

## **Approach**
- Find the **total number of digits in `n`** (to determine the required width).
- Print each number from `m` to `n` with **leading zeros** until it matches the width of `n`.

---

## **Java Implementation (Using Simple Loops)**
```java
import java.util.Scanner;

public class ZeroPadding {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int m = sc.nextInt();
        int n = sc.nextInt();
        sc.close();

        // Find the number of digits in n
        int width = 0, temp = n;
        while (temp > 0) {
            width++;
            temp /= 10;
        }

        // Print numbers with leading zeros
        for (int i = m; i <= n; i++) {
            int numDigits = 0, temp2 = i;
            while (temp2 > 0) {
                numDigits++;
                temp2 /= 10;
            }

            // Print leading zeros
            for (int j = 0; j < (width - numDigits); j++) {
                System.out.print("0");
            }

            // Print actual number
            System.out.print(i + " ");
        }
    }
}
```

---

## **Python Implementation (Without Built-in Methods)**

```python
# Read input values
m, n = input().split()
m = int(m)
n = int(n)

# Find the width of the number n
temp = n
width = 0
while temp > 0:
    width += 1
    temp //= 10

# Print numbers from m to n with proper zero-padding
for num in range(m, n + 1):
    temp2 = num
    num_digits = 0
  
    # Count digits in num
    while temp2 > 0:
        num_digits += 1
        temp2 //= 10

    # Print leading zeros
    for _ in range(width - num_digits):
        print("0", end="")

    # Print the actual number
    print(num, end=" ")
```

---

## **How to Run**

#### **Java**

1. Save the Java code in a file named `ZeroPadding.java`.
2. Compile and run using:
   ```sh
   javac ZeroPadding.java
   java ZeroPadding
   ```
3. Provide input as per the format.

#### **Python**

1. Save the Python code in a file named `zero_padding.py`.
2. Run using:
   ```sh
   python zero_padding.py
   ```
3. Provide input as per the format.

### **Markdown File (`oddly_even.md`)**

```md
# Oddly Even

## **Problem Statement**
Given a number with a **maximum of 100 digits**, find the **absolute difference** between:
- The sum of digits at **odd positions** (1st, 3rd, 5th, etc.).
- The sum of digits at **even positions** (2nd, 4th, 6th, etc.).

---

## **Input Format**
- A single number with **up to 100 digits**.

---

## **Output Format**
- Print the **absolute difference** between the sum of odd-positioned and even-positioned digits.

---

## **Example 1**
#### **Input**
```

4567

```
#### **Output**
```

2

```
#### **Explanation**
- Odd position digits: **4, 6** → Sum = **10**
- Even position digits: **5, 7** → Sum = **12**
- Absolute difference: **|12 - 10| = 2**

---

## **Example 2**
#### **Input**
```

9834698765123

```
#### **Output**
```

1

```
#### **Explanation**
- Odd position digits: **9, 3, 6, 8, 6, 1, 3** → Sum = **36**
- Even position digits: **8, 4, 9, 7, 5, 2** → Sum = **35**
- Absolute difference: **|36 - 35| = 1**

---

## **Approach**
1. **Read the number as a string** (since it can have up to **100 digits**).
2. **Iterate through each digit**:
   - If **position is odd**, add to `sumOdd`.
   - If **position is even**, add to `sumEven`.
3. **Compute absolute difference** between `sumOdd` and `sumEven`.

---

## **Java Implementation (Using Simple Loops)**
```java
import java.util.Scanner;

public class OddlyEven {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String number = sc.next();
        sc.close();

        int sumOdd = 0, sumEven = 0;

        // Loop through the number's digits
        for (int i = 0; i < number.length(); i++) {
            int digit = number.charAt(i) - '0'; // Convert char to int
      
            if ((i + 1) % 2 == 1) { // Odd position
                sumOdd += digit;
            } else { // Even position
                sumEven += digit;
            }
        }

        // Print the absolute difference
        System.out.println(Math.abs(sumOdd - sumEven));
    }
}
```

---

## **Python Implementation (Without Built-in Methods)**

```python
# Read input number as a string
number = input().strip()

sum_odd = 0
sum_even = 0

# Loop through each digit
for i in range(len(number)):
    digit = ord(number[i]) - ord('0')  # Convert character to integer

    if (i + 1) % 2 == 1:  # Odd position
        sum_odd += digit
    else:  # Even position
        sum_even += digit

# Print the absolute difference
print(abs(sum_odd - sum_even))
```

---

## **How to Run**

#### **Java**

1. Save the Java code in a file named `OddlyEven.java`.
2. Compile and run using:
   ```sh
   javac OddlyEven.java
   java OddlyEven
   ```
3. Provide input as per the format.

#### **Python**

1. Save the Python code in a file named `oddly_even.py`.
2. Run using:
   ```sh
   python oddly_even.py
   ```
3. Provide input as per the format.

### **Markdown File (`minting_mints.md`)**

```md
# Minting Mints

## **Problem Statement**
A long queue of boys and girls is standing to buy provisions from a fair-price shop. Each child in the queue has a certain number of **mints**, following this pattern:

- The **first kid** has `n` mints.
- Every other kid in the queue has **one less than the sum of all the mints of kids before them**.

Given:
- `n`: The number of **mints** with the first kid (`2 < n < 10`).
- `len`: The **total number of kids in the queue** (`1 < len < 20`).

Write a program to **calculate the total number of mints** possessed by all the kids.

---

## **Input Format**
- Two space-separated integers:  
  - `n` → **Mints with the first kid**  
  - `len` → **Total number of kids in the queue**  

---

## **Output Format**
- A single integer representing the **total mints** possessed by all the kids.

---

## **Example 1**
#### **Input**
```

4 2

```
#### **Output**
```

7

```
#### **Explanation**
- Kid 1: **4** mints  
- Kid 2: **(4) - 1 = 3** mints  
- **Total: 4 + 3 = 7**

---

## **Example 2**
#### **Input**
```

4 3

```
#### **Output**
```

13

```
#### **Explanation**
- Kid 1: **4** mints  
- Kid 2: **(4) - 1 = 3** mints  
- Kid 3: **(4 + 3) - 1 = 6** mints  
- **Total: 4 + 3 + 6 = 13**

---

## **Approach**
1. **Start with the first kid** having `n` mints.
2. **For each subsequent kid**, compute the number of mints:
   - `mints[i] = (sum of all previous mints) - 1`
3. **Sum up all the mints**.

---

## **Java Implementation (Using Simple Loops)**
```java
import java.util.Scanner;

public class MintingMints {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();  // Mints with the first kid
        int len = sc.nextInt(); // Total number of kids
        sc.close();

        int totalMints = n; // First kid's mints
        int previousSum = n; // Sum of previous kids' mints

        for (int i = 1; i < len; i++) {
            int currentMints = previousSum - 1; // Rule: Sum of previous - 1
            totalMints += currentMints;
            previousSum += currentMints; // Update sum of previous kids
        }

        System.out.println(totalMints);
    }
}
```

---

## **Python Implementation (Without Built-in Methods)**

```python
# Read input values
n, length = map(int, input().split())

total_mints = n  # First kid's mints
previous_sum = n  # Sum of previous kids' mints

# Calculate mints for each kid in the queue
for i in range(1, length):
    current_mints = previous_sum - 1  # Rule: Sum of previous - 1
    total_mints += current_mints
    previous_sum += current_mints  # Update sum of previous kids

# Print total mints
print(total_mints)
```

---

## **How to Run**

#### **Java**

1. Save the Java code in a file named `MintingMints.java`.
2. Compile and run using:
   ```sh
   javac MintingMints.java
   java MintingMints
   ```
3. Provide input as per the format.

#### **Python**

1. Save the Python code in a file named `minting_mints.py`.
2. Run using:
   ```sh
   python minting_mints.py
   ```
3. Provide input as per the format.

### **Markdown File (`palindrome_check.md`)**

```md
# Palindrome Check

## **Problem Statement**
Write a function `isPalindrome` to check whether the given string `inputStr` is a **palindrome** or not.

A string is a **palindrome** if it reads the same **forward and backward**.

- The function should **return `1`** if the string is a palindrome, **otherwise return `0`**.
- **Case-sensitive check** (uppercase and lowercase letters are treated differently).
- **No extra array should be used**.
- The function should **not modify the input string**.

---

## **Example Cases**
#### **Example 1**
##### **Input**
```python
isPalindrome("DEED", 4)
```

##### **Output**

```
1
```

---

#### **Example 2**

##### **Input**

```python
isPalindrome("383", 3)
```

##### **Output**

```
1
```

---

#### **Example 3**

##### **Input**

```python
isPalindrome("Hello", 5)
```

##### **Output**

```
0
```

---

#### **Example 4**

##### **Input**

```python
isPalindrome("DeED", 4)
```

##### **Output**

```
0
```

##### **Python Implementation**

```python
def isPalindrome(inputStr, length):
    left, right = 0, length - 1

    while left < right:
        if inputStr[left] != inputStr[right]:
            return 0  # Not a palindrome
        left += 1
        right -= 1

    return 1  # It's a palindrome

# Test cases
print(isPalindrome("DEED", 4))   # Output: 1
print(isPalindrome("383", 3))    # Output: 1
print(isPalindrome("Hello", 5))  # Output: 0
print(isPalindrome("DeED", 4))   # Output: 0
```

---

## **Java Implementation**

```java
public class PalindromeCheck {
    public static int isPalindrome(String inputStr, int length) {
        int left = 0, right = length - 1;

        while (left < right) {
            if (inputStr.charAt(left) != inputStr.charAt(right)) {
                return 0; // Not a palindrome
            }
            left++;
            right--;
        }

        return 1; // It's a palindrome
    }

    public static void main(String[] args) {
        // Test cases
        System.out.println(isPalindrome("DEED", 4));   // Output: 1
        System.out.println(isPalindrome("383", 3));    // Output: 1
        System.out.println(isPalindrome("Hello", 5));  // Output: 0
        System.out.println(isPalindrome("DeED", 4));   // Output: 0
    }
}
```

---

## **How to Run**

### **Python**

1. Save the code in a file `palindrome_check.py`.
2. Run:
   ```sh
   python palindrome_check.py
   ```

### **Java**

1. Save the code in a file `PalindromeCheck.java`.
2. Compile and run:
   ```sh
   javac PalindromeCheck.java
   java PalindromeCheck
   ```

### **Markdown File (`magic_function.md`)**

```md
# Magic Function

## **Problem Statement**
Write a function `int magic(int x, int n)` that takes two **positive integers** `x` and `n` as arguments, where:
- `x >= 0`
- `n` is an **integer between 0 and 9**.

The function should return a new number **y**, which is generated by **adding `n` to each digit** in `x` using **modulo 10 arithmetic**.

For each digit `d` in `x`, the corresponding digit `d'` in `y` will be:
```

d' = (d + n) % 10

```

---

## **Example Cases**
#### **Example 1**
##### **Input**
```python
magic(328, 3)
```

##### **Output**

```
651
```

##### **Explanation**

```
3 → (3+3) % 10 = 6
2 → (2+3) % 10 = 5
8 → (8+3) % 10 = 1
Result: 651
```

---

#### **Example 2**

##### **Input**

```python
magic(2075, 5)
```

##### **Output**

```
7520
```

##### **Explanation**

```
2 → (2+5) % 10 = 7
0 → (0+5) % 10 = 5
7 → (7+5) % 10 = 2
5 → (5+5) % 10 = 0
Result: 7520
```

---

#### **Example 3**

##### **Input**

```python
magic(888, 2)
```

##### **Output**

```
0
```

##### **Explanation**

```
8 → (8+2) % 10 = 0
8 → (8+2) % 10 = 0
8 → (8+2) % 10 = 0
Result: 000 → 0
```

---

## **Approach**

1. **Extract each digit** of `x` from right to left.
2. **Modify the digit** using `(digit + n) % 10`.
3. **Reconstruct the new number** in correct order.

---

## **Python Implementation**

```python
def magic(x, n):
    result = 0
    place = 1

    while x > 0:
        digit = x % 10
        new_digit = (digit + n) % 10
        result = result + (new_digit * place)
        place *= 10
        x //= 10

    return result

# Test cases
print(magic(328, 3))    # Output: 651
print(magic(2075, 5))   # Output: 7520
print(magic(888, 2))    # Output: 0
```

---

## **Java Implementation**

```java
public class MagicFunction {
    public static int magic(int x, int n) {
        int result = 0, place = 1;

        while (x > 0) {
            int digit = x % 10;
            int new_digit = (digit + n) % 10;
            result = result + (new_digit * place);
            place *= 10;
            x /= 10;
        }

        return result;
    }

    public static void main(String[] args) {
        // Test cases
        System.out.println(magic(328, 3));  // Output: 651
        System.out.println(magic(2075, 5)); // Output: 7520
        System.out.println(magic(888, 2));  // Output: 0
    }
}
```

---

## **How to Run**

### **Python**

1. Save the code in a file `magic_function.py`.
2. Run:
   ```sh
   python magic_function.py
   ```

### **Java**

1. Save the code in a file `MagicFunction.java`.
2. Compile and run:
   ```sh
   javac MagicFunction.java
   java MagicFunction
   ```

---

**Markdown File (`verbal_kho_kho.md`)**

```md
# Verbal Kho-Kho

## **Problem Statement**
Alice and her friends are playing a game of **verbal Kho-Kho**. Alice acts as a **mediator**, and her `N` friends are **seated in a row**, one per chair.

- Alice provides a **single-digit number** on a paper to **F[1]** (the first friend).
- **F[1] enacts** the digit **silently** to **F[2]**.
- **F[2] does the same** to **F[3]**, and so on.
- This process continues until the **last friend F[N] writes the number** on a separate paper and hands it to Alice.

### **Game Rules**
- If the **final number matches** the initial number, **everyone gets a T-shirt**.
- If the numbers **do not match**, Alice checks the **individual responses** from `F[1]` to `F[N]` to find out **who made a mistake**.

### **Input**
- `N`: The number of friends (1 ≤ N ≤ 100).
- `D`: An **array of size `N`**, where:
  - `D[i]` represents the **digit understood** by friend `F[i]`.

### **Output**
- Print the number of **friends who misunderstood or miscommunicated** the digit.

---

## **Example Cases**
### **Example 1**
#### **Input**
```

5
[2, 2, 3, 3, 3]

```
#### **Output**
```

2

```
#### **Explanation**
- Alice gives `2` to **F[1]**.
- **F[1]** understands it as `2`, **F[2]** also gets `2`.
- **F[3]** miscommunicates **(wrongly gets 3)**.
- **F[4]** and **F[5]** continue the wrong value (`3`).
- **Incorrect friends:** F[3], F[4], F[5] → **Total = 2**

---

### **Example 2**
#### **Input**
```

4
[7, 7, 7, 7]

```
#### **Output**
```

0

```
#### **Explanation**
- Everyone understood the number correctly.
- No mistakes made → **Total = 0**

---

## **Approach**
1. **Compare each friend's number** with the **previous friend's number**.
2. If **any friend miscommunicates**, all subsequent friends **inherit the mistake**.
3. Count the **number of friends who made a mistake**.

---

## **Python Implementation**
```python
def count_misunderstood_friends(n, d):
    mistakes = 0
    for i in range(1, n):
        if d[i] != d[i - 1]:  # If mismatch occurs
            mistakes = n - i  # All remaining friends are wrong
            break
    return mistakes

# Test cases
print(count_misunderstood_friends(5, [2, 2, 3, 3, 3]))  # Output: 2
print(count_misunderstood_friends(4, [7, 7, 7, 7]))    # Output: 0
```

---

## **Java Implementation**

```java
public class VerbalKhoKho {
    public static int countMisunderstoodFriends(int n, int[] d) {
        int mistakes = 0;
      
        for (int i = 1; i < n; i++) {
            if (d[i] != d[i - 1]) {  // First wrong communication
                mistakes = n - i;  // Count remaining mistaken friends
                break;
            }
        }
      
        return mistakes;
    }

    public static void main(String[] args) {
        int[] d1 = {2, 2, 3, 3, 3};
        int[] d2 = {7, 7, 7, 7};

        System.out.println(countMisunderstoodFriends(5, d1));  // Output: 2
        System.out.println(countMisunderstoodFriends(4, d2));  // Output: 0
    }
}
```

---

## **How to Run**

### **Python**

1. Save the code in `verbal_kho_kho.py`.
2. Run:
   ```sh
   python verbal_kho_kho.py
   ```

### **Java**

1. Save the code in `VerbalKhoKho.java`.
2. Compile and run:
   ```sh
   javac VerbalKhoKho.java
   java VerbalKhoKho
   ```

---
