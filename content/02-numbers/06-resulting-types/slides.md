---
type: "reveal"
hidden: true
---

<section>
    <h3>Two Integers</h3>
    <div style="float: right; width: 50%">
        <h6>Output</h6>
        <pre class="language-plaintext stretch" style="font-size: 60px; line-height: 70px"><code><br><br><br>50
&lt;class 'int'></code></pre>
    </div>
    <div style="float: left; width: 50%">
        <h6>Code</h6>
        <pre class="python stretch" style="font-size: 60px; line-height: 70px"><code>x = 5
y = 10
z = x * y
print(z)
print(type(z))</code></pre>
    </div>
</section>
<section>
    <h3>Division - Always Float</h3>
    <div style="float: right; width: 50%">
        <h6>Output</h6>
        <pre class="language-plaintext stretch" style="font-size: 60px; line-height: 70px"><code><br><br><br><br>3.0
&lt;class 'float'><br><br>
2.25
&lt;class 'float'></code></pre>
    </div>
    <div style="float: left; width: 50%">
        <h6>Code</h6>
        <pre class="python stretch" style="font-size: 60px; line-height: 70px"><code>a = 9
b = 3
c = 4
x = a / b
print(x)
print(type(x))
print()
y = a / c
print(y)
print(type(y))</code></pre>
    </div>
</section>
<section>
    <h3>Two Floats</h3>
    <div style="float: right; width: 50%">
        <h6>Output</h6>
        <pre class="language-plaintext stretch" style="font-size: 60px; line-height: 70px"><code><br><br><br>7.0
&lt;class 'float'></code></pre>
    </div>
    <div style="float: left; width: 50%">
        <h6>Code</h6>
        <pre class="python stretch" style="font-size: 60px; line-height: 70px"><code>a = 2.5
b = 4.5
c = a + b
print(c)
print(type(c))</code></pre>
    </div>
</section>
<section>
    <h3>Mixed - Always Float</h3>
    <div style="float: right; width: 50%">
        <h6>Output</h6>
        <pre class="language-plaintext stretch" style="font-size: 60px; line-height: 70px"><code><br><br><br>3.0
&lt;class 'float'></code></pre>
    </div>
    <div style="float: left; width: 50%">
        <h6>Code</h6>
        <pre class="python stretch" style="font-size: 60px; line-height: 70px"><code>a = 5
b = 2.0
c = a - b
print(c)
print(type(c))</code></pre>
    </div>
</section>