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
An amazing solution
```sh
def solution(a):

    return [sum(a[::2]),sum(a[1::2])]
```
# 15- Add_Border
- Given a rectangular matrix of characters, add a border of asterisks to it.
Example
- For 
```
picture = ["abc",
           "ded"]
the output should be

solution(picture) = ["*****",
                      "*abc*",
                      "*ded*",
                      "*****"]
```

**Input**
array.string picture A non-empty array of non-empty equal-length strings.
Guaranteed constraints:
**1 ≤ picture.length ≤ 100,**
**1 ≤ picture[i].length ≤ 100.**
**Output**
array.string The same matrix of characters, framed with a border of asterisks of width 1

My solution
```sh
def solution(picture):
    top_bottom=len(picture[0])+2
    return ["*"*top_bottom]+[x.center(l,"*") for x in picture]+["*"*top_bottom]
```
# 16- Are Similar?
- Two arrays are called similar if one can be obtained from another by swapping at most one pair of elements in one of the arrays. Given two arrays a and b, check whether they are similar.
<br>
Example

- For a = [1, 2, 3] and b = [1, 2, 3], the output should be **solution(a, b) = true.**,  The arrays are equal, no need to swap any elements.
- For a = [1, 2, 3] and b = [2, 1, 3], the output should be **solution(a, b) = true.**, We can obtain b from a by swapping 2 and 1 in b.
- For a = [1, 2, 2] and b = [2, 1, 1], the output should be **solution(a, b) = false.**, Any swap of any two elements either in a or in b won't make a and b equal.
**Input**
1- Two array of integers a,b.

Guaranteed constraints:
**3 ≤ (a,b).length ≤ 105,**
**1 ≤ (a,b).[i] ≤ 1000.**
**Output**
boolean true if a and b are similar, false otherwise.

My solution
```sh
def solution(a, b):

    counter = 0
    for i in range(len(a)):
        if a[i] != b[i]:
            counter+=1
            if counter==3:
                return False
    
    if sorted(a)==sorted(b): 
        return True
    else:
        return False
    
```
# 17- arrayChange
- You are given an array of integers. On each move you are allowed to increase exactly one of its element by one. Find the minimal number of moves required to obtain a strictly increasing sequence from the input.
- For inputArray = [1, 1, 1], the output should be **solution(inputArray) = 3.**
**Input**
array.integer inputArray
Guaranteed constraints:
**3 ≤ inputArray.length ≤ 105,**
**-105 ≤ inputArray[i] ≤ 105.**
**Output**
Integer The minimal number of moves needed to obtain a strictly increasing sequence from inputArray.
It's guaranteed that for the given test cases the answer always fits signed 32-bit integer type.

My solution
```sh
def solution(inputArray):
    counter = 0
    for i in range(1, len(inputArray)):
        if inputArray[i] <= inputArray[i - 1]:
            counter = counter + inputArray[i - 1] - inputArray[i] + 1
            inputArray[i] = inputArray[i] + \
                inputArray[i - 1] - inputArray[i] + 1

    return counter
```

# 18- palindromeRearranging
- Given a string, find out if its characters can be rearranged to form a palindrome.
**Palindrome**
```
A string that doesn't changed when reversed (it reads the same backward and forward).
Examples:

"eye" is a palindrome
"noon" is a palindrome
"decaf faced" is a palindrome
"taco cat" is not a palindrome (backwards it spells "tac ocat")
"racecars" is not a palindrome (backwards it spells "sracecar")
```
- For inputString = "aabb", the output should be **solution(inputString) = true.**
We can rearrange "aabb" to make "abba", which is a palindrome.

**Input**
 string inputString:  A string consisting of lowercase English letters.

Guaranteed constraints:

**1 ≤ inputString.length ≤ 50.**

**Output**
boolean: true if the characters of the inputString can be rearranged to form a palindrome, false otherwise.

My solution
```sh
# Method 1
def solution(inputString):
    if len(inputString) == 1:
        return True

    i = 0
    counter = 0
    char_set_list = list(set(inputString))
    while(i<len(char_set_list)):
        if  inputString.count(char_set_list[i]) % 2 !=0 :
            counter+=1
        if counter == 2:
            return False
        i+=1
        
    return True
# Method 2
def solution(inputString):

    return sum([inputString.count(i)%2 for i in set(inputString)]) <= 1
```



# 19- areEquallyStrong

- Call two arms equally strong if the heaviest weights they each are able to lift are equal. Call two people equally strong if their strongest arms are equally strong (the strongest arm can be both the right and the left), and so are their weakest arms. Given your and your friend's arms' lifting capabilities find out if you two are equally strong.

Example
- For yourLeft = 10, yourRight = 15, friendsLeft = 15, and friendsRight = 10, the output should be **solution(yourLeft, yourRight, friendsLeft, friendsRight) = true;**
- For yourLeft = 15, yourRight = 10, friendsLeft = 15, and friendsRight = 10, the output should be **solution(yourLeft, yourRight, friendsLeft, friendsRight) = true;**
- For yourLeft = 15, yourRight = 10, friendsLeft = 15, and friendsRight = 9, the output should be **solution(yourLeft, yourRight, friendsLeft, friendsRight) = false.**
**Input** integer yourLeft, yourRight A non-negative integer representing the heaviest weight you can lift with your left arm.
Guaranteed constraints:
**0 ≤ yourLeft,yourRight ≤ 20.**

**Output**  boolean true if you and your friend are equally strong, false otherwise.

My solution
```sh
def solution(yourLeft, yourRight, friendsLeft, friendsRight):
    if max(yourLeft,yourRight) != max(friendsLeft, friendsRight):
        return False
    return yourLeft+yourRight == friendsLeft+friendsRight

```
# 20- arrayMaximalAdjacentDifference

- Given an array of integers, find the maximal absolute difference between any two of its adjacent elements.
Example
- For inputArray = [2, 4, 1, 0], the output should be **solution(inputArray) = 3.**
**Input**
array.integer inputArray

Guaranteed constraints:
**3 ≤ inputArray.length ≤ 10,**
**-15 ≤ inputArray[i] ≤ 15.**

**Output**

integer The maximal absolute difference.

My solution
```sh
def solution(inputArray):
    max_value = 0
    for i in range(0, len(inputArray) - 1):
        max_value = max(max_value, abs(inputArray[i] - inputArray[i + 1]))

    return max_value
```

# 21- isIPv4Address
An IP address is a numerical label assigned to each device (e.g., computer, printer) participating in a computer network that uses the Internet Protocol for communication. There are two versions of the Internet protocol, and thus two versions of addresses. One of them is the IPv4 address.


```
An identification number for devices connected to the internet. An IPv4 addresses written in dotted quad notation consists of four 8-bit integers separated by periods.

In other words, it's a string of four numbers each between 0 and 255 inclusive, with a "." character in between each number. All numbers should be present without leading zeros.

Examples:

192.168.0.1 is a valid IPv4 address
255.255.255.255 is a valid IPv4 address
280.100.92.101 is not a valid IPv4 address because 280 is too large to be an 8-bit integer (the largest 8-bit integer is 255)
255.100.81.160.172 is not a valid IPv4 address because it contains 5 integers instead of 4
1..0.1 is not a valid IPv4 address because it's not properly formatted
17.233.00.131 and 17.233.01.131 are not valid IPv4 addresses because they contain leading zeros
```

Example
- For inputString = "172.16.254.1", the output should be **solution(inputString) = true;**
- For inputString = "172.316.254.1", the output should be **solution(inputString) = false.** 316 is not in range [0, 255].

- For inputString = ".254.255.0", the output should be **solution(inputString) = false.** There is no first number.

**Input**
string inputString A string consisting of digits, full stops and lowercase English letters.
Guaranteed constraints:
**1 ≤ inputString.length ≤ 30**
**Output**
boolean true if inputString satisfies the IPv4 address naming rules, false otherwise.
****
My solution
```sh
def solution(inputString):

    arr = inputString.split('.')

    return len(arr) == 4 and all(
        i.isdigit() and 0 <= int(i) < 256 and not (
            len(i) > 1 and i[0] == "0") for i in arr)
```
# 22- avoidObstacles

You are given an array of integers representing coordinates of obstacles situated on a straight line. Assume that you are jumping from the point with coordinate 0 to the right. You are allowed only to make jumps of the same length represented by some integer. Find the minimal length of the jump enough to avoid all the obstacles.

Example
- For inputArray = [5, 3, 6, 7, 9], the output should be **solution(inputArray) = 4.**
Check out the image below for better understanding:
<br>

![image](https://user-images.githubusercontent.com/30151596/165720287-ab93d435-56d8-4e7c-b875-a74f1077d008.png)

**Input**
array.integer inputArray Non-empty array of positive integers.
**Output**
Guaranteed constraints:
**2 ≤ inputArray.length ≤ 1000,**
**1 ≤ inputArray[i] ≤ 1000.**
**Output**
integer

The desired length.<br>
My solution
```sh
def solution(inputArray):
    # inputArray.sort()

    for counter in range(2, max(inputArray) + 2):
        if sum([i % counter != 0 for i in inputArray]) == len(inputArray):
            return counter

```
# 23- Box Blur
Last night you partied a little too hard. Now there's a black and white photo of you that's about to go viral! You can't let this ruin your reputation, so you want to apply the [box blur algorithm](https://en.wikipedia.org/wiki/Box_blur) to the photo to hide its content.

The pixels in the input image are represented as integers. The algorithm distorts the input image in the following way: Every pixel x in the output image has a value equal to the average value of the pixel values from the 3 × 3 square that has its center at x, including x itself. All the pixels on the border of x are then removed.

Return the blurred image as an integer, with the fractions rounded down.<br>

Example
- For
```
image = [[1, 1, 1], 
         [1, 7, 1], 
         [1, 1, 1]]
```
the output should be **solution(image) = [[1]].**

To get the value of the middle pixel in the input 3 × 3 square: (1 + 1 + 1 + 1 + 7 + 1 + 1 + 1 + 1) = 15 / 9 = 1.66666 = 1. The border pixels are cropped from the final result.

- For
```
image = [[7, 4, 0, 1], 
         [5, 6, 2, 2], 
         [6, 10, 7, 8], 
         [1, 4, 2, 0]]
```

the output should be
```
solution(image) = [[5, 4], 
                  [4, 4]]
```
There are four 3 × 3 squares in the input image, so there should be four integers in the blurred output. To get the first value: (7 + 4 + 0 + 5 + 6 + 2 + 6 + 10 + 7) = 47 / 9 = 5.2222 = 5. The other three integers are obtained the same way, then the surrounding integers are cropped from the final result.


**Input**
 array.array.integer image An image, stored as a rectangular matrix of non-negative integers.
 
 Guaranteed constraints:
**3 ≤ image.length ≤ 100,**
**3 ≤ image[0].length ≤ 100,**
**0 ≤ image[i][j] ≤ 255.**


**Output**

array.array.integer A blurred image represented as integers, obtained through the process in the description.

```sh
def solution(image):
    import numpy as np
    arr = np.array(image)
    row, col = np.shape(arr)
    new_image = numpy.empty([row - 2, col - 2], dtype=int)
    for i in range(1, row - 1):
        for j in range(1, col - 1):
            new_image[i - 1][j - 1] = sum([arr[i + k][j + l]
                                          for k in [-1, 0, 1] for l in [-1, 0, 1]]) // 9

    return new_image

```
# 24- Minesweeper
In the popular Minesweeper game you have a board with some mines and those cells that don't contain a mine have a number in it that indicates the total number of mines in the neighboring cells. Starting off with some arrangement of mines we want to create a Minesweeper game setup.

<br>
Example
For
```
matrix = [[true, false, false],
          [false, true, false],
          [false, false, false]]
```
the output should be
```
solution(matrix) = [[1, 2, 1],
                       [2, 1, 1],
                       [1, 1, 1]]
```
Check out the image below for better understanding:

![image](https://user-images.githubusercontent.com/30151596/166096299-7fe24c3d-ce43-440e-99b7-93ce1ad03e9b.png)

**Input**
array.array.boolean matrix

A non-empty recta
ngular matrix consisting of boolean values - true if the corresponding cell contains a mine, false otherwise.

Guaranteed constraints:

**2 ≤ matrix.length ≤ 100,**
**2 ≤ matrix[0].length ≤ 100.**

**Output**

array.array.integer

Rectangular matrix of the same size as matrix each cell of which contains an integer equal to the number of mines in the neighboring cells. Two cells are called neighboring if they share at least one corner.

My solution

```sh
def solution(matrix):
    import numpy as np
    arr = np.array(matrix)
    row, col = np.shape(arr)
    result_arr = np.empty([row, col], dtype=int)

    for i in range(row):
        for j in range(col):
            va = sum([arr[i - k][j - l] for k in [-1, 0, 1] if i - k < row and i -
                     k >= 0 for l in [-1, 0, 1] if j - l < col and j - l >= 0])

            if arr[i][j]:
                va = va - 1
                result_arr[i][j] = va
            else:
                result_arr[i][j] = va
    return result_arr
```

# 25- Array Replace

Given an array of integers, replace all the occurrences of elemToReplace with substitutionElem.
- For inputArray = [1, 2, 1], elemToReplace = 1, and **substitutionElem = 3, the output should be
solution(inputArray, elemToReplace, substitutionElem) = [3, 2, 3].**
Exaple
**Input**
array.integer inputArray


Guaranteed constraints:
**0 ≤ inputArray.length ≤ 104,**
**0 ≤ inputArray[i] ≤ 109.**

**input** integer elemToReplace

Guaranteed constraints:
**0 ≤ elemToReplace ≤ 109.**

**input** integer substitutionElem

Guaranteed constraints:
**0 ≤ substitutionElem ≤ 109.**

**Output**
array.integer

```sh
import numpy as np
def solution(inputArray, elemToReplace, substitutionElem):            
    return [x if x != elemToReplace else substitutionElem for x in inputArray]
```











