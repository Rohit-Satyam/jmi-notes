# Python as a calculator

Python is perfectly suited to do basic calculations. Apart from addition, subtraction, multiplication and division, there is also support for more advanced operations such as:

-   Exponentiation:  `**`. This operator raises the number to its left to the power of the number to its right. For example  `4**2`  will give  `16`.
-   Modulo:  `%`. This operator returns the remainder of the division of the number to the left by the number on its right. For example  `18 % 7`  equals  `4`.


# Extend a list

If you can change elements in a list, you sure want to be able to add elements to it, right? You can use the  `+`  operator:

```
x = ["a", "b", "c", "d"]
y = x + ["e", "f"]
```

# Delete list elements

Finally, you can also remove elements from your list. You can do this with the  `del`  statement:

```
x = ["a", "b", "c", "d"]
del(x[1])
```

The  `;`  sign is used to place commands on the same line. The following two code chunks are equivalent:

```
# Same line
command1; command2

# Separate lines
command1
command2
```
# Methods

To be absolutely clear: in Python, everything is an object, and each object has specific methods associated. Depending on the type of the object, list, string, float, whatever, the available methods are different. A string object like sister has a replace method, but a list like fam doesn't have this, as you can see from this error.


# String Methods

Strings come with a bunch of methods. Follow the instructions closely to discover some of them. If you want to discover them in more detail, you can always type  `help(str)`  in the IPython Shell.


Most list methods will change the list they're called on. Examples are:

-   [`append()`](https://docs.python.org/3/library/stdtypes.html#typesseq-mutable), that adds an element to the list it is called on,
-   [`remove()`](https://docs.python.org/3/library/stdtypes.html#typesseq-mutable), that removes the first element of a list that matches the input, and
-   [`reverse()`](https://docs.python.org/3/library/stdtypes.html#typesseq-mutable), that reverses the order of the elements in the list it is called on.

## Reverse Strings

To reverse strings (like pallindroms) we can use the following notation `[::-1]`.

```python
In [9]:
movie
Out[9]:
'oh my God! desserts I stressed was an ugly movie'
# Get the word
movie_title = movie[11:30]

# Obtain the palindrome
palindrome = movie_title[::-1]

# Print the word if it's a palindrome
if movie_title == palindrome:
	print(palindrome)
  
  #desserts I stressed
  ```
  
  ## Split strings
  
  To split string we use `my_string.split()` function (to split from left) or `my_string.rsplit()` to split from the right.
  
  ```python
  my_string = "This string is to be split"
  
  my_string.split(sep = " ")
  my_string.rsplit(sep = " ")
  
  ## maxsplit creates list of defined size. If this is not specified, both method split in same way. For example
  
  my_string.split(sep = " ", maxsplit=2)
  my_string.rsplit(sep = " ",maxsplit=2)
  
  # if string containes the \n character and if you wish to split by newline character or carriage space (\r), u can use newline split function as follows
  my_string = "This string is to\nbe split"
  my_string.splitlines()
  
  ## to remove the leading and the trailing whitespace we use .strip() function, .rstrip() to remove from right only and .lstrip to remove from left only.
  my_string = " This string is to be split\n"
  my_string.strip()
  #"This string is to be split"
  
  ## You can also strip special characters by specifying my_string.strip("$")
  
  ## the broken strings can be joined using
  # Join back together and print results
mystring_join = " ".join(mystring_no_comma)
  ```
  
