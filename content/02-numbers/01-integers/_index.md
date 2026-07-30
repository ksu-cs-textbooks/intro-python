---
title: "Integers"
pre: "1. "
weight: 10
---

{{< youtube UhfUfBRwSPc >}}

<!-- Old: u7UKG-BAbGI -->
#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

So far, we've only worked with **string** values in Python. Strings are a very useful **data type** in programming languages such as Python, but they are very limited in their use. Recall that a **data type** simply defines how a particular value is stored in a computer. The **`str`** data type is used to store string values in Python. 

Python supports many different data types for handling various data that we'd like to store and manipulate in our programs. In this lab, we're going to cover the two basic types used for storing numbers in Python, the **`int`** or integer type, and the **`float`** or floating-point type. 

## Integers

In mathematics, an **integer** is a whole number, such as {{< math >}}$ 3 ${{< /math >}}, {{< math >}}$ -5 ${{< /math >}}, or even {{< math >}}$ 0 ${{< /math >}}. Basically, any positive or negative number that doesn't include a fractional or decimal portion is a whole number, and therefore it is an **integer**. In Python, those numbers can be stored in the **`int`** data type. 

In Python, we can store an integer value in a variable using an assignment statement:

```python
x = 5
```

That statement will store the integer value {{< math >}}$ 5 ${{< /math >}} in the variable `x`. Notice that the value {{< math >}}$ 5 ${{< /math >}} does not have quotation marks around it. This is because we want to store the integer value {{< math >}}$ 5 ${{< /math >}} and not the string value `"5"` in the variable. Also, as we learned earlier, this is why we cannot create variable names that begin with a number - since numerical values start with a number, this is how Python can tell the difference between a numerical value and a variable. 

We can also store negative numbers in a variable by placing a negative symbol `-` in front of the numerical value:

```python
y = -8
```

We'll need to be careful and make sure that there is a space after the equals sign `=`, but no space between the negative symbol `-` and the number after it. Otherwise, the negative symbol could be confused for the minus symbol, which is an operator that we'll learn about later in this lab.

In Python, there is effectively no maximum size for an integer, so we can store any arbitrarily large whole number (either positive or negative) in an `int` variable. 