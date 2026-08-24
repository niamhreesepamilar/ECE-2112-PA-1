# ECE-2112-PA-1
**Submitted by: Niamh Reese B. Pamilar | 2ECE-C**
**Date Submitted: September 25, 2026**

This repository contains Programming Assignment 1 for the course **ECE 2112: Advanced Computer Programming and Algorithms**. The assignment, titled **Experiment 1: Introduction to Python Programming**, consists of three Python problems that apply basic functions, operators, string operations, slicing, string methods, and sequence unpacking.

**Objectives:**
By the end of this activity, students should be able to:
1. use basic Python functions, operators, and string operations;
2. manipulate strings through indexing, slicing, and built-in methods;
3. apply sequence unpacking to manipulate list elements; and
4. create simple Python functions that return specified results.

## A. Word Rotation Problem
Create a function named `rotate_word()` that accepts a non-empty string. The function moves the first character of the string to the end while preserving the order and capitalization of the remaining characters.

The following functions and methods were used in this problem:
- `text[1:]`  - uses string slicing to select every character beginning at index `1`, which is the second character, up to the end of the string. 
    Example: `"electronics"[1:]` returns `"lectronics"`.
- `text[0]` - uses string indexing to select the first character of the string. 
    Example: `"electronics"[0]` returns `"e"`.

These operations were combined in one function:
```python
def rotate_word(text):
    return text[1:] + text[0]
```

The function was tested using the required examples:
```python
print(rotate_word("python"))
print(rotate_word("logic"))
print(rotate_word("Code"))
print(rotate_word("A"))
```

Output:
```text
ythonp
ogicl
odeC
A
```

For a one-character string such as `"A"`, `text[1:]` produces an empty string. Adding the original first character returns `"A"`, so the function still produces the correct result.

## B. Username Builder Problem
Create a function named `make_username()` that accepts a first name and a last name. The function converts both names to lowercase, removes all spaces, and joins the processed names with one period (`.`).

The following string methods and operations were used in this problem:
- `.lower()` - converts every letter in a string to lowercase.
    Example: `"Niamh Reese".lower()` returns `"niamh reese"`.
- `.replace(" ", "")` - replaces every space with an empty string, which removes all spaces from the name.
    Example: `"niamh reese".replace(" ", "")` returns `"niamhreese"`.
- `+` - combines the cleaned first name, one period and the cleaned last name into a single username.
    Example: `"niamhreese" + "." + "pamilar"`.

The processed names were first stored in the variables `clean_first` and `clean_last`. They were then joined to form the completed username:
```python
def make_username(first_name, last_name):
    clean_first = first_name.lower().replace(" ", "")
    clean_last = last_name.lower().replace(" ", "")
    return clean_first + "." + clean_last
```

The function was tested using the required examples:
```python
print(make_username("Ada", "Lovelace"))
print(make_username("Alan", "Turing"))
print(make_username("Ana Maria", "De Leon"))
```

Output:
```text
ada.lovelace
alan.turing
anamaria.deleon
```

## C. Bookend Swap Problem
Create a function named `swap_bookends()` that accepts a list containing at least two elements. The function exchanges the first and last elements while keeping all middle elements in their original order. It returns a new list without modifying the input list.

Extended sequence unpacking was used to divide the list into three variables:
```python
first, *middle, last = items
```

Each variable receives the following part of the list:
- `first` - stores the first element.
- `*middle` - collects all elements between the first and last elements into a list.
- `last` - stores the last element.

For example, if `items = [1, 2, 3, 4, 5, 6]`, the unpacked values are:
```python
first = 1
middle = [2, 3, 4, 5]
last = 6
```

The expression `[last] + middle + [first]` constructs a new list in the required order. Square brackets are placed around `last` and `first` so that all three values being joined are lists.

Combining these operations gives the final function:
```python
def swap_bookends(items):
    first, *middle, last = items
    return [last] + middle + [first]
```

The function was tested using the required examples:
```python
print(swap_bookends([1, 2, 3, 4, 5, 6]))
print(swap_bookends(["red", "green", "blue"]))
print(swap_bookends([8, 3]))
```

Output:
```text
[6, 2, 3, 4, 5, 1]
['blue', 'green', 'red']
[3, 8]
```

When the input contains only two elements, `middle` becomes an empty list. The first and last elements are still exchanged correctly.

## Jupyter Notebook

To view the complete Python program for Programming Assignment 1, open or download ___. Open the file in Jupyter Notebook and select **Run All** to execute every cell.

Thank you for reading!
