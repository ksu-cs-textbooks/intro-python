---
type: "reveal"
hidden: true
---

<section>
    <h3>Determining Type</h3>
    <div style="float: right; width: 50%">
        <h6>Output</h6>
        <pre class="language-plaintext stretch" style="font-size: 70px; line-height: 80px"><code><br><br><br>&lt;class 'str'>
&lt;class 'int'>
&lt;class 'float'></code></pre>
    </div>
    <div style="float: left; width: 50%">
        <h6>Code</h6>
        <pre class="python stretch" style="font-size: 70px; line-height: 80px"><code>x = "Hello"
y = 5
z = 6.7
print(type(x))
print(type(y))
print(type(z))</code></pre>
    </div>
</section>
<section>
    <h3>Converting Types</h3>
    <div style="float: right; width: 50%">
        <h6>Output</h6>
        <pre class="language-plaintext stretch" style="font-size: 60px; line-height: 70px"><code><br>5.7
&lt;class 'str'><br><br>
5.7
&lt;class 'float'><br><br>
5
&lt;class 'int'></code></pre>
    </div>
    <div style="float: left; width: 50%">
        <h6>Code</h6>
        <pre class="python stretch" style="font-size: 60px; line-height: 70px"><code>x = "5.7"
print(x)
print(type(x))
print()
y = float(x)
print(y)
print(type(y))
print()
z = int(y)
print(z)
print(type(z))</code></pre>
    </div>
</section>
<section>
    <h3>Exceptions</h3>
    <pre><code style="font-size: 60px; line-height: 70px" class="language-python stretch">a = "5.7"
print(a)
print(type(a))
print()
b = int(a)
print(b)
print(type(b))</code></pre>
    <br>
</section>
<section>
    <h3>Exceptions</h3>
    <pre><code style="font-size: 60px; line-height: 70px" class="language-python stretch">a = "5.7"
print(a)
print(type(a))
print()
<mark style="color:red">b = int(a)</mark>
print(b)
print(type(b))</code></pre>
    <br>
</section>
<section>
    <h3>Exceptions</h3>
    <pre><code style="font-size: 60px; line-height: 70px" class="language-python stretch">a = "5.7"
print(a)
print(type(a))
print()
<mark style="color:red">b = int(a)</mark>
print(b)
print(type(b))</code></pre>
    <br>
    <pre><code class="language-plaintext"  style="font-size: 40px; line-height: 50px">Traceback (most recent call last):
File "tutor.py", line 5, in &lt;module>
    b = int(a)
ValueError: invalid literal for int() with base 10: '5.7'</code></pre>
</section>