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
```sh
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

```sh
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
```sh
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

```sh
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
```sh
def solution(n):
    return n**2 + (n-1)**2
```

# 6- Make Array Consecutive 2
- Ratiorg got statues of different sizes as a present from CodeMaster for his birthday, each statue having an non-negative integer size. Since he likes to make things perfect, he wants to arrange them from smallest to largest so that each statue will be bigger than the previous one exactly by 1. He may need some additional statues to be able to accomplish that. Help him figure out the minimum number of additional statues needed.
<br>
Example
- For statues = [6, 2, 3, 8] , the output should be solution(statues) = 3. Ratiorg needs statues of sizes 4, 5 and 7.
 
**Input**
array.integer statues An array of distinct non-negative integers.
Guaranteed constraints:
**1 ≤ statues.length ≤ 10,
0 ≤ statues[i] ≤ 20**

**Output** The minimal number of statues that need to be added to existing statues such that it contains every integer size from an interval [L, R] (for some L, R) and no other sizes.

My solution
```sh
def solution(statues):

    return max(statues) - min(statues) + 1 - len(statues)
```

# 7- almostIncreasingSequence

Given a sequence of integers as an array, determine whether it is possible to obtain a strictly increasing sequence by removing no more than one element from the array.
**Note:** sequence a0, a1, ..., an is considered to be a strictly increasing if a0 < a1 < ... < an. Sequence containing only one element is also considered to be strictly increasing.<br>
Example
<br>
- For sequence = [1, 3, 2, 1], the output should be **solution(sequence) = false.** There is no one element in this array that can be removed in order to get a strictly increasing sequence.
- For sequence = [1, 3, 2], the output should be **solution(sequence) = true.** You can remove 3 from the array to get the strictly increasing sequence [1, 2]. Alternately, you can remove 2 to get the strictly increasing sequence [1, 3].
**Input**
Array of integer
Guaranteed constraints:
**2 ≤ sequence.length ≤ 105,**
**-105 ≤ sequence[i] ≤ 105**
**Output**
boolean Return true if it is possible to remove one element from the array in order to get a strictly increasing sequence, otherwise return false.
```sh
def solution(sequence):
    j = bad_pair(sequence)
    if j == -1:
        return True
    if bad_pair(sequence[j-1:j] + sequence[j+1:]) == -1:
        return True
    if bad_pair(sequence[j:j+1] + sequence[j+2:]) == -1:
        return True
        
    else:
        return False


def bad_pair(arr):
    for i in range(len(arr)-1):
        if arr[i]>=arr[i+1]:
            return  

    return -1
```
# 8- matrixElementsSum
After becoming famous, the CodeBots decided to move into a new building together. Each of the rooms has a different cost, and some of them are free, but there's a rumour that all the free rooms are haunted! Since the CodeBots are quite superstitious, they refuse to stay in any of the free rooms, or any of the rooms below any of the free rooms. Given matrix, a rectangular matrix of integers, where each value represents the cost of the room, your task is to return the total sum of all rooms that are suitable for the CodeBots (ie: add up all the values that don't appear below a 0).
<br>
Example
<br>
- For
```sh
matrix = [[0, 1, 1, 2], 
          [0, 5, 0, 0], 
          [2, 0, 3, 3]]
```
the output should be **solution(matrix) = 9**<br>
![image](https://user-images.githubusercontent.com/30151596/162610480-cdcae1c6-bf65-4f4a-9720-4083aecfcaeb.png)

- There are several haunted rooms, so we'll disregard them as well as any rooms beneath them. Thus, the answer is 1 + 5 + 1 + 2 = 9.
- For 
```sh
matrix = [[1, 1, 1, 0], 
          [0, 5, 0, 1], 
          [2, 1, 3, 10]]
```
the output should be **solution(matrix) = 9.**<br>
![image](https://user-images.githubusercontent.com/30151596/162610562-1923a710-4721-44a3-9e2d-bcfb7309908d.png)

Note that the free room in the final column makes the full column unsuitable for bots (not just the room directly beneath it). Thus, the answer is **1 + 1 + 1 + 5 + 1 = 9.**
**Input**
A 2-dimensional array of integers representing the cost of each room in the building. A value of 0 indicates that the room is haunted.
Guaranteed constraints:
**1 ≤ matrix.length ≤ 5,**
**1 ≤ matrix[i].length ≤ 5,**
**0 ≤ matrix[i][j] ≤ 10.**
**Output**
The total price of all the rooms that are suitable for the CodeBots to live in.


My solution
```sh
import numpy as np


def solution(matrix):
    arr = np.array(matrix)
    row, col = np.shape(arr)
    sum = 0
    col_ = []

    for i in range(row):
        for j in range(col):
            if arr[i][j] != 0 and j not in col_:
                sum += arr[i][j]
            if arr[i][j] == 0:
                col_.append(j)

    return sum
```

# 9- All Longest Strings
- Given an array of strings, return another array containing all of its longest strings.
Example
- For inputArray = ["aba", "aa", "ad", "vcd", "aba"], the output should be **solution(inputArray) = ["aba", "vcd", "aba"].**
**Input**
A non-empty array.
Guaranteed constraints:
**1 ≤ inputArray.length ≤ 10,**
**1 ≤ inputArray[i].length ≤ 10.**
**Output**
Array of the longest strings, stored in the same order as in the inputArray

My solution
```sh
def solution(inputArray):

    
    longest_len = max([ len(x) for x in inputArray ])
        
        
    return [item fo**r item in inputArray if len(item) == longest_len]
```

# 10- commonCharacterCount
- Given two strings, find the number of common characters between them.
- For s1 = "aabcc" and s2 = "adcaa", the output should be **solution(s1, s2) = 3.** Strings have 3 common characters - 2 "a"s and 1 "c".
**Input** Two string consisting of lowercase English letters.
Guaranteed constraints:
**1 ≤ s1.length < 15.**
**Output**
a integer: number of common characters between them
My solution
```sh
def solution(s1, s2):

    s_1 = []
    s_2 = []
    s_1[:] = s1
    s_2[:] = s2

    counter = 0
    for i in s_1:
        if i in s_2:
            # del s_2[s_2.index(i)]
            s_2.pop(s_2.index(i))

            counter += 1

    return counter

```
An amazing solution
```sh
def solution(s1, s2):
    com = [min(s1.count(i),s2.count(i)) for i in set(s1)]
    return sum(com)
```

# 11- isLucky
- Ticket numbers usually consist of an even number of digits. A ticket number is considered lucky if the sum of the first half of the digits is equal to the sum of the second half.
<br>
Given a ticket number n, determine if it's lucky or not.
<br>
Example

- For n = 1230, the output should be **solution(n) = true;**
- For n = 239017, the output should be **solution(n) = false.**

**Input** Integer n A ticket number represented as a positive integer with an even number of digits
Guaranteed constraints: **10 ≤ n < 106**
**Output**booleantrue if n is a lucky ticket number, false otherwise.

My solution
```sh
def solution(n):
    st_n = [i for i in str(n)]
    first_half = sum([int(i)for i in (st_n[:len(st_n) // 2])])
    second_half = sum([int(i)for i in (st_n[len(st_n) // 2:])])

    return (first_half == second_half)

```
# 12- Sort by Height
- Some people are standing in a row in a park. There are trees between them which cannot be moved. Your task is to rearrange the people by their heights in a non-descending order without moving the trees. People can be very tall!
<br>
Example
<br>

- For a = [-1, 150, 190, 170, -1, -1, 160, 180], the output should be **solution(a) = [-1, 150, 160, 170, -1, -1, 180, 190].**
**Input**
Array.Integer If a[i] = -1, then the ith position is occupied by a tree. Otherwise a[i] is the height of a person standing in the ith position.
Guaranteed constraints:
**1 ≤ a.length ≤ 1000,**
**-1 ≤ a[i] ≤ 1000.**
**Output**

Array.Integer Sorted array a with all the trees untouched.
My solution
O(n<sup>2</sup>)

```sh
def solution(a):
    temp = 0
    summ = 0
    for i in range(len(a)):
        for j in range(0, len(a)):
            if a[i] < a[j] and a[i] != -1 and a[j] != -1:
                temp = a[i]
                a[i] = a[j]
                a[j] = temp
    return a
```
My solution O(n)
```sh
for i in range(1,len(a)):
        if a[i] == -1 or a[i-1]==-1:
            continue
        if a[i]<a[i-1]:
            a[i],a[i-1] = a[i-1],a[i]
    return a
```
# 13- reverseInParentheses
- Write a function that reverses characters in (possibly nested) parentheses in the input string. Input strings will always be well-formed with matching ()s.
<br>Example<br>
- For inputString = **"(bar)"**, the output should be **solution(inputString) = "rab";**
- For inputString = **"foo(bar)baz"**, the output should be **solution(inputString) = "foorabbaz";**
- For inputString = **"foo(bar)baz(blim)"**, the output should be **solution(inputString) = "foorabbazmilb";**
- For inputString = **"foo(bar(baz))blim"**, the output should be **solution(inputString) = "foobazrabblim".** Because "foo(bar(baz))blim" becomes "foo(barzab)blim" and then "foobazrabblim".

**Input**
string inputString
A string consisting of lowercase English letters and the characters ( and ). It is guaranteed that all parentheses in inputString form a regular bracket sequence.
**Regular Bracket Sequence**
```
A bracket sequence is called regular if it is possible to insert some numbers and signs into the sequence in such a way that the new sequence will represent a correct arithmetic expression.
```
Guaranteed constraints:
**0 ≤ inputString.length ≤ 50**
**Output**
a string
Return inputString, with all the characters that were in parentheses reversed.
```sh
def solution(inputString):
    s = inputString
    if len(s) < 2:
        return s
    chars = list(s)
    open_bracket_indexes = []
    for i, c in enumerate(chars):
        if c == '(':
            open_bracket_indexes.append(i)
        elif c == ')':
            j = open_bracket_indexes.pop()
            chars[j:i] = chars[i:j:-1]
    return ''.join(c for c in chars if c not in '()')
 The idea of soultion is to search for '('and save its index, then if ')' is found, return reverse from index of '(' to index of')' 
 ```

# 14- alternatingSums
- Several people are standing in a row and need to be divided into two teams. The first person goes into team 1, the second goes into team 2, the third goes into team 1 again, the fourth into team 2, and so on. You are given an array of positive integers - the weights of the people. Return an array of two integers, where the first element is the total weight of team 1, and the second element is the total weight of team 2 after the division is complete.
<br>
Example

- For a = [50, 60, 60, 45, 70], the output should be **solution(a) = [180, 105].**
**Input**
array.integer a
Guaranteed constraints:
**1 ≤ a.length ≤ 105,**
**45 ≤ a[i] ≤ 100.**
**Output**
array.integer

My solution
```sh
def solution(a):
    team1 = [a[i] for i in range(len(a)) if (i % 2) == 0]
    team2 = [a[i] for i in range(len(a)) if (i % 2) != 0]
    
    return [sum(team1),sum(team2)]

```
