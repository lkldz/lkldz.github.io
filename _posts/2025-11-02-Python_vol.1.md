---
title: Python vol.1 - Interpreter
date: 2025-11-12 01:10:00 +100
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
</ol>
---

&nbsp;&nbsp; to be continued...