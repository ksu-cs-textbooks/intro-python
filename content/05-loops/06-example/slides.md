---
type: "reveal"
hidden: true
---

<section>
    <h3>Problem Statement</h3>
    <p style="font-size: 55px">The game will select two random numbers from  to , one for each player. Then, each player will guess a number in the range, and the game will print either “higher” if that player’s secret number is larger than the guess, or “lower” if the player’s secret number is smaller than the guess. Players will alternate turns until one player correctly guesses their secret number and wins the game.</p>
</section>

<section>
    <h3>Random Numbers</h3>
    <pre><code style="font-size: 70px; line-height: 80px" class="language-python stretch">import random
</code></pre>
</section>

<section>
    <h3>Random Numbers</h3>
    <pre><code style="font-size: 34px; line-height: 40px" class="language-python stretch">import random
<br>a = int(input("Enter a minimum value: "))
b = int(input("Enter a maximum value: "))
x = random.randint(a, b)
print("A random number between {} and {} is {}".format(a, b, x))
</code></pre>
</section>

<section>
    <pre><code style="font-size: 35px; line-height: 40px" class="language-python stretch">import random
<br>p1_secret = random.randint(0, 100)
p2_secret = random.randint(0, 100)
</code></pre>
</section>

<section>
    <pre><code style="font-size: 35px; line-height: 40px" class="language-python stretch">import random
<br>p1_secret = random.randint(0, 100)
p2_secret = random.randint(0, 100)
player = 1
while( ): # player has not guessed correctly
    # swap player
    # get new guess from player
    # check if secret is higher or lower
</code></pre>
</section>

<section>
    <h3>Boolean Expression</h3>
    <pre><code style="font-size: 45px; line-height: 50px" class="language-python stretch">not ((player == 1 and guess == p1_secret) or 
            (player == 2 and guess == p2_secret))
</code></pre>
</section>

<section>
    <h3>Handling Input</h3>
    <pre><code style="font-size: 33px; line-height: 40px" class="language-python stretch">x = int(input(f"Enter a guess for player {player}: "))
while x < 0 or x > 100:
    print("Invalid Input!")
    x = int(input(f"Enter a guess for player {player}: "))
</code></pre>
</section>

<section>
    <h3>Main Code</h3>
    <pre><code style="font-size: 33px; line-height: 40px" class="language-python stretch">p1_secret = random.randint(0, 100)
p2_secret = random.randint(0, 100)
player = 1
while(not ((player == 1 and guess == p1_secret) or 
        (player == 2 and guess == p2_secret))): 
    # player has not guessed correctly
    # swap player
    x = int(input(f"Enter a guess for player {player}: "))
    while x < 0 or x > 100:
        print("Invalid Input!")
        x = int(input(f"Enter a guess for player {player}: "))
    guess = x
    # check if secret is higher or lower
</code></pre>
</section>

<section>
    <h3>Main Code</h3>
    <pre><code style="font-size: 33px; line-height: 40px" class="language-python stretch">p1_secret = random.randint(0, 100)
p2_secret = random.randint(0, 100)
player = 1
while(not ((player == 1 and guess == p1_secret) or 
        (player == 2 and guess == p2_secret))): 
    # player has not guessed correctly
    <mark>if player == 1:
        player = 2
    else:
        player = 1</mark>
    x = int(input(f"Enter a guess for player {player}: "))
    while x < 0 or x > 100:
        print("Invalid Input!")
        x = int(input(f"Enter a guess for player {player}: "))
    guess = x
    # check if secret is higher or lower
</code></pre>
</section>

<section>
    <h3>Branches</h3>
    <pre><code style="font-size: 40px; line-height: 45px" class="language-python stretch">if player == 1:
    if guess < p1_secret:
        print("Higher")
    elif guess > p1_secret:
        print("Lower")
    else:
        print("Correct!")
else:
    if guess < p2_secret:
        print("Higher")
    elif guess > p2_secret:
        print("Lower")
    else:
        print("Correct!")
</code></pre>
</section>

<section>
    <pre><code style="font-size: 24px; line-height: 27px" class="language-python stretch">import random
<br>p1_secret = random.randint(0, 100)
p2_secret = random.randint(0, 100)
player = 1
while(not ((player == 1 and guess == p1_secret) or 
        (player == 2 and guess == p2_secret))): 
    # player has not guessed correctly
    if player == 1:
        player = 2
    else:
        player = 1
    x = int(input(f"Enter a guess for player {player}: "))
    while x < 0 or x > 100:
        print("Invalid Input!")
        x = int(input(f"Enter a guess for player {player}: "))
    guess = x
    if player == 1:
        if guess < p1_secret:
            print("Higher")
        elif guess > p1_secret:
            print("Lower")
        else:
            print("Correct!")
    else:
        if guess < p2_secret:
            print("Higher")
        elif guess > p2_secret:
            print("Lower")
        else:
            print("Correct!")
</code></pre>
</section>

<section>
	<img class="stretch plain" src="/images/05/error1.png">
</section>

<section>
	<img class="stretch plain" src="/images/05/error2.png">
</section>

<section>
    <pre><code style="font-size: 24px; line-height: 27px" class="language-python stretch">import random
<br>p1_secret = random.randint(0, 100)
p2_secret = random.randint(0, 100)
<mark>player = 2</mark>
<mark>guess = -1</mark>
while(not ((player == 1 and guess == p1_secret) or 
        (player == 2 and guess == p2_secret))): 
    # player has not guessed correctly
    if player == 1:
        player = 2
    else:
        player = 1
    x = int(input(f"Enter a guess for player {player}: "))
    while x < 0 or x > 100:
        print("Invalid Input!")
        x = int(input(f"Enter a guess for player {player}: "))
    guess = x
    if player == 1:
        if guess < p1_secret:
            print("Higher")
        elif guess > p1_secret:
            print("Lower")
        else:
            print("Correct!")
    else:
        if guess < p2_secret:
            print("Higher")
        elif guess > p2_secret:
            print("Lower")
        else:
            print("Correct!")
</code></pre>
</section>

<section>
	<img class="stretch plain" src="/images/05/correct1.png">
</section>

<section>
    <pre><code style="font-size: 24px; line-height: 27px" class="language-python stretch">import random
<br>p1_secret = random.randint(0, 100)
p2_secret = random.randint(0, 100)
player = 2
guess = -1
while(not ((player == 1 and guess == p1_secret) or 
        (player == 2 and guess == p2_secret))): 
    # player has not guessed correctly
    if player == 1:
        player = 2
    else:
        player = 1
    x = int(input(f"Enter a guess for player {player}: "))
    while x < 0 or x > 100:
        print("Invalid Input!")
        x = int(input(f"Enter a guess for player {player}: "))
    guess = x
    if player == 1:
        if guess < p1_secret:
            print("Higher")
        elif guess > p1_secret:
            print("Lower")
        else:
            print("Correct!")
    else:
        if guess < p2_secret:
            print("Higher")
        elif guess > p2_secret:
            print("Lower")
        else:
            print("Correct!")
</code></pre>
</section>