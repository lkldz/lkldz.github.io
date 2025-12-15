---
title: Python vol.1 - Interpreter
date: 2025-12-12 01:10:00 +100
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


#### <b><span style="color:lightcoral">Types of Python interpreters: </span></b>
<ul>
<li><b><span style="color:salmon">CPython</span></b> - the default and most widely used interpreter, <em><span style="color:salmon">written in C</span></em>. </li>&nbsp;
<li><b><span style="color:salmon">PyPy</span></b> - a faster alternative with a <em><span style="color:salmon">Just-In-Time (JIT) compiler.</span></em>. </li>&nbsp;
<li><b><span style="color:salmon">Jython</span></b> - runs python code on the <em><span style="color:salmon">Java Virtual Machine.</span></em> </li>&nbsp;
<li><b><span style="color:salmon">IronPython</span></b> - <em><span style="color:salmon">integrates with .NET</span></em> and runs on the Common Language Runtime (CLR).</li>&nbsp;
<li><b><span style="color:salmon">MicroPython</span></b> - designed <em><span style="color:salmon">for microcontrollers and embedded systems.</span></em></li>&nbsp;
</ul>&nbsp;&nbsp;


#### <b><span style="color:MediumSeaGreen">Interpreter components: </span></b>
<ul>
<li><b><span style="color:SeaGreen">Lexer/Tokenizer</span></b> - converts <em><span style="color:SeaGreen">source code into tokens</span></em>. </li>&nbsp;
<li><b><span style="color:SeaGreen">Parser</span></b> - <em><span style="color:SeaGreen">analyzes tokens</span></em> according to Python grammar rules and <em><span style="color:SeaGreen">builds syntax tree from tokens</span></em>.</li>&nbsp;
<li><b><span style="color:SeaGreen">AST (Abstract Syntax Tree) Generator</span></b> - represents <em><span style="color:SeaGreen">code structure</span></em>. </li>&nbsp;
<li><b><span style="color:SeaGreen">Compiler</span></b> - compiles <em><span style="color:SeaGreen">AST into bytecode</span></em>. </li>&nbsp;
<li><b><span style="color:SeaGreen">Bytecode</span></b> - low-level <em><span style="color:SeaGreen">intructions for PVM</span></em>. </li>&nbsp;
<li><b><span style="color:SeaGreen">PVM (Python Virtual Machine)</span></b> - it <em><span style="color:SeaGreen">executes bytecode</span></em>. </li>&nbsp;
<li><b><span style="color:SeaGreen">Memory Manager</span></b> - handles <em><span style="color:SeaGreen">memory and garbage collection</span></em>. </li>&nbsp;
<li><b><span style="color:SeaGreen">Standard Library</span></b> - provides <em><span style="color:SeaGreen">built-in modules and functions</span></em>. </li>&nbsp;
<li><b><span style="color:SeaGreen">C API (Runtime)</span></b> - underlaying <em><span style="color:SeaGreen">implementation in C</span></em>. </li>&nbsp;
</ul>

---

### <span style="color:SandyBrown">Lexer/Tokenizer</span> 

A <b><span style="color:sandybrown">lexer (lexical analyzer)</span></b> is the <b><span style="color:sandybrown">first stage of processing</span></b> Python source code.

Its job is to <b><span style="color:sandybrown">read raw text and convert it into a stream of tokens</span></b>.

In <b><span style="color:sandybrown">CPython</span></b>, the <b><span style="color:sandybrown">tokenizer is part of the C module defined in tokenizer.c</span></b>.

#### <em><span style="color:DarkOrange">How Lexer/Tokenizer works?</span></em>

<ol>
<li>Lexer <b><span style="color:DarkOrange">scans through the entire source text</span></b> and <b><span style="color:DarkOrange">reads the code character by character</span></b>.</li>&nbsp;
<li><b><span style="color:DarkOrange">Groups characters into tokens</span></b>.</li>&nbsp;
<li><b><span style="color:DarkOrange">Ignores irrelevant text</span></b>. For example comments (# ...).</li>&nbsp;
<li><b><span style="color:DarkOrange">Handles indentation levels.</span></b></li>&nbsp;
<li><b><span style="color:DarkOrange">Processes multiline strings and f-strings.</span></b></li>&nbsp;
<li><b><span style="color:DarkOrange">Sends tokens to the parser</span></b>.</li>
</ol>&nbsp;

<em><span style="color:RosyBrown">Examples of token types:</span></em>
<ul>
<li><span style="color:RosyBrown">NAME</span> — variable or function name</li>
<li><span style="color:RosyBrown">NUMBER</span> — numeric literal</li>
<li><span style="color:RosyBrown">STRING</span> — string literal</li>
<li><span style="color:RosyBrown">OP</span> — operator (+, ==, **, etc.)</li>
<li><span style="color:RosyBrown">NEWLINE</span> — end of line</li>
<li><span style="color:RosyBrown">INDENT / DEDENT</span> — indentation changes</li>
<li><span style="color:RosyBrown">KEYWORD</span> — e.g., if, for, def</li>
</ul>&nbsp;

#### <em><span style="color:peru">The token’s characteristics</span></em>

<ol>
<li>Tokens are <b><span style="color:peru">flat and don't know about Python's syntax </span></b>.</li>&nbsp;
<li>A token is just a <b><span style="color:peru">simple, linear item produced by the tokenizer</span></b>.</li>&nbsp;
<li>They are <b><span style="color:peru">produced one after another, in a flat sequence</span></b>.</li>&nbsp;
<li>The flat sequence means - <b><span style="color:peru">there is no hierarchical structure (no tree, no nesting, no precedence awareness)</span></b>.</li>&nbsp;
<li>The <b><span style="color:peru">tokenizer only reads characters and emits tokens</span></b>.</li>&nbsp;
<li><b><span style="color:peru">The tokenizer does not attempt to understand</span></b> expressions, control flow, operator precedence and so on.</li>&nbsp;
<li>The tokenizer <b><span style="color:peru">does not understand the grammar of Python</span></b>.</li>&nbsp;
<li>The tokenizer <b><span style="color:peru">only classifies substrings into categories</span></b>.</li>&nbsp;
</ol>

#### <em><span style="color:tan">How the tokenizer works?</span></em>

```python
import tokenize
from io import BytesIO

code = b"x = 10 + 20"

tokens = tokenize.tokenize(BytesIO(code).readline)

for token in tokens:
    print(token)
```
Output is:
```python
TokenInfo(type=65 (ENCODING), string='utf-8', start=(0, 0), end=(0, 0), line='')
TokenInfo(type=1 (NAME), string='x', start=(1, 0), end=(1, 1), line='x = 10 + 20')
TokenInfo(type=55 (OP), string='=', start=(1, 2), end=(1, 3), line='x = 10 + 20')
TokenInfo(type=2 (NUMBER), string='10', start=(1, 4), end=(1, 6), line='x = 10 + 20')
TokenInfo(type=55 (OP), string='+', start=(1, 7), end=(1, 8), line='x = 10 + 20')
TokenInfo(type=2 (NUMBER), string='20', start=(1, 9), end=(1, 11), line='x = 10 + 20')
TokenInfo(type=4 (NEWLINE), string='', start=(1, 11), end=(1, 12), line='x = 10 + 20')
TokenInfo(type=0 (ENDMARKER), string='', start=(2, 0), end=(2, 0), line='')
```


<b><span style="color:plum">import tokenize</span></b> - imports Python’s built-in tokenizer module.&nbsp;

<b><span style="color:plum">from io import BytesIO</span></b>&nbsp;

<em><b><span style="color:orange">from io</span></b></em>&nbsp;

<ul>
<li>&emsp;<b><span style="color:orange">load the module named io</span></b>.</li>&nbsp;

<li>&emsp;io is a <b><span style="color:orange">standard Python module</span></b>.</li>&nbsp;

<li>&emsp;It <b><span style="color:orange">provides tools for input/output (I/O): reading files, writing files, working with in-memory streams</span></b> <em>[file-like object that lives in RAM instead of on disk, no real file is created.]</em> (text or bytes). So this line is just an importing the module's code.</li>&nbsp;
</ul>
<em><b><span style="color:MediumSeaGreen">import BytesIO</span></b></em>&nbsp;
<ul>
<li>&emsp;from the io module, <b><span style="color:MediumSeaGreen">import only the BytesIO class</span></b>.</li>&nbsp;

<li>&emsp;BytesIO is a <b><span style="color:MediumSeaGreen">file-like object that lives in memory</span></b>.</li>&nbsp;

<li>&emsp;It lets you <b><span style="color:MediumSeaGreen">treat bytes stored in a variable as if they were coming from a file</span></b></li>&nbsp;

<li>&emsp;This matters as the <b><span style="color:MediumSeaGreen">tokenizer expects a file, not a string</span></b>.</li>&nbsp;
</ul>
<b><span style="color:plum">code = b"x = 10 + 20"</span></b>&nbsp;

- <b><span style="color:LightSalmon">Store the text x = 10 + 20 as raw bytes</span></b>.
- The <b><span style="color:LightSalmon">b before the quotes means this is a bytes</span></b> literal, not a normal string.
- <b><span style="color:LightSalmon">Bytes are numbers between 0–255 that represent characters</span></b>.
```python
print(list(b"x = 10 + 20"))
```
Output
```csharp
[120, 32, 61, 32, 49, 48, 32, 43, 32, 50, 48]
```
<b><span style="color:LightSalmon">Each number is the ASCII value of a character</span></b>:

120 → 'x'

61 → '='

43 → '+'

<em><b><span style="color:orange">Why is b"x = 10 + 20" used?</span></b></em>&nbsp;
<ul>
<li>Because <b><span style="color:orange">tokenizer works with bytes, not strings</span></b>.</li>&nbsp;

<li>The <b><span style="color:orange">tokenizer expects input that:</span></b></li>&nbsp;
<ol>
<li><b><span style="color:orange">comes line by line</span></b></li>

<li><b><span style="color:orange">is bytes</span></b></li>

<li>like <b><span style="color:orange">reading from a .py file</span></b></li>
</ol>
</ul>

---

&nbsp;&nbsp; to be continued...