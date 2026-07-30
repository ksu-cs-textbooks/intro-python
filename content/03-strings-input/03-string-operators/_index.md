---
title: "String Operators"
pre: "3. "
weight: 30
---

{{< youtube ZXUk67wLdiY >}}
<!-- Old: k14bakCbKTw -->
#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

## Concatenate

Python includes an operator that can be used to concatenate, or combine, two strings together, one after another. We can use the plus symbol `+` between two strings to concatenate them together into a single string, making it much simpler to build more complex strings and outputs. 

A simple example is shown below:

```python
first = "Hello"
second = "World"
print(first + second)
```

When executed, this code will display this output:

```tex
HelloWorld
```

As we can see, using the `+` operator in Python to concatenate two strings together is a quick and easy way to simplify our print statements.

## Concatenating Numbers

Python also requires both sides of the `+` operator to be strings in order for concatenation to work. So, if we want to concatenate a string with a numeric value, we'll have to convert it to a string using the special `str()` function. Here's an example:

```python
text = "Your total is $"
value = 2.75
print(text + str(value))
```

When we run this program, we'll receive the following output:

```tex
Your total is $2.75
```

However, if we forget to convert the `value` variable to a string, as in this example:

```python
text = "Your total is $"
value = 2.75
print(text + value)
```

we'll receive an error instead:

```tex
Traceback (most recent call last):
  File "tutor.py", line 3, in <module>
    print(text + value)
TypeError: must be str, not float
```

So, we'll have to be careful and make sure that we convert all of our numbers to strings before trying to concatenate them together. Of course, if both sides of the `+` operator are numbers, then it will perform addition instead of concatenation!

## Repeat

Python also includes an operator that allows us to quickly repeat strings. We can use the asterisk `*` operator to effectively "multiply" a string. Consider this example:

```python
word = "repeat"
print(word * 2)
print(word * 4)
```

When we run this program, we'll see the following output:

```tex
repeatrepeat
repeatrepeatrepeatrepeat
```

This allows us to build outputs that consist of repeated strings. We can also use this to quickly format our output into various shapes and structures!

## Escape

Finally, we can also use the escape operator `\` to handle some certain special characters in Python strings. We've already seen this used in the newline character, which is simply the escape operator `\` followed by the letter `n`, as in `\n`.

However, we can also use it to include quotation marks in our string itself. Consider the following example:

```python
sentence = "Hello from "the little apple!""
print(sentence)
```

When we try to run this code, we'll get the following error:

```tex
  File test.py, line 1
    sentence = "Hello from "the little apple!""
                            ^
SyntaxError: invalid syntax
```

This is because the double quotation mark `"` is used to show which part of the code is a string value, but the Python interpreter gets confused when we try to include quotation marks inside of our strings. So, we can use the escape operator `\` to tell it to treat those quotation marks as part of the string value itself, and not part of the Python code:

```python
sentence = "Hello from \"the little apple!\""
print(sentence)
```

This program will execute properly and produce the following output:

```tex
Hello from "the little apple!"
```

Notice that the quotation marks now appear correctly in the output, but the escape operators are not shown. There are many other special ways to use the escape operator in Python, all of which can be found in the [Python Documentation](https://docs.python.org/3/reference/lexical_analysis.html#string-and-bytes-literals).

{{% notice tip "Single and Double Quotes" %}}

Python also allows us to mix single and double quotes in a string, as long as we use them consistently, So, we can change the previous example to use single quotes around the string itself, and remove the escape operator from the double quotes, which will result in this code:

```python
sentence = 'Hello from "the little apple!"'
print(sentence)
```

This code will also produce the desired output. However, in this class we won't use single quotes around strings, just for consistency. Many other programming languages don't allow this, so we encourage you to learn how to use the escape operator to handle these situations.

{{% /notice %}}