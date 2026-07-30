---
title: "Floats"
pre: "2. "
weight: 20
---

{{< youtube  RKkdKIl--BE >}}
<!-- Old: 1Zy_rkTbwow -->

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

The other type of number we can store in Python is a **floating-point** number. We won't go into too much detail about floating-point values here, since you'll learn about them elsewhere in this class. For the purposes of programming, the only thing to know about floating-point numbers is that they are used to represent numbers that include a fractional or decimal portion. In Python, these values are stored in the **`float`** data type. 

To create a variable that stores a floating-point value in Python, we can use an assignment statement that includes a value with a decimal point, like this:

```python
a = 5.8
```

We can also create negative values using the negative symbol `-`:

```python
b = -7.987
```

Finally, it is possible to store a whole number in a floating-point value by simply adding a decimal point and a `0` at the end of the value, as in this example:

```python
c = 42.0
```

Later in this lab, we'll see a couple of situations where that may be useful.

For now, we're just going to assume that Python can easily handle any reasonable number we want it to store in a `float` variable, but there are some limits to the size and accuracy of those numbers. To reach these limits, we usually have to be dealing with numbers that have {{< math >}}$ 100 ${{< /math >}} or more digits, either before or after the decimal place. So, for the purposes of this class, those limits really won't apply to what we're doing. You'll learn about these limits in detail in later programming classes.