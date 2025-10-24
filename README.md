# Python Week 5 Assessed Workshop

Work in CodeSpaces. 

If CodeSpaces does not load after 5 mins (like last week) open JupyterLab and add your answers to the below exercises in a single notebook.

You may use the following cheat sheets if you need to look up any Python commands.

https://github.com/phil-lewis-exe/PythonCheatSheets

**This week you may not use any other websites to help you code.**

**You must ask if you need to use a website to translate the task questions**

**Mobile phones may not be used in class**

---

## TASKS


### Part 1: Say Hi

*If you are working in CodeSpaces work in file **`5b_part1.py`***

Write a Python function called `say_hi` that takes one argument `n`.

The function should display the message `hi` `n`-times each on a single line.

(i.e. when called with the value 9 it would display hi 9 times).

After writing the function show how to call it, using the example value 4.

The output should be:

```
hi
hi
hi
hi
```

---

### Part 2: Calculating a percentage change

*If you are working in CodeSpaces work in file **`5b_part2.py`***

A programmer wants to write code to calculate the percentage change between two values `a` and `b`.

This can be found using the following formula:

$$\texttt{percent change} = \frac{b - a}{a} \times 100$$

Write a function `percent_change` that takes two arguments `a` and `b` and returns the percent change.

After writing your code add the following code lines to test it. 

```python
check_a = percent_change(50,55)
check_b = percent_change(50,25)

print(check_a, check_b)
```

The output should be 

```
10.0 -50.0
```

---


### Part 3: Validating an age variable

*If you are working in CodeSpaces work in file **`5b_part3.py`***

A programmer wants to write code to validate that a provide age is sensible.

This must be done in function `validate` that takes a single argument `age`.

This will **return** the string `passed` if the age is an integer, between 0 and 120 inclusive.

It will **return** the string `failed` for any other age value.

The following code shows a way to check if the age is an integer:

```python
if age == int(age):
    print("age is an integer")
else:
    print("age is not an integer")
```

Write a function `validate` that takes an argument `age` to do this.

After writing your code add the following code lines to test it. 

```python
check_minus = validate(-5)
check_20 = validate(20)
check_150 = validate(150)
check_non_int = validate(7.2)

print(check_minus, check_20, check_150, check_non_int)
```

The output should be:

```
failed passed failed failed
```

---

### Part 4: Finding the net change over a series

*If you are working in CodeSpaces work in file **`5b_part4.py`***

A programmer wants to write code to calculate the net change between the start and end of a timeseries.

For example look at this example timeseries,

```
[ 16, 15, 12, 13, 14, 11 ]
```

Here the first value is 16 the last value is 11 and the net change is -5.

i.e. the net change can be found using:

$$\texttt{net change} =  \texttt{last value} - \texttt{first value}$$

Write a function `net_change` that takes a single argument `time_series`.

It should return the net change over the time series provided. 

You can assume the time series passed is always valid and contains at least two values.

After writing your code add the following code lines to test it. 

```python 
series1 = [ 1, 0, 2, 4 ]
series2 = [ 10, 0, 2 ]

check_series1 = net_change(series1)
check_series2 = net_change(series2)

print(check_series1, check_series2)
```

This should produce the following output:

```
3 -8
```

### Part 5: Generating a set of sequences

*If you are working in CodeSpaces work in file **`5b_part5.py`***

A programmer is writing code to explore a mathematical sequence.

In this sequence the next value is found by taking the product of the last two values.

For example for the sequence starting : **2, 3**

The next value is $2 \times 3$, growing the sequence to: **2, 3, 6**

The next value is $3 \times 6$, growing the sequence to: **2, 3, 6, 18**

The next value is $6 \times 18$, growing the sequence to: **2, 3, 6, 18, 108**

Write a function `grow_list` that takes an input argument `mylist` that stores a sequence in a Python list.

The function should calculate the next term in the sequence.

It should return a **new** list that contains the extended sequence.

After writing your code add the following code lines to test it. 

```python
list1 = [ 2, 3 ]
list2 = grow_list(list1)
list3 = grow_list(list2)

print(list1, list2, list3)
```

This should produce the output:

```
[2, 3] [2, 3, 6] [2, 3, 6, 18]
```

Hint. to make a copy of a list you can use either code like:

```python
mylist = [1,2,3]
mylist_copy1 = mylist.copy()
mylist_copy2 = mylist[:]
```

---

### Submitting your work

Run the following lines in the terminal to stage, commit and push your code back to your GitHub repository:

```
git add .
git commit -m "completed 5b"
git push
```

To check your work has been saved you can run the line of code below in the terminal to get the web address of the repository in GitHub. Goto the repository and check the completed code files are stored.

```
git config --get remote.origin.url
```
