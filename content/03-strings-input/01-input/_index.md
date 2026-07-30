---
title: "Input"
pre: "1. "
weight: 10
---

{{< youtube X6BVvQTA6IQ >}}
<!-- Old: iLuRm6d3pDc -->
#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

The Python programs we've written up to this point are very static - each time we run the program, it will perform the same exact operations. Since we're running these programs on a real computer, it might be helpful to build programs that can read and respond to input from the user, making them much more useful overall. Python includes many different ways to handle user input, but in this lab we'll just focus on the simple `input()` function.

## Input in Python

The `input()` function is used to display a prompt the user and then record input. Let's look at a quick example:

```python
name = input("Enter your name: ")
print("Hello ", end="")
print(name)
```

Here, we see that the `input()` function actually accepts a message as an argument, which will be displayed to the user. After the message is printed, the user will be given a cursor to enter text immediately after it. Once the user presses the ENTER key, the `input()` function will read the input that was entered and store it as a string value or `str` data type in the variable called `name`. 

For example, if the user inputs `Willie Wildcat` at the prompt, this program's output will look like this:

```tex
Enter your name: Willie Wildcat
Hello Willie Wildcat
```

We can see this even more clearly in the terminal. When we first run the program, we'll see the prompt `"Enter your name:"` printed, followed by a cursor prompting the user to enter something:

![Terminal Before Input](/images/03/terminal1.png?classes=border,shadow)

Once the user types the input and presses ENTER, the rest of the program will run:

![Terminal Before Input](/images/03/terminal2.png?classes=border,shadow)

Now we see the cursor is at the next command prompt, ready to run another program.