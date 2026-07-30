---
title: "Numerical Input"
pre: "2. "
weight: 20
---

{{< youtube ashRrEHM9Ng >}}
<!-- Old: D6HF7S_J_i8-->
#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

Of course, we can also read numerical input in Python using the `input()` function. To do this, we must simply use either the `int()` or `float()` function to convert the input received as a string to the correct data type.

Here's a quick example program that requires two inputs for the price and quantity of an item being purchased:

```python
text_one = input("Enter the price of one item: ")
price = float(text_one)
text_two = input("Enter the quantity of items: ")
quantity = int(text_two)
cost = price * quantity
print("The total cost is $", end="")
print(cost)
```

If the user wishes to purchase {{< math >}}$ 3 ${{< /math >}} items at the price of {{< math >}}$ 2.75 ${{< /math >}} per item, then the program's output would look like this:

```tex
Enter the price of one item: 2.75
Enter the quantity of items: 3
The total cost is $8.25
```

In the program, we simply read each input from the user as a string value, then use the appropriate conversion function to convert it to the correct data type. For numbers including a decimal point, we use `float()`, but for whole numbers we use the `int()` function.

This works well if the user enters values that make sense. But, what if the user wishes to purchase a fraction of an item? Will this program work? Unfortunately, if the user enters a value with a decimal point for the second input, it can no longer be converted to an integer and we'll get an error:

```tex
Enter the price of one item: 2.75
Enter the quantity of items: 3.5
Traceback (most recent call last):
  File "tutor.py", line 4, in <module>
    quantity = int(text_two)
ValueError: invalid literal for int() with base 10: '3.5'
```

For right now, there's not much we can do about that error other than write programs that clearly tell the user what type of data is expected, but later we'll learn how to handle errors like this and prompt the user for input again.

