---
title: "Input with Loops"
pre: "4. "
weight: 40
---

{{< youtube tqN5vsqtz4M >}}
<!-- Old: ouUJglULdW8 -->
<!-- Older: P71riBkGxKw -->

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

Loops in Python are also a great way to handle situations where a user must input a value that meets certain criteria. Previously, we used an if statement to determine if the input was valid, but if it wasn't valid all we could do was print an error and end the program. If we use a loop instead, we can prompt the user to provide additional input until we receive a valid value.

To make this process easy to use, we can develop a block of code just to handle input from the user. For example, if we want the user to input a percentage, we could use code similar to this:

```python
x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
while(x < 0 or x > 1):
    print("Invalid Input!")
    x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
```

This code starts by prompting the user to input a number, and stores it as a floating-point value in the variable `x`. Then, it will reach the start of the while loop. The Boolean expression will check to see if the value provided is not a percentage, so if it is less than {{< math >}}$ 0 ${{< /math >}} or greater than {{< math >}}$ 1 ${{< /math >}} it is considered invalid. 

If the input is invalid, we'll print an error and prompt the user for input again. We'll keep repeating this process until the user provides a value between {{< math >}}$ 0 ${{< /math >}} and {{< math >}}$ 1 ${{< /math >}}, at which point the loop will terminate. At this point, we know that the value stored in `x` is a valid value. 

## Reading Input

With code such as that in our program, we can use it to actually read input directly from the user. For example, we can write a quick program to calculate a weighted average of exam scores as shown below:

```python
print("This program will compute weighted average for three exam scores")

print("Enter the first exam's score")
x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
while(x < 0 or x > 1):
    print("Invalid Input!")
    x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
exam1_score = x

print("Enter the first exam's weight")
x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
while(x < 0 or x > 1):
    print("Invalid Input!")
    x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
exam1_weight = x

print("Enter the second exam's score")
x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
while(x < 0 or x > 1):
    print("Invalid Input!")
    x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
exam2_score = x

print("Enter the second exam's weight")
x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
while(x < 0 or x > 1):
    print("Invalid Input!")
    x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
exam2_weight = x

print("Enter the third exam's score")
x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
while(x < 0 or x > 1):
    print("Invalid Input!")
    x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
exam3_score = x

print("Enter the third exam's weight")
x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
while(x < 0 or x > 1):
    print("Invalid Input!")
    x = float(input("Enter a percentage as a decimal number from 0 to 1: "))
exam3_weight = x

total = exam1_score * exam1_weight + exam2_score * exam2_weight + exam3_score * exam3_weight
print(f"Your total score is {total}")
```

A quick execution of this program is shown here:

![Execution of Program](/images/05/input.png?classes=border,shadow)

Take a minute to confirm that the program works by running it yourself, either in Python Tutor or directly in Python. You can even adapt this program to help calculate your final grade in this course!

Learning to how to create building blocks of larger programs, such as loop for checking input described here, is a great way to develop our programming skills. If we can learn to take a large program and break it down into smaller, repeatable chunks, then the entire program becomes much easier to develop and maintain.

{{% notice tip "Repeated Code" %}}

Are you starting to ask yourself if there is a better way to handle repeated blocks of code like this? If so, that's great! We'll cover functions, which is a way to build repeatable pieces of code that can be used throughout our programs, in the next chapter!

{{% /notice %}}
