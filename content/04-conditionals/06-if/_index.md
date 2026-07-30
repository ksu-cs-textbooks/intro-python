---
title: "If"
pre: "6. "
weight: 60
---

{{< youtube G7__fW15Log >}}

<!-- Old: SfaAhCS6vAY -->
<!-- Older: J0Zv4807Quw -->

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

Now that we understand how to use Boolean values in our programs, it's time to put those values to use. One way to think of the result of a Boolean expression is that it helps us make a **decision** in our programs. For example, if we want to do something special in our program when the user inputs the value {{< math >}}$ 42 ${{< /math >}} into the variable `x`, then we can write the Boolean expression `x == 42` to help us decide if the user input the correct value.

Once we have that decision made, we need some way to tell our program to run a different piece of code based on the outcome of that decision. In Python, as well as most other programming languages, we can use a special construct called an **if statement** to do this. If statements are one example of a **conditional statement** in programming. 

These conditional statements allow us to affect the **control flow** of our programs. Effectively, we can use a Boolean expression to determine whether a particular piece of code should be executed or not. In an **if statement**, we include a Boolean expression and a block of statements. If the Boolean expression evaluates to `True`, then we execute the code in the block of statements. If it is `False`, then we skip the block and continue with the rest of the program.

The structure of an if statement in Python is shown below:

```python
if <boolean expression>:
    <block of statements>
```

In this structure, we have a `<boolean expression>` that is evaluated. After the Boolean expression is a colon `:`. 

Then, the `<block of statements>` is included below the if statement's first line, and it must be indented one level. In Python, the `<block of statements>` must include at least one line of code, otherwise Python won't be able to understand it. 

## Indentation in Python

Let's briefly discuss **indentation** in Python, since it is very important and is usually something that trips up new Python developers. Most programming languages use symbols such as curly braces `{}` to surround blocks of statements in code, making it easy to tell where one block ends and another begins. Similarly, those languages also use symbols such as semicolons `;` at the end of each line of code, indicating the end of a particular statement.

These programming languages use those symbols to make it clear to both the developer and the computer where a particular line or block of code begins and ends, and it makes it very easy for tools to understand and run the code. As an interesting side effect, it also means that the code doesn't need to follow any particular structure beyond the use of those symbols - many of the languages allow developers to place multiple statements, or even entire programs, on a single line of code. Likewise, indentation is completely optional, and only done to help make the code more readable. 

Python takes a different approach. Instead of using symbols like semicolons `;` and curly braces `{}` to show the structure of the code, Python uses newlines and indentation for this purpose. By doing so, Python is simultaneously simpler (since it has fewer symbols to learn) and more complex (the indentation has meaning) than other languages. It's really a tradeoff, though most Python programmers will admit that not having to deal with special symbols in Python is well worth the effort of making sure that the indentation is correct, especially since most other languages follow the same conventions anyway, even if it isn't strictly required.

So, how can we **indent** code in Python? Typically, we use four consecutive spaces for each level of indentation. So, below the conditional statement `if <boolean expression>:` shown above, we would place four spaces before the first line of the `<block of statements>`, and then continue to do so for each line below that should be included in the block of code. 

Thankfully, most text editors used for programming, such as Codio, Atom, Visual Studio Code, and more, are all configured to convert tabs to spaces. So, we can simply press the **Tab** key on the keyboard to insert the correct amount of spaces for one level of indentation. Likewise, we can usually use **Shift+Tab** to remove four spaces. 

Finally, it is worth noting that there is a special symbol that actually is a **tab** in text, which is represented as `\t` in a string. Like the newline symbol, we can't see it in our UI in most cases, but it is there. Some non-programming text editors, such as Notepad in Windows, will insert that symbol instead of four spaces when we press the **Tab** key. If we try to run a program that contains those symbols, the Python interpreter may not be able to read our program and will give us an error about inconsistent use of tabs and spaces. If that happens, we'll need to make sure our program is consistently using only tabs or spaces for indentation. Most editors used for programming have a special function for converting tabs to spaces, and there are lots of online tools available for this as well. 

## Code Tracing Example - False

Let's go through a couple of code tracing examples in Python Tutor to see how an if statement works in code.

Consider this program in Python:

```python
x = int(input("Enter a number: "))
if x == 7:
    print("That's a lucky number!")
print("Thanks for playing!")
```

We can see this example by clicking on this [Python Tutor](https://pythontutor.com/visualize.html#code=x%20%3D%20int%28input%28%22Enter%20a%20number%3A%20%22%29%29%0Aif%20x%20%3D%3D%207%3A%0A%20%20%20%20print%28%22That's%20a%20lucky%20number!%22%29%0Aprint%28%22Thanks%20for%20playing!%22%29&cumulative=false&curInstr=0&heapPrimitives=nevernest&mode=display&origin=opt-frontend.js&py=3&rawInputLstJSON=%5B%5D&textReferences=false) link. At first, our window should look something like this:

When we step through the program, the first line of code will ask the user to input a number, so Python Tutor will show an input box at the bottom of the window:

![Tutor 1](/images/04/tutor5_1.png?classes=border,shadow)

For this first time through the program, let's assume the user inputs the string `"42"` as input:

![Tutor 2](/images/04/tutor5_2.png?classes=border,shadow)

So, when we click Submit, we'll see the integer value {{< math >}}$ 42 ${{< /math >}} stored in the variable `x` in the `Global` frame:

![Tutor 3](/images/04/tutor5_3.png?classes=border,shadow)

At this point, we've reached the if statement. The first step is to evaluate the Boolean expression `x == 7`. Since `x` is actually storing the value {{< math >}}$ 42 ${{< /math >}}, this statement will evaluate to `False`. So, when we click the Next button on the state below:

![Tutor 4](/images/04/tutor5_4.png?classes=border,shadow)

We'll see that the program arrow jumps past the block of statements in the if statement. So, the next line will simply print the goodbye message:

![Tutor 5](/images/04/tutor5_5.png?classes=border,shadow)

The entire process is shown in the animation below:

![Tutor 5 GIF](/images/04/tutor5.gif?classes=border,shadow)

As we can see, when the Boolean expression evaluates to `False`, we'll just skip the block of statements inside of the if statement.

## Code Tracing Example - True

Now let's see what happens when the Boolean expression evaluates to `True` instead. To see that, we can go back to the point where our program is asking for input, as shown below:

![Tutor 1](/images/04/tutor6_1.png?classes=border,shadow)

This time, we'll assume the user inputs the string `"7"` as input. 

![Tutor 2](/images/04/tutor6_2.png?classes=border,shadow)

So, when we click Submit, we'll see the integer value {{< math >}}$ 7 ${{< /math >}} stored in the variable `x` in the `Global` frame:

![Tutor 3](/images/04/tutor6_3.png?classes=border,shadow)

This time, when we reach the if statement, we'll see that the Boolean expression `x == 7` will evaluate to `True`. So, when we click the Next button, we'll be taken to the block of statements inside of the if statement:

![Tutor 10](/images/04/tutor6_4.png?classes=border,shadow)

Here, we'll print the special message for finding a lucky number:

![Tutor 11](/images/04/tutor6_5.png?classes=border,shadow)

Then, we'll print the program's goodbye message:

![Tutor 12](/images/04/tutor6_6.png?classes=border,shadow)

The entire process can be seen in this animation:

![Tutor 2 Gif](/images/04/tutor6.gif?classes=border,shadow)

So, when the Boolean expression evaluates to `True`, we'll run the code inside the if statement. If it is `False`, then we'll just skip past the if statement and continue with the rest of our program. 

## If Statement Flowchart

Another way to visualize an if statement is using a flowchart. Consider the following Python code:

```python
x = int(input("Input: "))
if x > 0:
  print(x)
print("Goodbye")
```

This Python code can also be represented as the flowchart shown below:

![If Flowchart](/images/04/ifthen.png?classes=border,shadow)

When we read flowcharts like this, we typically go from top to bottom, starting with the circle labeled "START". The first  step is to read input from the user, and store that value in the variable `x`. 

Then, we reach a decision node, which uses a diamond shape. This node asks if the value in the variable `x` is greater than 0. Notice that there are two lines coming from the decision node: one labeled "True" and another labeled "False". They correspond to the possible values that can result from evaluating the Boolean expression `x > 0`. So, if the result of that expression is `True`, then we'll follow the path that exits the diamond from the side labeled "True", and we'll output the value `x` to the terminal. Once that is done, we can follow that path around to the next box that will output the string `"Goodbye"`. 

If that result is `False`, then we'll follow the downward path labeled "False" and skip the path to the side. Instead, we'll just reach the line that prints `"Goodbye"` and then end the program.

As we learn how to use if statements in our code, we might find it easier to use flowcharts or other tools to help understand exactly what our program will do. The path that a program takes through a flowchart like this is called the **control flow** of the program. We'll discuss that topic a bit more toward the end of this lab. 