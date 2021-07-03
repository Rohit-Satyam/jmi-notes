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
