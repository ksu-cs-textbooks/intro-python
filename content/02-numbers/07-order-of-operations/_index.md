---
title: "Order of Operations"
pre: "7. "
weight: 70
---

{{< youtube KmFinP55cTo >}}
<!-- Old: wjEIbu3HV7s -->
#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

Finally, just like in mathematics, we must also be aware of the order that these operators are applied, especially if they are combined into a single expression. Thankfully, the same rules we learned in mathematics apply in programming as well. Specifically, operators in Python are applied in this order:

1. Operations in parentheses are resolved first, moving from left to right.
1. `**` is resolved second, moving from left to right 
1. `*`, `/`, `//` and `%` are resolved third, moving from left to right.
1. `+` and `-` are resolved fourth, moving from left to right.

You might recall the "PEMDAS" acronym for remembering the order of operations in math, and thankfully it still applies here. Of course, this means that there are now 4 operators that all fit in the "multiplication and division" portion, so we have to carefully make sure they are all taken care of in the correct way. 

Also, as you've probably already learned in math, it is always best to add extra parentheses to any expression to make the intent very clear instead of relying on the order of operations. So, when in doubt, use extra parentheses wherever needed!

Let's work through a quick example just to see the order of operations in practice. Here's a complex expression in Python that we can try to evaluate:

```python
x = 8 / 4 + 5 * (3 + 1) - 7 % 4
```

Looking at our order of operations, the first step is to handle any expressions inside of parentheses. So, we'll first start with the expression `(3 + 1)` and evaluate it to `4`.

```python
x = 8 / 4 + 5 * 4 - 7 % 4
```

Then, we'll go left to right and perform any multiplication, division, and modulo operations. This means we'll evaluate `8 / 4`, `5 * 4` and `7 % 4` and replace them with the resulting values:

```python
x = 2.0 + 20 - 3
```

Notice that `8 / 4` was reduced to `2.0` instead of just `2`. This is because the division operator is the one exception to the rule where an operator applied to two integers will result in an integer. The division operator always produces a floating-point value. 

Finally, we'll perform addition and subtraction from left to right. So, we'll evaluate `2.0 + 20` first, and then subtract `3` from the result of that operation. At the end, we'll have this statement:

```tex
x = 19.0
```

So, we were able to use our knowledge of the order of operations to evaluate that complex expression to a single value, {{< math >}}$ 19.0 ${{< /math >}}, which will be stored in the variable `x`. 