---
title: "If-Else"
pre: "7. "
weight: 70
---

{{< youtube 1kwuH5dQmME >}}

<!-- Old: Gs0THQo15Gk -->
<!-- Older: eX2PD1z3au8 -->
#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

Python also supports another kind of conditional statement, the **if-else statement**. An if-else statement contains a single Boolean expression, but two blocks of code. If the Boolean expression evaluates to `True`, then one block of statements is executed. If it is `False`, then the other block will be executed. 

The general structure of an if-else statement in Python is shown below:

```python
if <boolean expression>:
    <block of statements 1>
else:
    <block of statements 2>
```

Notice that the `else` keyword is followed by a colon, just like the first line of the if-else statement. As we'd expect, the first block of statements is executed if the `<boolean expression>` portion is `True` and the second block is executed if it is `False`. 

Once again, let's go through a couple of code traces using Python Tutor to explore how an if-else statement works in Python.

## Code Tracing Example - True

Here's a simple Python program that contains an if-else statement:

```python
x = int(input("Enter a number: "))
if x >= 0:
    print("Your number is positive!")
else:
    print("Your number is negative")
print("Thanks for playing!")
```

This program accepts an input from the user, converts it to an integer, and then determines if the integer is a positive or negative number. Let's go through this program a couple of times in Python Tutor to see how it works. As always, you can copy and paste this code into Python Tutor, or click this [Python Tutor](https://pythontutor.com/visualize.html#code=x%20%3D%20int%28input%28%22Enter%20a%20number%3A%20%22%29%29%0Aif%20x%20%3E%3D%200%3A%0A%20%20%20%20print%28%22Your%20number%20is%20positive!%22%29%0Aelse%3A%0A%20%20%20%20print%28%22Your%20number%20is%20negative%22%29%0Aprint%28%22Thanks%20for%20playing!%22%29&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=3&rawInputLstJSON=%5B%5D&textReferences=false) link to follow along!

We'll start an input prompt as shown here:

![Tutor 1](/images/04/tutor7_1.png?classes=border,shadow)

Let's assume that the user inputs the string `"5"` here. 

![Tutor 2](/images/04/tutor7_2.png?classes=border,shadow)

That means that the integer value {{< math >}}$ 5 ${{< /math >}} will be stored in the variable named `x`:

![Tutor 3](/images/04/tutor7_3.png?classes=border,shadow)

Now we've reached the if-else statement. So, we'll need to evaluate the Boolean expression `x >= 0`. Since `x` is currently storing the value {{< math >}}$ 5 ${{< /math >}}, this expression will evaluate to `True`. Therefore, we'll move into the first block of statements in the if-else statement:

![Tutor 4](/images/04/tutor7_4.png?classes=border,shadow)

From here, we'll print the message that the user's input was a positive number, as well as the goodbye message at the end of the program. It will entirely skip the second block of statements in the if-else statement, as we can see here:

![Tutor 6](/images/04/tutor7_6.png?classes=border,shadow)

A full execution of this program is shown in the animation below:

![Tutor 7 GIF](/images/04/tutor7.gif?classes=border,shadow)

## Code Tracing Example - False

What if the user inputs a negative value, such as {{< math >}}$ -7 ${{< /math >}}? In that case, we'll be at this state in our program:

![Tutor 10](/images/04/tutor8_3.png?classes=border,shadow)

From here, we'll evaluate the Boolean expression `x >= 0` again. This time, however, we'll see that it evaluates to `False`, so we'll jump down to the second block of statements inside the if-else statement:

![Tutor 11](/images/04/tutor8_4.png?classes=border,shadow)

This will print a message to the user that the input was a negative number, and then it will print the goodbye message. We completely skipped the first block of statements:

![Tutor 12](/images/04/tutor8_6.png?classes=border,shadow)

A complete run through this program is shown in this animation:

![Tutor Gif 2](/images/04/tutor8.gif?classes=border,shadow)

So, as we expect, an if-else statement allows us to run one block of statements or the other, based on the value of the Boolean expression. It is a very powerful piece of code, and it allows us to write programs that perform different actions based on the input provided by the user or the values of other variables. 

## If-Else Statement Flowchart

Another way to visualize an if-else statement is using a flowchart. Consider the following Python code:

```python
x = int(input("Input: " ))
if x >= 0:
  print(x)
else:
  print(-1 * x)
print("Goodbye")
```

This code can also be represented as the flowchart shown below:

![If Flowchart](/images/04/ifthenelse.png?classes=border,shadow)

Once again, we start at the top of the flowchart at the circle labeled "START". From there, we read an input from the user and store it in the variable `x`. At this point, we reach our if-else statement's decision node, represented by the diamond. Here, we are using the Boolean expression `x >= 0` to determine which branch to follow. So, if the user inputs a positive value, then we'll follow the path to the right that is labeled "True", which will simply print the value of `x` to the screen.

However, if the user inputs a negative value for `x`, then the Boolean expression will be `False` and we'll follow the path to the left labeled "False". In this branch, we'll print the value of `(-1 * x)` to the screen, which simply removes the negative sign from the value in `x`. 

Finally, after each path, we'll merge back together to run the last piece of code, which prints the `"Goodbye"` message to the screen.

Notice that there is no way to print both `x` and `-1 * x` in the same execution of this program. If we follow the arrows through the flowchart, we see that we can only follow one branch or the other, and not both. This is an important concept to remember when working with if-else statements! The **control flow** of the program can only pass through one of the two blocks of statements, but not both. 



