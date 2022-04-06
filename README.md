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
<br>

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
