# 2-0. Comments

In Python if we don't want to execute any line of code, we place a # at the beginning of the line  
Such a line is called a **comment**  
We use comments in our code to leave ourselves some notes about the program  
If you use a # in the middle of a line of code, Python ignores everything to the right of the #

```python
# this is a comment
# and will not be executed
```

In most editors, you can use the shortcut Ctrl + / to toggle commenting in your code  
You can comment one line or multiple lines  
Highlight the lines you want to comment or uncomment and press Ctrl + /

<details>
  <summary>
    👉 Try this:
  </summary>
  Place a comment in main.py with your full name
</details>

<details>
  <summary>
    👀 Answer:
  </summary>
  # My name is Suchi Rodda
</details>

# 2-1. Print Function

We use print to display data to the user  
**Syntax:**  
print("\<whatever you want to print\>") _or_  
print('\<whatever you want to print\>') _or_  
print("""\<whatever you want to print\>""")


## a. Printing phrases
```python
print("Hello World") # We can use single quotes also
```

#### Any statement that starts after a # in python is called a comment and will not be executed

<details>
  <summary>
    👉 Try this:
  </summary>
  Display  I am Mary's cat
</details>

<details>
  <summary>
    👀 Answer:
  </summary>
  print("I am Mary's cat") # you cannot use single quotes because the string has single quote in it 
</details>


<details>
  <summary>
    👉 Try this:
  </summary>
  Display  Mary said, "Hello There!"
</details>

<details>
  <summary>
    👀 Answer:
  </summary>
  print('Mary said, "Hello There!"') # you cannot use double quotes because the string has double quote in it 
</details>

## b. Printing paragraphs
We use `'''` or `"""` when we need to display large amount of text that might contain single or double quotes
```python
print(""" This is paragraph data with "  
and '  and 
this won't break the code.
It also allows me to display in multiple lines""")
```

## c. Multiple print statements 
Each print statement displays data in new line
```python
print("Hello")
print("World")
```

<details>
  <summary>
    👉 Try this:
  </summary>
  Using multiple print statements display<br><br>
  Alabama<br>
  Arizona<br>
  Alaska<br>
  Arkansas
</details>

<details>
  <summary>
    👀 Answer:
  </summary>
  print("Alabama")<br>
  print('Arizona')<br>
  print("Alaska")<br>
  print("Arkansas")<br>
</details>


## d. Printing multiple values
We can use comma-separated values in the same print statement  
They will be separated by space by default when displayed

```python
print("Hello","world","there","!")
```

<details>
  <summary>
    👉 Try this:
  </summary>
  Print four strings `Lord`, `of`, `the`, `Rings` so it will look like<br><br>
  Lord of the Rings
</details>

<details>
  <summary>
    👀 Answer:
  </summary>
  # you may use single or double quotes<br>

```python
print("Lord ", "of ", 'the ', 'Rings')
```
</details>

# 2-2. Python Variables

Variables are _containers_ to store values  
These values can be
- numeric
- alphabetic
- alphanumeric
- or a special type called Boolean (True/False)

## a. Defining a variable
A variable can be defined as follows  
**Syntax:** \<variable_name> = \<value> or \<expression>

```python
# assigning a value of 5 to a variable named var1
var1 = 5

# assigning an expression to a variable named var2
var2 = 4 + 5

```

## b. Printing a variable
To print the value stored in a variable, we use the print statement with the variable name inside the parenthesis  
**Syntax:** print(<variable_name>)

```python
# printing variables
print(var1)
print(var2)
```

<details>
  <summary>
    🚩 Important:
  </summary>
  You must print the variable name without any single or double quotes
</details>

## c. Variable naming rules
A valid variable name
- CANNOT have blank spaces, meaning, it has to be one word
- CANNOT be a python keyword

  (For example: if, for, while etc.). You can find the complete list [here](https://realpython.com/lessons/reserved-keywords/)
- CANNOT start with a number
- CANNOT have any special character except an underscore
- CAN have a mix of alphabetical or numerical characters or underscores 

## d. Variable naming conventions

### Variable names are case-sensitive.  
Which means:  
`Age`, `age`, `aGe`, `AgE`, `agE`, `AGe`, `AGE` are all **different** variables

```python
age = 25
print(Age) # Will give an error

```

<details>
  <summary>
    👉 Try this:
  </summary>
  Fix the above print statement
</details>

<details>
  <summary>
    👀 Answer:
  </summary>
  print(age)
</details>

### Variable names can be as long as you want
But, it is a good practice to keep the length between 8 and 20 characters

### Variable names can be anything
As long as they follow above rules  
But a good convention is to name variables descriptively

```python
i = 2.7
interest_rate_percent = 2.7

# both are valid names
# but which one is more descriptive?
```

### Variable naming styles
Different programmers choose different styles of variable naming.  
Two popular ones are:
1. **Camel Case:**

   First character is lower case, first character of each of the words will be uppercase and the rest will be lowercase
    ```python
    # Style 1: Camel case
    interestRatePercent = 2.7
    ```

2. **Snake Case:**

   All characters are lowercase, and each word is separated by an underscore

    ```python
    # Style 2: Snake case
    interest_rate_percent = 2.7
    ```

You choose your style!

# 2-3. Python Datatypes

There are four simple built-in data types in Python 
1. String
2. Integer
3. Float
4. Boolean

There are complex data types/data structures that we will see in later chapters
1. Lists
2. Tuples
3. Dictionaries
4. Sets

## a. Finding the type

You can find out the type of variable, by using the type function  
**Syntax:** print(type(<variable_name))

```python
var = 3
print(type(var))
```

<details>
  <summary>
    👉 Try this:
  </summary>
  print the type of this variable<br>
  my_college = "ULM"
</details>

<details>
  <summary>
    👀 Answer:
  </summary>
  print(type(my_college))
</details>

# 2-4. Python Datatype - Integer
Any whole number (no decimal points) between -2147483648 through 2147483647 is an integer  
_For example_: 35 is an integer

## a.Defining an empty integer
We can define an integer variable even when we don't have the value yet  
For that, we use the int()  
**Syntax**: <variable_name> = int()

```python
my_int = int()
```

<details>
  <summary>
    👉 Try this:
  </summary>
  print the type of the above empty integer<br>
</details>

<details>
  <summary>
    👀 Answer:
  </summary>
  print(type(my_int))
</details>

## b. Creating an integer with value
To assign an integer value to a variable, we assign a whole number to the variable  
**Syntax**: <variable_name> = <whole_number>

```python
population_of_india = 139300000
num_of_students_in_cins3002 = 10
```

<details>
  <summary>
    👉 Try this:
  </summary>
  Create an integer variable with a value of your choice and print its type<br>
</details>

<details>
  <summary>
    👀 Answer:
  </summary>
  planets = 8
  print(type(planets))
</details>

## c. Printing an integer variable
We can use the print function  
**Syntax**: print(<variable_name>)

```python
my_int = 5
print(my_int)
```

<details>
  <summary>
    👉 Try this:
  </summary>
  Print the planets variable we defined earlier
</details>

<details>
  <summary>
    👀 Answer:
  </summary>
  print(planets)
</details>

# 2-5. Python Datatype - String

Any alphanumeric character or text enclosed in single quotes or double quotes (or in some instances `'''`, three single quotes or `"""` three double quotes) is referred to as a string  
For example:
- "Apple"
- 'Suchi says, "Welcome to Python Programming"'
- "Sally's best friend is Suzy"
- `''' "This is very interesting", said Suchi's student. I'm excited to learn more about how to write paragraphs spanning multiple lines, consisting of single and double quotes using three single quotes in Python. '''`
- "67859" (even though this looks numeric, because we enclosed it in double quotes, Python treats it as a string)

## a. Define/declare an empty string
To define/declare a string whose value we don't know yet, we can use the str()  
**Syntax**: <variable_name> = str()

```python
my_string = str()
```
## b. Assigning a string value to a variable

```python
my_string = 'Suchi says, "Welcome to Python Programming"'
```

## c. Printing string variable
We can use the print function

```python
print(my_string)
```

## 3d. Converting other datatypes to string

You can convert any other data type into a string using the str() function.

```python
my_variable = 2.7
print(type(my_variable))
print(my_variable)
converted_to_string = str(my_variable)
print(type(converted_to_string))
print(converted_to_string)
```
<details>
  <summary>
    🚩 To remember:
  </summary>input() statement in Python always stores the user entered value in a string even though it might all be numeric
</details>

# 2-6. Python Datatype - Float
Float (we know it as real number) is a numeric data type, which supports decimals  
For example: `67859.78` is a float  

## a. Creating an empty float variable
When we don't know the value, we create a float using float()
**Syntax**: <variable_name> = float()

```python
my_float = float()
```

## b. Assigning float value to a variable
**Syntax**: <variable_name> = <real_number>

```python
my_float = 67859.7886
```

## c. Printing the value of a float
We use the print function
**Syntax**: print(<variable_name>)

```python
print(my_float)

# to print only two decimal points
print(f'{my_float:.2f}')

```
We will see formatting later on in print function chapter

# 2-7. Python Datatype - Boolean
A data type that has a value True or False is called a boolean  
This looks like a string but is **NOT** a string  

## a. Create an empty boolean variable
We do this when we don't know the value  
**Syntax:** <variable_name> = bool()

```python
my_boolean = bool()
```
## b. Assigning a boolean value to a variable

```python
my_boolean = True
my_boolean = False
```

### Invalid booleans:

```python
# This is a string and not a boolean
my_not_a_boolean = "True"

# These are not valid booleans
my_wrong_bool1 = true # true is not the same as True
my_wrong_bool2 = false # false is not the same as False

```
<details>
  <summary>
    🚩 To remember:
  </summary>
  Python is case-sensitive
</details>  

## c. Printing a boolean variable
We use the print function  
**Syntax:** print(<variable_name>)

```python
print(my_boolean)
```

# 2-8. Bad Variable Values

Variable values must be one of these built-in datatypes   
or mathematical expressions that evaluate to numbers  
or logical expressions that evaluate to True or False  

Variable values CANNOT be some of these  

## a.
```python
amount = $5

# you can correct it to
amount_in_dollars = 5

# or
amount = "$5" # you will not be able to do any mathematical operations on this variable because it is a string
```

## b.
```python
interest = 2.99%

# you can correct it to
interest_percentage = 2.99
```

## c.
```python
height = 150cm

# you can correct it to
height_in_cm = 150
```

# 2-9. Converting Datatypes To Integer
To convert a string, float or boolean to integer, we use the int() function  
**Syntax**: int(<other_datatype_variable>)

### a. String to Int

```python
my_phone = "3185551234"

# @TODO: Write a print statement to print the my_phone_number variable

# We can convert this to an integer
my_phone_number = int(my_phone)

# @TODO: Write a print statement to print the my_phone_number variable

# @TODO: Write a print statement to print the type of my_phone_number variable

```
<details>
  <summary>
    🚩 To remember:
  </summary>
  You can convert a string to an integer only if ALL the characters are numeric
</details>

### b. Float to Int

```python
gpa = 3.5

# @TODO: Write a print statement to print the type of gpa variable

# We can convert this to an integer
# and store in the same variable if we want to
gpa = int(gpa)

# Write a print statement to print the gpa variable


# Write a print statement to print the type of gpa variable
```
<details>
  <summary>
    🚩 To remember:
  </summary>
  When you convert a float to an integer, the numbers after the decimal point are stripped<br>
  The number will NOT be rounded to the nearest whole number
</details>


### c. Boolean to Int

```python
valid = True

# Write a print statement to print the type of valid variable


# We can convert this to an integer
valid_int = int(valid)

# Write a print statement to print the valid_int variable


# Write a print statement to print the type of valid_int variable
```
<details>
  <summary>
    🚩 To remember:
  </summary>
  When you convert a boolean to an integer, True is converted to 1 and False is converted to 0
</details>

# 2-10. Converting Datatypes To Float
To convert a string, integer or boolean to float, we use the float() function  
**Syntax**: float(<other_datatype_variable>)

### a. String to Float

```python
my_gpa = "3.58"

# @TODO: Write a print statement to print the type of my_gpa

# We can convert this to a float
my_gpa = float(my_gpa)

# @TODO: Write a print statement to print the my_gpa

# @TODO: Write a print statement to print the type of my_gpa
```
<details>
  <summary>
    🚩 To remember:
  </summary>
  You can convert a string to a float only if ALL the characters are numeric, and one . (denoting the decimal point)
</details>

### b. Integer to Float

```python
score = 98

# @TODO: Write a print statement to print the type of score variable

# We can convert this to a float
score = float(score)

# @TODO: Write a print statement to print the score variable


# @TODO: Write a print statement to print the type of score variable
```

### c. Boolean to Float

```python
valid = True

# Write a print statement to print the type of valid variable

# We can convert this to a float
valid_float = float(valid)

# Write a print statement to print the valid_float variable


# Write a print statement to print the type of valid_float variable
```
<details>
  <summary>
    🚩 To remember:
  </summary>
  When you convert a boolean to a float, True is converted to 1.0 and False is converted to 0.0
</details>

# 2-11. Converting Datatypes To String
To convert an integer, float or boolean to string, we use the str() function  
**Syntax**: str(<other_datatype_variable>)

### a. Integer to String

```python
score = 75

# @TODO: Write a print statement to print the type of score

# We can convert this to a string
score = str(score)

# @TODO: Write a print statement to print the score

# @TODO: Write a print statement to print the type of score
```

### b. Float to String

```python
interest_rate = 2.99

# @TODO: Write a print statement to print the type of interest_rate variable

# We can convert this to a string
interest_rate = str(interest_rate)

# @TODO: Write a print statement to print the interest_rate variable


# @TODO: Write a print statement to print the type of interest_rate variable
```

### c. Boolean to String

```python
valid = True

# Write a print statement to print the type of valid variable

# We can convert this to a string
valid = string(valid)

# Write a print statement to print the valid variable


# Write a print statement to print the type of valid variable
```

# 2-12. Converting Datatypes To Boolean
To convert a float, integer or string to boolean, we use the bool() function  
**Syntax**: bool(<other_datatype_variable>)

### a. Float to Boolean

```python
my_gpa = 3.58

# @TODO: Write a print statement to print the type of my_gpa

# We can convert this to a boolean
my_gpa = bool(my_gpa)

# @TODO: Write a print statement to print the my_gpa

# @TODO: Write a print statement to print the type of my_gpa
```
<details>
  <summary>
    🚩 To remember:
  </summary>
  Any float other than 0.0 when converted to boolean will evaluate to True, 0.0 will evaluate to False
</details>

### b. Integer to Boolean

```python
score = 98

# @TODO: Write a print statement to print the type of score variable

# We can convert this to a float
score = bool(score)

# @TODO: Write a print statement to print the score variable


# @TODO: Write a print statement to print the type of score variable
```

<details>
  <summary>
    🚩 To remember:
  </summary>
  Any integer other than 0 when converted to boolean will evaluate to True, 0 will evaluate to False
</details>

### c. String to Boolean

```python
my_string = "Hello World"

# Write a print statement to print the type of my_string variable

# We can convert this to a boolean
my_string = bool(my_string)

# Write a print statement to print the my_string variable


# Write a print statement to print the type of my_string variable
```
<details>
  <summary>
    🚩 To remember:
  </summary>
  When you convert a string to a boolean, empty string evaluates to False and any other string evaluates to True
</details>

# 2-13. Input Function
If we need the user to interact with our program by providing some data, we must use input function

### Syntax:
a. <variable_name> = input() or  
b. <variable_name> = input(\<string\>)

## a.
```python
name = input()
print(name)
```

<details>
  <summary>
    🔎 Closer look
  </summary>
  name = input() - prompt the user to enter a value and, we store that in a variable called name<br>
  print(name) - we print the user entered value
</details>


<details>
  <summary>
    🚩 2-13a. To remember
  </summary>
  input is a value returning function<br>
  so you must always have collect the value (entered by the user) in a variable
</details>


## b. 
We can send a string inside the parentheses to give some instructions to the user on what he/she is expected to enter

```python
name = input("Enter your name: ")
print(name)
```

<details>
  <summary>
    👉 2-13b. Try this
  </summary>
  ask the user to enter age and print it
</details>

<details>
  <summary>
    👀 Answer
  </summary>
  age = input("Enter age: ")
</details>


## c. Datatype

input() function always returns a string

```python
height = input("Enter your height: ")
print(type(height))
```

<details>
  <summary>
    👉 2-13c. Try this
  </summary>
  ask the user to enter age and add 1 to it and print Next year, you will be __ years old
</details>

<details>
  <summary>
    👀 Answer
  </summary>
  age = input("Enter age: ")<br>
  age = float(age)<br>
  age = age + 1<br>
  print(f"Next year, you will be {age} years old")
</details>


<details>
  <summary>
    🚩 2-13c. To remember
  </summary>
  input() function always returns a string
</details>

# 2-14. Operators

## a. Arithmetic Operators

| Operator | Description                                                                                |
|----------|--------------------------------------------------------------------------------------------|
| +        | Addition                                                                                   |
| -        | Subtraction                                                                                |  
| *        | Multiplication                                                                             |  
| /        | **Division** - Divides one number with another and gives the result as floating point      |  
| //       | **Integer Division** -  Divides one number with another and gives the result as an integer |  
| %        | **Remainder** -  Divides one number with another and gives the remainder                   |  
| **       | **Exponent** -  Raises a number to a power                                                 |  

<details>
  <summary>
    👉 2-14a. Try this
  </summary>
  Write code to solve this problem. If you have 25 cookies and 7 people, how many cookies will you have left, after each person gets the same number of cookies? How many cookies will each person get?
</details>

<details>
  <summary>
    👀 Answer
  </summary>
  cookies = 25<br>
  people = 7<br>
  remaining_cookies = cookies % people # get remainder<br>
  cookies_per_person = cookies // people # get integral quotient<br>
  print(f"Remaining Cookies: {remaining_cookies}")<br>
  print(f"Cookies per person: {cookies_per_person}")
</details>

### Operator Precedence
The order in which a mathematical expression is calculated in Python is similar to that we learned in Algebra  
The acronym PEMDAS stands for Parentheses, Exponents, Multiplication/Division, Addition/Subtraction 

<details>
  <summary>
    👍 2-14a. Rule of Thumb
  </summary>
  To remember PEMDAS use the mnemonic "Please Excuse My Dear Aunt Sally"
</details>

<details>
  <summary>
    👉 2-14a2. Try this
  </summary>
  Write code to get user input a value in centigrade and convert it to Fahrenheit. <a href="/c-to-f.png">See Formula</a>
</details>

<details>
  <summary>
    👀 Answer
  </summary>
  user_centigrade = input("Enter temperature in centigrade: ")<br>
  user_centigrade = float(user_centigrade)<br>
  fahrenheit = user_centigrade * (9/5) + 32 <br>
  print(f"Temperature in fahrenheit: {fahrenheit}")<br>
  # When testing this program, enter only numeric values for temperature
</details>


## b. Assignment Operators

| Operator | Description                                                                            |
|----------|----------------------------------------------------------------------------------------|
| +=       | **Increment** -  Adds a value to a number and stores it in the number on the left      |  
| -=       | **Decrement** -  Subtracts a value to a number and stores it in the number on the left |  
| *=       | _a *= b_ means a = a * b                                                               |
| /=       | _a /= b_ means a = a / b                                                               |

```python
# In 2-13c. Try this Answer
# We incremented user's age by 1

age = input("Enter age: ")
age = float(age)
age = age + 1
print(f"Next year, you will be {age} years old")
```

Instead of age = age + 1, we can concisely use age += 1

<details>
  <summary>
    👉 2-14b. Try this
  </summary>
  Write a program to decrement a user's age by 1 and print Last year you were __ years old
</details>

<details>
  <summary>
    👀 Answer
  </summary>
  age = float(input("Enter age: ")) # you can convert to float in the same line<br>
  age -= 1<br>
  print(f"Last year, you were {age} years old")
</details>

## c. Comparison Operators

Comparison operators are used to compare two values  

| Operator | Description              |
|----------|--------------------------|
| >        | Greater than             |  
| <        | Less than                |  
| ==       | Equal to                 |
| >=       | Greater than or equal to |
| <=       | Less than or equal to    |
| !=       | Not equal to             |

```python
result = 5>7
print(result)
```

<details>
  <summary>
    🔎 Closer look
  </summary>
  python will compare if 5 is greater than 7<br>
  since 5 is not greater than 7, the result is false<br>
  it is stored in the result variable which is a boolean<br>
  print statement prints that boolean - False
</details>

### \>, <, >=, <= cannot be used to compare strings

<details>
  <summary>
    👉 2-14c. Try this
  </summary>
  Ask user to input his score and print if the entered score is less than or equal to 60
</details>

<details>
  <summary>
    👀 Answer
  </summary>
  score = int(input("Enter score: ")) # convert to int <br>
  result = score<=60<br>
  print(result)
</details>

<details>
  <summary>
    🚩 2-14c. To remember
  </summary>
  >, <, >= and <= cannot be used when one side is a string
</details>

## d. Logical Operators

| Operator | Description                                            |
|----------|--------------------------------------------------------|
| and      | Returns True if all conditions are True                |  
| or       | Returns True if at least one of the conditions is True |  
| not      | Reverse the result                                     |

```python
result = 5<7 and 6<9
print(result)
```

<details>
  <summary>
    🔎 Closer look
  </summary>
  python will compare if 5 is less than 7, and it evaluates to True<br>
  then python will compare if 6 is greater than 9, and it evaluates to True<br>
  since both the conditions are True, the and operator will return True<br>
  that is stored in the result variable
  print statement prints that variable - True
</details>

```python
result = 5<7 and 6>9 and 7>10
print(result)
```

<details>
  <summary>
    🔎 Closer look
  </summary>
  python will compare if 5 is less than 7, and it evaluates to True<br>
  then python will compare if 6 is greater than 9, and it evaluates to True<br>
  then python will compare if 7 is greater than 10, and it evaluates to False<br>
  since all the conditions are not True, the and operator will return False<br>
  that is stored in the result variable
  print statement prints that variable - False
</details>

<details>
  <summary>
    👉 2-14d. Try this
  </summary>
  Ask user to input his score and print if the entered score is between 79 and 90, not including 79.<br>
  Hint: User score greater than 79 or score less than or equal to 90
</details>

<details>
  <summary>
    👀 Answer
  </summary>
  score = int(input("Enter score: "))<br>
  result = score>79 or score<=90<br>
  print(result)
</details>

<details>
  <summary>
    🚩 2-14c,d. Remember
  </summary>
    The expressions using comparison and logical operators will evaluate to True or False<br>
    We will use these expressions in Chapter 3 - in if statement
  
</details>

# 2-15. String Concatenation

# 2-16. print using end, sep and escape characters

## a. Using end in print  
### Suppressing the ending newline
Each print statement always starts the display in a new line  

```python
# Execute the two statements below
print("Hello")
print("World")
```

To suppress the newline, we use a special argument called **end**  

```python
print("Hello", end = '')
print("World")
```

## b. Using end with argument 
When multiple arguments are passed to a print function, they are automatically separated by a space 
We can use the **end** to display anything we want after the last string

```python
print("Uno", "Dos", "Tres", end = ' ** ')
```

<details>
  <summary>
    👉 2-16b. Try this
  </summary>
  Write a print statement to display Uno Dos Tres |
</details>

<details>
  <summary>
    👀 Answer
  </summary>
  print("Uno", "Dos", "Tres", end = ' |')
</details>


## c. Using sep in Print
When multiple arguments are passed to a print function, they are automatically separated by a space  
If we don't want a space printed between the items, we can use a special argument called **sep**  
The specified string will be inserted between each item  

```python
name = "Johnny Vince"
major = "ACCT"
gpa = 3.54
print(name, major, gpa, sep = ' ** ')
```

<details>
  <summary>
    👉 2-16c. Try this
  </summary>
  Given<br>
  name = "Johnny Vince"<br>
  major = "ACCT"<br>
  gpa = 3.54<br>
  Write ONE print statement to display Johnny Vince, ACCT, 3.54
</details>

<details>
  <summary>
    👀 Answer
  </summary>
  print(name, major, gpa, sep = ', ')
</details>

## d. Escape Characters

| Escape Character | Effect                                              |
|------------------|-----------------------------------------------------|
| \n               | Causes output to be advanced to the next line       |
| \t               | Causes output to skip over to the next tab position |
| \\'              | Causes a single quote mark to be printed            |
| \\"              | Causes a double quote mark to be printed            |
| \\\              | Causes a backslash character to be printed          |

```python
# Execute these statements one at a time and see

print("Uno\nDos\nTres")
print("Uno\t\tDos\t\tTres")
print('I\'m taking CINS 3002')
print('The path is C:\\Users\\rodda')
```

<details>
  <summary>
    👉 2-16d. Try this
  </summary>
  Given<br>
  name = "Johnny Vince"<br>
  major = "ACCT"<br>
  gpa = 3.54<br>
  Write ONE print statement to display<br>
  Johnny Vince<br>
  ACCT<br>
  3.54
</details>

<details>
  <summary>
    👀 Answer
  </summary>
  print(name, major, gpa, sep = '\n')
</details>

# 2-17. Formatting with F-strings
F-string is a special type of string literal that allow you to format values in a variety of ways in a print statement  
By using **f**, short for format, and curly braces, **{ }**, we can print the value of the variable

## a. Placeholder Values
```python
name = "John Smith"
print(f'My name is: {name}')
```

<details>
  <summary>
    🚩 To remember
  </summary>
  {name} is called a placeholder for the value of name
</details>

<details>
  <summary>
    👉 2-17a. Try this
  </summary>
  Write one print statement to display<br>
  Name: John Smith<br>
  Major: CINS<br><br>
  name = "John Smith"<br>
  major = "CINS"<br>
</details>

<details>
  <summary>
    👀 Answer
  </summary>
  print(f'Name: {name}\nMajor: {major}')
</details>

## b. Placeholder Expressions
We can also use expressions inside {}

```python
num = 80
print(f'The square of {num} is: {num ** 2}')
```

<details>
  <summary>
    👉 2-17b. Try this
  </summary>
  Using placeholder expressions<br>
  Print the remainder the given number when divided by 7<br>
  It should display:<br><br>
  The remainder of 80/7 is 3<br><br>
  num = 80
</details>

<details>
  <summary>
    👀 Answer
  </summary>
  print(f'The remainder of {num}/7 is {num%7}')
</details>

## c. Formatting Values - Precision

**Syntax:** {<variable_name>: .\<number-of-decimals>f}  

- We can use the . as format specifier to round float variables  
- The number following the . specifies desired digits after the decimal places  
- The f after that specifies that it is a float

```python
my_float = 587435684235 / 63

print(f'Unformatted float: {my_float}')

# To format a float to two decimal points
print(f'Formatted float: {my_float: .2f}')
```

<details>
  <summary>
    👉 2-17c. Try this
  </summary>
  Format the float to three decimal points<br>
  The output should be<br><br>
  Three decimal point float:  9324375940.238<br><br>
  my_float = 587435684235 / 63
</details>

<details>
  <summary>
    👀 Answer
  </summary>
  print(f'Three decimal point float: {my_float: .3f}')
</details>


## d. Formatting Values - Comma
We can insert comma separators for accounting numbers by using the `,` specifier  
**Syntax:** {<variable_name> : ,}

```python
my_float = 587435684235 / 63

print(f'Unformatted float: {my_float}')
print(f'Comma formatted float: {my_float: ,}')
```

### Using both specifiers - precision and comma
```python
# To format a float to two decimal points and comma separator

print(f'Comma formatted float: {my_float: ,.2f}')
```

<details>
  <summary>
    👉 2-17d. Try this
  </summary>
  Format the above float to comma separated and with no decimal point<br>
  The output should be<br><br>
  Sales revenue: $ 9,324,375,940
</details>

<details>
  <summary>
    👀 Answer
  </summary>
  print(f'Sales revenue: $ {my_float : ,.0f}')
</details>

## e. Formatting Values - Type

| Type Character | Effect                                             |
|----------------|----------------------------------------------------|
| d or D         | Causes text to be formatted as integer             |
| f              | Causes text to be formatted as float               |
| %              | Causes text to be formatted as a percentage        |
| e              | Causes text to be formatted in scientific notation |

### 1. Formatting integers
So far we have seen formatting floats  
We can format integers using the d or D designator  

```python
number_of_people = 452302

# To format an integer
print(f'Number of people: {number_of_people:d}')
```

<details>
  <summary>
    🚩 To remember
  </summary>
  When we use d or D, we cannot use the . (precision) designator
</details>


<details>
  <summary>
    👉 2-17e1. Try this
  </summary>
  Write a print statement to format<br>
  the number of people with comma separation<br>
  The output should be<br><br>
  Number of people: 452,302<br><br>
  number_of_people = 452302
</details>

<details>
  <summary>
    👀 Answer
  </summary>
  print(f'Number of people: {number_of_people: ,d}')
</details>

### 2. Formatting as a percentage
We use **%** as format specifier to display a float as a percentage
```python
my_float = 0.25

# To format a float as a percentage
print(f'Formatted float: {my_float: %}')

# To format a float as a percentage with 0 decimal places
print(f'Formatted float: {my_float: .0%}')

```

<details>
  <summary>
    👉 2-17e2. Try this
  </summary>
  Write a print statement to format
  the given float as a percentage with 1 decimal place<br><br>
  interest_rate = 0.25
</details>

<details>
  <summary>
    👀 Answer
  </summary>

```python
print(f'{interest_rate: .1%}')
```
</details>


### 3. Formatting in scientific notation
We use **_e_** to specify the scientific notation 

```python
number_of_stars = 456987123023155

# To format a float using scientific notation
print(f'Number of stars: {number_of_stars: e}')
```

<details>
  <summary>
    👉 2-17e3. Try this
  </summary>
  Write a print statement to format<br>
  as a scientific notation with 2 decimal places<br>
  The output should be<br><br>
  Number of stars:  4.57e+14<br><br>
  number_of_stars = 456987123023155
</details>

<details>
  <summary>
    👀 Answer
  </summary>
  
```python
print(f'Number of stars: {number_of_stars: .2e}')
```
</details>

## f. Formatting Values - Width
**Syntax:** {<variable_name : <number_of_characters_side>}  
No specifier, we simply put a number after the :   
That will format the placeholder to span that many characters  

```python
product = "Sony TV"
sales = 568495.5638

# To format the variable to span 20 characters
print(f'{product}: {sales: 20}')
```

### Multiple specifiers: width and precision

```python
product = "Sony TV"
sales = 568495.5638

# To format sales to span 20 characters and two decimal places
# Notice the \t for tab space
print(f'{product}\t{sales: 20.2f}')

```

<details>
  <summary>
    👉 2-17f. Try this
  </summary>
  Write a print statement to<br>
  Print the product name and a colon<br>
  Format the float to span across 30 characters<br>
  with 3 decimal places and comma<br>
  The output should be<br><br>
  Sony TV &ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;568495.5638<br><br>
  product = "Sony TV"<br>
  sales = 568495.5638
</details>

<details>
  <summary>
    👀 Answer
  </summary>

```python
print(f'{product}\t{sales: 30,.3f}')
```
</details>

## g. Formatting Values - Alignment
We can use the >,<,^ specifiers to get right, left and center aligned data, respectively  

**Syntax:** {<variable_name> : <alignment_specifier>\<width>}
<details>
  <summary>
    🚩 To Remember
  </summary>
  When using alignment specifier width MUST be specified
</details>


| Alignment Character | Effect                           |
|---------------------|----------------------------------|
| ^                   | Causes text to be center aligned |
| <                   | Causes text to be left aligned   |
| >                   | Causes text to be right aligned  |

```python
my_float = 568495.5698

# To format a float to right align across 20 characters
print(f'Right-aligned float: {my_float: >20}')

```

<details>
  <summary>
    💡 2-17g. Note
  </summary>
  If width is specified alignment is not, then float or integer defaults to right
</details>


<details>
  <summary>
    👉 2-17g. Try this
  </summary>
  Write a print statement to<br>
  format the following float to <br>
  center align across 30 characters<br>
  print only two decimal places<br>
  and as a percentage<br>
  The output should be:<br><br>
  The percentage is:&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;84.24% <br><br>
  this_percentage = 0.842365
</details>

<details>
  <summary>
    👀 Answer
  </summary>

```python
print(f'The percentage is: {this_percentage: ^30.2%}')
```
</details>



<details>
  <summary>
    👉 2-17g-2. Try this
  </summary>
  Given products and sales values below<br>
  Write two print statements to display the following<br>
  1. product name right aligned spanning 20 characters<br>
  2. a tab character, a colon, a space and $ symbol<br>
  3. the sales value right aligned spanning 15 characters
      comma separated, with no decimal places<br>
  The output should be<br><br>
               Sony TV&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;: $&ensp;&ensp;&ensp;568,496<br>
            Samsung TV&ensp;&ensp;&ensp;: $&ensp;&ensp;&ensp;425,678<br><br>
  product1 = "Sony TV"<br>
  sales1 = 568495.5638<br>
  product2 = "Samsung TV"<br>
  sales2 = 425678.2145<br>
</details>

<details>
  <summary>
    👀 Answer
  </summary>
  print(f'{product1 : >20}\t: ${sales1 : >15,.0f}')<br>
  print(f'{product2 : >20}\t: ${sales2 : >15,.0f}')
</details>

## h. Order of Designators
When using multiple designators in a format specifier, we have to use the correct order  
The order is `[alignment </>/^] [width] [,] [.precision] [type d/e/f/%]`

<details>
  <summary>
    🤓 2-17h. To remember
  </summary>
  You may use the mnemonic<br><br>
  Andy Was Clearly Preoccupied Today<br><br>
  A - alignment<br>
  W - width<br>
  C - comma<br>
  P - precision<br>
  T - type
</details>

## i. Concatenation with F-strings
We can concatenate multiple f-strings in a single print statement
We can use + or a space

#### For example
In our previous example:  
We wrote TWO print statements to get the output  
Sony TV&ensp;&ensp;&ensp;&ensp;: $&ensp;&ensp;&ensp;&ensp;&ensp;568,496  
Samsung TV: $&ensp;&ensp;&ensp;&ensp;&ensp;425,678

Instead, we can write one print statement by simply using +
 ```python
product1 = "Sony TV"
sales1 = 568495.5638
product2 = "Samsung TV"
sales2 = 425678.2145

print(f'{product1 : >20}\t: ${sales1 : >15,.0f}\n'
      +
      f'{product2 : >20}\t: ${sales2 : >15,.0f}')
```

<details>
  <summary>
    👉 2-17i. Try this
  </summary>
  Given<br> 
  name1 = "Jon Snow"<br>
  major1 = "ACCT"<br>
  gpa1 = 3.54897<br>
  email1 = "snow@ed.edu"<br>
  name2 = "David Willis"<br>
  major2 = "HIST"<br>
  gpa2 = 3.858812<br>
  email2 = "willis@ed.edu"<br>
  Print the data in a tabular fashion like this<br><br>

  | Name         | Major | GPA  | Email         |
  |--------------|-------|------|---------------|
  | Jon Snow     | ACCT  | 3.54 | snow@ed.edu   |
  | David Willis | HIST  | 3.85 | willis@ed.edu |

  Format as follows<br>
  name left aligned over 20 characters<br>
  major center aligned over 6 characters<br>
  gpa right aligned over 6 characters, rounded to two decimal points<br>
  email left aligned over 20 characters<br>
  
</details>

<details>
  <summary>
    👀 Answer
  </summary>

```python
print(f'{"Name": ^20}', f'{"Major": ^6}', f'{"GPA": ^6}', f'{"Email": ^20}', sep = ' | ') # header row<br>
print("-" * 62) # line under the header, hyphen printed 62 times<br>
print(f'{name1: <20}', f'{major1: ^6}', f'{gpa1: >6.2f}', f'{email1: <20}', sep = ' | ') # first data row<br>
print(f'{name2: <20}', f'{major2: ^6}', f'{gpa2: >6.2f}', f'{email2: <20}', sep = ' | ') # second data row
```
</details>


