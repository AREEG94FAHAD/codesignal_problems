# codesignal_problems

# 1- add
 Write a function that returns the sum of two numbers.<br>
 Example
 <br>
 - For **param1 = 1** and **param1 = 1**, the output should be
**solution(param1, param2) = 3.**
<br>

**input** two integers 
Guaranteed constraints:
**-1000 ≤ param1,param2 ≤ 1000.**
<br>
**output** a integer The sum of the two inputs.

My solution
```
def solution(param1, param2):
    return param1 + param2
```
# 2- centuryFromYear
- Given a year, return the century it is in. The first century spans from the year 1 up to and including the year 100, the second - from the year 101 up to and including the year 200, etc.
Example 
- For year = 1905, the output should be **solution(year) = 20 **
- For year = 1700, the output should be **solution(year) = 17.**

**Input**
A positive integer, designating the year.

Guaranteed constraints:
**1 ≤ year ≤ 2005.**

**output** a integer

The number of the century the year is in.
My solution

```
import math

def solution(year):
    return(math.ceil(year / 100))

```

# 3- checkPalindrome"decaf faced" is a palindrome
- Given the string, check if it is a palindrome.
```sh
Palindrome: A string that doesn't changed when reversed (it reads the same backward and forward).
- "eye" is a palindrome
- "decaf faced" is a palindrome
- "taco cat" is not a palindrome (backwards it spells "tac ocat")
```
 - For inputString = "aabaa", the output should be solution(inputString) = true;
 - For inputString = "abac", the output should be solution(inputString) = false;
 - For inputString = "a", the output should be solution(inputString) = true.

**Input** 1 ≤ inputString.length ≤ 105.
A non-empty string consisting of lowercase characters Guaranteed constraints: **1 ≤ inputString.length ≤ 105.**
**Output** boolean **True** if inputString is a palindrome, **False** otherwise.

My solution
```
def solution(inputString):
    if inputString == ''.join(reversed(inputString)):
        return True
    else:
        return False

```
# 4- adjacentElementsProduct
- Given an array of integers, find the pair of adjacent elements that has the largest product and return that product.<br>
- For inputArray = **[3, 6, -2, -5, 7, 3]**, the output should be
**solution(inputArray) = 21.**

7 and 3 produce the largest product.
**Input**
An array of integers containing at least two elements.<br>
Guaranteed constraints:
```sh
2 ≤ inputArray.length ≤ 10,
-1000 ≤ inputArray[i] ≤ 1000
```
**Output**
The largest product of adjacent elements.

My solution

```
def solution(inputArray):

    return max([inputArray[i] * inputArray[i + 1] for i in range(len(inputArray) - 1)])
```
# 5- shapeArea
- Below we will define an n-interesting polygon. Your task is to find the area of a polygon for a given n.
- A 1-interesting polygon is just a square with a side of length 1. An n-interesting polygon is obtained by taking the n - 1-interesting polygon and appending 1-interesting polygons to its rim, side by side. You can see the 1-, 2-, 3- and 4-interesting polygons in the picture below.
![image](https://user-images.githubusercontent.com/30151596/162259748-c030063c-7e18-4d87-b49e-1e57359bee61.png)
Example
- For **n = 2**, the output should be **solution(n) = 5;**
- For **n = 3**, the output should be **solution(n) = 13.**
**Input** integer n
Guaranteed constraints: **1 ≤ n < 104.**
**Output** Integer => the area of the n-interesting polygon.

```sh
def solution(n):
    sum = 1

    for i in range(1, n):
        sum = sum + (4 * i)
    return sum

```
Amazing solution 
```
def solution(n):
    return n**2 + (n-1)**2
```

# 6- Make Array Consecutive 2
- Ratiorg got statues of different sizes as a present from CodeMaster for his birthday, each statue having an non-negative integer size. Since he likes to make things perfect, he wants to arrange them from smallest to largest so that each statue will be bigger than the previous one exactly by 1. He may need some additional statues to be able to accomplish that. Help him figure out the minimum number of additional statues needed.
<br>
Example
- For **statues = [6, 2, 3, 8]** , the output should be **solution(statues) = 3**. Ratiorg needs statues of sizes 4, 5 and 7.
**Input**
array.integer statues An array of distinct non-negative integers.
Guaranteed constraints:
**1 ≤ statues.length ≤ 10,
0 ≤ statues[i] ≤ 20**

**Output** The minimal number of statues that need to be added to existing statues such that it contains every integer size from an interval [L, R] (for some L, R) and no other sizes.

My solution
```
def solution(statues):

    return max(statues) - min(statues) + 1 - len(statues)
```
