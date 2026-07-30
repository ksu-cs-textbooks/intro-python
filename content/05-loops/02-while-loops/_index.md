---
title: "While Loops"
pre: "2. "
weight: 20
---

{{< youtube RgTyitSONSE  >}}
<!-- Old: thv1c8bwzpc -->
<!-- Older: UObqXaT2hXg -->

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

The first type of loop to explore in Python is the **while loop**. A while loop uses a Boolean expression, and will repeat the code inside of the loop as long as the Boolean expression evaluates to `True`. These loops are typically used when we want to repeat some steps, but we aren't sure exactly how many times it must be done. Instead, we typically know that there is some condition that must be `True` while we repeat the code, and once it turns `False` we can stop looping and continue with the program.

The general syntax for a while loop in Python is shown here:

```python
while <boolean expression>:
    <block of statements>
```

Notice that this syntax is very similar to an if statement. We start with the keyword `while`, followed by some sort of a `<boolean expression>` that will evaluate to either `True` or `False`. The Boolean expression in Python does not need to be placed inside of parentheses. After the Boolean expression is a single colon `:`. Then, starting on the next line and indented one level is a `<block of statements>` that will be executed when the Boolean expression evaluates to `True`. Once again, just like in an if statement, we know which statements are part of the block within a while loop based solely on indentation. 

It is possible for the Boolean expression to evaluate to `False` initially, which will bypass the loop entirely and never execute the code inside of it. Likewise, if we aren't careful, we can also write a loop where the Boolean expression will always be `True`, and the loop will run infinitely, causing our program to lock up and never terminate. 

## Code Tracing Example

To truly understand how a while loop works in Python, let's go through a simple code tracing example in Python Tutor. Consider the following Python program:

```python
x = int(input("Enter a number from 0 to 100: "))
total = 0
while total % 100 != x:
    total = total + 9
print(f"The smallest multiple of 9 that ends in {x} is {total}")
```

See if you can figure out what this program does before moving on!

As always, you can copy and paste this code into Python Tutor, or click this [Python Tutor](https://pythontutor.com/visualize.html#code=x%20%3D%20int%28input%28%22Enter%20a%20number%20from%200%20to%20100%3A%20%22%29%29%0Atotal%20%3D%200%0Awhile%20total%20%25%20100%20!%3D%20x%3A%0A%20%20%20%20total%20%3D%20total%20%2B%209%0Aprint%28f%22The%20smallest%20multiple%20of%209%20that%20ends%20in%20%7Bx%7D%20is%20%7Btotal%7D%22%29&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=3&rawInputLstJSON=%5B%5D&textReferences=false) link.

When we load this code in Python Tutor, we should see the usual default state. The first line of the program will prompt the user for input and store it in the variable `x`. 

![Tutor 1](/images/05/tutor9_1.png?classes=border,shadow)

For this example, let's assume the user inputs the string `"27"`.

![Tutor 2](/images/05/tutor9_2.png?classes=border,shadow)

Therefore, we'll store the value {{< math >}}$ 27 ${{< /math >}} in the variable `x`. 

![Tutor 3](/images/05/tutor9_3.png?classes=border,shadow)

The next line will store the value {{< math >}}$ 0 ${{< /math >}} in the variable `total`, as shown here:

![Tutor 4](/images/05/tutor9_4.png?classes=border,shadow)

At this point, we've reached the beginning of the while loop. So, we'll need to determine if the Boolean expression evaluates to `True` or `False`. In this case, the value of `total % 100` is equal to {{< math >}}$ 0 ${{< /math >}}, so it is not equal to the value stored in `x`. Therefore, the Boolean expression is `True`, and we should enter the loop.

![Tutor 5](/images/05/tutor9_5.png?classes=border,shadow)

Inside of the loop, we are simply adding {{< math >}}$ 9 ${{< /math >}} to the value in `total`. So, we'll see that variable is updated, and the execution pointer goes back to the top of the loop. 

![Tutor 6](/images/05/tutor9_6.png?classes=border,shadow)

Now that we are back at the top of the loop, we need to check the Boolean expression again. This time the value of `total % 100` is {{< math >}}$ 9 ${{< /math >}}, which still isn't equal to the value stored in `x`, so we'll enter the loop again.

![Tutor 7](/images/05/tutor9_7.png?classes=border,shadow) 

We'll add {{< math >}}$ 9 ${{< /math >}} to the `total` here, and jump to the top again.

![Tutor 8](/images/05/tutor9_8.png?classes=border,shadow) 

Once again, we will check the Boolean expression and see that it is still `True`, so we'll enter the loop and add {{< math >}}$ 9 ${{< /math >}} to the `total` yet again before repeating the process from the top of the loop. At this point, we should see this state in Python tutor.

![Tutor 10](/images/05/tutor9_10.png?classes=border,shadow)

When we compute `total % 100`, we get the value {{< math >}}$ 27 ${{< /math >}}, which is the same as the value stored in `x`. This will make the Boolean expression evaluate to `False`, so we can skip the loop and jump to the bottom of the program.

![Tutor 11](/images/05/tutor9_11.png?classes=border,shadow) 

Here, we are simply printing out the output, and then the program will terminate.

![Tutor 12](/images/05/tutor9_12.png?classes=border,shadow) 

A full animation of this program's execution in Python Tutor is shown here.

![Tutor Animation 9](/images/05/tutor9.gif?classes=border,shadow)

Tracing the execution of a while loop is quite simple, especially with tools such as Python Tutor to help us make sure we're updating the variables in the correct order. 