
---

### **Markdown File (`fair_sequence.md`)**

```md
# Fair Sequence

## **Problem Statement**
You are given an array `A` of size `N`. Your friend has given you an interesting task.  
He likes a specific type of sequence, which he calls a **Fair Sequence**.  

A **Fair Sequence** is a subsequence where:
- The elements must **alternate in sign**: positive, negative, positive… OR negative, positive, negative…
- Your goal is to **select a fair sequence of maximum length** from the array.
- You need to **maximize the sum** of elements from the selected sequence.

---

## **Input Format**
- `N`: An integer, the size of the array (1 ≤ N ≤ 1000).
- `A`: An array of `N` integers (-10^6 ≤ A[i] ≤ 10^6).

## **Output Format**
- Print a **single integer**, the **maximum possible sum** from a valid fair sequence.

---

## **Example Cases**
### **Example 1**
#### **Input**
```

10
-1 18 13 18 -2 -16 7 -1 -213 11

```
#### **Output**
```

32

```
#### **Explanation**
A fair sequence with **maximum length**:
```

[-1, 18, -2, 7, -1, 11]

```
Sum = **32**.

---

### **Example 2**
#### **Input**
```

5
5 -3 2 -4 6

```
#### **Output**
```

10

```
#### **Explanation**
A fair sequence:
```

[5, -3, 2, -4, 6]

```
Sum = **10**.

---

## **Approach**
1. **Iterate through the array** while keeping track of signs.
2. **Pick numbers alternately** (positive after negative, and vice versa).
3. **Maximize the sum** by choosing **only alternating numbers**.
4. **Use a greedy approach** to pick elements while maintaining alternation.

---

## **Python Implementation (Without Built-in Functions)**
```python
def max_fair_sequence_sum(n, a):
    if n == 0:
        return 0

    total_sum = a[0]
    prev_sign = 1 if a[0] > 0 else -1  # Track sign of last picked number

    for i in range(1, n):
        current_sign = 1 if a[i] > 0 else -1
        if current_sign != prev_sign:  # If signs alternate
            total_sum += a[i]
            prev_sign = current_sign

    return total_sum

# Sample Input Handling
n = int(input())  # Read N (size of array)
a = list(map(int, input().split()))  # Read array elements

print(max_fair_sequence_sum(n, a))  # Output the result
```

---

## **Java Implementation (Without Built-in Functions)**

```java
import java.util.Scanner;

public class FairSequence {
    public static int maxFairSequenceSum(int n, int[] a) {
        if (n == 0) return 0;

        int totalSum = a[0];
        int prevSign = (a[0] > 0) ? 1 : -1;  // Track sign of last picked number

        for (int i = 1; i < n; i++) {
            int currentSign = (a[i] > 0) ? 1 : -1;
            if (currentSign != prevSign) {  // If signs alternate
                totalSum += a[i];
                prevSign = currentSign;
            }
        }

        return totalSum;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt(); // Read N (size of array)
        int[] a = new int[n];

        for (int i = 0; i < n; i++) {
            a[i] = sc.nextInt(); // Read array elements
        }

        System.out.println(maxFairSequenceSum(n, a)); // Output result
        sc.close();
    }
}
```

---

## **Complexity Analysis**

* **O(N)** → We traverse the array once.
* **O(1) Space** → Uses only a few extra variables.

---

## **How to Run**

### **Python**

1. Save the code in `fair_sequence.py`.
2. Run:
   ```sh
   python fair_sequence.py
   ```

### **Java**

1. Save the code in `FairSequence.java`.
2. Compile and run:
   ```sh
   javac FairSequence.java
   java FairSequence
   ```

---

### **Markdown File (`selling_price.md`)**

```md
# Selling Price Calculation

## **Problem Statement**
In a shop, every item has an **alphanumeric code** printed on its label.  
Each **consecutive sequence of digits** in the code represents a **multi-digit number**.  

The **selling price** of the product is the **sum of all such numbers** extracted from the alphanumeric string.

---

## **Input Format**
- `Str`: A **string** containing alphanumeric characters.

## **Output Format**
- Print the **sum of all numbers** extracted from the given string.

---

## **Example Cases**
### **Example 1**
#### **Input**
```

1xyz23

```
#### **Output**
```

24

```
#### **Explanation**
- **Extracted numbers**: `1`, `23`
- **Sum** = `1 + 23 = 24`

---

### **Example 2**
#### **Input**
```

1g2a30t20

```
#### **Output**
```

53

```
#### **Explanation**
- **Extracted numbers**: `1`, `2`, `30`, `20`
- **Sum** = `1 + 2 + 30 + 20 = 53`

---

## **Approach**
1. **Iterate through each character** in the string.
2. **Extract consecutive digits** and form multi-digit numbers.
3. **Add the extracted numbers** to the total sum.

---

## **Python Implementation (Without Built-in Functions)**
```python
def compute_selling_price(Str):
    num = 0
    total = 0

    for char in Str:
        if '0' <= char <= '9':  # Check if character is a digit
            num = num * 10 + (ord(char) - ord('0'))  # Form the number
        else:
            total += num  # Add the number to sum
            num = 0  # Reset number

    total += num  # Add the last number if any
    return total

# Read input
Str = input()
print(compute_selling_price(Str))
```

---

## **Java Implementation (Without Built-in Functions)**

```java
import java.util.Scanner;

public class SellingPrice {
    public static int computeSellingPrice(String str) {
        int sum = 0, num = 0;

        for (int i = 0; i < str.length(); i++) {
            char ch = str.charAt(i);
          
            if (ch >= '0' && ch <= '9') {  // Check if character is a digit
                num = num * 10 + (ch - '0');  // Form the number
            } else {
                sum += num;  // Add number to sum
                num = 0;  // Reset number
            }
        }
      
        sum += num;  // Add the last number if any
        return sum;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String str = sc.next();
      
        System.out.println(computeSellingPrice(str)); // Output result
        sc.close();
    }
}
```

---

## **Complexity Analysis**

* **O(N)** → We traverse the string once.
* **O(1) Space** → Uses only a few extra variables.

---

## **How to Run**

### **Python**

1. Save the code in `selling_price.py`.
2. Run:
   ```sh
   python selling_price.py
   ```

### **Java**

1. Save the code in `SellingPrice.java`.
2. Compile and run:
   ```sh
   javac SellingPrice.java
   java SellingPrice
   ```

---

**Markdown File (`diagonal_difference.md`)**

```md
# Diagonal Difference in a Square Matrix

## **Problem Statement**
Given a **square matrix**, calculate the **absolute difference** between the sum of its **primary diagonal** and **secondary diagonal**.

---

## **Input Format**
- `N`: An integer representing the size of the square matrix (1 ≤ N ≤ 100).
- `N x N` matrix: `N` lines of space-separated integers.

## **Output Format**
- Print a **single integer**, the absolute difference between the two diagonal sums.

---

## **Example Cases**
### **Example 1**
#### **Input**
```

3
1 2 3
4 5 6
9 8 9

```
#### **Output**
```

2

```
#### **Explanation**
- **Primary Diagonal**: `1 + 5 + 9 = 15`
- **Secondary Diagonal**: `3 + 5 + 9 = 17`
- **Absolute Difference**: `|15 - 17| = 2`

---

## **Approach**
1. **Iterate through the matrix row by row**.
2. Extract elements from:
   - **Primary diagonal** → Elements at `(i, i)`.
   - **Secondary diagonal** → Elements at `(i, N - i - 1)`.
3. Compute their **absolute difference**.

---

## **Python Implementation (Without Built-in Functions)**
```python
def diagonal_difference(n, matrix):
    primary_sum = 0
    secondary_sum = 0

    for i in range(n):
        primary_sum += matrix[i][i]  # Primary diagonal element
        secondary_sum += matrix[i][n - i - 1]  # Secondary diagonal element

    return abs(primary_sum - secondary_sum)

# Read input
n = int(input())
matrix = []

for _ in range(n):
    row = list(map(int, input().split()))
    matrix.append(row)

print(diagonal_difference(n, matrix))
```

---

## **Java Implementation (Without Built-in Functions)**

```java
import java.util.Scanner;

public class DiagonalDifference {
    public static int diagonalDifference(int n, int[][] matrix) {
        int primarySum = 0, secondarySum = 0;

        for (int i = 0; i < n; i++) {
            primarySum += matrix[i][i]; // Primary diagonal element
            secondarySum += matrix[i][n - i - 1]; // Secondary diagonal element
        }

        return Math.abs(primarySum - secondarySum);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt(); // Read N (matrix size)
        int[][] matrix = new int[n][n];

        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                matrix[i][j] = sc.nextInt(); // Read matrix elements
            }
        }

        System.out.println(diagonalDifference(n, matrix)); // Output result
        sc.close();
    }
}
```

---

## **Complexity Analysis**

* **O(N)** → We traverse the matrix once to compute both diagonal sums.
* **O(1) Space** → Uses only a few extra variables.

---

## **How to Run**

### **Python**

1. Save the code in `diagonal_difference.py`.
2. Run:
   ```sh
   python diagonal_difference.py
   ```

### **Java**

1. Save the code in `DiagonalDifference.java`.
2. Compile and run:
   ```sh
   javac DiagonalDifference.java
   java DiagonalDifference
   ```

---

**Markdown File (`maximize_fuel_volume.md`)**

```md
# Maximize Fuel Volume Purchase

## **Problem Statement**
Vijay, an industrialist, recently opened a **fuel industry** with `N` different **categories of fuel**, each stored in **fixed-size containers**.  
Each fuel container has:
- A **price** (cost to buy).
- A **volume** (fuel it holds).

Hari, a **fuel merchant**, has a **limited budget `K`** and wants to **buy fuel to maximize the total volume**.  
Hari **cannot buy more than one container** of any fuel category.

### **Objective**
Find the **maximum overall volume of fuel** that Hari can purchase within his budget `K`.

---

## **Input Format**
- An integer `N` → Number of fuel categories. (1 ≤ N ≤ 1000)
- An integer `K` → Available money units. (1 ≤ K ≤ 10⁶)
- A list of `N` integers → **Prices** of each fuel category.
- A list of `N` integers → **Volumes** of fuel in corresponding containers.

---

## **Output Format**
- A **single integer** representing the **maximum fuel volume** Hari can purchase.

---

## **Example Cases**
### **Example 1**
#### **Input**
```

3 50
10 20 30
60 100 120

```
#### **Output**
```

160

```
#### **Explanation**
- Budget: `K = 50`
- Best way to maximize volume:
  - Buy fuel 1 (Price `10`, Volume `60`).
  - Buy fuel 2 (Price `20`, Volume `100`).
  - Total Cost: `10 + 20 = 30` (≤ 50).
  - **Total Volume = 60 + 100 = 160**.

---

### **Example 2**
#### **Input**
```

4 15
5 10 15 20
50 80 120 200

```
#### **Output**
```

130

```
#### **Explanation**
- Budget: `K = 15`
- Best selection:
  - Buy fuel 1 (Price `5`, Volume `50`).
  - Buy fuel 2 (Price `10`, Volume `80`).
  - **Total Volume = 50 + 80 = 130**.

---

## **Approach**
1. **Sort fuels by price** to ensure we pick affordable options first.
2. **Use a greedy approach**:
   - Iterate over sorted fuel categories.
   - If Hari's budget allows, buy that fuel container.
   - Deduct cost from budget and add volume.
3. **Stop when no more fuels can be bought within the budget.**

---

## **Python Implementation (Without Built-in Functions)**
```python
def max_fuel_volume(n, k, prices, volumes):
    # Sort by price manually
    for i in range(n):
        for j in range(i + 1, n):
            if prices[i] > prices[j]:  # Swap to sort by price
                prices[i], prices[j] = prices[j], prices[i]
                volumes[i], volumes[j] = volumes[j], volumes[i]

    total_volume = 0
    for i in range(n):
        if k >= prices[i]:
            k -= prices[i]
            total_volume += volumes[i]
        else:
            break  # Stop when budget is exhausted

    return total_volume

# Read input
n, k = map(int, input().split())
prices = list(map(int, input().split()))
volumes = list(map(int, input().split()))

print(max_fuel_volume(n, k, prices, volumes))
```

---

## **Java Implementation (Without Built-in Functions)**

```java
import java.util.Scanner;

public class MaxFuelVolume {
    public static int maxFuelVolume(int n, int k, int[] prices, int[] volumes) {
        // Sort manually by price
        for (int i = 0; i < n - 1; i++) {
            for (int j = i + 1; j < n; j++) {
                if (prices[i] > prices[j]) {  // Swap to sort by price
                    int tempPrice = prices[i];
                    prices[i] = prices[j];
                    prices[j] = tempPrice;

                    int tempVolume = volumes[i];
                    volumes[i] = volumes[j];
                    volumes[j] = tempVolume;
                }
            }
        }

        int totalVolume = 0;
        for (int i = 0; i < n; i++) {
            if (k >= prices[i]) {
                k -= prices[i];
                totalVolume += volumes[i];
            } else {
                break;  // Stop when budget is exhausted
            }
        }

        return totalVolume;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int k = sc.nextInt();

        int[] prices = new int[n];
        int[] volumes = new int[n];

        for (int i = 0; i < n; i++) {
            prices[i] = sc.nextInt();
        }

        for (int i = 0; i < n; i++) {
            volumes[i] = sc.nextInt();
        }

        System.out.println(maxFuelVolume(n, k, prices, volumes));
        sc.close();
    }
}
```

---

## **Complexity Analysis**

* **O(N²) Sorting** → Uses a basic  **Bubble Sort** .
* **O(N) Selection** → Iterates through sorted fuels to maximize volume.
* **Total Complexity: O(N²) + O(N) ≈ O(N²)** .

---

## **How to Run**

### **Python**

1. Save the code in `maximize_fuel_volume.py`.
2. Run:
   ```sh
   python maximize_fuel_volume.py
   ```

### **Java**

1. Save the code in `MaxFuelVolume.java`.
2. Compile and run:
   ```sh
   javac MaxFuelVolume.java
   java MaxFuelVolume
   ```

---

**Markdown File (`nth_smallest_element.md`)**

```md
# Find Nth Smallest Element

## **Problem Statement**
You are given an **unsorted collection of `X` integers**.  
Your task is to **find the `N`th smallest element** in the collection.

---

## **Input Format**
1. An **integer `X`** → The size of the array. (1 ≤ X ≤ 10)
2. `X` **unsorted integers**, each on a new line. (1 ≤ A[i] ≤ 1000)
3. An **integer `N`** → The position of the smallest element to find. (1 ≤ N ≤ X)

---

## **Output Format**
- A **single integer**, the **Nth smallest element** in the array.

---

## **Example Cases**
### **Example 1**
#### **Input**
```

5
10
20
40
30
60
3

```
#### **Output**
```

30

```
#### **Explanation**
- Array: `[10, 20, 40, 30, 60]`
- **Sorted Array**: `[10, 20, 30, 40, 60]`
- **3rd Smallest Element**: `30`

---

## **Approach**
1. **Store the input values in an array**.
2. **Sort the array manually using a basic sorting algorithm** (e.g., Bubble Sort).
3. **Return the `N`th smallest element** (i.e., the `N-1` indexed element in sorted order).

---

## **Python Implementation (Without Built-in Functions)**
```python
def sort_array(arr, x):
    for i in range(x - 1):
        for j in range(i + 1, x):
            if arr[i] > arr[j]:  # Swap elements
                arr[i], arr[j] = arr[j], arr[i]

def nth_smallest_element(x, arr, n):
    sort_array(arr, x)  # Sort the array
    return arr[n - 1]  # Return the Nth smallest element

# Read input
x = int(input())  # Read X (size of array)
arr = [int(input()) for _ in range(x)]  # Read X elements
n = int(input())  # Read N

print(nth_smallest_element(x, arr, n))  # Output the result
```

---

## **Java Implementation (Without Built-in Functions)**

```java
import java.util.Scanner;

public class NthSmallestElement {
    public static void sortArray(int[] arr, int x) {
        for (int i = 0; i < x - 1; i++) {
            for (int j = i + 1; j < x; j++) {
                if (arr[i] > arr[j]) {  // Swap elements
                    int temp = arr[i];
                    arr[i] = arr[j];
                    arr[j] = temp;
                }
            }
        }
    }

    public static int findNthSmallest(int x, int[] arr, int n) {
        sortArray(arr, x); // Sort the array
        return arr[n - 1]; // Return the Nth smallest element
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int x = sc.nextInt(); // Read X (size of array)
        int[] arr = new int[x];

        for (int i = 0; i < x; i++) {
            arr[i] = sc.nextInt(); // Read elements
        }

        int n = sc.nextInt(); // Read N
        System.out.println(findNthSmallest(x, arr, n)); // Output result

        sc.close();
    }
}
```

---

## **Complexity Analysis**

* **Sorting Complexity: O(X²)** → Using **Bubble Sort** for simplicity.
* **Accessing `N`th element: O(1)** .

---

## **How to Run**

### **Python**

1. Save the code in `nth_smallest_element.py`.
2. Run:
   ```sh
   python nth_smallest_element.py
   ```

### **Java**

1. Save the code in `NthSmallestElement.java`.
2. Compile and run:
   ```sh
   javac NthSmallestElement.java
   java NthSmallestElement
   ```

---

**Markdown File (`replace_digits_game.md`)**

```md
# Replace Digits Game

## **Problem Statement**
A game development company is designing a **brain game** for kids.  
One of the tasks in this game requires **each digit of an existing number `N` to be replaced with another digit** based on the following mapping:

| Existing Digit | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |
|---------------|---|---|---|---|---|---|---|---|---|---|
| Replace By    | 9 | 8 | 7 | 6 | 5 | 4 | 3 | 2 | 1 | 0 |

---

## **Constraints**
- **0 ≤ N ≤ 1,000,000**
- If **N is out of range**, print `"Wrong Input"`.

---

## **Input Format**
- A **single integer `N`**.

## **Output Format**
- The **modified number** after replacing each digit.
- If `N` is out of range, print `"Wrong Input"`.

---

## **Example Cases**
### **Example 1**
#### **Input**
```

105201

```
#### **Output**
```

894798

```
#### **Explanation**
- **Mapping Digits**:
  - `1 → 8`
  - `0 → 9`
  - `5 → 4`
  - `2 → 7`
  - `0 → 9`
  - `1 → 8`
- **Final Output**: `894798`

---

### **Example 2**
#### **Input**
```

10000001

```
#### **Output**
```

Wrong Input

```
#### **Explanation**
- `10000001` is **greater than `1,000,000`**, so the system returns `"Wrong Input"`.

---

## **Approach**
1. **Check if `N` is within the valid range** (0 ≤ N ≤ 1,000,000).
2. **Extract each digit manually** and replace it based on the given table.
3. **Construct the modified number**.

---

## **Python Implementation (Without Built-in Functions)**
```python
def replace_digits(n):
    if n < 0 or n > 1000000:
        return "Wrong Input"

    mapping = ['9', '8', '7', '6', '5', '4', '3', '2', '1', '0']
    result = ""

    while n > 0:
        digit = n % 10
        result = mapping[digit] + result  # Construct the new number
        n //= 10

    return result

# Read input
n = int(input())
print(replace_digits(n))
```

---

## **Java Implementation (Without Built-in Functions)**

```java
import java.util.Scanner;

public class ReplaceDigitsGame {
    public static String replaceDigits(int n) {
        if (n < 0 || n > 1000000) {
            return "Wrong Input";
        }

        int[] mapping = {9, 8, 7, 6, 5, 4, 3, 2, 1, 0}; // Mapping table
        String result = "";

        while (n > 0) {
            int digit = n % 10;
            result = mapping[digit] + result; // Construct the new number
            n /= 10;
        }

        return result;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
      
        System.out.println(replaceDigits(n)); // Output result
        sc.close();
    }
}
```

---

## **Complexity Analysis**

* **O(K)** → Where `K` is the number of digits in `N`.
* **Efficient since we process each digit once** .

---

## **How to Run**

### **Python**

1. Save the code as `replace_digits_game.py`
2. Run:
   ```sh
   python replace_digits_game.py
   ```

### **Java**

1. Save the code as `ReplaceDigitsGame.java`
2. Compile and run:
   ```sh
   javac ReplaceDigitsGame.java
   java ReplaceDigitsGame
   ```

---

**Markdown File (`save_the_prisoner.md`)**

```md
# Save The Prisoner

## **Problem Statement**
A jail has a number of **prisoners** and a number of **treats** to distribute.  
The prisoners are seated **around a circular table** in sequentially numbered chairs.  

- A **random chair number is chosen** from a hat.
- Starting from that prisoner, **one candy is passed sequentially** to each prisoner **around the table**.
- The **last piece of candy** tastes **awful**.  
- We need to **determine the prisoner sitting in the chair** who will receive that last candy.

---

## **Input Format**
- The first line contains an integer **t**, denoting the **number of test cases**.
- Each of the next **t** lines contains **three space-separated integers**:
  - `n`: the **number of prisoners**.
  - `m`: the **number of sweets**.
  - `s`: the **chair number** where candy distribution begins.

## **Output Format**
- Print the **chair number** of the prisoner who receives the **awful treat**.

---

## **Example Cases**
### **Example 1**
#### **Input**
```

2
5 2 1
5 2 2

```
#### **Output**
```

2
3

```
#### **Explanation**
- **Test Case 1**:
  - `5` prisoners, `2` candies, starting from prisoner `1`.
  - **Order of candy distribution**: `1 → 2`
  - **Prisoner `2` gets the awful candy**.
  
- **Test Case 2**:
  - `5` prisoners, `2` candies, starting from prisoner `2`.
  - **Order of candy distribution**: `2 → 3`
  - **Prisoner `3` gets the awful candy**.

---

## **Approach**
### **Mathematical Formula**
To find the prisoner who gets the **last candy**, use the formula:

\[
\text{result} = (s + m - 1) \mod n
\]

- If **result = 0**, set it to `n` (because the last prisoner in the circle should be warned).

---

## **Python Implementation (Without Built-in Functions)**
```python
def saveThePrisoner(n, m, s):
    result = (s + m - 1) % n
    return result if result != 0 else n

# Read input
t = int(input())  # Number of test cases
for _ in range(t):
    n, m, s = map(int, input().split())
    print(saveThePrisoner(n, m, s))
```

---

## **Java Implementation (Without Built-in Functions)**

```java
import java.util.Scanner;

public class SaveThePrisoner {
    public static int saveThePrisoner(int n, int m, int s) {
        int result = (s + m - 1) % n;
        return (result == 0) ? n : result;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int t = sc.nextInt(); // Number of test cases
      
        for (int i = 0; i < t; i++) {
            int n = sc.nextInt();
            int m = sc.nextInt();
            int s = sc.nextInt();
            System.out.println(saveThePrisoner(n, m, s));
        }
      
        sc.close();
    }
}
```

---

## **Complexity Analysis**

* **O(1)** → Uses a mathematical formula for direct computation.

## **Space Complexity**

* **O(1)** → Uses only a few extra variables.

---

## **How to Run**

### **Python**

1. Save the code in `save_the_prisoner.py`.
2. Run:
   ```sh
   python save_the_prisoner.py
   ```

### **Java**

1. Save the code in `SaveThePrisoner.java`.
2. Compile and run:
   ```sh
   javac SaveThePrisoner.java
   java SaveThePrisoner
   ```

---

**Markdown File (`selling_price.md`)**

```md
# Selling Price Calculation

## **Problem Statement**
In a shop, every item has an **alphanumeric code** printed on its label.  
Each **consecutive sequence of digits** in the code represents a **multi-digit number**.  

The **selling price** of the product is the **sum of all such numbers** extracted from the alphanumeric string.

---

## **Input Format**
- `Str`: A **string** containing alphanumeric characters.

## **Output Format**
- Print the **sum of all numbers** extracted from the given string.

---

## **Example Cases**
### **Example 1**
#### **Input**
```

1xyz23

```
#### **Output**
```

24

```
#### **Explanation**
- **Extracted numbers**: `1`, `23`
- **Sum** = `1 + 23 = 24`

---

### **Example 2**
#### **Input**
```

1g2a30t20

```
#### **Output**
```

53

```
#### **Explanation**
- **Extracted numbers**: `1`, `2`, `30`, `20`
- **Sum** = `1 + 2 + 30 + 20 = 53`

---

## **Approach**
1. **Iterate through each character** in the string.
2. **Extract consecutive digits** and form multi-digit numbers.
3. **Add the extracted numbers** to the total sum.

---

## **Python Implementation (Without Built-in Functions)**
```python
def compute_selling_price(Str):
    num = 0
    total = 0

    for char in Str:
        if '0' <= char <= '9':  # Check if character is a digit
            num = num * 10 + (ord(char) - ord('0'))  # Form the number
        else:
            total += num  # Add the number to sum
            num = 0  # Reset number

    total += num  # Add the last number if any
    return total

# Read input
Str = input()
print(compute_selling_price(Str))
```

---

## **Java Implementation (Without Built-in Functions)**

```java
import java.util.Scanner;

public class SellingPrice {
    public static int computeSellingPrice(String str) {
        int sum = 0, num = 0;

        for (int i = 0; i < str.length(); i++) {
            char ch = str.charAt(i);
          
            if (ch >= '0' && ch <= '9') {  // Check if character is a digit
                num = num * 10 + (ch - '0');  // Form the number
            } else {
                sum += num;  // Add number to sum
                num = 0;  // Reset number
            }
        }
      
        sum += num;  // Add the last number if any
        return sum;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String str = sc.next();
      
        System.out.println(computeSellingPrice(str)); // Output result
        sc.close();
    }
}
```

---

## **Complexity Analysis**

* **O(N)** → We traverse the string once.
* **O(1) Space** → Uses only a few extra variables.

---

## **How to Run**

### **Python**

1. Save the code in `selling_price.py`.
2. Run:
   ```sh
   python selling_price.py
   ```

### **Java**

1. Save the code in `SellingPrice.java`.
2. Compile and run:
   ```sh
   javac SellingPrice.java
   java SellingPrice
   ```

---

**Markdown File (`unique_digit_count.md`)**

```md
# Count Numbers Without Repeated Digits

## **Problem Statement**
Given two **non-negative integers** `n1` and `n2`, where `n1 < n2`,  
Find the **total number of integers** in the range **[n1, n2]** (both inclusive) that **have no repeated digits**.

---

## **Input Format**
- **n1**: Integer (lower bound of the range).
- **n2**: Integer (upper bound of the range).

### **Constraints**
- `0 ≤ n1 < n2 ≤ 1,000,000`

## **Output Format**
- Print a **single integer** representing the count of numbers in the range `[n1, n2]` that have **no repeated digits**.

---

## **Example Cases**
### **Example 1**
#### **Input**
```

11
15

```
#### **Output**
```

4

```
#### **Explanation**
- **Numbers in range**: `11, 12, 13, 14, 15`
- **Valid numbers (no repeated digits)**: `12, 13, 14, 15`
- **Count** = `4`

---

### **Example 2**
#### **Input**
```

101
200

```
#### **Output**
```

72

```
#### **Explanation**
- **Valid numbers in range**: 72 numbers **without repeated digits**.

---

## **Approach**
1. **Iterate through all numbers from `n1` to `n2`**.
2. **Check if each number has unique digits**:
   - Extract digits manually.
   - Use a loop to check for **duplicates**.
3. **Count valid numbers**.

---

## **Python Implementation (Without Built-in Functions)**
```python
def has_unique_digits(num):
    digits = [0] * 10  # Array to track digit occurrences

    while num > 0:
        digit = num % 10
        if digits[digit] > 0:  # Found duplicate digit
            return False
        digits[digit] += 1
        num //= 10
    return True

def count_unique_digit_numbers(n1, n2):
    count = 0
    for num in range(n1, n2 + 1):
        if has_unique_digits(num):
            count += 1
    return count

# Sample Input Handling
n1 = int(input())
n2 = int(input())

print(count_unique_digit_numbers(n1, n2))
```

---

## **Java Implementation (Without Built-in Functions)**

```java
import java.util.Scanner;

public class UniqueDigitNumbers {
    public static boolean hasUniqueDigits(int num) {
        int[] digitCount = new int[10];  // Array to track digit occurrences

        while (num > 0) {
            int digit = num % 10;
            if (digitCount[digit] > 0) return false; // Found duplicate
            digitCount[digit]++;
            num /= 10;
        }
        return true;
    }

    public static int countUniqueDigitNumbers(int n1, int n2) {
        int count = 0;
        for (int num = n1; num <= n2; num++) {
            if (hasUniqueDigits(num)) count++;
        }
        return count;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n1 = sc.nextInt();
        int n2 = sc.nextInt();

        System.out.println(countUniqueDigitNumbers(n1, n2));
        sc.close();
    }
}
```

---

## **Complexity Analysis**

* **Checking unique digits** : **O(K)** (where K is the number of digits in `num`).
* **Iterating through range** : **O(N)** (where N = `n2 - n1`).
* **Total Complexity** :  **O(N * K)** .

---

## **How to Run**

### **Python**

1. Save the code as `unique_digit_count.py`
2. Run:
   ```sh
   python unique_digit_count.py
   ```

### **Java**

1. Save the code as `UniqueDigitNumbers.java`
2. Compile and run:
   ```sh
   javac UniqueDigitNumbers.java
   java UniqueDigitNumbers
   ```

---

**Markdown File (`rearrange_multiples.md`)**

```md
# Rearrange Multiples of 10

## **Problem Statement**
Given an **array `Arr[]` of `N` integers**, rewrite the array by moving all **multiples of 10** to the **end** while **preserving the order** of other elements.  

### **Conditions:**
- The order of **non-multiples of 10** must remain the same.
- The order of **multiples of 10** must also remain the same.

---

## **Input Format**
- An **integer `N`** → The size of the array. (1 ≤ N ≤ 1000)
- An array `Arr[]` of `N` integers.

## **Output Format**
- Print the **modified array** where all multiples of 10 are at the end.

---

## **Example Cases**
### **Example 1**
#### **Input**
```

9
10 12 5 40 30 7 5 9 10

```
#### **Output**
```

12 5 7 5 9 10 40 30 10

```
#### **Explanation**
- **Multiples of 10**: `{10, 40, 30, 10}`
- **Non-multiples of 10**: `{12, 5, 7, 5, 9}`
- Rearrange: `{12, 5, 7, 5, 9, 10, 40, 30, 10}`

---

### **Example 2**
#### **Input**
```

9
100 21 5 6 3 7 11 89 10

```
#### **Output**
```

21 5 6 3 7 11 89 100 10

```
#### **Explanation**
- **Multiples of 10**: `{100, 10}`
- **Non-multiples of 10**: `{21, 5, 6, 3, 7, 11, 89}`
- Rearrange: `{21, 5, 6, 3, 7, 11, 89, 100, 10}`

---

## **Approach**
1. **Iterate through the array**, separating:
   - **Non-multiples of 10** → Add to `non_multiples` list.
   - **Multiples of 10** → Add to `multiples` list.
2. **Combine both lists**: first all non-multiples, then multiples.
3. **Output the rearranged array**.

---

## **Python Implementation (Without Built-in Functions)**
```python
def rearrange_multiples(n, arr):
    non_multiples = []
    multiples = []

    for i in range(n):
        if arr[i] % 10 == 0:
            multiples.append(arr[i])  # Collect multiples of 10
        else:
            non_multiples.append(arr[i])  # Collect other numbers

    result = non_multiples + multiples  # Merge both lists
    print(" ".join(map(str, result)))

# Read input
n = int(input())
arr = list(map(int, input().split()))

rearrange_multiples(n, arr)
```

---

## **Java Implementation (Without Built-in Functions)**

```java
import java.util.Scanner;

public class RearrangeMultiples {
    public static void rearrangeMultiples(int n, int[] arr) {
        int[] result = new int[n];
        int index = 0;

        // Collect non-multiples of 10 first
        for (int i = 0; i < n; i++) {
            if (arr[i] % 10 != 0) {
                result[index++] = arr[i];
            }
        }

        // Collect multiples of 10 next
        for (int i = 0; i < n; i++) {
            if (arr[i] % 10 == 0) {
                result[index++] = arr[i];
            }
        }

        // Print the rearranged array
        for (int i = 0; i < n; i++) {
            System.out.print(result[i] + " ");
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt(); // Read N (size of array)
        int[] arr = new int[n];

        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt(); // Read array elements
        }

        rearrangeMultiples(n, arr); // Output result
        sc.close();
    }
}
```

---

## **Complexity Analysis**

* **O(N)** → We traverse the array twice.
* **O(N) Space** → Uses additional space for output storage.

---

## **How to Run**

### **Python**

1. Save the code in `rearrange_multiples.py`.
2. Run:
   ```sh
   python rearrange_multiples.py
   ```

### **Java**

1. Save the code in `RearrangeMultiples.java`.
2. Compile and run:
   ```sh
   javac RearrangeMultiples.java
   java RearrangeMultiples
   ```

---

### **Markdown File (`car_rental_cost.md`)**

```md
# Car Rental Cost Calculation

## **Problem Statement**
A travel agency charges **R1 rupees per hour** for the first **N hours** and then **R2 rupees per hour** for any additional time.  

Given the total travel time in **minutes (X)**, determine the **total cost**.  
- The number of **hours should be rounded up** (ceiling value).  
- Example: `90 minutes = 2 hours`, `121 minutes = 3 hours`.

---

## **Input Format**
1. An integer **R1** → Cost per hour for the first `N` hours. (1 ≤ R1 ≤ 1000)
2. An integer **N** → Number of hours charged at rate `R1`. (1 ≤ N ≤ 100)
3. An integer **R2** → Cost per hour after `N` hours. (1 ≤ R2 ≤ 1000)
4. An integer **X** → Total travel time in minutes. (1 ≤ X ≤ 10⁶)

## **Output Format**
- A **single integer**, the total cost in rupees.

---

## **Example Cases**
### **Example 1**
#### **Input**
```

20
4
40
300

```
#### **Output**
```

120

```
#### **Explanation**
- **300 minutes** → **Ceil to 5 hours**.
- First **4 hours** → `4 × 20 = 80`
- Remaining **1 hour** → `1 × 40 = 40`
- **Total Cost**: `80 + 40 = 120`

---

### **Example 2**
#### **Input**
```

30
5
35
500

```
#### **Output**
```

290

```
#### **Explanation**
- **500 minutes** → **Ceil to 9 hours**.
- First **5 hours** → `5 × 30 = 150`
- Remaining **4 hours** → `4 × 35 = 140`
- **Total Cost**: `150 + 140 = 290`

---

## **Approach**
1. **Convert minutes to hours**, rounding up.
2. **Calculate cost for first `N` hours** at `R1` rate.
3. **Calculate remaining hours** at `R2` rate.
4. **Sum the costs** and return the result.

---

## **Python Implementation (Without Built-in Functions)**
```python
def calculate_rental_cost(r1, n, r2, x):
    hours = (x + 59) // 60  # Ceiling division without built-in functions

    if hours <= n:
        return hours * r1
    else:
        return (n * r1) + ((hours - n) * r2)

# Read input
r1 = int(input())
n = int(input())
r2 = int(input())
x = int(input())

print(calculate_rental_cost(r1, n, r2, x))
```

---

## **Java Implementation (Without Built-in Functions)**

```java
import java.util.Scanner;

public class CarRentalCost {
    public static int calculateRentalCost(int r1, int n, int r2, int x) {
        int hours = (x + 59) / 60;  // Ceiling division

        if (hours <= n) {
            return hours * r1;
        } else {
            return (n * r1) + ((hours - n) * r2);
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
      
        int r1 = sc.nextInt();
        int n = sc.nextInt();
        int r2 = sc.nextInt();
        int x = sc.nextInt();

        System.out.println(calculateRentalCost(r1, n, r2, x));
        sc.close();
    }
}
```

---

## **Complexity Analysis**

* **O(1) Time Complexity** → Simple mathematical operations.
* **O(1) Space Complexity** → Uses only a few extra variables.

---

## **How to Run**

### **Python**

1. Save the code in `car_rental_cost.py`.
2. Run:
   ```sh
   python car_rental_cost.py
   ```

### **Java**

1. Save the code in `CarRentalCost.java`.
2. Compile and run:
   ```sh
   javac CarRentalCost.java
   java CarRentalCost
   ```

---
