---
title: "Main Function"
pre: "3. "
weight: 30
---

{{< youtube NquM9CD3y10 >}}
<!-- Old: Jv59-FW3UOY -->
<!-- Older: eLcFDbHMIKU -->

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

Let's review a couple other concepts related to functions in Python.

## Main Function

We can also create a **`main` function** in Python. The use of a `main` function in Python is not required at all - Python is designed as a scripting language, meaning we can write code directly in a Python file without using any functions at all. However, it is generally considered good practice to make sure all code is part of a function, and then we can include a `main` function as the starting point for any program.

So, we can update the example we saw previously to include a `main` function by simply placing the three function calls in a new function called `main`, and then including a call to the `main` function at the bottom of the program:

```python
def foo():
    print("eye")


def bar():
    print("to")


def main():
    foo()
    bar()
    foo()


main()
```

From here on out in this course, we'll follow this convention in our complete Python programs. Specifically:

1. All programs must contain a function named `main` as the starting point of the program.
1. All code in a program must be contained within a function, with the exception of a single call to the `main` function at the bottom of the program.

This will make our Python programs easy to follow, and it will help us later on down the road if we choose to learn another language such as Java or C# that requires a main function.