---
title: "Basic Operators"
pre: "4. "
weight: 40
---

{{< youtube G5v-eSnlzDQ >}}
<!-- Old: P4IJU6AQwPE -->
#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

Now that we have the ability to store numerical data in variables in Python, we should also learn how to manipulate that data into something new. To do that, let's learn about **operators**. An **operator** in programming is a special symbol that can be used in an expression to manipulate the data in some way. 

Most operators are **binary operators**, which means they perform an operation that uses two values as input and produces a single value as output. In fact, in some programming languages, the operators themselves are implemented as functions in the language! Finally, we have to be careful not to confuse these with **bitwise operators**, which are operators perform operations on the binary value stored in a variable. We won't cover those operators in this class, but the terminology is a bit confusing.

An expression containing a binary operator typically follows this format:

```tex
<expression> <operator> <expression>
```

As before, the `<expression>` parts can be any valid expression in the language that can be reduced to a single value, and the `<operator>` part is typically a single symbol, but it can also be a short keyword as well.

Thankfully, these operators should all be very familiar to us from mathematics already, so this is just a quick discussion of how they can be used in programming.

## Addition and Subtraction

For starters, we can use the plus `+` and minus `-` symbols as operators to perform addition and subtraction in Python, just like in math. For example, we can add two variables together to create a third variable as shown in this example:

```python
a = 5
b = 7
c = a + b
print(c)
```

When we run this code in the Python interpreter, we should get this result:

```tex
12
```

Likewise, we can subtract two variables using the minus symbol `-` as shown here:

```python
x = 24
y = 10
z = x - y
print(z)
```

This code should produce this output:

```tex
14
```

## Multiplication and Division

In Python, we use the asterisk `*`, sometimes referred to as the star symbol, to multiply two values together. For example, we can find the product of two values as shown in this Python block:

```python
a = 6
b = 7
c = a * b
print(c)
```

When we run this code, we should see the following result displayed to the user:

```tex
42
```

Division is performed using the slash `/` symbol. A great way to think of division in programming is just like a fraction, since it uses the same symbol between the two numbers. For example, if we execute this code:

```python
x = 27
y = 3
z = x / y
print(z)
```

we would see this output:

```tex
9.0
```

What if the division would result in a remainder? In that case, we'll simply use decimal values in Python so that the result is exactly correct. For example, if we try to divide {{< math >}}$ 19 ${{< /math >}} by {{< math >}}$ 5 ${{< /math >}}, as in this example:

```python
a = 19
b = 5
c = a / b
print(c)
```

When we run this code, the Python interpreter will produce the following output:

```tex
3.8
```

So, as we can see, all of these operators in Python work exactly like their counterparts in math. So, we can easily use them in a way that should be very familiar to us.