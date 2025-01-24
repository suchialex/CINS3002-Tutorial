# 7-1. Intro

## Sequence
- A sequence is an object that holds multiple items of data, stored one after the other
- There are several different types of sequence objects in Python
- Each sequence is distinguished by three characteristics
  - Order
  - Mutability
  - Duplicity (having duplicate values)

## Lists and Tuples

- In this chapter, we will look at two sequences: lists and tuples
- Lists/Tuples can contain any arbitrary number of elements, of any datatypes
- The only difference between lists and tuples is mutability
  - Lists are mutable, which means that a program can change its contents
  - Tuples are immutable, which means that once created, a tuple's contents cannot be changed. 

<details>
  <summary>
    🚩 To Remember
  </summary>
  Lists are mutable, tuples are immutable
</details>

# 7-2, 7-3. Creating a List

## 7-2. Creating an empty list
Syntax: <list_name> = []
```python
scores = []

# or

scores = list()
```

## 7-3. Creating list with elements/values
Syntax: <list_name> = [\<element1\>, \<element2\>,\<element3\> ]
- List elements are enclosed in brackets and separated by commas
- Elements can be of any datatype

### a. Integer list
All elements are ints

```python
# Example of an integer list
even_numbers = [2, 4, 6, 8, 10]
suchi_print(even_number)  # We can print elements of a list using print
```

<details>
  <summary>
    💡 Note:
  </summary>
  I have written a function called suchi_print which prints any sequence in a pretty format.<br>
  We will be using that instead of print<br>
  To use my function we need to import it
  <code>from suchi_pretty_print import suchi_print</code>
</details>

After the list is created even_numbers refers to the data elements like so:
![List Creation](../.tutorial/images/list-creation.png)


### b. float list
All elements are floats
```python
# Example of a float list
sales = [4.5, 5.6, 6.3, 7.8, 5.7]
suchi_print(sales)
```

### c. string list
All elements are strings
```python
# Example of a string list
favorite_actors = ["George Clooney", "Tom Hanks", "Henry Cavill"]
suchi_print(favorite_actors)
```

### d. bool list (all elements are booleans)
```python
# Example of a bool list
bool_list = [True, False, False, True, True]
suchi_print(bool_list)
```

### e. Multiple Datatypes:
Lists can have elements of any datatype including a list

```python
# Multiple Datatypes in a list
student = [123678, "James Smith", "COSC", 3.67, [90, 95, 67]]
suchi_print(student)
```


## Lists are ordered

The order in which elements appear in a list is important

```python
favorite_actors1 = ["George Clooney", "Tom Hanks", "Henry Cavill"]

favorite_actors2 = ["Tom Hanks", "George Clooney", "Henry Cavill"]

if favorite_actors1 == favorite_actors2:
  print("Lists are the same")
else:
  print("Lists are not the same")
```

## Duplicity

Lists can have the same value appear multiple times

```python
l1 = [1, 2, 3, 2, 3]

```
Values 2 and 3 are repeating

<details>
  <summary>
    🚩 To remember:
  </summary>
  Sets cannot have duplicate values 
</details>

# 7-4. Creating List Using range() function

<details>
  <summary>
   💡 7-4 Remember:
  </summary>
   range() function returns an object that holds a series of values<br><br>
  When you pass three arguments to the range function<br>
  - the first argument is the starting value<br>
  -  the second argument is the ending limit<br>
  -  and the third argument is the step value
</details>

We can use the built-in list() function to convert a range of elements to a list

Syntax: <list_name> = list(range(\<start\>, \<stop\>, \<step\>))

```python
numbers = list(range(5))
print(numbers)

# another example
numbers = list(range(1, 10, 2))
suchi_print(numbers)
```

<details>
  <summary>
   👉 Try this: 7-4
  </summary>
  Using list and range functions, can you create a list like this<br>
  [3, 8, 13, 18, 23, 28]
</details>


<details>
  <summary>
   👀 Answer
  </summary>

  ```python
  my_list = list(range(3,30,5))
  ```
  Infact, it doesn't have to be 30 in the second argument, it could be 29 or 30 or 31 or 32 or 33
</details>

# 7-5. Creating List Using Repetition Operator

<details>
  <summary>
    💡 7-5 Remember
  </summary>
  We learned that * can be a multiplication operator or a repetition operator
</details>

- Similarly, if we have a number and a sequence (like list or tuple), then \* acts as a repetition operator

```python
repeated_list = [7] * 6
suchi_print(repeated_list)
```

<details>
  <summary>
    🔍 Close Look:
  </summary>
  In line 1, the expression [7] * 6 makes six copies of the list [7] and joins them all together in a single list. The resulting list is assigned to the repeated_list variable<br><br>
  In line 2, the repeated_list variable is passed to the print function
</details>

<details>
  <summary>
   👉 Try this: 7-5
  </summary>
  Can you create a list like this?
  [1, 2, 3, 1, 2, 3, 1, 2, 3, 1, 2, 3]
</details>


<details>
  <summary>
   👀 Answer
  </summary>

  ```python
  my_list = [1, 2, 3] * 3
  ```
</details>

<details>
  <summary>
   🚩 7-5 To Remember:
  </summary>
  The number must be int, so convert any float or str to int before using it to repeat a string
</details>

# 7-6. Indexing

## a. Indexing

- We can access the individual elements in a list is with an index
- Each element in a list has an index that specifies its position in the list
- Indexing starts at 0, so the index of the first element is 0, the index of the second element is 1, and so forth.
- The index of the last element in a list is 1 less than the number of elements in the list
- Syntax: \<variable_name\> = \<list_name\>[\<index_position\>]

```python
row_1 = ['Facebook', 0.0, 'USD', 2974676, 3.5]
# To get the first element we put the index in square brackets
first = row_1[0]
print(first)
```

<details>
  <summary>
   🚩 7-6a To Remember:
  </summary>
  Indexing in lists/tuples ALWAYS starts at 0
</details>


## b. Negative Indexing

- We can also use negative indexes with lists to identify element positions relative to the end of the list
- The Python interpreter adds negative indexes to the length of the list to determine the element position
- The index −1 identifies the last element in a list, −2 identifies the next to last element, and so forth

```python
row_1 = ['Facebook', 0.0, 'USD', 2974676, 3.5]
# To get the last element using negative index
last = row_1[-1]
print(last)
```

### See image below

![Image](../.tutorial/images/list_indexes.svg)


<details>
  <summary>
   👉 7-6b Try this: 
  </summary>
  In the row_1 list, can you print USD using<br>
  1. positive index<br>
  2. negative index
</details>


<details>
  <summary>
   👀 Answer
  </summary>

  ```python
  element_positive_index = row_1[2]
  element_negative_index = row_1[-3]
  print(element_positive_index)
  print(element_negative_index)
  ```
  📝 You may choose any variable names as long as the list name and indexes are correct 🙂
</details>

## What happens when you use an index that doesn't exist?

```python
row_1 = ['Facebook', 0.0, 'USD', 2974676, 3.5]
var = row_1[5]
print(var)

# Exception is raised
```

<details>
  <summary>
   🚩 7-6 To Remember:
  </summary>
  An exception is raised when we access an index that doesn't exist in the list/tuple
</details>

# 7-8. Accessing List Index Using Value

## Syntax: <list_name>.index(<element_value>)
- The index method is a value-returning method
```python
# To find the index position of James Smith in the list

student = [123678, "James Smith", "COSC", 3.67, [90, 95, 67]]
index_position = student.index("James Smith")

# This has to be case-sensitive
```

<details>
  <summary>
   🚩 7-8 To Remember: 
  </summary>
  If we look for a value that doesn't exist in the list, an exception is raised
</details>


<details>
  <summary>
   👉 Try this: 7-8
  </summary>
  In the list below, find the index position of 28678 and using that index, print the name<br>
<code>employee = ["28678", "Bob Singer", "HR", [90, 95, 67], ["Manager", "Supervisor", "Team Leader"]]</code>
</details>

<details>
  <summary>
   👀 Answer 
  </summary>

  ```python
empid_index = employee.index("28678")
employee_name = employee[empid_index+2]
print(employee_name)
```
</details>


# 7-9. Adding elements to the list

Lists are mutable, so we can add, modify and delete elements

## a. Adding element at the end
- Syntax: <list_name>.append(<element_value>)
```python
# To add 70000 as the last element of the list

employee = ["28678", "Bob Singer", "HR", [90, 95, 67], ["Manager", "Supervisor", "Team Leader"]]
employee.append(75000)
suchi_print(employee)
```

<details>
  <summary>
   🚩 7-9a To Remember: 
  </summary>
  append method takes only one argument
</details>

## b. Adding element at a specified location
- Syntax: <list_name>.insert(<index>, <element_value>)
```python
# To add a 75000 at the third index position

employee = ["28678", "Bob Singer", "HR", [90, 95, 67], ["Manager", "Supervisor", "Team Leader"]]
employee.insert(3, 75000)
suchi_print(employee)
```

<details>
  <summary>
   🚩 7-9b To Remember: 
  </summary>
  The first argument passed to the index method must be an integer
</details>


<details>
  <summary>
   👉 7-9b Try this: 
  </summary>
Add a new value bob@company.com at fourth index position of the list<br>
employee = ["28678", "Bob Singer", "HR", [90, 95, 67], ["Manager", "Supervisor", "Team Leader"]]
</details>

<details>
  <summary>
   👀 Answer 
  </summary>

  ```python
employee.insert(4, "bob@company")
print(employee)
```
</details>


<details>
  <summary>
   🚩 7-9b2 To Remember: 
  </summary>
  If index doesn't exist, value is added at the end
</details>

```python
employee = ["28678", "Bob Singer", "HR", [90, 95, 67], ["Manager", "Supervisor", "Team Leader"]]
employee.insert(10, 75000) # index 10 is obviously out of the scope of this list, will it raise an exception?
suchi_print(employee)
```

# 7-10. Deleting Elements From List

## a. Deleting element using value
Syntax: <list_name>.remove(<value>)


```python
# To remove Javascript from the list
# value must be a case-sensitive match

programming_languages = ["JavaScript", "Python", "Java", "C++"]
programming_languages.remove("JavaScript")
suchi_print(programming_languages)
```

<details>
  <summary>
   🚩 7-10a To Remember: 
  </summary>
  Exception is raised if value is not in the list
</details>

 

<details>
  <summary>
   👉 Try this: 7-10a
  </summary>
Delete the programming language Java<br>
programming_languages = ["JavaScript", "Python", "Java", "C++"]
</details>

<details>
  <summary>
   👀 Answer 
  </summary>

  ```python
employee.remove("Java")
print(employee)
```
</details>


## b. Deleting element using index
Syntax: del <list_name>[\<index\>]

```python
programming_languages = ["JavaScript", "Python", "Java", "C++"]
del programming_languages[3]
suchi_print(programming_languages)

# Exception is raised if index is not in the list
```


<details>
  <summary>
   👉 Try this: 7-10b
  </summary>
Delete the element at index 1<br>
programming_languages = ["JavaScript", "Python", "Java", "C++"]
</details>

<details>
  <summary>
   👀 Answer 
  </summary>

  ```python
del employee[1]<br>
print(employee)
  ```
</details>

# 7-11. in operator

## To check if a value is present in the list
Syntax: if <value> in <list_name>:
```python
# To check if George Clooney is in the list

favorite_actors = ["George Clooney", "Tom Hanks", "Henry Cavill"]
if "George Clooney" in favorite_actors:
  print(True)
```
  
<details>
  <summary>
   👉 Try this: 7-11
  </summary>
Check if Tom Cruise is in the list, if yes, delete Tom Cruise from the list using the value, else print - Actor not present<br>
  favorite_actors = ["George Clooney", "Tom Hanks", "Henry Cavill"]
</details>

<details>
  <summary>
   👀 Answer 
  </summary>

  ```python
if "Tom Cruise" in favorite_actors:
  favorite_actors.remove("Tom Cruise")
else:
  print("Actor not present")
  ```
</details>

# 7-12. len() Function

## Find the number of elements in a list
Syntax: <variable_name> = len(<list_name>) - returns an integer

```python
favorite_actors = ["George Clooney", "Tom Hanks", "Henry Cavill"]
number_of_actors = len(favorite_actors)
print(number_of_actors)
```

<details>
  <summary>
   👉 Try this: 7-12
  </summary>
Find the number of elements in this list<br>
employee = ["28678", "Bob Singer", "HR", [90, 95, 67], ["Manager", "Supervisor", "Team Leader"]]
</details>

<details>
  <summary>
   👀 Answer 
  </summary>
  
  ```python
elements = len(employee)
print(elements)
```
</details>


# 7-13. Modify Elements in a List 

## a. Change Value At Given Index

Syntax: <list_name>[\<index\>] = <new_value>

```python
# To change the value at index position 2 to Tom Cruise

favorite_actors = ["George Clooney", "Tom Hanks", "Henry Cavill"]
favorite_actors[2] = "Tom Cruise"
suchi_print(favorite_actors)
```


<details>
  <summary>
   👉 Try this: 7-13
  </summary>
Change the value at index 3 to PHP<br>
programming_languages = ["JavaScript", "Python", "Java", "C++"]
</details>

<details>
  <summary>
   👀 Answer 
  </summary>

  ```python
programming_languages[3] = "PHP"
```
</details>

## a. Change Value At Of An Element

Syntax: <list_name>[\<index\>] = <new_value>

```python
# To change the value Tom Hanks to Brad Pitt

favorite_actors = ["George Clooney", "Tom Hanks", "Henry Cavill"]
# first check if Tom Hanks is there
if "Tom Hanks" in favorite_actors:
  # Get the index
  position = favorite_actors.index("Tom Hanks")
  favorite_actors[position] = "Brad Pitt"
  suchi_print(favorite_actors)
```

# 7-14. for Loop in List

## a. Loop through just list element values
Syntax: for <loop_variable> in <list_name>:
```python
programming_languages = ["JavaScript", "Python", "Java", "C++"]
for language in programming_languages:
  print(language)
```

<details>
  <summary>
    🔍 Close Look:
  </summary>
  Second line has the for loop going over the list<br>
  Python will read it as, "As long as there are elements in the list keep going"<br><br>
  
  The first time for loop executes, it prints the first element - Javascript<br>
  And checks, are there more elements? YES!<br><br>
  Then it loops again, and this time it prints the second element - Python<br>
  And checks, are there more elements? YES!<br><br>
  Then it loops again, and this time it prints the third element - Java<br>
  And checks, are there more elements? YES!<br><br>
  Then it loops again, and this time it prints the fourth element - C++<br>
  And checks, are there more elements? NO!<br><br>
  So it stops and program execution ends<br>
</details>

<details>
  <summary>
   👉 Try this: 7-14
  </summary>
Use a for loop to print each element of the list<br>
employee = ["28678", "Bob Singer", "HR", [90, 95, 67], ["Manager", "Supervisor", "Team Leader"]]
</details>

<details>
  <summary>
   👀 Answer 
  </summary>

```python
for value in employee:
  print(value)
```

I have used value as my variable name, you may choose any name as long as the list name is correct
</details>


## b. Loop through list element values and indexes
Syntax: for <index_name>, <value_name> in enumerate(<list_name>):

```python
programming_languages = ["JavaScript", "Python", "Java", "C++"]
for index, language in enumerate(programming_languages):
  print(index, '->', language)
```

<details>
  <summary>
   👉 Try this: 
  </summary>
Use a for loop to print each element and its index<br>
employee = ["28678", "Bob Singer", "HR", [90, 95, 67], ["Manager", "Supervisor", "Team Leader"]]
</details>

<details>
  <summary>
   👀 Answer 
  </summary>

```python
for idx, value in enumerate(employee):
  print(idx, '->', value)
```

I have used idx and value as my variable names, you may choose any names as long as the list name is correct
</details>


# 7-15. Find min, max, sum

Syntax:  
15a. `max(<list_name>)` - returns the maximum element of the list  
15b. `min(<list_name>)` - returns the minimum element of the list  
15c. `sum(<list_name>)` - returns the sum of elements of the list

```python
scores_list = [99, 98, 96, 94, 100, 92, 90]
maximum_score = max(scores_list)
print(maximum_score)

gpa_list = [3.45, 2.37, 3.22, 4.0]
minimum_gpa = min(gpa_list)
print(minimum_gpa)

scores_list = [99, 98, 96, 94, 100, 92, 90]
total_score = sum(scores_list)
print(total_score)
```
**NOTE 📝** :
These functions is used only if values are **_all_** numeric or all strings

<details>
  <summary>
   👉 Try this: 
  </summary>
Calculate the min, max and sum of the list

```python
sales_data = [100.45, 102.67, 230.22, 115.75, 201.33, 118.56]
```
</details>

<details>
  <summary>
   👀 Answer 
  </summary>

  ```python  
max(sales_data)
min(sales_data)
sum(sales_data)
```
</details>


# 7-16. Reverse the list

**Syntax:**  `<list_name>.reverse()` - returns `None` 


```python
sales_data = [100.45, 102.67, 230.22, 115.75, 201.33, 118.56]
sales_data.reverse()
print(sales_data)
```

<details>
  <summary>
   👉 Try this: 
  </summary>
Reverse the list and print it

```python
scores_list = [99, 98, 96, 94, 100, 92, 90]
```
</details>

<details>
  <summary>
   👀 Answer 
  </summary>

  ```python  
scores_list.reverse()
print(scores_list)
```
</details>

# 7-17. Sort elements of the list

**Syntax:**  `<list_name>.sort()` - returns `None` 


```python
scores_list = [99, 98, 96, 94, 100, 92, 90]
scores_list.sort()
print(scores_list)
```
**NOTE 📝** :
This function is used only if values are **_all_** int or float or string or boolean

<details>
  <summary>
   👉 Try this: 
  </summary>
Sort the elements of the list and print it

```python
sales_data = [100.45, 102.67, 230.22, 115.75, 201.33, 118.56]
```
</details>

<details>
  <summary>
   👀 Answer 
  </summary>

  ```python  
sales_data.sort()
```
</details>

# 7-18. Merging two lists

## a. Using operator +

```python
l1 = [1, 5, 3, 7, 9]
l2 = ["alpha", "beta", "psi"]

l3 = l1 + l2
suchi_print(l3)

# l3 = l2 + l1
# suchi_print(l3)
```

 ## b. Using method

 ```python
 l1 = [1, 5, 3, 7, 9]
 l2 = ["alpha", "beta", "psi"]

 l1.extend(l2)
 suchi_print(l1)

 # l2.extend(l1)
 # suchi_print(l2)
 ```

<details>
  <summary>
   🎉 Fun exercise: 
  </summary>
See the difference between append and extend

```python
employee = ["28678", "Bob Singer", "HR"]
more_data = ["08/01/1982", "bob@company.com" ]
employee.extend(more_data)
# employee.append(more_data)
suchi_print(employee)
```

**HINT:** The `append()` method adds a list as a single element to the end of a list, whereas the `extend()` method concatenates the first list with another list.
</details>


<details>
  <summary>
    🚩 To Remember
  </summary>

`list3_name = <list1_name> + <list2_name>`
and 
`list1_name.extend(list2_name)`
are almost equivalent.
</details>

# 7-19. Conversion - Tuples and Lists

## a. Tuple to List
We use the list() initializer to convert a tuple to list
Syntax: \<list_name> = list(\<tuple_name\>)


```python
t1 = (1, 2, 4, 5, 7, 9)
my_list = list(t1)
suchi_print(my_list)
```

## b. List to Tuple
We use the tuple() initializer to convert a list to tuple
Syntax: \<tuple_name> = tuple(\<list_name\>)


```python
my_list = [1, 2, 4, 5, 7, 9]
my_tup = tuple(my_list)
suchi_print(my_tup)
```


# 7-20. Conversion - Strings and Lists

## String to List:

Syntax: \<list_name> = \<string>.split([\<delimiter_string\>])
## a. Without Using delimiter

```python
string1 = "Hello World"
list1 = string1.split()
suchi_print(list1)
```

## b. Using delimiter

```python
string1 = "1001,David Collins,HIST,3.79"
list1 = string1.split(",")
suchi_print(list1)
```

## c. List to String

Why convert list to a string?  
- In the case of storing or transmitting data, it is better to do it in the form of a string rather than a list.
- In the case of printing output to the console or a file, you have to format the data in a particular way. When we convert a list to a string, we can easily format the output using string manipulation techniques.
- Some libraries or APIs require data to be passed as a string instead of a list. In these cases, you have to convert your list to a string before passing it to the library or API.
  
```python
employee = ["1001", "David Collins", "HIST", "3.79"]
my_string = ",".join(employee)
```

# 7-21. Create a copy of the list

**Syntax:**  `<list_name>.copy()`


```python
employee = ["28678", "Bob Singer", "HR"]
new_employee = employee.copy()
suchi_print(new_employee)
```

<details>
  <summary>
   👉 Try this: 
  </summary>
Create a copy of the sales_data list

```python
sales = [100.45, 102.67, 230.22, 115.75, 201.33, 118.56]
```
</details>

<details>
  <summary>
   👀 Answer 
  </summary>

  ```python  
sales2 = sales.copy()
suchi_print(sales2)
```
</details>


# 7-22. Clear the contents of a list

**Syntax:**  `<list_name>.clear()`


```python
employee = ["28678", "Bob Singer", "HR"]
employee.clear()
suchi_print(employee)
```

<details>
  <summary>
   👉 Try this: 7-22
  </summary>
Clear the sales_data from the list

```python
sales = [100.45, 102.67, 230.22, 115.75, 201.33, 118.56]
```
</details>

<details>
  <summary>
   👀 Answer 
  </summary>

  ```python  
sales.clear()
suchi_print(sales)
```
</details>


# 7-23. Delete the list

**Syntax:**  `del <list_name>`


```python
sales = [100.45, 102.67, 230.22, 115.75, 201.33, 118.56]
del sales
suchi_print(sales)
```

<details>
  <summary>
   👉 Try this: 7-23
  </summary>
  Delete the employee list

```python
employee = ["28678", "Bob Singer", "HR"]
```
</details>

<details>
  <summary>
   👀 Answer 
  </summary>

  ```python  
del employee
suchi_print(employee)
```
</details>


# 7-24. List Slicing

A slicing expression selects a range of elements from a sequence.  

A slice is a span of items that are taken from a sequence.  

General synatx: \<slice_name\> = \<list_name\>[\<start\>:\<end\>:\<step\>]  

A slice from a list will be a list

```python
january_sales_data = [540.26, 626.09, 550.08, 600.26, 761.85, 707.5, 802.65, 736.12, 838.17, 857.73, 518.97, 826.85, 919.85, 555.68, 767.36, 754.61, 795.04, 776.61, 773.46, 975.42, 614.68, 808.86, 905.62, 617.78, 881.28, 767.0, 927.12, 506.16, 611.36, 992.22, 893.3]

# To get all data

print(january_sales_data[:])

# To get only first week data

print(january_sales_data[:7])

```

## Get student id slice
Consider another example where we read a file data of student records into a list and just get the student id slice

```python
from suchi_pretty_print import suchi_print
def main():
  try:
    f = open("data/students.txt", "r")
  except:
    print("File not found")
  else:

    students = []  # first create an empty list
    for line in f: # Use a for loop to go over file lines
      line = line.rstrip("\n") # remove the newline character
      students.append(line) # add each line to the end of the list
    suchi_print(students)

    # to get just the student ids, we get a slice
    id_slice = students[0::4]
    suchi_print(id_slice)

    # using this slice, we can also calculate the next student id

if __name__ == "__main__":
  main()

```

<details>
  <summary>
    🚩 To remember:
  </summary>
  Invalid indexes do not cause slicing expressions to raise an exception.<br>

  If the end index specifies a position beyond the end of the list, Python will use the length of the list instead.<br>

  If the start index specifies a position before the beginning of the list, Python will use 0 instead.<br>

  If the start index is greater than the end index, the slicing expression will return an empty list.<br>
</details>


<details>
  <summary>
  👉 Try this: 7-24 
  </summary>
  Print the slice that has elements Wednesday and Thursday<br>
  <code>weeks = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"]</code>
</details>

<details>
  <summary>
  👀 Answer 
  </summary>
  print(weeks[3:5])
</details>

# 7-25. List Comprehension

A list comprehension is a concise expression that creates a new list by iterating over the elements of an existing list or a file or any other sequence.  

Consider a list with each element having a tab character at the end and we are to create a new list which has elements without the tab characters

```python
student = ["23344\t", "Robert\t", "CINS\t", "3.88\t"]

# Without List comprehension
modified_student = []
for element in student:
  modified_student.append(element.rstrip("\t"))

# Using list comprehension
# modified_student = [element.rstrip("\t") for element in student]

print(modified_student)
```

Consider the example of reading a file

```python
def main():
  try:
    f = open("data/students.txt", "r")
  except:
    print("File not found")
  else:

    # Without List comprehension
    students = []  # first create an empty list
    for line in f: # Use a for loop to go over file lines
      line = line.rstrip("\n") # remove the newline character
      students.append(line) # add each line to the end of the list

    # Using List comprehension
    students = [line.rstrip("\n") for line in f]

    
    print(students)

if __name__ == "__main__":
  main()
```

<details>
  <summary>
    👉 Try this: 7-25
  </summary>
  Generate a list of 30 random floats between 500 and 1000, rounded to two decimal points, and write to a list named april_sales_data. Use list comprehension
</details>

<details>
  <summary>
    👀 Answer
  </summary>

  ```python
  from random import uniform
  april_sales_data = [round(uniform(500, 1000),2) for i in range(30)]
  ```
</details>


<details>
  <summary>
    👉 Try this: 7-25
  </summary>
  Using list comprehension, convert each month to all lower case and store in a list<br>
  <code>months = ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"]</code>
</details>

<details>
  <summary>
    👀 Answer
  </summary>

  ```python
  months_in_lower = [each_month.lower() for each_month in months]
  ```
</details>



<details>
  <summary>
    👉 Try this: 7-25
  </summary>
  Using list comprehension, convert each element to float and store in a list<br>
  <code>int_list = [3, 6, 4, 8, 10, 4, 5, 8, 9, 1]</code>
</details>

<details>
  <summary>
    👀 Answer
  </summary>

  ```python
  float_list = [float(each_int) for each_int in int_list]
  ```
</details>

## b. Using IF in list comprehension

```python
# Create a list with only even numbers from this list
int_list = [3, 6, 4, 8, 10, 4, 5, 8, 9, 1]

# Without comprehension
even_number_list = []
for each_number in int_list:
  if each_number % 2 == 0:
    even_number_list.append(each_number)

# With comprehension
even_number_list = [each_number for each_number in int_list if each_number % 2 == 0]

suchi_print(even_number_list)

```

<details>
  <summary>
    👉 Try this: 7-25b
  </summary>
  Make a list of all sales less than 150.0 and print it - use list comprehension
  
  ```python
  sales_data = [100.45, 102.67, 230.22, 115.75, 201.33, 181.56]
  ```
</details>


<details>
  <summary>
    👀 Answer
  </summary>
  
  ```python
  sales_data = [100.45, 102.67, 230.22, 115.75, 201.33, 181.56]
  new_list = [amount for amount in sales_data if amount<150]
  print(new_list)
  ```
</details>

# 7-26. Multi-dimensional lists

- We know that lists can have any datatypes, including another list
- Such a list is called a multi-dimensional list

```python
student = [123678, "James Smith", "COSC", 3.67, [90, 95, 67]]
suchi_print(student)
```

<details>
  <summary>
    🔍 Close Look:
  </summary>
  student list has five elements<br>
  first element is an int<br>
  second and third are strings<br>
  fourth element is a float<br>
  the last element is a list
</details>

## How to access the second scores in the student list
```python
student = [123678, "James Smith", "COSC", 3.67, [90, 95, 67]]
# We know how to get the scores
scores = student[4]
# scores is a list, so to get the second score, we use index position 1
second_score = scores[1]
suchi_print(second_score)

# Or we can consolidate both these lines into one
suchi_print(student[4][1])
```

## Let's see another example
```python
student1 = [123678, "James Smith", "COSC", 3.67, [90, 95, 67]]
student2 = [987654, "John Decker", "HIST", 4.35, [89, 87, 90]]
students = [student1, student2]
```

<details>
  <summary>
    🔍 Close Look:
  </summary>
  students list has two elements, both lists<br>
  each of these lists has five elements, with fifth element a list<br>
  so, students is three levels deep, list inside a list inside a list 😲<br>
</details>


## So, how to get John Decker's gpa? 
```python

# because John Decker is the second student, we use index 1 to get John's data (stored in a list)
john = student[1]
suchi_print(john)

# john is a list and his gpa is the fourth element
# johns_gpa = john[3]
# suchi_print(gpa)

# to consolidate and eliminate creating more variables
# suchi_print(student[1][3])
```

## How to get James Smith's third score?
```python

# because James Smith is the first student, we use index 0 to get James' data (stored in a list)
james = student[0]
suchi_print(james)

# james is a list and his scores is the last element
# james_scores = james[-1]

# Now we need the third score in the scores list
# third_score = james_scores[2]
# suchi_print(third_score)

# to consolidate and eliminate creating more variables
# suchi_print(student[0][-1][2])
```

<details>
  <summary>
   👉 Try this: 7-26
  </summary>
  Can you get John Decker's first score
</details>


<details>
  <summary>
   👀 Answer
  </summary>
  print(students[1][-1][0])
</details>


# 7-27. Creating Tuples

## a. Creating an empty tuple
Syntax: <tuple_name> = tuple()
```python
scores = tuple()

# or

scores = ()

suchi_print(scores)
```

## b. Creating tuple with one element

```python
scores = (89, ) # must place a comma

suchi_print(scores)
```

## c. Creating tuple with elements/values
Syntax: <tuple_name> = (\<element1\>, \<element2\>,\<element3\> )
- Tuple elements are parantheses in brackets and separated by commas
- Elements can be of any datatype

### 1. Integer tuple
All elements are ints

```python
# Example of an integer tuple
even_numbers = (2, 4, 6, 8, 10)
suchi_print(even_number) 
```


### 2. float tuple
All elements are floats
```python
# Example of a float tuple
sales = (4.5, 5.6, 6.3, 7.8, 5.7)
suchi_print(sales)
```

### 3. string tuple
All elements are strings
```python
# Example of a string tuple
favorite_actors = ("George Clooney", "Tom Hanks", "Henry Cavill")
suchi_print(favorite_actors)
```

### 4. bool tuple (all elements are booleans)
```python
# Example of a bool tuple
bool_t = (True, False, False, True, True)
suchi_print(bool_t)
```

### e. Multiple Datatypes:
Tuples can have elements of any datatype including a list or a tuple

```python
# Multiple Datatypes in a tuple
student = (123678, "James Smith", "COSC", 3.67, [90, 95, 67], ("yellow", "blue", "orange"))
suchi_print(student)
```

## d. Creating tuples using range()

```python
numbers = tuple(range(5))
print(numbers)

# another example
numbers = tuple(range(1, 10, 2))
suchi_print(numbers)
```

## e. Creating tuple using repetition operator

```python
t1 = (7, ) * 6
suchi_print(t1)

# another example
t1 = (1, 3, 5) * 4
suchi_print(t1)
```

## Tuples are ordered

The order in which elements appear in a tuple is important

```python
favorite_actors1 = ("George Clooney", "Tom Hanks", "Henry Cavill")

favorite_actors2 = ("Tom Hanks", "George Clooney", "Henry Cavill")

if favorite_actors1 == favorite_actors2:
  print("Same Tuples")
else:
  print("Different tuples")
```

## Duplicity

Tuples can have the same value appear multiple times

```python
l1 = (1, 2, 3, 2, 3)

```
Values 2 and 3 are repeating


# 7-28. Accessing elements of a tuple using index

## a. Positive Index
Syntax: \<tuple_name>[\<position-1\>] 
- we use square brackets for index in tuples also  
- this returns a value, so print it or save it in a variable

```python
# To print the fourth element
student = (123678, "James Smith", "COSC", 3.67, [90, 95, 67])
suchi_print(student[3])
```

<details>
  <summary>
    🚩 Remember:
  </summary>
  Exception is raised if you use an index that is not in the tuple
</details>


<details>
  <summary>
    👉 Try this 7-27a:
  </summary>
  Print the FOURTH element of the student tuple<br>
  <code>student = [123678, "James Smith", "COSC", 3.67, [90, 95, 67], ('Basketball', 'Soccer')]</code>
</details>

<details>
  <summary>
    👀 Answer:
  </summary>
  print(student[3])
</details>

## b. Negative Index: 
Gets index from the end of the tuple  
Syntax: \<tuple_name\>[-\<position\>]

```python
student = (123678, "James Smith", "COSC", 3.67, [90, 95, 67], "08/01/2005")
# # To get the last element we just use -1
print(student[-1])
```

<details>
  <summary>
    👉 Try this 7-28b:
  </summary>
  Print the value COSC from the student tuple using negative index<br>
  <code>student = [123678, "James Smith", "COSC", 3.67, [90, 95, 67], ('Basketball', 'Soccer')]</code>
</details>

<details>
  <summary>
    👀 Answer:
  </summary>
  print(student[-4])
</details>


# 7-29. Accessing Tuple Index Using Value

## Syntax: \<tuple_name\>.index(\<element_value\>)
- The index method is a value-returning method
  
```python
# To find the index position of James Smith in the tuple

student = (123678, "James Smith", "COSC", 3.67, [90, 95, 67])
index_position = student.index("James Smith")

# This has to be case-sensitive
```

<details>
  <summary>
   🚩 7-29 To Remember: 
  </summary>
  If we look for a value that doesn't exist in the tuple, an exception is raised
</details>


<details>
  <summary>
   👉 Try this: 7-29
  </summary>
  In the tuple below, find the index position of 28678 and using that index, print the name<br>
<code>employee = ("28678", "Bob Singer", "HR", [90, 95, 67], ["Manager", "Supervisor", "Team Leader"])</code>
</details>

<details>
  <summary>
   👀 Answer 
  </summary>

  ```python
empid_index = employee.index("28678")
employee_name = employee[empid_index+1]
print(employee_name)
```
</details>

# 7-30. Tuples: in Operator

## To check if a value is present in the tuple
Syntax: if <value> in <tuple_name>:
```python
# To check if George Clooney is in the tuple

favorite_actors = ("George Clooney", "Tom Hanks", "Henry Cavill")
if "George Clooney" in favorite_actors:
  print(True)
```

<details>
  <summary>
   👉 Try this: 7-30
  </summary>
Ask user of an actor name, check if it is in the list, if yes, get the index of that actor and print it else print - Actor not present<br>
  actors = ("George Clooney", "Tom Hanks", "Henry Cavill")
</details>

<details>
  <summary>
   👀 Answer 
  </summary>

```python
actor = input("Enter an actor name: ")
if actor in actors:
  idx = actors.index(actor)
  print(idx)
else:
  print("Actor not present")
```
</details>

# 7-31. Tuples: for loop

## a. Loop through just tuple element values
Syntax: for <loop_variable> in <tuple_name>:
```python
programming_languages = ("JavaScript", "Python", "Java", "C++")
for language in programming_languages:
  print(language)
```

<details>
  <summary>
    🔍 Close Look:
  </summary>
  Second line has the for loop going over the tuple<br>
  Python will read it as, "As long as there are elements in the tuple keep going"<br><br>
  
  The first time for loop executes, it prints the first element - Javascript<br>
  And checks, are there more elements? YES!<br><br>
  Then it loops again, and this time it prints the second element - Python<br>
  And checks, are there more elements? YES!<br><br>
  Then it loops again, and this time it prints the third element - Java<br>
  And checks, are there more elements? YES!<br><br>
  Then it loops again, and this time it prints the fourth element - C++<br>
  And checks, are there more elements? NO!<br><br>
  So it stops and program execution ends<br>
</details>

<details>
  <summary>
   👉 Try this: 7-31
  </summary>
Use a for loop to print each element of the tuple<br>
employee = ("28678", "Bob Singer", "HR", [90, 95, 67], ["Manager", "Supervisor", "Team Leader"])
</details>

<details>
  <summary>
   👀 Answer 
  </summary>

```python
for value in employee:
  print(value)
```

I have used value as my variable name, you may choose any name as long as the list name is correct
</details>


## b. Loop through tuple element values and indexes
Syntax: for <index_name>, <value_name> in enumerate(<tuple_name>):

```python
programming_languages = ("JavaScript", "Python", "Java", "C++")
for index, language in enumerate(programming_languages):
  print(index, '->', language)
```

<details>
  <summary>
   👉 Try this: 
  </summary>
Use a for loop to print each element and its index<br>
employee = ("28678", "Bob Singer", "HR", [90, 95, 67], ["Manager", "Supervisor", "Team Leader"])
</details>

<details>
  <summary>
   👀 Answer 
  </summary>

```python
for idx, value in enumerate(employee):
  print(idx, '->', value)
```

I have used idx and value as my variable names, you may choose any names as long as the list name is correct
</details>

# 7-32. Some Tuple Functions

## len() Function

## Find the number of elements in a tuple
Syntax: <variable_name> = len(<tuple_name>) - returns an integer

```python
favorite_actors = ("George Clooney", "Tom Hanks", "Henry Cavill")
number_of_actors = len(favorite_actors)
print(number_of_actors)
```

<details>
  <summary>
   👉 Try this: 7-32a
  </summary>
Find the number of elements in this tuple<br>
employee = ["28678", "Bob Singer", "HR", [90, 95, 67], ["Manager", "Supervisor", "Team Leader"]]
</details>

<details>
  <summary>
   👀 Answer 
  </summary>

  ```python
elements = len(employee)
print(elements)
```
</details>

## b. min, max, sum

Syntax:  
32b1. `max(<tuple_name>)` - returns the maximum element of the tuple  
32b2. `min(<tuple_name>)` - returns the minimum element of the tuple  
32b3. `sum(<tuple_name>)` - returns the sum of elements of the tuple

```python
scores_tuple = (99, 98, 96, 94, 100, 92, 90)
maximum_score = max(scores_tuple)
print(maximum_score)

gpa = (3.45, 2.37, 3.22, 4.0)
minimum_gpa = min(gpa)
print(minimum_gpa)

scores = (99, 98, 96, 94, 100, 92, 90)
total_score = sum(scores)
print(total_score)
```
**NOTE 📝** :
These functions is used only if values are **_all_** numeric or all strings

<details>
  <summary>
   👉 Try this: 7-32b
  </summary>
Calculate the min, max and sum of the list

```python
sales_data = [100.45, 102.67, 230.22, 115.75, 201.33, 118.56]
```
</details>

<details>
  <summary>
   👀 Answer 
  </summary>

  ```python  
max(sales_data)
min(sales_data)
sum(sales_data)
```
</details>

# 7-33. Tuple Methods

Tuples are immutable, so we can't use the following methods on tuples

- append
- sort
- reverse
- extend
- copy
- clear

There are only two methods we can use on tuples

- index - returns the index of an element
- count - returns the number of occurences of an element in the tuple

```python

t = (67, 68, 78, 89, 34, 78, 45)
num = t.count(78)
print(num)

```

# 7-34. Tuples: Operators

## a. = Operator to make a copy

To make a copy of a tuple, we simply use the = operator and assign it a new tuple

```python

employee = ("28678", "Bob Singer", "HR")
new_employee = employee

```

## b. + Operator to merge two tuples

To merge two tuple contents and create a new tuple we can use +

```python
```python
l1 = (1, 5, 3, 7, 9)
l2 = ("alpha", "beta", "psi")

l3 = l1 + l2
suchi_print(l3)

```

## c. * Operator to create a tuple

To create a tuple with repeated elements we use *

```python
l1 = (1, 5, 3, 7, 9) * 3
suchi_print(l3)

```

# 7-35. Tuples: More operations


- Tuple slicing works the same as list slicing
- Multi-dimensional Tuples work the same way as mutli-dimensional lists
- Comprehension is NOT possible
  - Meaning, you cannot create a tuple using comprehension