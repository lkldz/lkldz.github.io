---
title: Python vol.1
date: 2025-11-02 01:10:00 +100
categories: [Python]
tags: [python]
---

# <span style="color:olive">Python vol.1 - Interpreter</span> 
---

### <span style="color:royalblue">Interpreted language</span> 

1. Python is an <b><span style="color:limegreen">interpreted language</span></b>.

2. <b><u><span style="color:limegreen">Interpreted language</span></u></b> - <em><span style="color:goldenrod">Python code is executed line by line by an interpreter</span></em>, rather than being fully converted (compiled) into machine code before running — like in languages such as C or C++

![localImage](/assets/images/python/interpreter/helloworld.png)


---

### <span style="color:royalblue">Code interpretation</span> 

<b><span style="color:gray">Interpretation workflow</span></b>

The Python <em><span style="color:goldenrod">interpreter reads the code line by line</span></em>.

↓

It <em><span style="color:goldenrod">compiles each line into bytecode</span></em> (an intermediate form).

↓

The <em><span style="color:goldenrod">Python Virtual Machine (PVM) executes that bytecode</span></em> immediately.

---

### <span style="color:royalblue">Interpreter</span> 

<ul>
<li>Interpreter is the <b><span style="color:DarkKhaki">program that reads and runs Python code</span></b>.</li>&nbsp;
<li>It <b><span style="color:DarkKhaki">translates human-readable Python source code into machine-executable instructions.</span></b></li>&nbsp;
<li>Its structure includes <b><span style="color:DarkKhaki">several key components</span></b> that work together to perform:</li>&nbsp;
<ul>
<li><em><span style="color:DarkKhaki">lexical analysis</span></em>,</li> 
<li><em><span style="color:DarkKhaki">parsing</span></em>,</li> 
<li><em><span style="color:DarkKhaki">compilation to bytecode</span></em></li> 
<li>and <em><span style="color:DarkKhaki">execution by a virtual machine.</span></em></li>
</ul>
</ul>&nbsp;&nbsp;


<b><span style="color:lightcoral">Types of Python interpreters: </span></b>
<ul>
<li><b><span style="color:salmon">CPython</span></b> - the default and most widely used interpreter, <em><span style="color:salmon">written in C</span></em>. </li>&nbsp;
<li><b><span style="color:salmon">PyPy</span></b> - a faster alternative with a <em><span style="color:salmon">Just-In-Time (JIT) compiler.</span></em>. </li>&nbsp;
<li><b><span style="color:salmon">Jython</span></b> - runs python code on the <em><span style="color:salmon">Java Virtual Machine.</span></em>. </li>&nbsp;
<li><b><span style="color:salmon">IronPython</span></b> - <em><span style="color:salmon">integrates with .NET</span></em> and runs on the Common Language Runtime (CLR).</li>&nbsp;
<li><b><span style="color:salmon">MicroPython</span></b> - designed <em><span style="color:salmon">for microcontrollers and embedded systems.</span></em></li>&nbsp;
</ul>

&nbsp;&nbsp; to be continued...