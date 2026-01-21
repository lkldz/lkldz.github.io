---
title: Python vol.4 - Rounding values using round()
date: 2026-01-20 03:10:00 +100
categories: [python,]
tags: [python]
---

# <span style="color:olive">Python vol.4 - Rounding values using round()</span> 
---

### <span style="color:tan">round() function</span> 

1. <b><span style="color:SeaGreen">round() is a Python built-in function</span></b> that is used to round numbers

2. It rounds a number:
<ul>
<li> to the <b><span style="color:SeaGreen">nearest integer</span></b></li>
<li>or to a <b><span style="color:SeaGreen">specified number of decimal places</span></b></li>
</ul>

3. How to use the round() function?

```python
round(number, ndigits)
 ```

### <span style="color:tan">round() function - examples</span>

<b><span style="color:SeaGreen">**Default rounding (the nearest integer):**</span></b>


![localImage](/assets/images/python/roundings/round_function1.png)


---

<b><span style="color:SeaGreen">**Rounding with ndigit=2 (second digital place):**</span></b>


![localImage](/assets/images/python/roundings/round_function2.png)


---

<b><span style="color:SeaGreen">**Rounding negative numbers:**</span></b>


![localImage](/assets/images/python/roundings/round_function3.png)


---

### <span style="color:tan">Negative ndigits</span> 

<b><span style="color:SeaGreen">If ndigits is negative, Python rounds to the left of the decimal point.</span></b>

Rule:
<ul>
<li>ndigits = -1 → rounds to tens</li>
<li>ndigits = -2 → rounds to hundreds</li>
<li>ndigits = -3 → rounds to thousands </li>
</ul>


![localImage](/assets/images/python/roundings/round_function5.png)