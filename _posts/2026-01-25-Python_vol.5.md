---
title: Python vol.5 - Variables
date: 2026-01-25 03:10:00 +100
categories: [python,]
tags: [python]
---

# <span style="color:olive">Python vol.5 - Variables</span> 
---

### <span style="color:tan">Why variables are needed?</span> 

1. Variables in Python are <b><span style="color:SeaGreen">containers that store data, allowing you to preserve and manipulate information</span></b> in your program.

2. A variable <b><span style="color:SeaGreen">has three main elements: a name, a data type, and a value</span></b>.

3. When you create a variable, you <b><span style="color:SeaGreen">reserve space in your computer's memory to store data</span></b>.

4. They <b><span style="color:SeaGreen">allow you to save information that you'll need later in the program</span></b>. Without variables, you'd have nowhere to store calculation results or user input.

5. Easy updates — <b><span style="color:SeaGreen">if you need to change a value, you only change it in one place</span></b>, and the entire program works with the new value.

6. Code readability — <b><span style="color:SeaGreen">variable names can describe what they contain, making code understandable</span></b> for you and other programmers.

---

### <span style="color:tan">Rules for variables names.</span> 

- Must <b><span style="color:SeaGreen">start with a letter or underscore</span></b>.

- <b><span style="color:SeaGreen">Can't start with a number </span></b>.

```python
name = "John"       # ✓ Valid
_age = 25           # ✓ Valid
2name = "John"      # ✗ Invalid
```


- Can only <b><span style="color:SeaGreen">contain letters, digits, and underscores</span></b>. 

- <b><span style="color:SeaGreen">No spaces or special characters</span></b>.


```python
first_name = "John"  # ✓ Valid
first-name = "John"  # ✗ Invalid (hyphen not allowed)
first name = "John"  # ✗ Invalid (space not allowed)
```


- <b><span style="color:SeaGreen">Case-sensitive</span></b> — Name, name, and NAME are different variables

```python
age = 25
Age = 30
# These are two different variables
```

- <b><span style="color:SeaGreen">Cannot use Python keywords</span></b> — can't use reserved words like if, for, while, class, etc.

```python
for = 5      # ✗ Invalid (for is a keyword)
class = 10   # ✗ Invalid (class is a keyword)
```

- <b><span style="color:SeaGreen">No spaces allowed</span></b>  — use underscores to separate words instead.

```python
student_name = "Anna"     # ✓ Valid (snake_case)
studentName = "Anna"      # ✓ Valid (camelCase - less common)
student name = "Anna"     # ✗ Invalid
```

- <b><span style="color:SeaGreen">Python recommends snake_case</span></b> — lowercase letters with underscores between words:

```python
first_name = "John"      # ✓ Recommended
user_age = 30            # ✓ Recommended
_private_var = 100       # ✓ Underscore often indicates private
```


---


### <span style="color:tan">Dynamic typing.</span> 

1. You <b><span style="color:SeaGreen">don't need to declare the type when creating a variable</span></b>.

2. Dynamic typing means that a <b><span style="color:SeaGreen">variable's type can change during program execution</span></b>. 

3. <b><span style="color:SeaGreen">Python automatically determines the type based on the value</span></b> you assign.

```python
name = "Anna"   # Python sees a string and knows name is string type
age = 25        # Python sees an integer and knows age is integer type
height = 1.75   # Python sees a float and knows height is float type
```


**Advantages:**
<ul>
<li><b><span style="color:SeaGreen">Faster to write</span></b> — no need for type declarations like in Java or C++</li>
<li><b><span style="color:SeaGreen">More flexible</span></b> — variables can adapt to different data types as needed</li>
<li>Less verbose — cleaner, simpler code</li>
</ul>

**Disadvantages:**

<ul>
<li>Can cause errors — <b><span style="color:SeaGreen">type mismatches might not be caught until runtime</span></b></li>
<li>Less predictable — <b><span style="color:SeaGreen">a function might receive unexpected types</span></b></li>
<li>Harder to debug — <b><span style="color:SeaGreen">type-related bugs can be harder to track</span></b></li>
</ul>

```python
x = 10
y = "5"
result = x + y  # ✗ Error! Can't add int and string
```

---

### <span style="color:tan">Variable reassignment.</span> 

- <b><span style="color:SeaGreen">Reassignment means changing the value of a variable that already exists</span></b>. 


- We can reassign a variable as many times as you want.


- Each time we use the = operator with an existing variable name, we overwrite its previous value.

```python
x = 10
print(x)  # 10

x = 20    # Reassign x to a new value
print(x)  # 20

x = 30    # Reassign again
print(x)  # 30
```

- Thanks to dynamic typing, <b><span style="color:SeaGreen">we can reassign a variable to a completely different type</span></b>.


```python
value = 100        # Integer
print(value)       # 100

value = "Hello"    # Now it's a string
print(value)       # Hello

value = 3.14       # Now it's a float
print(value)       # 3.14

value = True       # Now it's a boolean
print(value)       # True
```

- Using current value in reassignment - <b><span style="color:SeaGreen">we can use a variable's current value to calculate its new value</span></b>.

Example 1:

```python
a = 10
a = a + a
print(a)
20
```

Examples 2:

```python
count = 5
count = count + 1   # Use old value to calculate new value
print(count)        # 6

count += 1          # Shorthand for count = count + 1
print(count)        # 7
```


---


### <span style="color:tan">Saving original value.</span> 

- <b><span style="color:SeaGreen">When you reassign a variable, the old value is lost</span></b> (unless you save it in another variable).


```python
name = "Anna"
name = "John"   # Old value "Anna" is now gone
# You can't get "Anna" back unless you saved it
```


- <b><span style="color:SeaGreen">If you need to keep the original value, save it first</span></b>:


```python
name = "Anna"
old_name = name     # Save the original value
name = "John"       # Reassign

print(old_name)     # Anna
print(name)         # John
```

---


### <span style="color:tan"> Swapping values.</span> 

```python
a = 5
b = 10

a, b = b, a  # Swap values
print(a, b)  # 10 5
```

---

### <span style="color:tan"> Multiple assignment. </span> 

```python
x, y, z = 1, 2, 3
print(x, y, z)  # 1 2 3

x, y, z = 10, 20, 30  # Reassign all at once
print(x, y, z)  # 10 20 30
```

---
### <span style="color:tan"> Shorthand operators. </span> 

Python provides convenient shorthand operators for reassignment.

```python
x = 10

x += 5      # Same as x = x + 5
print(x)    # 15

x -= 3      # Same as x = x - 3
print(x)    # 12

x *= 2      # Same as x = x * 2
print(x)    # 24

x /= 4      # Same as x = x / 4
print(x)    # 6.0
```

---
### <span style="color:tan"> Function type() </span>

1. The type() function <b><span style="color:SeaGreen">returns the data type of a variable or object</span></b>. 

2. It's useful <b><span style="color:SeaGreen">for checking what kind of data you're working with</span></b>.

<b><span style="color:SeaGreen">Syntax:</span></b>
```python
type(object)
```

Examples 1:
```python
print(type(5))           # <class 'int'>
print(type(3.14))        # <class 'float'>
print(type("Hello"))     # <class 'str'>
print(type(True))        # <class 'bool'>
print(type([1, 2, 3]))   # <class 'list'>
```

Examples 2:
```python
name = "Anna"
age = 25
height = 1.75
is_student = True

print(type(name))        # <class 'str'>
print(type(age))         # <class 'int'>
print(type(height))      # <class 'float'>
print(type(is_student))  # <class 'bool'>
```

Examples 3:
```python
# Strings
print(type("text"))           # <class 'str'>

# Numbers
print(type(42))               # <class 'int'>
print(type(3.14))             # <class 'float'>
print(type(2 + 3j))           # <class 'complex'>

# Boolean
print(type(True))             # <class 'bool'>
print(type(False))            # <class 'bool'>

# Collections
print(type([1, 2, 3]))        # <class 'list'>
print(type((1, 2, 3)))        # <class 'tuple'>
print(type({1, 2, 3}))        # <class 'set'>
print(type({"a": 1}))         # <class 'dict'>

# Special
print(type(None))             # <class 'NoneType'>
```
---

### <span style="color:tan"> Function type() in practise. </span>

- <b><span style="color:SeaGreen">Debugging</span></b> — check if a variable has the expected type:

```python
value = "123"
print(type(value))  # <class 'str'>
# Oops! It's a string, not an integer
```

- <b><span style="color:SeaGreen">Conditional logic</span></b> — make decisions based on type:

```python
x = 10

if type(x) == int:
    print("x is an integer")
elif type(x) == str:
    print("x is a string")
```

- <b><span style="color:SeaGreen">Type checking in functions</span></b>:


```python
def add_numbers(a, b):
    if type(a) != int or type(b) != int:
        print("Both arguments must be integers!")
        return
    return a + b

print(add_numbers(5, 10))      # 15
print(add_numbers(5, "10"))    # Both arguments must be integers!

```


---


## <span style="color:tan"> Function isinstance() </span>

- For type checking, <b><span style="color:SeaGreen">isinstance() is often preferred</span></b>.

- The <b><span style="color:SeaGreen">isinstance() function checks if an object is an instance of a class or type</span></b>. 

- It <b><span style="color:SeaGreen">returns True if the object is of that type, and False otherwise</span></b>.


Syntax:

```python

isinstance(object, classinfo)

```

Example 1:

```python

x = 10
print(isinstance(x, int))        # True

y = "Hello"
print(isinstance(y, str))        # True

z = 3.14
print(isinstance(z, float))      # True

is_active = True
print(isinstance(is_active, bool))  # True

```

- <b><span style="color:SeaGreen">Can check multiple types at once</span></b>.

```python

x = 10

# Is x either int or float?
print(isinstance(x, (int, float)))   # True

y = "text"
print(isinstance(y, (int, float)))   # False

z = 3.14
print(isinstance(z, (int, float)))   # True

```

- In <b><span style="color:SeaGreen">conditional statements</span></b>:

```python

value = 42

if isinstance(value, int):
    print("It's an integer")
elif isinstance(value, str):
    print("It's a string")
elif isinstance(value, float):
    print("It's a float")
else:
    print("Unknown type")

```

- <b><span style="color:SeaGreen">Function with type checking</span></b>:

```python

def double_value(num):
    if isinstance(num, (int, float)):
        return num * 2
    else:
        print("Error: Please provide a number!")
        return None

print(double_value(5))      # 10
print(double_value(2.5))    # 5.0
print(double_value("5"))    # Error: Please provide a number!

```

- <b><span style="color:SeaGreen">With collections</span></b>:

```python

my_list = [1, 2, 3]
my_dict = {"name": "Anna"}
my_tuple = (1, 2, 3)
my_set = {1, 2, 3}

print(isinstance(my_list, list))    # True
print(isinstance(my_dict, dict))    # True
print(isinstance(my_tuple, tuple))  # True
print(isinstance(my_set, set))      # True

```

- <b><span style="color:SeaGreen">Checking with None</span></b>:

```python

value = None
print(isinstance(value, type(None)))  # True
print(value is None)                  # Better way to check for None

```

- <b><span style="color:SeaGreen">Practical example — data validation</span></b>:

```python

def process_input(data):
    if isinstance(data, int):
        print(f"Processing integer: {data * 2}")
    elif isinstance(data, str):
        print(f"Processing string: {data.upper()}")
    elif isinstance(data, list):
        print(f"Processing list: {len(data)} items")
    else:
        print("Unsupported type!")

process_input(10)              # Processing integer: 20
process_input("hello")         # Processing string: HELLO
process_input([1, 2, 3])       # Processing list: 3 items
process_input(3.14)            # Unsupported type!

```

## <span style="color:tan"> isinstance() vs type()</span>
 
- Can check multiple types at once.

- Returns a boolean (True/False) for easy conditional logic.

- Recommended in professional Python code.

- The key difference is how they handle inheritance. isinstance() is more flexible:

```python

x = True

# Using type()
print(type(x) == int)           # False (bool is separate)
print(type(x) == bool)          # True

# Using isinstance()
print(isinstance(x, bool))      # True
print(isinstance(x, int))       # True (bool is a subclass of int)

```

In Python, <b><span style="color:SeaGreen"> bool is a subclass of int, so isinstance() recognizes this relationship, while type() doesn't</span></b>.
