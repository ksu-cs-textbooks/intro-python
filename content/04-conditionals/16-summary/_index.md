---
title: "Summary"
pre: "16. "
weight: 160
---

In this lab, we introduced several major important topics in Python. Let's quickly review them.

## Booleans in Python

* `True`
* `False`
* `bool()` procedure to convert values
  * If the input is the value `False`, the value `0`, the value `None`, or anything with 0 length, including the empty string, it will return `False`.
  * Otherwise, for all other values it will return `True`.

## Boolean Operators

* `and` 
* `or`
* `not`

## Boolean Comparators

* `==` equal
* `!=` not equal
* `<` less than
* `<=` less than or equal to
* `>` greater than
* `>=` greater than or equal to

## Comparators and Strings

Strings are compared using [lexicographic order](https://en.wikipedia.org/wiki/Lexicographic_order)

## Boolean Order of Operations

1. Math operators (following their order of operations)
1. Boolean comparators
1. `not`
1. `and`
1. `or`

## Conditional Statements

* if statement

```python
if <boolean expression>:
    <block of statements>
```

* if-else statement

```python
if <boolean expression>:
    <block of statements 1>
else:
    <block of statements 2>
```

## Testing

* Branch Coverage - all possible branches are executed at least once
* Path Coverage - all possible paths through branches are executed at least once
* Edge Cases - values that are near the point where Boolean expressions go from `False` to `True`

## Mutually Exclusive

Conditional statements are **mutually exclusive** when only one of the many branches will be executed for any possible input.

## Chained Conditionals

```python
if condition_1:
    print("1")
else:
    if condition_2:
        print("2")
    else:
        if condition_3:
            print("3")
        else:
            print("4")
```

is equivalent to:

```python
if condition_1:
    print("1")
elif condition_2:
    print("2")
elif condition_3:
    print("3")
else:
    print("4")
```

## Nested Conditionals

```python
if condition_1:
    if condition_2:
        print("1 and 2")
    elif condition_3:
        print("1 and 3")
    else:
        print("1 and not 2 or 3")
elif condition_4:
    if condition_2:
        print("4 and 2")
    elif condition_3:
        print("4 and 3")
    else:
        print("4 and not 2 or 3")
else:
    print("neither 1 nor 4")
```

## Variable Scope

**Variable scope** refers to what parts of the code a particular variable is accessible in. Python uses **function scope**, which means that a variable defined anywhere in a function is available below that definition in any part of the same function.

Other languages use **block scope**, where variables are only available within the block where they are defined. 
