---
title: "Using Print"
pre: "4. "
weight: 40
---

{{< youtube HlwOm4rAVVM >}}

<!-- Old: HLkbubuv4sE -->
<!-- Older: BhpTb-i4ELg -->

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

One important key to remember: by default, the `print(expression)` statement in Python will add a newline to the end of the output by default. This means that multiple `print(expression)` statements will print on multiple lines. Let's look at some examples!

Throughout this course, we'll show many different code examples and their output here in the lab. To test them out, feel free to copy the code examples to a Python file and run it yourself. You can even tweak them to do something new and see how Python interprets different pieces of code. In the end, the best way to learn programming is to explore, and running these examples on your own is a great way to get started!

## Example 1 - Multiple Statements

First, let's write a simple program that prints 4 letters separated by spaces:

```python
print("a b c d")
```

Just like our "Hello World" program, when we run this program, we'll see that string printed in the user interface:

```tex
a b c d
```

Ok, that makes sense based on what we've previously seen. The `print(expression)` statement will simply display any string expression in our user interface.

Of course, programs can consist of multiple statements or lines of code. So, what if we write a program that contains multiple `print(expression)` statements, like this one:

```python
print("one")
print("two")
print("three")
print("four")
```

What do you think will happen when we try to execute this program on our "mental model?" Have we learned a rule that tells us what should happen yet? Recall on the previous page we learned that it will print the value on the user interface, but that's it. So, when we execute this program, we'll see the following output:

```tex
one
two
three
four
```

That's a very interesting result! We can see that four separate `print(expression)` statements will generate four lines of output by default. Each statement is printed on its own line. So, in Python we can print multiple lines of output simply by using multiple `print(expression)` statements!

## Example 2 - Multiple Lines from Single Statement

What if we want to print output on multiple lines using a single `print(expression)` statement? How can we do that? In this case, we need to introduce a special symbol, the **newline** symbol. In most programming languages, the newline symbol is represented by a backslash followed by the letter "n", like `\n`, in a string. When our user interface sees a newline symbol, it will move to the next line before printing the rest of the string. The newline symbol itself won't appear in our output.

For example, we can update our previous program to contain newline symbols between each letter:

```python
print("a\nb\nc\nd")
```

This might be a bit difficult to read at first, but as we become more and more familiar with reading code, we'll start to see special symbols like the newline symbol just like any other letter. For now, we'll just have to read closely and make sure we are on the lookout for special symbols in our text.

When we run this program, we should see the following output on our user interface:

```tex
a
b
c
d
```

There we go! We've now figured out how to print text on multiple lines using a single `print(expression)` statement.

## Example 3 - Multiple Statements on Same Line

What if we want to display multiple `print(expression)` statements on the same line? To do that, we must add an additional option to the `print(expression)` statement - the `end` option. 

For example, the following code will produce output all on the same line:

```python
print("Hello ", end="")
print("World!")
```

In this example, we set `end` to be an empty string `""`. When we run this program, we'll get the following output:

```tex
Hello World!
```

In fact, in Python, the `print(expression)` statement is an example of a **function** in Python. **Functions** are just repeatable procedures in our code - when we use them, we write the name of the function, followed by a set of parentheses and then inputs, or "arguments," separated by commas within the parentheses. This is known as "calling" a function. So, in actuality, the `expression` in the `print(expression)` statement is just the first argument when we call the `print` function. 

Therefore, the `end` option that we showed above is just a second argument that is optional - it simply lets us choose what to put at the end of the output. By default, the `end` parameter is set to the newline symbol `\n`, so if we don't provide an argument for `end` it will just add a newline at the end of the value.

We can set the value of `end` to be any string. If we want to include a space at the end of the output, we can add `end=" "` to the `print` function call. 

In this course, we won't spend much time talking about optional parameters and default values in Python functions, but it is important to understand that statements like `print` are actually just Python functions behind the scenes!