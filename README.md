# Python Week 6b Practice Workshop

You may use the following cheat sheets if you need to look up any Python commands.

https://github.com/phil-lewis-exe/PythonCheatSheets

---

## TASKS

### Part 1a: Default Function Arguments

*If you are working in `.py` files work in file **`practise_workshop_6_part1a.py`***

Type in the following Python function called `print_details` that takes three arguments:
- `name`
- `age` (which should default to `None`)
- `job` (which should default to `"not provided"`)

The function should print the person's details over three lines.
1.  It should print the `name`, capitalised using `.title()`.
2.  If the age is provided it should print the age. E.g. `Age: 40`, otherwise if it should print `Age: unknown`.
3.  It should print the `job`, capitalised using `.title()`.

e.g. `print_details("fred flintstone", 40, "construction worker")`

will display:

```
Name: Fred Flintstone
Age: 40
Job: Construction Worker
```


After writing the function, add the following lines to call it and test your code.

```python
print_details("fred flintstone", 40, "construction worker")
print("---")
print_details("wilma flintstone")
print("---")
print_details("pebbles flitstone", age=3)
print("---")
print_details("barney rubble", job="construction worker")
```

The output should be:

```
Name: Fred Flintstone
Age: 40
Job: Construction Worker
---
Name: Wilma Flintstone
Age: unknown
Job: Not Provided
---
Name: Pebbles Flitstone
Age: 3
Job: Not Provided
---
Name: Barney Rubble
Age: unknown
Job: Construction Worker
```

<details><summary>Model answer</summary>
    
```python
def print_details(name, age=None, job="not provided"):
    print(f"Name: {name.title()}")
    if age is not None:
        print(f"Age: {age}")
    else:
        print(f"Age: unknown")
    print(f"Job: {job.title()}")
```

</details>

---

### Part 1b: Variable-length `*args`

*If you are working in `.py` files work in file **`practise_workshop_6_part1b.py`***

Type in the following function `list_to_str` that takes a variable number of positional arguments (`*args`) and one keyword argument `sep` which defaults to `,`.

The function should join all positional arguments into a single string, separated by the `sep` string, and **return** it.

For example, calling `list_to_str("a","b","c")` should return the string `"a,b,c"`.
Calling `list_to_str("x","y","z",sep="-")` should return the string `"x-y-z"`.


After writing the function, add the following lines to test it:

```python
print( list_to_str("a","b","c") )
print( list_to_str("x","y","z",sep="-") )
```

The output should be:

```
a,b,c
x-y-z
```

<details><summary>Model answer</summary>

```python
def list_to_str(*args, sep=","):
    mystr = ""
    first = True
    for item in args:
        if first:
            first = False
        else:
            mystr = mystr + sep
        mystr = mystr + item
    return mystr
```

</details>

---

### Part 1c: Variable-length `**kwargs`

*If you are working in `.py` files work in file **`practise_workshop_6_part1c.py`***

Type in the following function `print_args` that can accepts any sets of positional arguments (`*args`) and keyword arguments (`**kwargs`).

The function should loop through and print all arguments it receives, numbering them sequentially.
-   It should first print the positional arguments in the format: `arg {i} (position arg) is {value}`
-   It should first print the keyowrd arguments in the format:  `arg {i} (keyword arg) is {key}={value}`

For example, calling `print_args("a", "b" value="c")` would print:

```
arg 1 (position arg) is a
arg 2 (position arg) is b
arg 3 (keyword arg) is value = c
```


After writing the function, add the following line to test it:

```python
print_args("a","b","c", kw1="d", kw2="e")
```

The output should be:

```
arg 1 (position arg) is a
arg 2 (position arg) is b
arg 3 (position arg) is c
arg 4 (keyword arg) is kw1 = d
arg 5 (keyword arg) is kw2 = e
```

<details><summary>Model answer</summary>

```python
def print_args(*args, **kwargs):
    i = 1
    for arg in args:
        print(f"arg {i} (position arg) is {arg}")
        i=i+1
    for k in kwargs.keys():
        print(f"arg {i} (keyword arg) is {k} = {kwargs[k]}" )
        i=i+1
```

</details>

---

### Part 2: Creating a Module

Create a **new file** named **`mymaths.py`**.

In this file, add the following functions. This file will act as a module, so do **not** add any test calls or `print()` statements to this file.

You will need to create the following functions:
- `def add(a,b)`: should return the sum of `a` and `b`.
- `def minus(a,b)`: should return `b` subtracted from `a`.
- `def times(a,b)`: should return the product of `a` and `b`.
- `def divide(a,b)`: should return `a` divided by `b`.
- `def square(a)`: should return the square of `a`. **This function must use your `times` function.**
- `def double(a)`: should return double the value of `a`. **This function must use your `add` function.**
- `def half(a)`: should return half the value of `a`. **This function must use your `divide` function.**

<details><summary>Model answer</summary>

```python
# saved in file mymaths.py
def add(a,b):
    return a+b

def minus(a,b):
    return a-b

def times(a,b):
    return a*b

def divide(a,b):
    return a/b

def square(a):
    return times(a,a)

def double(a):
    return add(a,a)

def half(a):
    return divide(a,2)
```

</details>

---

### Using Your Module

*If you are working in `.py` files work in file **`practise_workshop_6_part2.py`***

Now, write a script that imports your `mymaths` module and uses the functions you created to perform the following calculations.

**You must not use the `+`, `-`, `*`, `/`, or `**` operators in this file.** 

All calculations must be done using your imported functions.

i. Find 5 + 7 and store in variable `a`

ii. Find 8 / 2 and store in variable `b`

iii. Find $10^2$ and store in variable `c`

iv. Find **half of 25** and store in variable `d`

Print the result of each calculation, to check them using code:

print(a,b,c,d)


The output should be:

```
12 4.0 100 12.5
```

<details><summary>Model answer</summary>

```python
import mymaths

# a = 5 + 7 
a = mymaths.add(5, 7)

# b = 8 / 2
b = mymaths.divide(8, 2)

# c = 10**2
c = mymaths.square(10)

# d = half of 25
d = mymaths.half(25)
print(a,b,c,d)
```

</details>
