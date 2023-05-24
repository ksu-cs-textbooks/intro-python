---
type: "reveal"
hidden: true
---

<section>
    <h3>Numerical Input</h3>
    <pre><code style="font-size: 45px; line-height: 55px" class="language-python stretch">text_one = input("Enter the price of one item: ")
price = float(text_one)
text_two = input("Enter the quantity of items: ")
quantity = int(text_two)
cost = price * quantity
print("The total cost is $", end="")
print(cost)
</code></pre>
    <br>
    <pre><code style="font-size: 40px; line-height: 50px" class="language-plaintext"><br><br>
</code></pre>
</section>
<section>
    <h3>Numerical Input</h3>
    <pre><code style="font-size: 45px; line-height: 55px" class="language-python stretch">text_one = input("Enter the price of one item: ")
price = float(text_one)
text_two = input("Enter the quantity of items: ")
quantity = int(text_two)
cost = price * quantity
print("The total cost is $", end="")
print(cost)
</code></pre>
    <br>
    <pre><code style="font-size: 40px; line-height: 50px" class="language-plaintext">Enter the price of one item: 2.75
Enter the quantity of items: 3
The total cost is $8.25</code></pre>
</section>
<section>
    <h3>Numerical Input</h3>
    <pre><code style="font-size: 45px; line-height: 55px" class="language-python stretch">text_one = input("Enter the price of one item: ")
price = float(text_one)
text_two = input("Enter the quantity of items: ")
quantity = int(text_two)
cost = price * quantity
print("The total cost is $", end="")
print(cost)
</code></pre>
    <br>
    <pre><code style="font-size: 40px; line-height: 50px" class="language-plaintext">Enter the price of one item: 2.75
Enter the quantity of items: <mark>3.5</mark><br>
</code></pre>
</section>
<section>
    <h3>Numerical Input</h3>
    <pre><code style="font-size: 45px; line-height: 55px" class="language-python stretch">text_one = input("Enter the price of one item: ")
price = float(text_one)
text_two = input("Enter the quantity of items: ")
quantity = int(text_two)
cost = price * quantity
print("The total cost is $", end="")
print(cost)
</code></pre>
    <br>
    <pre><code style="font-size: 40px; line-height: 50px" class="language-plaintext">Enter the price of one item: 2.75
Enter the quantity of items: <mark style="color:red">3.5</mark>
Traceback (most recent call last):
  File "tutor.py", line 4, in &lt;module>
    quantity = int(text_two)
ValueError: invalid literal for int() with base 10: '3.5'
</code></pre>
</section>