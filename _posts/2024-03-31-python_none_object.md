---
title: Python - Something about None.
date: 2024-03-31 20:10:00 +100
categories: [python,]
tags: [python]
---

# <span style="color:olive">Something about None</span> 

- **None** represents literally any type of value.
- Use **is None** operator in conditions

```python
var_a = None

if var_a is None:
    print(f"This is a value of var: {var_a}")
else:
    print("Lorem ipsum")
```
![localImage](/assets/images/python/none_value.PNG)


- **None is not equal to any other objects. However None == None gives True.**

![localImage](/assets/images/python/none_equality.PNG)


- **None is used to indicate lack of any value**

```python
def test_value(param=None):
    print(f'This is the value of param {param}')

test_value(param='abc')
test_value(param={'zxc':123})
test_value(param=9)
```

![localImage](/assets/images/python/none_any_value.PNG)



- **None is an output of function with not defined _return_**

```python
def test_math(param1, param2):
    result = param1 + param2
    return result

a = test_math(3, 5)
print(a)

def test_math2(param1, param2):
    result = param1 + param2

b = test_math2(3, 5)
print(b)
```

![localImage](/assets/images/python/function_wthout_return.PNG)


### <span style="color:darkgreen">None vs False</span> 
- 0 is treated as False
- empty lists [] are treated as False
- empty dictionaries {} are treated as False 
- empty string '' is treated as False
- empty tuple () is treated as False

```python
def test_value(param):
    if param is None:
        print("This is None ")
    elif param:
        print(f"{param} is True")
    else:
        print(f"{param} is False")

test_value(0)
test_value([])
test_value({})
test_value('')
test_value(())
test_value(None)
test_value(1)
test_value([1])
test_value({"a": 1})
test_value('a')
test_value((1))
```
![localImage](/assets/images/python/none_test.PNG)

### <span style="color:darkgreen">Why print() returns None?</span>

![localImage](/assets/images/python/print_none.PNG)

print() function is used to send output directly to standard output, therefore _return_ is not defined inside print() function.

Inner print is executed as the first, so _Hello World_ is displayed
in terminal.

As print() does not have return, so from inner print _None_ is given.
An external print takes output from inner print - _None_ is printed on the terminal.
