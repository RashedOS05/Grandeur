---
publish: true
created: 2025-03-05T14:15:24.773+03:00
modified: 2026-05-27T01:04:46.435+03:00
---

## Lecture 0

_-#comments can be used as an outline for your code before starting to work on it_
-**backslash** `\` is an escape character. In layman terms, it tells the system that this piece of text isn't supposed to be doing its typical function0--0.
Ex: `\`  won't be considered text holders but a normal piece of text instead. Counterintuitively, it sometimes can be used the other way around; \n means that this isn't a normal piece of text but actually serves the function of starting a new line.
-Putting the letter **F** before the printing output indicates to python that the text in the quotation is special; allowing you to use functions like: `{}`, which is a recently added feature that allows you to output variables within quotations without having to print them out on their own.
-In python, multiple methods can be chained with dots
-using the .split method, you can assign the output to multiple variables at a time, ex:
`first, last = order.split(" ")`
This would assign the **' first '** variable to the segment before the splitting happens, and the **' last '** variable to the segment after the splitting. The splitting happens at the part that is decided by the user, which is a blank space in this example, but it can be a letter, a number, or anything else.
-def is used to defining functions
-within the function, you can include a default value for the parameters, ex: `function(num=1)`
-It's not necessary to have a main function in python, but it improves the quality of life when you define it at the very start of the file and then call it at the very end, as that will allow you to technically define the functions after they're called in code.

## Lecture 1

- Match has the same functionality as 'switch' from other languages, and its syntax for "or" is '|'. you don't need a break statement after each case, and putting 'case \_' replaces the 'default' from other languages.
-

## Lecture 2

-If you type for 'i' in range (3), the loop will iterate thrice, but 'i' is obsolete in the loop so it doesn't matter what you name it. The conventional naming for such variables is '\_'
-Combining while True: with a break statement within the loop makes the loop play infinitely as long as the break statement isn't triggered.

## Lecture 3

-Python handles exceptions with 'try' and 'except'
-Using else at the end of the exception handling is for when an exception isn't triggered
-The word 'pass' beneath 'except' makes the program catch the exception without doing anything with it (good for if you don't wanna do anything about the exception but just don't want the user to be jumpscared by it)

## Lecture 4

-[PyPI · The Python Package Index](https://pypi.org) goated for downloading libraries (but nowadays people just download stuff via the terminal itself)
-requests is a 3rd party library that allows for fetching data from APIs (insane)
-JSON library is another famous one for formatting JSON data nicely
-adding a conditional with "\_\_ name \_\_ " makes python not run the main function of an imported file

## Lecture 5

##### Assert:

Basically asserts to the code that something is true, and if it isn't, it returns an AssertionError

##### Pytest:

A 3rd party program for making testing codes easier and quicker (you have to type pytest instead of python in the terminal when testing).

##### with:

A keyword within pytest that when paired with pytest.raises(Error): makes sure that the test should be expecting that exception to occur without counting it as a failure.

##### \_\_ init \_\_ .py:

creating a file with this name within a folder tells Python to treat said folder as a package, making interactions between the files within the folder easier.

## Lecture 6

### Files  I / O :

#### Functions:

**Open:** A python function that allows you to open and then read information from a specific file.
_Ex: open("file.txt", "w")_
🔼 the "w" argument tells python to enable me to do changes within that file.
"a" would allow you to append at the end of the file instead of overwriting whatever's there (what "w" does).
**File.close():** Python's equivalent to Java's `Scanner.close()`
**However,** typing `with open("file.txt", "a") as file:` saves you the hassle of having to close it.
-Just like Java, reading all the texts within a text file can be done using a `for loop`.
**Lambda:** used to define and use a method on the spot (helpful for a one-time-use method).

#### CSV:

**Definition:** stands for _Comma-Seprated-Values_ which is a file that is commonly used to store info that are related within the same file, and is used a lot to transfer data to apps like Excel.
