---
title: "Introduction"
pre: "1. "
weight: 10
---

{{< youtube Fn_iiG0wJR8 >}}
<!-- Old: 2xU3oUU7D0s -->
#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

As our Python programs continue to get larger and more complex, we may notice that we are reusing certain pieces of code over and over again. A great example is the loop structure to repeatedly get input from the user until a valid input is received. 

```python
x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
while(x < 0 or x > 1):
    print("Invalid Input!")
    x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
```

This is a very useful piece of code, and we can easily copy and paste it wherever we need it in our programs. Unfortunately, this means that anytime we want to update or change that code, we have to manually change every location where it is used in our programs. In a large program, this can be very tricky to do correctly without causing other errors in the code.

Thankfully, Python allows us to create small, repeatable blocks of code called **functions** that we can write once, and then use anywhere we'd like within our programs. We've already used many different functions in our programs, from the `print()` function used to display output to the user and the `input()` function used to get input from the user, all the way to the `random.randint()` function we've used to generate random numbers in our code.

Functions also allow us to break our larger programs up into smaller, easier to understand steps. This makes our code much easier to read, test, and debug. Learning how to build programs in terms of individual functions instead of just simple steps is a big part of becoming a more experienced programmer. So, in this lab, we're going to learn all about how to build, use, and test our own functions in Python. 

