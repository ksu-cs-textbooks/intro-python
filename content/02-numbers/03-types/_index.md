---
title: "Types"
pre: "3. "
weight: 30
---

{{< youtube 7Jz-hDTgerM >}}
<!-- Old: sYEgJljj2K0 -->

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

## Determining Variable Type

One thing that is very useful to know how to do in Python is determining the type of data stored in a variable. Python is very flexible, and we can store any type of data in any variable. In fact, a variable's data type can even change in Python, which is something that many other programming languages won't allow. Technically speaking, we would say that Python uses **strong typing**, which means that each variable has a known data type that we can find, and **dynamic typing**, meaning that the type of the variable can change while the program is running. 

To determine the type of a variable, we can use the `type(expression)` function in Python. We can simply place any variable or expression in the `expression` argument, and then it will tell us the type of the value that results from evaluating that expression. Then, we can simply use the `print()` function to print it to the screen. We won't use this in our programs themselves, but it can be helpful for debugging purposes or to just better understand what is going on with data types.

Here's a quick example program showing the `type()` function in Python:

```python
x = "Hello"
y = 5
z = 6.7
print(type(x))
print(type(y))
print(type(z))
```

When we execute this code in Python, we should see the following output:

```tex
<class 'str'>
<class 'int'>
<class 'float'>
```

Based on that output, we can assume that the variable `x` is the `str` data type for strings, `y` is the `int` data type for whole numbers, and `z` is the `float` data type for decimal numbers. The `type()` function is pretty handy!

## Converting Between Data Types

We can also convert values between the various data types in Python. To do this, there are special functions that match the name of the data types themselves. So, to convert any value to a string, we can use the `str()` function. Likewise, to convert anything to an integer, we can use the `int()` function. And finally, to convert anything to a floating-point value, we can use the `float()` function.

So, we can extend the previous example a bit by showing how we can convert values between different data types:

```python
x = "5.7"
print(x)
print(type(x))
print()
y = float(x)
print(y)
print(type(y))
print()
z = int(y)
print(z)
print(type(z))
```

When we run this program, we'll get this output:

```tex
5.7
<class 'str'>

5.7
<class 'float'>

5
<class 'int'>
```

In this program, we're starting with the string value `"5.7"` stored in variable `x`. So, the first two `print()` statements will print that string value, and show that `x` is indeed storing a `str` data type. Then, we'll use the `float()` function to convert the string value `"5.7"` stored in `x` to the floating-point value {{< math >}}$ 5.7 ${{< /math >}} and store that in `y`. The next two print statements will print that value, and show that `y` is storing a `float` data type. Notice that the value printed for both variables `x` and `y` looks identical, but the data type of each variable is different!

Finally, we can use the `int()` function to convert the floating-point value {{< math >}}$ 5.7 ${{< /math >}} to an integer. In math, when we are asked to convert the number {{< math >}}$ 5.7 ${{< /math >}} to a whole number, our first instinct is probably to just round up to {{< math >}}$ 6 ${{< /math >}}, since that is the closest value. However, in Python, as in most other programming languages, this function will simply **truncate** the value instead. **Truncating** a value simply means we take off the end of the value, so to convert {{< math >}}$ 5.7 ${{< /math >}} to an integer we just remove the decimal portion, and we're left with the value {{< math >}}$ 5 ${{< /math >}}. So, in the output above, we see that `z` stores the integer value {{< math >}}$ 5 ${{< /math >}}, and it is the `int` data type.

Notice that we are careful to say that the `int()` function will **truncate** the value, and not that it will round down. This is due to how Python handles negative numbers like {{< math >}}$ -5.7 ${{< /math >}}. When converting that to an integer, it will also truncate it to {{< math >}}$ -5 ${{< /math >}} instead of rounding down to {{< math >}}$ -6 ${{< /math >}}. So, we use the word **truncate** as the best way to describe the `int()` function.

## Exceptions

Since we are running our Python programs on a real computer, we have to be a bit careful about how we use these functions. Specifically, if we try to convert a value to a different data type and Python can't figure out how to do that, we'll cause an **exception** to occur. An **exception** in programming is any error that happens when the computer tries to run our code. 

For example, what if we try to convert the string value `"5.7"` directly to an `int` data type, as in this example:

```python
a = "5.7"
print(a)
print(type(a))
print()
b = int(a)
print(b)
print(type(b))
```

When we try to run this code in a file, such as the `tutor.py` file shown here, we'll see this output printed on the terminal:

```tex
5.7
<class 'str'>

Traceback (most recent call last):
  File "tutor.py", line 5, in <module>
    b = int(a)
ValueError: invalid literal for int() with base 10: '5.7'
```

Uh oh! That's not good. In the output, we can see that we've caused a `ValueError`, which is an exception that happens when we try to use a value in an incorrect way. So, we'll need to carefully look at our code to see if we can find and fix the error.

Thankfully, in the output, it will tell us that the error occurred on line 5 of the file `tutor.py`, so we can open that file and scroll to that line of code:

```python
b = int(a)
```

This is where the error occurred. There are several ways we can fix it. The easiest would be to simply convert `a` to a floating-point value using the `float()` function instead.

Learning how to find and fix these exceptions is a key part of learning how to program. We'll inevitably run into a few exceptions as we start to build larger and more complex programs. In this course, most exceptions can be easily handled simply by working carefully through the code, but every once in a while we may run into an exception that is truly difficult to solve. That's one of the important things to remember when learning how to program - it is sometimes much easier to cause an exception than it is to figure out how to fix it, and sometimes you may need to reach out for help to get past a particularly tricky exception. So, don't be afraid to ask the instructors or TAs for help if you get stuck on an exception. Many times, it's a great chance for you to learn some new programming skills. 