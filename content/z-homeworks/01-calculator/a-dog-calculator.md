+++
title = "Interest Calculator"
hidden = true
pre = "A. "
+++

## Calculating Compound Interest

In the first programming homework assignment, we'll create a simple program to help us calculate how much compound interest we can make over our lifetime by saving money in a retirement account. It's a great way to see the value of saving early and often, as it pays substantial dividends later on!

{{% notice note "Learning Objectives" %}}

The goal of this assignment is to demonstrate understanding of the following topics in Python:

* Variables
* Data Types `int`, `float`, and `str`
* Reading User Input using `input()`
* Mathematical Operators
* String `format()` and Output

{{% /notice %}}

### What is Interest?

*Interest* is money you can earn from saving your money in a bank account or by purchasing bonds. Over time, your money can be used by the bank or the issuer of the bond, and they pay you a little bit each year for the use of your money.

### What is Compound Interest?

In some cases, you can take the interest you earn in a year back into your account, and then earn interest *on your interest*. This is known as **compound interest**, and it is one of the key tools involved in saving money for retirement.

In fact, by saving just a little money when you are {{< math >}}$ 25 ${{< /math >}} to {{< math >}}$ 30 ${{< /math >}} years old, you can end up with just as much money later as someone who saved lots of money from age {{< math >}}$ 40 ${{< /math >}} to {{< math >}}$ 60 ${{< /math >}}!

### Calculating Compound Interest

The formula to calculate compound interest is very simple:

{{< math >}}$$
\text{Final Amount} = \text{Savings} * (1 + \text{Interest Rate})^{\text{Time Span}}
$${{< /math >}}

For example, if we save {{< math >}}$ \$1,000 ${{< /math >}} for {{< math >}}$ 5 ${{< /math >}} years in an account that pays {{< math >}}$ 5\text{%} ${{< /math >}} interest per year, we can use that formula to calculate how much money we would have after {{< math >}}$ 5 ${{< /math >}} years:

{{< math >}}$$
1276.28 = 1000 * (1 + 0.05)^{5}
$${{< /math >}}

So, we would have {{< math >}}$ \$1,276.28 ${{< /math >}} after {{< math >}}$ 5 ${{< /math >}} years - we made over {{< math >}}$ 275 ${{< /math >}} dollars! That's pretty great!

## The Assignment

Write your program in a file named `homework1.py`. This should be a complete Python program consisting of the following elements:

1. Prompts asking the user to input their savings details
2. Output demonstrating the rate of return on savings
3. Prompts asking the user for retirement spending
4. Output showing the user how many years their savings will last

Each element will be described in detail below.

### 1. Savings Details Prompts

First, the program should prompt the user to provide the following inputs **in this order**:

1. The amount of money being saved in the account initially, entered as a whole number
2. The yearly interest rate, entered as a decimal number between 0 and 1
3. The number of years the money will be saved, entered as a whole number

You may provide whatever descriptive text you wish to help your users input the correct values.

In the examples below, let's assume that the user input the following values for those inputs:

* `1234` (amount in the account initially)
* `0.04` (interest rate of 4%)
* `42` (years)

### 2. Rate of Return Outputs

Then, your program should calculate the amount of money that will be present in the account after many different time periods, and produce {{< math >}}$ 6 ${{< /math >}} lines of output. These outputs will detail the total savings plus compounded interest after the following time periods **in this order**:

* 1 year
* 5 years
* 10 years
* 25 years
* 40 years
* `<x>` years (the number of years the user input earlier)

An example of possible output is shown below:

```tex
After 1 year, you will have $1,283.36
After 5 years, you will have $1,501.35
After 10 years, you will have $1,826.62
After 25 years, you will have $3,289.64
After 40 years, you will have $5,924.46
After 42 years, you will have $6,407.90
```

Your program should always output all {{< math >}}$ 6 ${{< /math >}} of these lines of output, even if the user inputs a number of years less than {{< math >}}$ 40 ${{< /math >}}. Part of the goal is to encourage everyone to save more money for longer periods of time!

{{% notice info "Formatting Dollar Amounts" %}}

Notice that each dollar amount is formatted using commas if needed, as well as only two digits after the decimal place. You can do this by using the format specifier `,.2f` as part of your f-string placeholder, as shown in this example:

```python
value = 12345.6789
print(f"You have ${value:,.2f} in your account")
```

which will print:

```tex
You have $12,345.68 in your account
```

The format string `${value:,.2f}`  in the placeholder can be interpreted as follows:

* `$` will place a dollar sign before the number (it is not technically part of the placeholder since it is outside the curly braces).
* `{}` curly braces are used to denote a placeholder in a template string, just like before. Placeholders can include additional information such as a format specification.
* `value` is the name of the variable containing the value to be printed
* `:` is the start of a **format specification** for reformatting the output in various ways.
* `,` will add commas as **grouping options** for large numbers, as in `1,234,567`.
* `.2` denotes the **precision** of the value, meaning that any numerical value printed will have 2 digits after the decimal place, and will be rounded if needed.
* `f` is the **type of the value** provided - in this case `f` denotes the `float` data type.

You can refer to the [Python Documentation](https://docs.python.org/3/library/string.html#formatstrings) for more information these format specifications.

{{% /notice %}}

### 3. Retirement Spending Prompts

Next, the program should prompt the user to provide the following input:

1. The amount of money to be spent yearly in retirement, entered as a whole number

You may provide whatever descriptive text you wish to help your users input the correct values.

In the examples below, let's assume that the user input the following values for those inputs:

* `1000` (money spent each year)

### 4. Spending Output

Finally, the program should then compute the number of years that the user will be able to spend that amount while in retirement, and the amount left over, and print that to the terminal. Continuing the example above, this code would create this possible output:

```tex
You will be able to spend $1000.00 per year for 6 years.
You will have $407.90 left over after 6 years.
```

## Documentation & Comments

You may add any comments to your code to help explain how it works. In Python, you can use the hash symbol `#` (also known as a pound sign or octothorpe) in front of a line of text in a Python file to make it a comment:

```python
# This is a code comment
x = 15
y = 7  # comments can be at the end of lines, too
```

## Required Documentation Comment

Your file must include a **documentation comment**, also known as a **docstring** at the top of your file. The **docstring** should be formatted like this:

```python
"""
File Name: <filename>
Author: <your name>
Version: <submission date>
Section: <your section>
Description: <detailed description of this program>
"""
```

Notice that the start and end of the documentation comment uses three double-quotes `"""` on a single line.

## Sample Execution

Below is a screenshot showing a sample execution of the model solution for this homework assignment. Your submission should have similar functionality and output, but the text for input prompts may differ slightly:

![Sample Run](/images/hw1/interest.png?classes=border,shadow)

## Grading Rubric

Your project will be graded according to the following rubric:

* Interest & Savings Inputs: 20%
* Interest Computations: 25%
* Interest Outputs: 25%
* Savings Computation & Output: 20%
* Documentation Comments: 10%

## Submitting

Once you have completed this program, submit your `homework1.py` file via Codio or the assignment on Canvas.

{{% notice warning "Bad Financial Advice!" %}}

This grossly over simplifies retirement savings by ignoring inflation.  Do not use this for actual retirement planning.

{{% /notice %}}
