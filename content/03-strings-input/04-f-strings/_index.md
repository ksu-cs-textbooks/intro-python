---
title: "F-Strings"
pre: "4. "
weight: 40
---

{{< youtube CTlt7UmSAqA >}}
<!-- Old: xrClRO_OQg8 -->
#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

Python also includes another method of building strings, which are known as "F-strings". F-strings allow us to put placeholders in strings that are later replaced with values from variables, effectively creating a way to build "templates" that can be used throughout our program.

The easiest way to see how this works is looking at a few examples. Let's start with a simple one:

```python
name = input("Enter your name: ")
print(f"Hello {name}")
```

If the user inputs `"Willie Wildcat"` when prompted, then this code will produce this output:

```tex
Enter your name: Willie Wildcat
Hello Willie Wildcat
```

There are many important parts to this example, so let's look at each one individually. First, in the `print()` statement, we see the string `"Hello {name}"`. This is an example of a **template string**, which includes a set of curly braces `{}` as **placeholders** for data to be inserted. Each template string can have unlimited sets of curly braces. Inside of each set of curly braces, we can place the variable or expression that will be printed at that location. 

Also, we notice that in front of the string, we see the character `f`. Preceding a string with `f` outside of the quotation marks will denote the string as an f-string (hence the name), which allows the values inside to be **interpolated**. Interpolation is the term used when formatting marks in a string, such as the curly braces in an f-string, are interpreted and replaced with the correct values they represent.

{{% notice tip "Advanced Formatting" %}}

Python f-strings can do many powerful things, such as handle more complex formatting and multiple lines. For right now, we'll just use simple variable placeholders in our f-strings, but over time we'll introduce additional ways to use f-strings to achieve the desired output.

{{% /notice %}}

The most powerful use of f-strings is to insert numerical values directly into strings without having to convert each value directly to the `str` data type - the interpolation process handles this for us.

For example, we can update our previous program to use f-strings to display the output in a single `print()` statement, and we can also add additional information with ease:

```python
text_one = input("Enter the price of one item: ")
price = float(text_one)
text_two = input("Enter the quantity of items: ")
quantity = int(text_two)
cost = price * quantity
print(f"{quantity} items at ${price} each is ${cost} total")
```

When we execute this program, we'll see output that looks like this:

```tex
Enter the price of one item: 2.75
Enter the quantity of items: 3
3 items at $2.75 each is $8.25 total
```

This example shows how easy it is to build complex output strings using f-strings.

{{% notice info "Format Method" %}}

Prior to the introduction of f-strings, it was common to use the `format()` method to place values inside of a template string. The last line of the previous example would look like this using the format method:

```python
print("{} items at ${} each is ${} total".format(quantity, price, cost))
```

As we can see, the `format()` method receives each value as an argument, and it will replace the curly brace placeholders `{}` in the template string with each value, working from left to right. The output produced will be identical to the f-string in the example above. 

We won't use the `format()` method in this class, but you may see it in many online tutorials and documentation since f-strings were introduced relatively recently. 

{{% /notice %}}
