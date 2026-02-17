+++
title = "Vending Machine"
hidden = true
pre = "A. "
+++

## Implementing a Vending Machine

In the third programming assignment, we're going to build a simple finite state machine program that represents a real-life vending machine. This is a great way to practice both loops and conditional statements in our code.

{{% notice note "Learning Objectives" %}}

The goal of this assignment is to demonstrate understanding of the following topics in Python:

* Boolean Logic
* Conditional Statements
* Loops
* Nested Loops & Conditional Statements
* Loops for Input

{{% /notice %}}

### Finite State Machine in Code

A finite state machine is a simple representation of a real-world system that has a defined set of states and transitions between those states. Finite state machines can be described using diagrams that show the various states and transitions. Consider the following example of a finite state machine for a coin-operated turnstile:

![Finite State Machine Turnstile](/images/hw3/turnstile.svg?classes=border,shadow)[^1]

[^1]: File:Turnstile state machine colored.svg. (2023, February 8). Wikimedia Commons. Retrieved 17:19, May 30, 2023 from https://commons.wikimedia.org/w/index.php?title=File:Turnstile_state_machine_colored.svg&oldid=731038380.

The turnstile is initially in the **locked** state. If someone tries to push the turnstile, it will go through the _push_ transition but it will arrive back at the **locked** state. However, if someone inserts a coin, the _coin_ transition will cause the turnstile to move to the **unlocked** state. From there, any additional coins will not change the state, but if someone pushes on the turnstile, it will allow them through and transition back to the **locked** state. 

In code, we could represent this turnstile using the following Python code:

```python
# initial state
state = "locked"

# initial state transition
x = "start"

while x != "quit":
    print(f"The turnstile is in the {state} state.")
    
    # locked state
    if state == "locked":
        # can customize input prompt to be different for each state
        x = input("Enter \"coin\" or \"push\" to change state, or \"quit\" to quit: ")

        # coin transition
        if x == "coin":
            # change state
            state = "unlocked"

        # push transition
        elif x == "push":
            # do nothing
            print("The turnstile is locked!")

        # check for quit
        elif x != "quit":
            # invalid input
            print("Invalid input!")

    # unlocked state
    elif state == "unlocked":
        # can customize input prompt to be different for each state
        x = input("Enter \"coin\" or \"push\" to change state, or \"quit\" to quit: ")

        # coin transition
        if x == "coin":
            # do nothing
            print("The turnstile is already unlocked!")

        # push transition
        elif x == "push":
            # change state
            state = "locked"

        # check for quit
        elif x != "quit":
            # invalid input
            print("Invalid input!")

    # unexpected state
    else:
        print("Error! Unexpected State")

print("Goodbye")
```

This code uses a while loop so that the program will repeat indefinitely as long as the user does not input the `"quit"` command. Inside of the loop, there is a set of if statements that determine the current state. Each state has a prompt for input, which can be customized with the transitions allowed in that state. Then, there is a second set of if statements that will analyze the user's input and determine if a state transition is required. 

Notice that some of the inputs do nothing, so we just print a message letting the user know that nothing has changed. These may be carefully removed without affecting the overall program, but they are included here for clarity.

There are many ways to implement a finite state machine in Python, and this is just one example. However, hopefully this example is a helpful structure that you can use to build the solution to this assignment.

## The Assignment

Write your program in a file named and the HW number `homework#.py`. This should be a complete Python program consisting of the following elements:

1. It should represent a finite state machine as described by the diagram below.
1. It should prompt the user for the inputs required in each state. If an invalid input is provided, it should display an error to the user and prompt for input again.
   1. If a state requires multiple inputs, it is acceptable to start from the beginning of the state if an invalid input is received.
1. When valid input is received, it should transition to the appropriate state and clearly inform the user what state the finite state machine is currently in.
1. The program should make use of several required variables as described below. These variables will be used to assess your program and confirm that it matches the finite state machine given.

### Finite State Machine Diagram

Your program should conform to the following finite state machine diagram:

![Finite State Machine](/images/hw3/vending_fsm.png?classes=border,shadow)

### Required Variables

Your program should contain the following variables:

* `state` - this will store the current state of the machine. Initial value: `"A"`
* `cost` - this is the cost of each item in the machine. Initial value: `7`
* `money` - the total amount of money currently inserted into the machine. Initial value: `0`
* `item` - the item selected by the user in state C and dispensed in state D. `1` is soda, `2` is snack, `3` is candy. Initial value: `0`
* `inv_soda` - this the number of sodas in the machine. Initial value: `4`
* `inv_snack` - this the number of snacks in the machine. Initial value: `2`
* `inv_candy` - this the number of candy bars in the machine. Initial value: `3`

You may use more variables than this, but each of these must be used correctly in your code.

### States

Each state in the finite state machine is described in detail below. 

{{% notice warning "Is this real life?" %}}

The vending machine we are simulating is provided by the "Cheap but Not Quite Right" vending machine company. Because of this, their vending machines have a few quirks that are not (usually) present in real-world vending machines. So, make sure you read the state descriptions below carefully and implement them as described here, even if you don't think a _real_ vending machine would be built this way.

{{% /notice %}}

* **State A:** Start/Idle. This state will wait for the user to input `"start"` to transition to state B. The user can also input `"restock"` to transition to state F. If the user inputs `"quit"` at this state only, the program will transition to state G and exit.
* **State B:** Insert Coins. This state will prompt the user to input an amount of coins (as an integer greater than 0). The user can also input `"refund"` to cancel the transaction and move to state E. Once a valid number of coins is input, store the value in `money` and automatically transition to state C.
    * **Quirk**: The vending machine has a 30% chance to not detect the money that is inserted. So, if the user inputs a value but before transitioning to state C, determine if the money is lost. If so, print `"Oops, I lost your money"` and remain in state B. _Hint: you can use random numbers to determine if something happens with a 30% chance._**
* **State C:** Select. This state will prompt the user to choose an item to be dispensed, either `"soda"`, `"snack"` or `"candy"`. The user can also input `"refund"` to cancel the transaction and move to state E. If the user makes a valid selection, store the value in `item` and automatically transition to state D. 
* **State D:** Dispense. This state will determine if the user has input enough money to purchase the product, and if there is at least 1 of the product remaining in inventory If so, the vending machine will print `"Dispensing {item}"` and deduct the cost from the money inserted. If not, the vending machine will print `"Not enough money"` or `"Not enough product"`, whichever is appropriate. The machine will automatically transition to state E.
* **State E:** Making Change. This state should print a message to the user in the form "Returning {value} in change" for any remaining money. The machine will automatically transition to state A.
* **State F:** Restock. In this state, the machine will reset the stock for the three items back to the initial values. The machine will automatically transition back to state A. 
* **State G:** Off. In this state, the program will exit.
    * _Hint: You can check for this state in your outermost while loop to determine when to terminate the loop._

Your program **should not** include any additional states. 

{{% notice tip "Checking for Digits" %}}

You may find it useful to be able to determine if a user has input a string that consists solely of digits. In Python, we can use the `.isdigit()` function as shown below:

```python
x = input("Enter an integer: ")
if x.isdigit():
  print("Your input is a valid number")
  value = int(x)
  print(f"your number is {value}")
else:
  print("Your input is not a number")
```

This can also be done using a try-catch statement, which we haven't covered in this class.

{{% /notice %}}

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

Below are a couple of screenshots showing a sample execution of the model solution for this homework assignment. Your submission should have similar functionality and output, but the text for input prompts may differ slightly:

![Sample Run 1](/images/hw3/hw3a.png?classes=border,shadow)

![Sample Run 2](/images/hw3/hw3b.png?classes=border,shadow)

## Grading Rubric

Your project will be graded according to the following rubric:

* Initial State & State A: 10%
* States B and C: 30%
* State D: 30%
* States E, F and G: 20%
* Documentation Comments: 10%

## Submitting

Once you have completed this program, submit your `homework` file via Codio or the assignment on Canvas.
