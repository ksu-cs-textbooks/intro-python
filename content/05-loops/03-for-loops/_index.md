---
title: "For Loops"
pre: "3. "
weight: 30
---

{{< youtube LwyWTsQL_9s >}}
<!-- Old: MkwFVwOoFCY -->
<!-- Older: _XArnG4R6r4 -->

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

Python also includes a second type of loop that is very useful, the **for loop**. A for loop is used when we want to repeat the steps a certain number of times. However, in Python, we can't just say that we want to repeat something {{< math >}}$ 10 ${{< /math >}} times. Instead, we use the built-in `range()` function in Python to generate a list of numbers that we use in our loop. Then, our for loop will repeat once for each number in the list, and we can even access that number using an **iterator variable**

{{% notice note "Lists in Python" %}}

We'll learn more about lists in Python in a later lab. For now, we're just going to use the `range()` function to generate them for use with for loops.

{{% /notice %}}

## Range Function

The `range()` function can be used in three different ways, depending on the number of arguments given when calling the function:

* `range(stop)` - with a single argument, the `range()` function will generate a list of numbers that begins at {{< math >}}$ 0 ${{< /math >}} and stops before it reaches the `stop` value. For example, `range(10)` will generate a list of numbers from {{< math >}}$ 0 ${{< /math >}} through {{< math >}}$ 9 ${{< /math >}}. This is great, since there will be {{< math >}}$ 10 ${{< /math >}} numbers in total, so a for loop using `range(10)` will repeat {{< math >}}$ 10 ${{< /math >}} times.
* `range(start, stop)` - with two arguments, the `range()` function will generate a list of numbers that begins at `start` and stops before it reaches the `stop` value. So, `range(3,8)` will generate the list `[3, 4, 5, 6, 7]`. There will be `stop - start` numbers in the range. 
* `range(start, stop, step)` - with three arguments, the `range()` function will generate a list of numbers that begins at `start`, increases by `step` each time, and stops before the `stop` value. Therefore, `range(0, 10, 2)` will generate the list `[0, 2, 4, 6, 8]`. We can also use a negative value for `step` to count backwards. So, `range(5, 0, -1)` will generate the list `[5, 4, 3, 2, 1]`. 

You can read more about the Python `range()` function in the [Python Documentation](https://docs.python.org/3/library/stdtypes.html#range)

## For Loops

The general structure of a for loop in Python is shown here:

```python
for <iterator variable> in <list>:
    <block of statements>
```

The first time we reach a for loop, we'll keep track of the `<list>` that we'll be iterating over. In general, once you start repeating in a for loop, the `<list>` cannot be changed. 

If the list contains at least one item, then we'll store the first item in the list in the `<iterator variable>` and enter the for loop to execute the code in the `<block of statements>` When we reach the end of the block, we'll jump back to the top and check to see if the `<list>` contains another item. If so, we'll store that item in the `<iterator variable>` and execute the code in the `<block of statements>` again.

This process will repeat until we've used every item in the `<list>`. Then, we'll jump to the end of the for loop and continue the program from there.

## Code Tracing Example

To really see how a for loop works in Python, let's use Python Tutor to trace through a quick sample program. Consider this Python program:

```python
x = int(input("Enter a number: "))
line = ""
for i in range(x):
    line = line + "*"
    print(line)
```

Before working through the code in Python Tutor, see if you can determine what this program does just by reading it!

To step through the code, we can load it into Python Tutor by copy and pasting it there, or by clicking this [Python Tutor](https://pythontutor.com/visualize.html#code=x%20%3D%20int%28input%28%22Enter%20a%20number%3A%20%22%29%29%0Aline%20%3D%20%22%22%0Afor%20i%20in%20range%28x%29%3A%0A%20%20line%20%3D%20line%20%2B%20%22*%22%0A%20%20print%28line%29&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=3&rawInputLstJSON=%5B%5D&textReferences=false) link.

We'll start with the usual default state as shown here. The first line will read the input from the user.

![Tutor 1](/images/05/tutor10_1.png?classes=border,shadow)

For this example, let's assume the user inputs the string `"5"`:

![Tutor 2](/images/05/tutor10_2.png?classes=border,shadow)

This means that we'll store the number {{< math >}}$ 5 ${{< /math >}} in the variable `x`. The program will also create an empty string value in the `line` variable, which we'll use to generate output. 

![Tutor 3](/images/05/tutor10_3.png?classes=border,shadow)

At this point, we should have reached the beginning of the for loop.

![Tutor 4](/images/05/tutor10_4.png?classes=border,shadow)

Behind the scenes, Python will generate a list of numbers based on the `range()` function. Since the `range()` function is called with a single argument, we know it will be a list of numbers starting at {{< math >}}$ 0 ${{< /math >}} and ending before it reaches the value in `x`, which is {{< math >}}$ 5 ${{< /math >}}. So, the list will contain the numbers `[0, 1, 2, 3, 4]`, and it will cause the for loop to repeat {{< math >}}$ 5 ${{< /math >}} times. For the first iteration of the loop, Python will store the first number in the list, {{< math >}}$ 0 ${{< /math >}}, in the iterator variable `i`. In programming, we typically use the variable name `i` to represent our iterator variable. So, once the program has entered the loop, we should see this state:

![Tutor 5](/images/05/tutor10_5.png?classes=border,shadow)

Inside of the loop, the first statement will update the `line` value by adding an asterisk `*` to the end of the string. So, after this statement is executed, the `line` variable will store a string containing a single asterisk.

![Tutor 6](/images/05/tutor10_6.png?classes=border,shadow)

The second statement will print the `line` variable to the output.

![Tutor 7](/images/05/tutor10_7.png?classes=border,shadow)

At this point, we've reached the end of the for loop, so our execution pointer jumps back up to the top of the loop. Then, we check to see if the list we are iterating through contains more values. Again, this list isn't shown in Python tutor, so we have to mentally keep track, but we can see the current value in `i`, and we know what the list contains by looking at the `range()` function. So, we'll update `i` to store the value {{< math >}}$ 1 ${{< /math >}}, and repeat the loop once again.

![Tutor 8](/images/05/tutor10_8.png?classes=border,shadow)

Just like before, this iteration will add an asterisk to the string in the `line` variable, and then print that to the output before repeating once again.

![Tutor 10](/images/05/tutor10_10.png?classes=border,shadow)

There are still more items in the list, so we'll update `i` to the value {{< math >}}$ 2 ${{< /math >}} and enter the loop:

![Tutor 11](/images/05/tutor10_11.png?classes=border,shadow)

In the loop, we'll update `line` to contain one more asterisk, and then print it before looping back to the top.

![Tutor 13](/images/05/tutor10_13.png?classes=border,shadow)

The list still isn't empty, so we'll update `i` to be {{< math >}}$ 3 ${{< /math >}} this time:

![Tutor 14](/images/05/tutor10_14.png?classes=border,shadow)

And then we'll update `line` and print it.

![Tutor 16](/images/05/tutor10_16.png?classes=border,shadow)

By now, we should have a pretty good idea of what this loop does. There's one more item in the list, so we'll update `i` to be {{< math >}}$ 4 ${{< /math >}}:

![Tutor 17](/images/05/tutor10_17.png?classes=border,shadow)

Inside the loop, we'll add one more asterisk to `line` and then print it.

![Tutor 19](/images/05/tutor10_19.png?classes=border,shadow)

Finally, we're back at the top of the loop. Since there are no more items left in the list, we can jump to the bottom of the for loop and continue the program from there. 

![Tutor 20](/images/05/tutor10_20.png?classes=border,shadow)

In this case, there's no more code left in the `main()` function, so it will end and the program will terminate. 

Looking at the output, we see that this program will print a right triangle of asterisks that is `x` lines tall and `x` characters wide at the bottom.

A full execution of this program is shown in this animation.

![Tutor Animation 10](/images/05/tutor10.gif?classes=border,shadow)

As we can see, working with for loops in Python is a quick and easy way to repeat a block of statements a specific number of times using the `range()` function.

## Converting to a While Loop

It is possible to convert any for loop using the `range()` function in Python to a while loop. This can be done following a simple three-step pattern:

1. Set an initial value for the iterator variable before the loop
1. Update the iterator value at the end of each loop iteration
1. Convert to a while loop and check the ending value of the iterator variable in the Boolean expression

Let's look at the code from the example above:

```python
x = int(input("Enter a number: "))
line = ""
for i in range(x):
    line = line + "*"
    print(line)
```

To convert this for loop into a while loop, we can follow the three steps listed above. First, we must set an initial value for our iterator variable `i` before the loop. Since the first value stored in `i` is {{< math >}}$ 0 ${{< /math >}}, we'll set it to that value.

```python
x = int(input("Enter a number: "))
line = ""
i = 0
for i in range(x):
    line = line + "*"
    print(line)
```

Next, we need to update the value of the iterator variable at the end of each loop iteration. Since we didn't provide an argument for the `step` value in the `range()` function, we know that `i` will just be incremented by {{< math >}}$ 1 ${{< /math >}} each time. So, we'll add a short line to increment `i` at the bottom of the loop:

```python
x = int(input("Enter a number: "))
line = ""
i = 0
for i in range(x):
    line = line + "*"
    print(line)
    i = i + 1
```

Finally, we can switch the for loop to a while loop. In the Boolean expression, we want to repeat the loop while the iterator variable `i` has not reached the maximum value. So, we'll use the Boolean expression `i < x` in the new while loop:

```python
x = int(input("Enter a number: "))
line = ""
i = 0
while i < x:
    line = line + "*"
    print(line)
    i = i + 1
```

There we go! That's the basic process for converting any for loop using `range()` in Python to be a while loop. It's a useful pattern to know and recognize when it is used in code.
