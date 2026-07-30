---
title: "Resulting Types"
pre: "6. "
weight: 60
---

{{< youtube Lo-b6Ewwbqc >}}
<!-- Old: 89S89k9VowA -->
#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

Since Python has multiple numeric data types, there are some rules that govern which data type is produced as a result of various math operations. Thankfully, the rules themselves are pretty straightforward once they are explained.

## Resulting Data Types - Same Type

The basic rule to remember, **if a mathematical operator is applied to two variables of the same data type, the result will also be that data type.**

Let's see what that means in practice. Here's a quick example in Python using the multiplication operator on two integer values:

```python
x = 5
y = 10
z = x * y
print(z)
print(type(z))
```

When we run this code, we should see the following output:

```tex
50
<class 'int'>
```

Since both `x` and `y` are the `int` data type, the result of `x * y` will also be an `int` value, so the variable `z` will have that data type, as shown in this example.

However, there is **one exception** to this rule, which is the division operator `/`. In Python, the division operator will always return a `float` value, even if it is a whole number. Here's an example that demonstrates that:

```python
a = 9
b = 3
c = 4
x = a / b
print(x)
print(type(x))
print()
y = a / c
print(y)
print(type(y))
```

When we run this program, we'll see the following output:

```tex
3.0
<class 'float'>

2.25
<class 'float'>
```

So, as we can see, even though we are dividing two `int` values, we'll get a `float` value as a result each time we use the division operator.

Following the rule above, if we perform a mathematical operation between two `float` values, the resulting value will always be a `float` as well:

```python
a = 2.5
b = 4.5
c = a + b
print(c)
print(type(c))
```

Running this code will produce this output:

```tex
7.0
<class 'float'>
```

So, even though the result is a whole number, the value that is stored is the `float` data type.

## Resulting Data Types - Different Type

The other rule to remember is **anytime an operation involves a `float` value and an `int` value, the result will be a `float`**. So, if there are mixed types, Python will default to the `float` data type.

This can be seen in the following example:

```python
a = 5
b = 2.0
c = a - b
print(c)
print(type(c))
```

When this code is executed, the output should look like this:

```tex
3.0
<class 'float'>
```

Once again, even though the result is a whole number, because the variable `b` is a `float` value, the entire result will also be a `float` value. 

Learning the data types that are returned by a mathematical operator can be tricky, but most programmers slowly develop an intuition of how each operator works and what to expect. So, don't worry too much if this is confusing right now, since it will become much clearer with practice! Also, don't forget that we can always create a simple test program like the examples shown above to confirm the result for any operation.  