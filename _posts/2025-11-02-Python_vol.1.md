---
title: Python vol.1 - Interpreter
date: 2025-12-27 01:10:00 +100
categories: [python,]
tags: [python]
---

# <span style="color:olive">Python vol.1 - Interpreter</span> 
---

### <span style="color:tan">Interpreted language</span> 

1. Python is an <b><span style="color:SeaGreen">interpreted language</span></b>.

2. <b><u><span style="color:SeaGreen">Interpreted language</span></u></b> - <em><span style="color:SeaGreen">Python code is executed line by line by an interpreter</span></em>, rather than being fully converted (compiled) into machine code before running — like in languages such as C or C++

![localImage](/assets/images/python/interpreter/helloworld.png)


---

### <span style="color:tan">Code interpretation</span> 

<b><span style="color:peru">Interpretation workflow</span></b>

The Python <em><span style="color:SeaGreen">interpreter reads the code line by line</span></em>.

↓

It <em><span style="color:SeaGreen">compiles each line into bytecode</span></em> (an intermediate form).

↓

The <em><span style="color:SeaGreen">Python Virtual Machine (PVM) executes that bytecode</span></em> immediately.

---

### <span style="color:tan">Interpreter</span> 

<ul>
<li>Interpreter is the <b><span style="color:SeaGreen">program that reads and runs Python code</span></b>.</li>&nbsp;
<li>It <b><span style="color:SeaGreen">translates human-readable Python source code into machine-executable instructions.</span></b></li>&nbsp;
<li>Its structure includes <b><span style="color:SeaGreen">several key components</span></b> that work together to perform:</li>&nbsp;
<ul>
<li><em><span style="color:SeaGreen">lexical analysis</span></em>,</li> 
<li><em><span style="color:SeaGreen">parsing</span></em>,</li> 
<li><em><span style="color:SeaGreen">compilation to bytecode</span></em></li> 
<li>and <em><span style="color:SeaGreen">execution by a virtual machine.</span></em></li>
</ul>
</ul>&nbsp;&nbsp;


#### <b><span style="color:tan">Types of Python interpreters: </span></b>
<ul>
<li><b><span style="color:SeaGreen">CPython</span></b> - the default and most widely used interpreter, <em><span style="color:SeaGreen">written in C</span></em>. </li>&nbsp;
<li><b><span style="color:SeaGreen">PyPy</span></b> - a faster alternative with a <em><span style="color:SeaGreen">Just-In-Time (JIT) compiler.</span></em>. </li>&nbsp;
<li><b><span style="color:SeaGreen">Jython</span></b> - runs python code on the <em><span style="color:SeaGreen">Java Virtual Machine.</span></em> </li>&nbsp;
<li><b><span style="color:SeaGreen">IronPython</span></b> - <em><span style="color:SeaGreen">integrates with .NET</span></em> and runs on the Common Language Runtime (CLR).</li>&nbsp;
<li><b><span style="color:SeaGreen">MicroPython</span></b> - designed <em><span style="color:SeaGreen">for microcontrollers and embedded systems.</span></em></li>&nbsp;
</ul>&nbsp;&nbsp;


#### <b><span style="color:Tan">Interpreter components: </span></b>
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

### <span style="color:Tan">Lexer/Tokenizer</span> 

A <b><span style="color:SeaGreen">lexer (lexical analyzer)</span></b> is the <b><span style="color:SeaGreen">first stage of processing</span></b> Python source code.

Its job is to <b><span style="color:SeaGreen">read raw text and convert it into a stream of tokens</span></b>.

In <b><span style="color:SeaGreen">CPython</span></b>, the <b><span style="color:SeaGreen">tokenizer is part of the C module defined in tokenizer.c</span></b>.

#### <em><span style="color:Tan">How Lexer/Tokenizer works?</span></em>

<ol>
<li>Lexer <b><span style="color:SeaGreen">scans through the entire source text</span></b> and <b><span style="color:SeaGreen">reads the code character by character</span></b>.</li>&nbsp;
<li><b><span style="color:SeaGreen">Groups characters into tokens</span></b>.</li>&nbsp;
<li><b><span style="color:SeaGreen">The tokenizer does not turn source code into bytes — the source code already is bytes.</span></b>
The tokenizer simply groups bytes into tokens.</li>&nbsp;
<li><b><span style="color:SeaGreen">A .py file on disk is simply a sequence of bytes</span></b>. The tokenizer does not convert anything into bytes — it receives bytes from the operating system.</li>&nbsp;
<li><b><span style="color:SeaGreen">Ignores irrelevant text</span></b>. For example comments (# ...).</li>&nbsp;
<li>A tokenizer does not need to know Python syntax to assign tokens. <b><span style="color:SeaGreen">It does not understand meaning, only character patterns, based on simple lexical rules (regexes an so on).</span></b></li>&nbsp;
<li>The tokenizer reads characters from left to right and asks: <b><span style="color:SeaGreen">“Which pattern of characters does this fragment match?”</span></b></li>&nbsp;
<li><b><span style="color:SeaGreen">Handles indentation levels.</span></b></li>&nbsp;
<li><b><span style="color:SeaGreen">Processes multiline strings and f-strings.</span></b></li>&nbsp;
<li><b><span style="color:SeaGreen">Sends tokens to the parser</span></b>.</li>
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

#### <em><span style="color:tan">The token’s characteristics</span></em>

<ol>
<li>Tokens are <b><span style="color:SeaGreen">flat and don't know about Python's syntax </span></b>.</li>&nbsp;
<li>A token is just a <b><span style="color:SeaGreen">simple, linear item produced by the tokenizer</span></b>.</li>&nbsp;
<li>They are <b><span style="color:SeaGreen">produced one after another, in a flat sequence</span></b>.</li>&nbsp;
<li>The flat sequence means - <b><span style="color:SeaGreen">there is no hierarchical structure (no tree, no nesting, no precedence awareness)</span></b>.</li>&nbsp;
<li>The <b><span style="color:SeaGreen">tokenizer only reads characters and emits tokens</span></b>.</li>&nbsp;
<li><b><span style="color:SeaGreen">The tokenizer does not attempt to understand</span></b> expressions, control flow, operator precedence and so on.</li>&nbsp;
<li>The tokenizer <b><span style="color:SeaGreen">does not understand the grammar of Python</span></b>.</li>&nbsp;
<li>The tokenizer <b><span style="color:SeaGreen">only classifies substrings into categories</span></b>.</li>&nbsp;
</ol>

#### <em><span style="color:tan">The pracitcal example</span></em>

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


<b><span style="color:SeaGreen"><u><em>import tokenize</em></u></span></b> - imports Python’s built-in tokenizer module.&nbsp;

<b><span style="color:SeaGreen"><u><em>from io import BytesIO</em></u></span></b>&nbsp;

<em><b><span style="color:tan">from io</span></b></em>&nbsp;

<ul>
<li>&emsp;<b><span style="color:SeaGreen">load the module named io</span></b>.</li>&nbsp;

<li>&emsp;io is a <b><span style="color:SeaGreen">standard Python module</span></b>.</li>&nbsp;

<li>&emsp;It <b><span style="color:SeaGreen">provides tools for input/output (I/O): reading files, writing files, working with in-memory streams</span></b> <em>[file-like object that lives in RAM instead of on disk, no real file is created.]</em> (text or bytes). So this line is just an importing the module's code.</li>&nbsp;
</ul>
<em><b><span style="color:tan">import BytesIO</span></b></em>&nbsp;
<ul>
<li>&emsp;from the io module, <b><span style="color:SeaGreen">import only the BytesIO class</span></b>.</li>&nbsp;

<li>&emsp;BytesIO is a <b><span style="color:SeaGreen">file-like object that lives in memory</span></b>.</li>&nbsp;

<li>&emsp;It lets you <b><span style="color:SeaGreen">treat bytes stored in a variable as if they were coming from a file</span></b></li>&nbsp;

<li>&emsp;This matters as the <b><span style="color:SeaGreen">tokenizer expects a file, not a string</span></b>.</li>&nbsp;
</ul>
<b><span style="color:tan"><em>code = b"x = 10 + 20"</em></span></b>&nbsp;

- <b><span style="color:SeaGreen">Store the text x = 10 + 20 as raw bytes</span></b>.
- The <b><span style="color:SeaGreen">b before the quotes means this is a bytes</span></b> literal, not a normal string.
- <b><span style="color:SeaGreen">Bytes are numbers between 0–255 that represent characters</span></b>.
```python
print(list(b"x = 10 + 20"))
```
Output
```csharp
[120, 32, 61, 32, 49, 48, 32, 43, 32, 50, 48]
```
<b><span style="color:SeaGreen">Each number is the ASCII value of a character</span></b>:

120 → 'x'

61 → '='

43 → '+'

<em><b><span style="color:Tan"><u>Why bytes are used?</u></span></b></em>&nbsp;
<ul>
<li>Because <b><span style="color:SeaGreen">tokenizer works with bytes, not strings</span></b>.</li>&nbsp;
<li>Byte is a data unit. It consists of 8 bits. Byte can take one of values from 0 to 255. Each of alphanumeric sign can be represented by a specific value (0 to 255).</li>&nbsp;
<li>Because <b><span style="color:SeaGreen">Source code is a sequence of bytes, not “characters”</span></b>.</li>&nbsp;
<li><b><span style="color:SeaGreen">Bytes are the lowest, unambiguous, and fastest level</span></b> at which source code can be correctly and efficiently analyzed.</li>&nbsp;
<li>Only <b><span style="color:SeaGreen">later are those bytes decoded (e.g. as UTF-8) into characters</span></b> .</li>&nbsp;
<li>The tokenizer must start with bytes because files may use different encodings and encoding errors must be detected.</li>&nbsp;

<li>The <b><span style="color:SeaGreen">tokenizer expects input that:</span></b></li>&nbsp;
<ol>
<li><b><span style="color:SeaGreen">comes line by line</span></b></li>

<li><b><span style="color:SeaGreen">is bytes</span></b></li>

<li>like <b><span style="color:SeaGreen">reading from a .py file</span></b></li>
</ol>
</ul>&nbsp;


<b><span style="color:tan"><em><u>tokens = tokenize.tokenize(BytesIO(code).readline)</u></em></span></b>&nbsp;
<ul>
<li><b><span style="color:SeaGreen">It comes from the tokenize module.</span></b></li>&nbsp;
<li><b><span style="color:SeaGreen">tokenize.tokenize is a Python standard-library function that breaks Python source code into tokens,</span></b> which are the smallest meaningful units of the language.at which source code can be correctly and efficiently analyzed.</li>&nbsp;
<li><b><span style="color:SeaGreen">tokenize.tokenize() reads Python code as bytes and produces an iterator of tokens</span></b></li>&nbsp;
<li><b><span style="color:SeaGreen">BytesIO(code)
wraps the code in an in-memory byte stream</span></b> so it behaves like a file (tokenize.tokenize works with byte streams, not plain strings).</li>&nbsp;
<li><b><span style="color:SeaGreen">.readline is a method that reads one line of text (or bytes) at a time from a file-like object.</span></b></li>&nbsp;
</ul>

```python
with open("example.txt") as f:
    line = f.readline()
    print(line)
```
---

### <span style="color:SandyBrown">Parser</span> 

#### <em><span style="color:tan">Introduction</span></em>

<ul>
<li>A parser is a program that <b><span style="color:SeaGreen">understands the structure of text</span></b>. </li>&nbsp;

<li>It <b><span style="color:SeaGreen">checks whether the text is correctly constructed according to certain rules</span></b>, and if so, it <b><span style="color:SeaGreen">transforms it into an organized structure</span></b> that a computer can further work with. </li>&nbsp;

<li>The parser <b><span style="color:SeaGreen">checks whether your code follows the rules of the language</span></b> and turns it into a structured form that the computer can understand.</li>&nbsp;
</ul>


#### <em><span style="color:Tan">How it works?</span></em>

1. A <b><span style="color:SeaGreen">parser takes tokens from the lexer</span></b>.&nbsp;


    - The <b><span style="color:SeaGreen">parser does not read raw text (characters).</span></b> It reads tokens that were already identified by the lexer.&nbsp;


    <em>Example - parser took the following tokens:</em>&nbsp;


    ```
    NAME(x) = NUMBER(10) + NAME(y)
    ```

2. It <b><span style="color:SeaGreen">checks grammar rules</span></b>.
    
    <em>Example grammar rule is:</em>

    ```
    assignment → NAME "=" expression
    expression → NUMBER "+" NAME
    ```

   - Parser <b><span style="color:SeaGreen">detects syntax errors</span></b>.

3. <b><span style="color:SeaGreen">Builds a structured representation (AST - abstract syntax tree)</span></b> that the interpreter can execute.


---

### <span style="color:SandyBrown">AST</span> 


&nbsp;&nbsp; to be continued...