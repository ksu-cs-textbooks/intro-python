---
title: "New Operators"
pre: "5. "
weight: 50
---

{{< youtube HW8MUd7Qoco >}}
<!-- Old: GOnsob24hdQ -->
#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

## Modulo Operator

The Python programming language also includes a few math operators that are not commonly used outside of programming. 

The first one is the **modulo operator**. The **modulo operator** is used to find the **remainder** of a division operation. If we think back to math again, we've probably learned how to perform [long division](https://en.wikipedia.org/wiki/Long_division) when dividing two values. At the end, we might be left with a remainder, or a portion of the first number that is left over after the operation is complete. In many computer programs, that value is very useful, so we have a special operator we can use to find that value. In Python, we use the percent symbol `%` as the modulo operator.

For example, if we want to find the remainder after dividing {{< math >}}{{< math >}}$  19  ${{< /math >}}{{< /math >}} by {{< math >}}{{< math >}}$  5  ${{< /math >}}{{< /math >}}, we would use the following code:

```python
x = 19
y = 5
z = x % y
print(z)
```

When we run this code, we would get the following output:

```tex
4
```

This is because the value {{< math >}}{{< math >}}$  5  ${{< /math >}}{{< /math >}} will fit into the value {{< math >}}{{< math >}}$  19  ${{< /math >}}{{< /math >}} only {{< math >}}{{< math >}}$  3  ${{< /math >}}{{< /math >}} times, and then we'll have the value {{< math >}}{{< math >}}$  4  ${{< /math >}}{{< /math >}} left over. Mathematically, we are saying that {{< math >}}{{< math >}}$  19 / 5 = (3 * 5) + 4  ${{< /math >}}{{< /math >}}. Since {{< math >}}{{< math >}}$  4  ${{< /math >}}{{< /math >}} is the leftover portion, it is the resulting value when we use the modulo operator. 

In this course, we'll only worry about how the modulo operator works when applied to positive whole numbers. In practice, it can be applied to any numerical value, including decimal values and negative numbers, but those values are not really useful in most cases. So, to keep things simple, we'll only use positive whole numbers with this operator.

## Exponentiation Operator

The next operator introduced by Python is the **exponentiation operator**. The double star `**` operator is used to represent exponentiation, sometimes referred to the power operator. In Python, the expression `2 ** 3` would be written mathematically as {{< math >}}$ 2^3 ${{< /math >}}, which is the operation of taking {{< math >}}$ 2 ${{< /math >}} to the power of {{< math >}}$ 3 ${{< /math >}}, or multiplying {{< math >}}$ 2 ${{< /math >}} by itself {{< math >}}$ 3 ${{< /math >}} times.

Here's a quick example of using the `**` operator in code:

```python
x = 5 ** 3
print(x)
print(type(x))
```

When this code is run, we see the following output:

```tex
125
<class 'int'>
```

{{% notice tip "Don't use the Carat ^" %}}

Many other programming languages and tools use the carat `^` character to represent the exponentiation operation. However, in Python, the carat `^` character is used to represent the bitwise XOR operation. So, we must be careful not to accidentally use the `^` operator when we actually mean to use the `**` operator for exponentiation.

{{% /notice %}}

## Integer Division Operator

Finally, Python also includes the integer division operator, represented by two forward slashes `//`, which is used to perform division that **truncates** the result to an integer. However, as we'll see on the next page, if either of the values in the operation is a `float` value, it will return a value that is a `float` data type, even though the result is an integer value.

Let's look at an example with that operator in code:

```python
a = 17.5 // 4.5
print(a)
print(type(a))
```

As we expect, when we run this program, we'll get the following output:

```tex
3.0
<class 'float'>
```

So, we see that this operator will return a `float` value, even though it is truncating the result to an integer, simply because the input values contained a `float`. 

