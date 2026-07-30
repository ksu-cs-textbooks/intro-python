---
title: "Complex Statements"
pre: "5. "
weight: 50
---

{{< youtube aeIaYlNn6XQ >}}
<!-- Old: GIscaODlV8E -->
#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

Finally, let's look at how we can rewrite some of our previous Python programs by combining expressions into more complex statements. Python allows us to perform multiple actions on a single line of code, provided they can all be combined in some way to create a single statement.

Let's consider the example on the previous page, shown here:

```python
text_one = input("Enter the first number: ")
one = int(text_one)
text_two = input("Enter the second number: ")
two = int(text_two)
one = one * one
two = two * two
total = one + two
print(f"The sum of squares of {one} and {two} is {total}")
```

There are many ways we can write this program to perform the same work. For example, the process of computing the sum of squares itself can actually be reduced to a single line of code as seen below:

```python
total = (one * one) + (two * two)
```

We can perform multiple mathematical operations in a single expression, and as long as we either use parentheses or pay attention to the order of operations, we'll get the expected answer. We don't have to store the intermediate values in variables, since Python will do that for us when it evaluates the expression.

Likewise, we can put the `input()` function inside of the `int()` function, allowing us to read input as a string and convert it to an integer in a single line:

```python
one = int(input("Enter the first number: "))
two = int(input("Enter the second number: "))
total = (one * one) + (two * two)
print(f"The sum of squares of {one} and {two} is {total}")
```

Finally, we can also move the computation of the sum of squares directly into the f-string. When Python tries to print the f-string, the interpolation process must compute that value before it can print the output. 

```python
one = int(input("Enter the first number: "))
two = int(input("Enter the second number: "))
print(f"The sum of squares of {one} and {two} is {(one * one) + (two * two)}")
```

Functionally, this code will create the exact same output as the previous code, but it will do so using fewer variables and statements. Each statement is simply more complex, consisting of multiple expressions. 

## Concise and Readable

The real question is: which of these two examples is best? That is, which one is the preferred coding style to learn? The answer is that it really depends - both have their merits, and functionally they will work nearly identically on most modern computers and programming languages.

It really is a question of style - is it better to have more lines of code and variables, clearly spelling out what each step of the process is, or is it better to have shorter programs with more complex lines of code but maybe fewer variables? For beginning programmers, it is usually recommended to follow the first style, using as many variables as needed and focusing on short, concise lines of code over large, complex statements. 

However, as we become more accustomed to programming, we'll find that many times it is easier to read and understand complex statements, and our code can be written in a way that better reflects what it is actually doing. 

This is very similar to learning how to read, write, and speak in a new language. We must start with short, concise sentences, and slowly build up our knowledge of more complex statements and grammar rules until we become a fluent speaker. 

Overall, the best advice to follow is to make your code readable to both yourself and anyone else who may have to read and maintain the code. As long as it is clear what the code is doing based on what it says, it is probably a good style to follow. As we continue to learn more, we'll slowly refine our coding style to be one that is easy to follow and understand for everyone. 