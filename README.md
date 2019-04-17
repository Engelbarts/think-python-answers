# think_python
My answers to Think Python 2nd Edition excersises


## Exercise 1.1  
It is a good idea to read this book in front of a computer so you can try out the examples as you go.

Whenever you are experimenting with a new feature, you should try to make mistakes. For example, in the “Hello, world!” program, what happens if you leave out one of the quotation marks? What if you leave out both? What if you spell print wrong?

This kind of experiment helps you remember what you read; it also helps when you are programming, because you get to know what the error messages mean. It is better to make mistakes now and on purpose than later and accidentally.

In a print statement, what happens if you leave out one of the parentheses, or both?
If you are trying to print a string, what happens if you leave out one of the quotation marks, or both?
You can use a minus sign to make a negative number like -2. What happens if you put a plus sign before a number? What about 2++2?
In math notation, leading zeros are ok, as in 02. What happens if you try this in Python?
What happens if you have two values with no operator between them?
Exercise 2
Start the Python interpreter and use it as a calculator.

How many seconds are there in 42 minutes 42 seconds?
How many miles are there in 10 kilometers? Hint: there are 1.61 kilometers in a mile.
If you run a 10 kilometer race in 42 minutes 42 seconds, what is your average pace (time per mile in minutes and seconds)? What is your average speed in miles per hour?


```python
# TODO
```

## Exercise 2.1  
Repeating my advice from the previous chapter, whenever you learn a new feature, you should try it out in interactive mode and make errors on purpose to see what goes wrong.

* We’ve seen that n = 42 is legal. What about 42 = n?
* How about x = y = 1?
* In some languages every statement ends with a semi-colon, ;. What happens if you put a semi-colon at the end of a Python statement?
* What if you put a period at the end of a statement?
* In math notation you can multiply x and y like this: x y. What happens if you try that in Python?


```python
# TODO
```

## Exercise 2.2  
Practice using the Python interpreter as a calculator:

* The volume of a sphere with radius r is $4/3 π r3$. What is the volume of a sphere with radius 5?
* Suppose the cover price of a book is \\$24.95, but bookstores get a 40% discount. Shipping costs \\$3 for the first copy and 75 cents for each additional copy. What is the total wholesale cost for 60 copies?
* If I leave my house at 6:52 am and run 1 mile at an easy pace (8:15 per mile), then 3 miles at tempo (7:12 per mile) and 1 mile at easy pace again, what time do I get home for breakfast?


```python
# TODO
```

## Exercise 3.1  
Write a function named right_justify that takes a string named s as a parameter and prints the string with enough leading spaces so that the last letter of the string is in column 70 of the display.

<pre>
>>> right_justify('monty')
                                                                 monty
</pre>
Hint: Use string concatenation and repetition. Also, Python provides a built-in function called len that returns the length of a string, so the value of len('monty') is 5.


```python
def right_justify(word):
    nr_spaces = 70 - len(word)
    print(' ' * (nr_spaces - 1), word) # print adds a delimter ' '
```

## Exercise 3.2  
A function object is a value you can assign to a variable or pass as an argument. For example, do_twice is a function that takes a function object as an argument and calls it twice:

<pre>
def do_twice(f):
    f()
    f()
</pre>

Here’s an example that uses do_twice to call a function named print_spam twice.

<pre>
def print_spam():
    print('spam')

do_twice(print_spam)
</pre>

* Type this example into a script and test it.


```python
# TODO
```

* Modify do_twice so that it takes two arguments, a function object and a value, and calls the function twice, passing the value as an argument.


```python
# TODO
```

* Copy the definition of print_twice from earlier in this chapter to your script.


```python
# TODO
```

* Use the modified version of do_twice to call print_twice twice, passing 'spam' as an argument.


```python
# TODO
```

* Define a new function called do_four that takes a function object and a value and calls the function four times, passing the value as a parameter. There should be only two statements in the body of this function, not four.

Solution: http://thinkpython2.com/code/do_four.py.


```python
# TODO
```

## Exercise 3.3  
Note: This exercise should be done using only the statements and other features we have learned so far.

Write a function that draws a grid like the following:
<pre>
+ - - - - + - - - - +
|         |         |
|         |         |
|         |         |
|         |         |
+ - - - - + - - - - +
|         |         |
|         |         |
|         |         |
|         |         |
+ - - - - + - - - - +
</pre>
Hint: to print more than one value on a line, you can print a comma-separated sequence of values:

<pre>
print('+', '-')
</pre>

By default, print advances to the next line, but you can override that behavior and put a space at the end, like this:

<pre>
print('+', end=' ')
print('-')
</pre>

The output of these statements is '+ -' on the same line. The output from the next print statement would begin on the next line.

Write a function that draws a similar grid with four rows and four columns.
Solution: http://thinkpython2.com/code/grid.py. Credit: This exercise is based on an exercise in Oualline, Practical C Programming, Third Edition, O’Reilly Media, 1997.


```python
# TODO
```

## Casestudy Chapter 4

TODO

## Exercise 5.1  
The time module provides a function, also named time, that returns the current Greenwich Mean Time in “the epoch”, which is an arbitrary time used as a reference point. On UNIX systems, the epoch is 1 January 1970.

<pre>
>>> import time
>>> time.time()
1437746094.5735958
</pre>
Write a script that reads the current time and converts it to a time of day in hours, minutes, and seconds, plus the number of days since the epoch.


```python
# TODO
```

## Exercise 5.2

Fermat’s Last Theorem says that there are no positive integers a, b, and c such that

$a^n + b^n = c^n$

for any values of $n$ greater than 2.

Write a function named check_fermat that takes four parameters—a, b, c and n—and checks to see if Fermat’s theorem holds. If n is greater than 2 and

$a^n + b^n = c^n$

the program should print, “Holy smokes, Fermat was wrong!” Otherwise the program should print, “No, that doesn’t work.”


```python
def check_fermat(a, b, c, n):
    if not (a > 0 and b > 0 and c > 0):
        print('a, b and c must be greater than 0')
    elif n < 3:
        print('n must be greater than 2')
    elif a ** n + b ** n == c ** n:
        print('Holy smokes Fermat was wrong!')
    else:
        print('No. That does not work.')
```


```python
check_fermat(3, 4, 5, 3)
```

Write a function that prompts the user to input values for a, b, c and n, converts them to integers, and uses check_fermat to check whether they violate Fermat’s theorem.


```python
while True:
    a = input('a: ')
    a = int(a)
    b = input('b: ')
    b = int(b)
    c = input('c: ')
    c = int(c)
    n = input('n: ')
    n = int(n)
    check_fermat(a, b, c, n)

```

## Exercise 5.3

If you are given three sticks, you may or may not be able to arrange them in a triangle. For example, if one of the sticks is 12 inches long and the other two are one inch long, you will not be able to get the short sticks to meet in the middle. For any three lengths, there is a simple test to see if it is possible to form a triangle:

If any of the three lengths is greater than the sum of the other two, then you cannot form a triangle. Otherwise, you can. (If the sum of two lengths equals the third, they form what is called a “degenerate” triangle.)
Write a function named is_triangle that takes three integers as arguments, and that prints either “Yes” or “No”, depending on whether you can or cannot form a triangle from sticks with the given lengths.


```python
def is_triangle(a, b, c):
    if a > b + c:
        print('No.')
    elif b > a + c:
        print('No.')
    elif c > a + b:
        print('No.')
    else:
        print('Yes.')
```


```python
# Same function, shorter
def is_triangle(a, b, c):
    if a > b + c or b > a + c or c > a + b:
        print('No.')
    else:
        print('Yes.')
```


```python
is_triangle(1, 3, 5)
```

Write a function that prompts the user to input three stick lengths, converts them to integers, and uses is_triangle to check whether sticks with the given lengths can form a triangle.


```python
# TODO
```

## Exercise 5.4

What is the output of the following program? Draw a stack diagram that shows the state of the program when it prints the result.

<pre>
def recurse(n, s):
    if n == 0:
        print(s)
    else:
        recurse(n-1, n+s)

recurse(3, 0)
</pre>


```python
# TODO
```

What would happen if you called this function like this:

<pre>
recurse(-1, 0)?
</pre>

Write a docstring that explains everything someone would need to know in order to use this function (and nothing else).


```python
# TODO
```

The following exercises use the turtle module, described in Chapter 4:

## Exercise 5.5  
Read the following function and see if you can figure out what it does (see the examples in Chapter 4). Then run it and see if you got it right.

<pre>
def draw(t, length, n):
    if n == 0:
        return
    angle = 50
    t.fd(length*n)
    t.lt(angle)
    draw(t, length, n-1)
    t.rt(2*angle)
    draw(t, length, n-1)
    t.lt(angle)
    t.bk(length*n)
</pre>

Figure 5.2: A Koch curve.

## Exercise 5.6  
The Koch curve is a fractal that looks something like Figure 5.2. To draw a Koch curve with length x, all you have to do is

1. Draw a Koch curve with length x/3.
2. Turn left 60 degrees.
3. Draw a Koch curve with length x/3.
4. Turn right 120 degrees.
5. Draw a Koch curve with length x/3.
6. Turn left 60 degrees.
7. Draw a Koch curve with length x/3.

The exception is if x is less than 3: in that case, you can just draw a straight line with length x.

Write a function called koch that takes a turtle and a length as parameters, and that uses the turtle to draw a Koch curve with the given length.

Write a function called snowflake that draws three Koch curves to make the outline of a snowflake.
Solution: http://thinkpython2.com/code/koch.py.

The Koch curve can be generalized in several ways. See http://en.wikipedia.org/wiki/Koch_snowflake for examples and implement your favorite.


```python
TODO
```

## Exercise 6.1  
Draw a stack diagram for the following program. What does the program print?

<pre>
def b(z):
    prod = a(z, z)
    print(z, prod)
    return prod

def a(x, y):
    x = x + 1
    return x * y

def c(x, y, z):
    total = x + y + z
    square = b(total)**2
    return square

x = 1
y = x + 1
print(c(x, y+3, x+y))
</pre>


```python
# TODO
```

## Exercise 6.2  
The Ackermann function, A(m, n), is defined:

$ A(m, n) =
\begin{cases}
n+1 & \mbox{if } m = 0 \\
A(m-1, 1) & \mbox{if } m > 0 \mbox{ and } n = 0 \\
A(m-1, A(m, n-1)) & \mbox{if } m > 0 \mbox{ and } n > 0.
\end{cases}
$

See http://en.wikipedia.org/wiki/Ackermann_function.

Write a function named ack that evaluates the Ackermann function. Use your function to evaluate ack(3, 4), which should be 125. What happens for larger values of m and n? Solution: http://thinkpython2.com/code/ackermann.py.


```python
# TODO
```

## Exercise 3  
A palindrome is a word that is spelled the same backward and forward, like “noon” and “redivider”. Recursively, a word is a palindrome if the first and last letters are the same and the middle is a palindrome.

The following are functions that take a string argument and return the first, last, and middle letters:
<pre>
def first(word):
    return word[0]

def last(word):
    return word[-1]

def middle(word):
    return word[1:-1]
</pre>
We’ll see how they work in Chapter 8.

Type these functions into a file named palindrome.py and test them out. What happens if you call middle with a string with two letters? One letter? What about the empty string, which is written '' and contains no letters?
Write a function called is_palindrome that takes a string argument and returns True if it is a palindrome and False otherwise. Remember that you can use the built-in function len to check the length of a string.
Solution: http://thinkpython2.com/code/palindrome_soln.py.


```python
def first(word):
    return word[0]
```


```python
def last(word):
    return word[-1]
```


```python
def middle(word):
    return word[1:-1]
```


```python
def is_palindrome(word):
    if len(word) > 2:                           # If "word" has more than two characters
        if not is_palindrome(middle(word)):     # Recursively call is_palindrome for word
                                                # minus the first and the last character 
            return False                        # If the middle is not a palindrome neither
                                                # is the word, return False
    return first(word) == last(word)            # compare the first and last character of
                                                # word. Returns True or False
```


```python
# The same is_palidrome but without first/last/middle functions
def is_palindrome2(word):
    if len(word) > 2:
        if not is_palindrome2(word[1:-1]):
            return False
    return word[0] == word[-1]
```


```python
is_palindrome('palindrome')
```


```python
is_palindrome('redivider')
```

## Exercise 6.4  
A number, a, is a power of b if it is divisible by b and a/b is a power of b. Write a function called is_power that takes parameters a and b and returns True if a is a power of b. Note: you will have to think about the base case.


```python
# TODO
```

## Exercise 6.5  
The greatest common divisor (GCD) of a and b is the largest number that divides both of them with no remainder.

One way to find the GCD of two numbers is based on the observation that if r is the remainder when a is divided by b, then gcd(a, b) = gcd(b, r). As a base case, we can use gcd(a, 0) = a.

Write a function called gcd that takes parameters a and b and returns their greatest common divisor.

Credit: This exercise is based on an example from Abelson and Sussman’s Structure and Interpretation of Computer Programs.


```python
# TODO
```

## Exercise 7.1  
Copy the loop from Section 7.5 and encapsulate it in a function called mysqrt that takes a as a parameter, chooses a reasonable value of x, and returns an estimate of the square root of a.

To test it, write a function named test_square_root that prints a table like this:
<pre>
a   mysqrt(a)     math.sqrt(a)  diff
-   ---------     ------------  ----
1.0 1.0           1.0           0.0
2.0 1.41421356237 1.41421356237 2.22044604925e-16
3.0 1.73205080757 1.73205080757 0.0
4.0 2.0           2.0           0.0
5.0 2.2360679775  2.2360679775  0.0
6.0 2.44948974278 2.44948974278 0.0
7.0 2.64575131106 2.64575131106 0.0
8.0 2.82842712475 2.82842712475 4.4408920985e-16
9.0 3.0           3.0           0.0
</pre>
The first column is a number, a; the second column is the square root of a computed with mysqrt; the third column is the square root computed by math.sqrt; the fourth column is the absolute value of the difference between the two estimates.


```python
# TODO
```

Exercise 2  
The built-in function eval takes a string and evaluates it using the Python interpreter. For example:

>>> eval('1 + 2 * 3')
7
>>> import math
>>> eval('math.sqrt(5)')
2.2360679774997898
>>> eval('type(math.pi)')
<class 'float'>
Write a function called eval_loop that iteratively prompts the user, takes the resulting input and evaluates it using eval, and prints the result.

It should continue until the user enters 'done', and then return the value of the last expression it evaluated.


## Exercise 7.2  
The built-in function eval takes a string and evaluates it using the Python interpreter. For example:

<pre>
>>> eval('1 + 2 * 3')
7
>>> import math
>>> eval('math.sqrt(5)')
2.2360679774997898
>>> eval('type(math.pi)')
<class 'float'>
</pre>
Write a function called eval_loop that iteratively prompts the user, takes the resulting input and evaluates it using eval, and prints the result. It should continue until the user enters 'done', and then return the value of the last expression it evaluated.


```python
def eval_loop():
    value = None                  # Initialize value variable
    while True:
        cmd = input('> ')
        if cmd == 'done':         # If command is 'done' 
            print(value)          # Print last return value
            break                 # break loop
        value = eval(cmd)         # evaluate command and save returned value
```


```python
eval_loop()
```

## Exercise 7.3  
The mathematician Srinivasa Ramanujan found an infinite series that can be used to generate a numerical approximation of 1 / π:

$\frac{1}{\pi} = \frac{2\sqrt 2}{9801} \sum^\infty_{k=0} \frac{(4k)!(1103+26390k)}{(k!)^4 396^{4k}}.$
 
Write a function called estimate_pi that uses this formula to compute and return an estimate of π. It should use a while loop to compute terms of the summation until the last term is smaller than 1e-15 (which is Python notation for 10−15). You can check the result by comparing it to math.pi.


```python
# TODO
```

## Exercise 8.1  
Read the documentation of the string methods at http://docs.python.org/3/library/stdtypes.html#string-methods. You might want to experiment with some of them to make sure you understand how they work. strip and replace are particularly useful.

The documentation uses a syntax that might be confusing. For example, in find(sub[, start[, end]]), the brackets indicate optional arguments. So sub is required, but start is optional, and if you include start, then end is optional.

TODO

## Exercise 8.2  
There is a string method called count that is similar to the function in Section 8.7. Read the documentation of this method and write an invocation that counts the number of a’s in 'banana'.

TODO

## Exercise 8.3  
A string slice can take a third index that specifies the “step size”; that is, the number of spaces between successive characters. A step size of 2 means every other character; 3 means every third, etc.
<pre>
>>> fruit = 'banana'
>>> fruit[0:5:2]
'bnn'
</pre>

A step size of -1 goes through the word backwards, so the slice [::-1] generates a reversed string.

Use this idiom to write a one-line version of is_palindrome from Exercise 3.

TODO

## Exercise 8.4  
The following functions are all intended to check whether a string contains any lowercase letters, but at least some of them are wrong. For each function, describe what the function actually does (assuming that the parameter is a string).
<pre>
def any_lowercase1(s):
    for c in s:
        if c.islower():
            return True
        else:
            return False
</pre>

TODO

<pre>
def any_lowercase2(s):
    for c in s:
        if 'c'.islower():
            return 'True'
        else:
            return 'False'
</pre>

TODO

<pre>
def any_lowercase3(s):
    for c in s:
        flag = c.islower()
    return flag
</pre>

TODO

<pre>
def any_lowercase4(s):
    flag = False
    for c in s:
        flag = flag or c.islower()
    return flag
</pre>

TODO

<pre>
def any_lowercase5(s):
    for c in s:
        if not c.islower():
            return False
    return True
</pre>

TODO

## Exercise 8.5. 

A Caesar cypher is a weak form of encryption that involves “rotating” each letter by
a fixed number of places. To rotate a letter means to shift it through the alphabet, wrapping around
to the beginning if necessary, so ’A’ rotated by 3 is ’D’ and ’Z’ rotated by 1 is ’A’.
To rotate a word, rotate each letter by the same amount. For example, “cheer” rotated by 7 is “jolly”
and “melon” rotated by -10 is “cubed”. In the movie 2001: A Space Odyssey, the ship computer
is called HAL, which is IBM rotated by -1.


Write a function called rotate_word that takes a string and an integer as parameters, and returns
a new string that contains the letters from the original string rotated by the given amount.
You might want to use the built-in function ord, which converts a character to a numeric code, and chr, which converts numeric codes to characters. Letters of the alphabet are encoded in alphabetical
order, so for example:

<pre>
>>> ord('c') - ord('a')
2
</pre>

Because 'c' is the two-eth letter of the alphabet. But beware: the numeric codes for upper case
letters are different.


```python
def rotate_word(word, count):
    retStr = ''
    for letter in word:
        if letter.islower():
            start = ord('a')                       # The lowercase alphabet starts at ord('a')
        else:
            start = ord('A')                       # The uppercase alphabet starts at ord('A') 
        new_letter = ord(letter) - start           # Determine the alphabet index for letter
        new_letter = (new_letter + count) % 26     # Determine the new index, roll-over using modulo 26
        retStr = retStr + chr(start + new_letter)  # Add the offset of start and convert to char
    return retStr
```


```python
print('Melon rotated by -10 is', rotate_word('Melon', -10))
```

    Melon rotated by -10 is Cubed



```python
print('Cheer rotated by 7 is', rotate_word('Cheer', 7))
```

    Cheer rotated by 7 is Jolly



```python
print('IBM rotated by -1 is', rotate_word('IBM', -1))
```

    IBM rotated by -1 is HAL


## Casestudy Chapter 9

TODO

## 10.1

Write a function called nested_sum that takes a list of lists and adds up the elements of all the nested lists.


```python
def nested_sum_1(t):
    retVal = 0
    for elem in t:
        retVal += sum(elem)
    return retVal
```


```python
def nested_sum(t):
    retVal = 0
    for elem in t:
        if isinstance(elem, list):
            retVal += nested_sum(elem)
        elif isinstance(elem, int):
            retVal += elem
        else:
            pass # element is not an integer or list
    return retVal
```


```python
t = [[1,[2, 3]], 'pipo', 3, [4, [5, [6, 7]]]]
```


```python
nested_sum(t)
```




    31



## 10.2

Write a function called cumsum that takes a list of numbers and returns the cumulative sum; that is a new list where the ith element is the sum of the first i+1 elements from the original list. For example:
<pre>
>>> t = [1, 2, 3]
>>> cumsum(t)
[1, 3, 6]
</pre>



```python
def cumsum(t):
    retList = []
    for i in range(len(t)):
        print(t[:i+1])
        retList.append(sum(t[:i+1]))
    return retList
```


```python
cumsum([1, 2, 3])
```

    [1]
    [1, 2]
    [1, 2, 3]





    [1, 3, 6]



## 10.3

Write a function called middle that takes a list and returns all but the first and last elements. For example:
<pre>
>>> t = [1, 2, 3, 4]
>>> middle(t)
[2, 3]
</pre>


```python
def middle(t):
    return t[1:-1]
```


```python
t = [1, 2, 3, 4]
```


```python
middle(t)
```




    [2, 3]




```python
t
```




    [1, 2, 3, 4]



## 10.4

Write a function called chop that takes a list, modifies it by removing the first and last elements and returns None. For example:
<pre>
>>> t = [1, 2, 3, 4]
>>> chop(t)
>>> t
[2, 3]
</pre>


```python
def chop(t):
    del t[0], t[-1]
```


```python
t = [1, 2, 3, 4]
```


```python
print(chop(t))
```

    None



```python
t
```




    [2, 3]



## 10.5

Write a function called is_sorted that takes a list as a parameter and returns True if the list is sorted in ascending order and False otherwise. For example:
<pre>
>>> is_sorted([1, 2, 2])
True
>>> is_sorted(['b', 'a'])
False
</pre>


```python
def is_sorted(t):
    t1 = sorted(t)
    return t1 == t
```


```python
is_sorted([1, 2, 3])
```




    True



## 10.6

Two words are anagrams if you can rearrange the letters from one to spell the other. Write a function is_anagram that takes two strings and returns True if they are anagrams.


```python
def is_anagram(s1, s2):
    return sorted(s1.lower()) == sorted(s2.lower())
```


```python
is_anagram('Pipo', 'Opip')
```




    True



## 10.7

Write a function called has_duplicates that takes a list and returns True if there is any element that appears more than once. It should not modify the original list.


```python
def has_duplicates(t):
    t1 = sorted(t)
    for i in range(1, len(t1)):
        if t1[i] == t1[i-1]:
            return True
    return False # This is not required ...    
```


```python
has_duplicates([1, 2, 3, 3])
```




    True



## 11.1

Write a function that reads the words in words.txt and stores them as keys in a dictionary


```python
def read_words():
    wordlist = {}
    with open('words.txt', 'r') as file_in:
        for line in file_in:
            wordlist[line.strip()] = None
    return wordlist
```


```python
wordlist = read_words()
```

## 11.5

Write a program that finds all the rotate pairs in wordlist.



```python
def find_rotate_pairs(wordlist):
    for key in wordlist:
        for i in range(1, 14):
            rotated = rotate_word(key, i)
            if rotated in wordlist:
                print(key, i, rotated)

```


```python

```
