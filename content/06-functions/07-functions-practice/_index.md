---
title: "Functions Practice"
pre: "7. "
weight: 70
---

Let's try some simple practice problems. These problems are not graded - they are just for you to practice before doing the real exercises in the lab itself. You can find the answers below each question by clicking the button below each question.

#### 6.1 Reading Code

Write the output that is displayed to the user after running the following Python program:

```python
def foo(word):
    print(word, end=" ")


def bar(word1, word2, word3):
    foo(word1)
    foo(word2)
    print("don't make a", end=" ")
    print(word3)


def main():
    bar("two", "wrongs", "right")


main()
```

{{% expand "Answer" %}}

{{% notice primary "6.1 Answer" "check" %}}

The correct answer is:

```tex
two wrongs don't make a right
```

{{% /notice %}}

{{% /expand %}}


#### 6.2 Writing Code

Construct a **function** (not an entire program) that meets the following specification. When the function is called using this line of code:

```python
fun("s", "e", "l", "r")
```

it should produce the following output:

```tex
seller
```

When the same function is called using this line of code:

```python
fun("p", "i", "p", "n")
```

it should produce the following output:

```tex
pippin
```

{{% expand "Answer" %}}

{{% notice primary "6.2 Answer" "check" %}}

One possible answer is shown below:

```python
def fun(one, two, three, four):
    print(one, end="")
    print(two, end="")
    print(three, end="")
    print(three, end="")
    print(two, end="")
    print(four, end="")
```

There are many possible answers!

{{% /notice %}}

{{% /expand %}}

#### 6.3 Writing Code

Write a **complete program** in Python that meets the following specification:

1. It should include a function named `display` that requires a single parameter. When run, that function should print the value of the parameter to the terminal, but without a newline character at the end.
1. It should include a function named `square` that will call the `display` function multiple times to create an ASCII art square as shown in the output example below. The `square` procedure **may not** use the `print(expression)` statement directly - it must call the `display` function to produce output.  
1. It should include a `main` function that only calls the `square` function.
1. It should call the `main` function at the end of the code to start the program.

When the program is run, it should produce the following output:

```
* * * *
* * * *
* * * *
* * * *
```

{{% expand "Answer" %}}

{{% notice primary "6.3 Answer" "check" %}}

One possible solution is given below:

```python
def display(line):
    print(line, end="")


def square():
    display("* * * *\n")
    display("* * * *\n")
    display("* * * *\n")
    display("* * * *\n")


def main():
    square()


main()
```

Many others are possible!

{{% /notice %}}

{{% /expand %}}

