---
title: "Boolean Operators"
pre: "3. "
weight: 30
---

{{% youtube 9eI_Cxoekgw %}}

<!-- Old: a_CcsdoY3-o -->

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

Python also includes several operators that can be applied to one or two Boolean values. These operators make up the basis of Boolean logic, and allow us to construct complex expressions of Boolean values. Let's quickly review the three basic Boolean operators present in Python.

## And Operator

In Python, we use the keyword `and` to perform the Boolean `and` operation. This operator will return `True` if both input values are also `True`, otherwise it will return `False`. 

This corresponds to the following truth table:

| Variable 1 | Variable 2 | Result |
|:----------:|:----------:|:------:|
| F | F | F |
| F | T | F |
| T | F | F |
| T | T | T |

Here's a quick example of the `and` operator in Python:

```python
x = True
y = False
print(x and y)
```

When we run this Python code, we should see this output:

```tex
False
```

Since the variable `y` is `False`, the resulting value is also `False`.

## Or Operator

Likewise, the keyword `or` is used in Python for the Boolean `or` operation. This operator will return `True` if either of the input values is `True`, but it will return `False` if neither of them are `True`.

This corresponds to the following truth table:

| Variable 1 | Variable 2 | Result |
|:----------:|:----------:|:------:|
| F | F | F |
| F | T | T |
| T | F | T |
| T | T | T |

Let's look at an example:

```python
a = False
b = True
print(a or b)
```

When we execute this code, we'll get this output:

```tex
True
```

Since `b` is `True`, we know that at least one input is `True` and the result of `a or b` is also `True`.

## Not Operator

Finally, Python uses the keyword `not` to represent the Boolean `not` operation, which simply inverts a Boolean value from `True` to `False` and vice-versa.

This corresponds to the following truth table:

| Variable 1 | Result |
|:----------:|:------:|
| F | T |
| T | F |

Here's an example:

```python
x = True
print(not x)
print(not not x)
```

When we run this code, we'll see this printed to the terminal:

```tex
False
True
```

Since `x` is `True`, we know that `not x` is `False`. We can then perform the `not` operation again, on that result, as shown in `not not x`, which will result in the original value of `x`, which is `True`.