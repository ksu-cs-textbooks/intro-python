---
title: "Worked Example"
pre: "14. "
weight: 140
---

{{% youtube YCqzBO6W3XU %}}

#### Resources

* <a href="{{<relref "./slides">}}" target="_blank">Slides</a>

Let's go through another worked example to see how we can translate a problem statement into a working program. We'll also take a look at how we can test the program to verify that it is working as intended.

## Problem Statement

Here's a short and simple game that can be played by three players:

> Three players each guess a positive integer greater than {{< math >}}$ 0 ${{< /math >}}, and then share them simultaneously. The winner is chosen following this formula:
> * If any two players have chosen the same number, the game is a tie.
> * If all players have chosen even numbers, or all players have chosen odd numbers, then the smallest number wins.
> * Otherwise, the largest number wins.

This game has some similarities to Rock Paper Scissors, but the logic is quite a bit different. So, let's work through how we would build this program using conditional statements. 

## Initial Program

Our first step should be to build a simple program that handles user input. So, we'll create a new Python program that contains three variables to store user input. We'll also use the `input()` function to read input, and the `int()` function to convert each input to an integer. Below that, we'll add some print statements for testing. At this point, our program should look similar to this:

```python
p1 = int(input("Enter a positive integer for player 1: "))
p2 = int(input("Enter a positive integer for player 2: "))
p3 = int(input("Enter a positive integer for player 3: "))

# debugging statements
print(f"player 1 chose {p1}")
print(f"player 2 chose {p2}")
print(f"player 3 chose {p3}")
```

With this code in place, we've already created a Python program that we can run and test. So, before moving on, let's run this program at least once to verify that it works correctly. This will help us quickly detect and correct any initial errors in our program, and make it much easer to debug logic errors later on.

So, when we run this program, we should see output similar to this:

![Program Output 1](/images/04/output1.png?classes=border,shadow)

## Checking for Valid Input

Now that we have confirmed our program is working, let's start writing the logic in this program. Deciding which conditional statement to write first is a very important step in designing a program, but it is difficult to learn what works best without lots of practice. If we look at the problem statement above, we see that there are several clear conditions that we'll have to check:

* Are the numbers all even?
    * If so, which number is smallest?
* Are the numbers all odd?
    * If so, which number is smallest?
* Are the numbers not all even or odd?
    * If so, which number is largest?

However, there is one more condition that we should also keep in mind. This one isn't clearly stated in the rules, but implied in the problem statement itself:

* Are all numbers greater than {{< math >}}$ 0 ${{< /math >}}? 

So, to write an effective program, we should first make sure that all of the inputs are greater than {{< math >}}$ 0 ${{< /math >}}. We can do this using a simple conditional statement. We'll also remove our debugging statements, as they are no longer needed:

```python
p1 = int(input("Enter a positive integer for player 1: "))
p2 = int(input("Enter a positive integer for player 2: "))
p3 = int(input("Enter a positive integer for player 3: "))

if p1 <= 0 or p2 <= 0 or p3 <= 0:
    print("Error")
else:
    print("All numbers are greater than 0")
```

In this conditional statement, we are checking to see if any one of the numbers is less than or equal to {{< math >}}$ 0 ${{< /math >}}. Of course, using some Boolean algebra and De Morgan's law, we can see that this is equivalent to checking if all numbers are not greater than {{< math >}}$ 0 ${{< /math >}}. Either approach is valid.

## Checking for Ties

Once we know we have valid input, the next step in determining a winner is to first determine if there are any ties. For this, we simply need to check if any two players input the same number. Since there are three players, we need to have three different Boolean expressions to accomplish this. In our program, we could add a conditional statement as shown here:

```python
p1 = int(input("Enter a positive integer for player 1: "))
p2 = int(input("Enter a positive integer for player 2: "))
p3 = int(input("Enter a positive integer for player 3: "))

if p1 <= 0 or p2 <= 0 or p3 <= 0:
    print("Error")
elif p1 == p2 or p2 == p3 or p3 == p1:
    print("Tie")
else:
    print("Not a Tie")
```

This is a pretty simple Boolean expression that will check and see if any possible pair of inputs is equal. We use the `or` Boolean operator here since any one of those can be true in order for the whole game to be a tie.

## All Odds or Evens

Next, let's tackle whether the inputs are all odds or all evens. If we look at the rules above, this seems to be the next most logical thing we'll need to know in order to determine the winner of the game. Recall that we can determine if a number is even or odd by using the modulo operator `%` and the number {{< math >}}$ 2 ${{< /math >}}. If that result is {{< math >}}$ 0 ${{< /math >}}, the number is even. If not, the number is odd. 

In code, we can express that in a conditional statement as shown here:

```python
p1 = int(input("Enter a positive integer for player 1: "))
p2 = int(input("Enter a positive integer for player 2: "))
p3 = int(input("Enter a positive integer for player 3: "))

if p1 <= 0 or p2 <= 0 or p3 <= 0:
    print("Error")
elif p1 == p2 or p2 == p3 or p3 == p1:
    print("Tie")
elif p1 % 2 == 0 and p2 % 2 == 0 and p3 % 2 == 0:
    print("All numbers are even")
elif p1 % 2 != 0 and p2 % 2 != 0 and p3 % 2 != 0:
    print("All numbers are odd")
else:
    print("Numbers are both even and odd")
```

Notice that we are using the `and` Boolean operator in these conditional statements, because we want to be sure that all numbers are either even or odd. 

In this example, we're also choosing to use chained conditional statements with the `elif` keyword instead of nesting the conditionals. This helps clearly show that each outcome is **mutually exclusive** from the other outcomes. 

However, we chose to nest the program logic inside of the outermost conditional statement, which checks for valid input. This helps us clearly see the part of the program that is determining who wins the game, and the part of the program that is validating the input. Later on, we'll see how we can rewrite that conditional statement into a loop to prompt the user for new input, so it makes sense for us to keep it separate for now. 

## Determining the Smallest Number

Once we know if the numbers are either all even or all odd, we know that the winning number is the smallest number of the three inputs. So, how can we determine which number is the smallest? We can use a couple of nested conditional statements!

Let's handle the situation where all numbers are even first. We know that the smallest number must be smaller than both other numbers. So, we can use a couple of Boolean expressions to check if that is the case for each number:

```python
p1 = int(input("Enter a positive integer for player 1: "))
p2 = int(input("Enter a positive integer for player 2: "))
p3 = int(input("Enter a positive integer for player 3: "))

if p1 <= 0 or p2 <= 0 or p3 <= 0:
    print("Error")
elif p1 == p2 or p2 == p3 or p3 == p1:
    print("Tie")
elif p1 % 2 == 0 and p2 % 2 == 0 and p3 % 2 == 0:
    if p1 < p2 and p1 < p3:
        print("Player 1 wins")
    elif p2 < p1 and p2 < p3:
        print("Player 2 wins")
    else:
        print("Player 3 wins")
elif p1 % 2 != 0 and p2 % 2 != 0 and p3 % 2 != 0:
    print("All numbers are odd")
else:
    print("Numbers are both even and odd")
```

Here, we start by checking if player 1's number is smaller than both player 2's and player 3's. If so, then player 1 is the winner. If not, we do the same for player 2's number. If neither player 1 nor player 2 has the smallest number, then we can assume that player 3 is the winner without even checking. 

As it turns out, we would end up using the exact same code in the situation where all numbers are odd, so for now we can just copy and paste that set of conditional statements there as well:

```python
p1 = int(input("Enter a positive integer for player 1: "))
p2 = int(input("Enter a positive integer for player 2: "))
p3 = int(input("Enter a positive integer for player 3: "))

if p1 <= 0 or p2 <= 0 or p3 <= 0:
    print("Error")
elif p1 == p2 or p2 == p3 or p3 == p1:
    print("Tie")
elif p1 % 2 == 0 and p2 % 2 == 0 and p3 % 2 == 0:
    if p1 < p2 and p1 < p3:
        print("Player 1 wins")
    elif p2 < p1 and p2 < p3:
        print("Player 2 wins")
    else:
        print("Player 3 wins")
elif p1 % 2 != 0 and p2 % 2 != 0 and p3 % 2 != 0:
    if p1 < p2 and p1 < p3:
        print("Player 1 wins")
    elif p2 < p1 and p2 < p3:
        print("Player 2 wins")
    else:
        print("Player 3 wins")
else:
    print("Numbers are both even and odd")
```

That covers the situations where all players have input either even or odd numbers. We can quickly test this program a couple of times by providing various inputs that match those cases. So, when we run this program, we should see output like this:

![Program Output 2](/images/04/output2.png?classes=border,shadow)

## Determining the Largest Number

The last step is to determine the largest number in the case that the numbers are not all even or odd. Since we've already written some code to handle the opposite case, let's quickly copy and tweak that code to handle this case. We can then place that code `False` branch of our conditional statement handling the logic of the program:

```python
p1 = int(input("Enter a positive integer for player 1: "))
p2 = int(input("Enter a positive integer for player 2: "))
p3 = int(input("Enter a positive integer for player 3: "))

if p1 <= 0 or p2 <= 0 or p3 <= 0:
    print("Error")
elif p1 == p2 or p2 == p3 or p3 == p1:
    print("Tie")
elif p1 % 2 == 0 and p2 % 2 == 0 and p3 % 2 == 0:
    if p1 < p2 and p1 < p3:
        print("Player 1 wins")
    elif p2 < p1 and p2 < p3:
        print("Player 2 wins")
    else:
        print("Player 3 wins")
elif p1 % 2 != 0 and p2 % 2 != 0 and p3 % 2 != 0:
    if p1 < p2 and p1 < p3:
        print("Player 1 wins")
    elif p2 < p1 and p2 < p3:
        print("Player 2 wins")
    else:
        print("Player 3 wins")
else:
    if p1 > p2 and p1 > p3:
        print("Player 1 wins")
    elif p2 > p1 and p2 > p3:
        print("Player 2 wins")
    else:
        print("Player 3 wins")
```

There we go! We've written a complete program that implements the problem statement given above. Did you think it would end up being this complex? Sometimes even a simple problem statement ends up requiring quite a bit of code to implement it fully. 

## Testing - Branch Coverage

The next step is to perform some testing of our program to make sure it is fully working. To do that, we need to come up with a set of inputs that would achieve branch coverage, and possibly even path coverage. However, this time our program is spread across three different sets of conditional statements, so it makes it a bit more difficult to do. So, let's focus on each individual statement separately and see if we can find a set that work for each of them.

### Top-Level Statement

First, we see the top-level statement has 5 branches to cover, so we need to come up with 5 different sets of inputs in order to achieve branch coverage. We can keep the inputs very small, just to make our testing a bit simpler. Here are the 5 branches to cover, and an input that will reach each one:

* Invalid input: `-1, -1, -1`
* Tie: `1, 1, 1`
* All Even: `2, 4, 6`
* All Odd: `1, 3, 5`
* Mixed: `1, 2, 3`

Notice how we are trying to come up with the simplest possible inputs for each branch? That will make it easier to combine these inputs with the ones used in other conditional statements to find an overall set of inputs that will achieve branch coverage for the entire program.

### Smallest Statements

Next, we can look at the code to find the smallest number. This code is used when the inputs are either all even or all odd. So, we know that either inputs `2, 4, 6` or `1, 3, 5` will execute this code.

Within the code itself, we see three branches, depending on which player wins. So, if we start with the input `2, 4, 6`, we'll see that this will execute the branch where player 1 wins. To execute the other branches, we can simply reorder the inputs:

* Player 1 Wins: `2, 4, 6`
* Player 2 Wins: `4, 2, 6`
* Player 3 Wins: `4, 6, 2`

That will achieve branch coverage for the "smallest" conditional statement, and even overlaps with one of the inputs used in the top-level statement.

### Largest Statement

The same applies to the conditional statement to find the largest number, but in this case we need a mix of even and odd numbers in the input. So, the input `1, 2, 3` will execute this code, and that input results in player 3 winning. Once again, we can reorder that input a bit to execute all three branches of this code:

* Player 1 Wins: `3, 1, 2`
* Player 2 Wins: `1, 3, 2`
* Player 3 Wins: `1, 2, 3`

### Overall Program

Therefore, based on our analysis, we can achieve branch coverage across the entire program using 9 different inputs:

* Invalid input: `-1, -1, -1`
* Tie: `1, 1, 1`
* All Even:
    * Player 1 Wins: `2, 4, 6`
    * Player 2 Wins: `4, 2, 6`
    * Player 3 Wins: `4, 6, 2`
* All Odd: `1, 3, 5`
* Mixed:
    * Player 1 Wins: `3, 1, 2`
    * Player 2 Wins: `1, 3, 2`
    * Player 3 Wins: `1, 2, 3`

This will execute each branch of all conditional statements in the program at least once. 

## Path Coverage

Once we've achieved branch coverage, we should also quickly look at path coverage: is there any possible pathway through this program that we haven't tested yet? As it turns out, there are two, but they are somewhat difficult to find. Can you spot them? See if you can figure it out before continuing on in this page.

The paths we missed are situations where the numbers are all odd, but a player other than player 1 wins. While we tested all possible branches in the "smallest" conditional statement, we didn't test it using all odd numbers more than once. So, to truly achieve path coverage, we should add two more inputs to our list above:

* Invalid input: `-1, -1, -1`
* Tie: `1, 1, 1`
* All Even:
    * Player 1 Wins: `2, 4, 6`
    * Player 2 Wins: `4, 2, 6`
    * Player 3 Wins: `4, 6, 2`
* All Odd: 
    * Player 1 Wins: `1, 3, 5`
    * Player 2 Wins: `3, 1, 5`
    * Player 3 Wins: `3, 5, 1`
* Mixed:
    * Player 1 Wins: `3, 1, 2`
    * Player 2 Wins: `1, 3, 2`
    * Player 3 Wins: `1, 2, 3`

So, with a total of 11 inputs, we can finally say we've achieved both branch coverage and path coverage of this program. 