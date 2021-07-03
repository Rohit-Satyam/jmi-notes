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
