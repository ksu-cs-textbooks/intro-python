---
title: "Print Statement"
pre: "3. "
weight: 30
---

{{< youtube QN69944REys >}}

<!-- Old: B7W1w4H610k -->
<!-- Older: yveXTTVXzZ0 -->

#### Resources

* <a href="{{% relref "./slides" %}}" target="_blank">Slides</a>

Before we learn to write our first program, let's start by introducing some important vocabulary terms:

* **string**: A **string** in programming is any text that is stored as a value. We typically represent strings by placing them inside double quotes `""` in our code and elsewhere.
* **value**: A **value** is a piece of data that our program is storing and manipulating. In our pseudocode, values consist of either numbers or strings.
* **keyword**: A **keyword** is a reserved word in a programming language that defines a particular statement, expression, structure, or other use. As we'll learn later, we cannot use these keywords as variable or procedure names.
* **statement**: A **statement** refers to a piece of code that performs an action, but doesn't result in any value. Most complete lines of code are considered statements.
* **expression**: An **expression**, on the other hand, is a piece of code that, when evaluated, will result in a value that can be used or stored. An expression can even contain multiple expressions inside of it!

We'll use these terms to help us understand different parts of the code in our programs. Now that we've covered them them, we can start to discuss the various statements in Python. 

The first statement that we'll cover in the Python programming language is the `print(expression)` statement. This statement is used to display output to the user via the terminal. So, when Python runs this statement, it will evaluate the `expression` to a single value, and then print that value to the terminal. 

For example, the simplest Python code would be a simple Hello World program, where we use the `print(expression)` statement to display the text `"Hello World"` to the user:

```python
print("Hello World")
```

Notice that the `expression` part of the statement contains `"Hello World"` in quotation marks? That is because `"Hello World"` is text, so we should put it in quotes and make it into a string in our code. Also, since the string `"Hello World"` can be treated like a value, we can also say it is an expression, and therefore we can use it in the `expression` part of the statement. This may seem pretty straightforward now, but as our programs become more complex it is important to think about what pieces of code can be treated as values, expressions, and statements. 

When we run that program in Python, we'll see the following output:

```tex
Hello World
```

If you look at the output, you might notice something strange - the text on our user interface doesn't include the quotation marks `""` that the expression `"Hello World"` contained. When we display text to the user, Python will remove the quotation marks from the beginning and the end of the string, and just display the text inside. Pretty handy!

Let's go through the full process of writing and running that program in Python!

## Writing a Python Program

The first step to create a program in Python is to create a text file to store the code. This file should have the file extension `.py` to indicate that it is a Python program. So, we'll need to create that file either on our computers or in Codio or another tool if we are using one. For example, in Codio we can create the file in the `python` folder by right-clicking on it and selecting the **New File** option. We'll name the file `hello.py`:

![New File](/images/01/new_file.png?classes=border,shadow)

Once we've created that file, we can then open it by clicking on it. In Codio and in other online tools, it will open in the built-in editor. On a computer, we'll need to open it in a text editor specifically designed for programming. We recommend  [Visual Studio Code](https://code.visualstudio.com/), which is available on all platforms. Tools like the built-in Notepad tool on Windows, or a word processor like Word or Pages do not work for this task.

In that file, we'll simply place the code shown above, like this:

![Code](/images/01/code.png?classes=border,shadow)

That's all there is to it!

## Running a Python Program

Once we've written the code, we can open the **Terminal** and navigate to where the code is stored in order to run the program. On Codio, we'll just use the `cd python` command to enter the `python` directory. On a computer, we'll need to navigate the file system to find the location where we placed our code. We highly recommend creating a folder directly within the home directory and placing all of our code there - that will make it easy to find!

Once we are in the correct directory, we can use the `ls` command to see the contents of that directory. If we see our `hello.py` file, we are in the correct location:

![Show Python File](/images/01/file.png?classes=border,shadow)

If we don't see our file, we should make sure we've saved it and that our current working directory is the same location as where the file is stored. 

Finally, we can execute the file in Python using the `python3` command, followed by the name of the file:

```bash
python3 hello.py
```

If everything works correctly, we should see output similar to this:

![Hello World Output](/images/01/hello.png?classes=border,shadow)

There we go! We've just run our first program in Python! That's a great first step to take. 

Of course, there are lots of ways that this could go wrong. So, if you run into any issues getting this to work, please take the time to contact an instructor and ask for assistance. This process can be daunting the first time, since there are so many things to learn and so many intricacies we simply don't have time to cover up front. Don't be afraid to ask for help!