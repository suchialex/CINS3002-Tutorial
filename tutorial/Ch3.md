# 3-1. Decision Structures
So far, we have written Python programs that are sequence structures  
A **sequence structure** is a set of statements that execute sequentially    
But some situations cannot be solved by sequential steps, but based on decision-making    

We see such real life examples all the time -    
If the light is green, we have to **GO**  
If the light is orange, we have to **SLOW DOWN**  
If the light is red, we have to **STOP**  

To implement situations like this, we must use a decision structure or selection structure  

The decision structure used in Python is **if statement**

# 3-2. If Statement

**Syntax:**  
if \<condition>:  
\<indented statement1>  
\<indented statement2>  
etc..

It uses the `if` keyword, followed by the condition and a colon  
If this condition evaluates to **True**, the next statement or statements inside the if block will execute.    
To denote that a statement or group of statements belong in the if block, they are indented using
- a tab character or
- one or more space characters  

Any expression using comparison and/or logical operators is called a condition

<details>
  <summary>
    💡 Remember:
  </summary>
  We saw conditional and logical operators in 2-14c,d<br>  
  The expressions using these operators will evaluate to True or False
</details>

## a. Checking if user input is equal to a given val

```python
# == is the comparison operator
# user input is always a string

choice = input("Enter choice: ")
if choice == "1":
  print("You entered 1")
```

## b. Checking if user input is greater than or less than a given val


```python
# In 2-14d. Try this
# We wrote code to solve the following:
# Ask user to input his score and print if the entered score is between 79 and 90, not including 79

score = int(input("Enter score: "))
result = score>79 or score<=90
print(result)
```
Using the value of result (which is either True or False) we can decide to print **B grade**

```python
# In 2-14d. Try this
# We wrote code to solve the following:
# Ask user to input his score and print if the entered score is between 79 and 90, not including 79

score = int(input("Enter score: "))

result = score>79 or score<=90
if result:
  print("B grade")

# Or simply
if score>79 or score<=90:
  print("B grade")
```

```python
year = 2025
if year > 2023:
  print("Inside IF block")
  print("This is the future Doc")
print("Outside IF block")
```


<details>
  <summary>
    👉 3-2b. Try this
  </summary>
  Check if score is less than 60 and print F grade<br>
  score = 56<br>
</details>


<details>
  <summary>
    👀 Answer
  </summary>

  ```python
  if score < 60:
    print("F grade")
  ```
</details>

# 3-3. If-else Statement
The **if-else statements** are used to execute both the true part and the false part of a given condition.  

If the condition is true, the _if block_ code is executed otherwise, the _else block_ code is executed.

### Syntax:
```python
if condition:
  # Executes this block if the condition is true
else:
  # Executes this block if the condition is false
```

### Example:
```python
year = int(input("Enter a year: "))
if year > 2024:
  print("Inside IF block")
  print("This is the future Doc")
else:
  print("Inside ELSE block")
  print("Back to the future Doc")
```

<details>
  <summary>
    👉 3-3. Try this
  </summary>
  Accept user input for a score<br>
  Check if score is less than 60 and print Fail<br>
  otherwise, print Pass<br>
</details>


<details>
  <summary>
    👀 Answer
  </summary>

  ```python
  score = int(input("Enter score: "))
  if score < 60:
    print("Fail")<br>
  else:
    print("Pass")
  ```
</details>

# 3-4. Nested IF Statement
When an if a statement is present inside another if statement, it is called a nested IF statement.  

This situation occurs when you have to filter a variable multiple times.  
In nested IF statements, you should always take care of the indentation to define the scope of each statement. You can have as many levels of nesting as required  

But it makes the program less optimized, and as a result, can be more complex to read and understand.  
Therefore, you should always try to minimize the use of nested IF statements.

### Syntax:
```python
if condition1:
  # Executes if condition1 is true
  if condition2:
    # Executes if condition2 is true
  else:
    # Executes if condition2 is false
else:
  # Executes if condition1 is false
  if condition3:
    # Executes if condition3 is true
  else:
    # Executes if condition3 is false
```

### Example:

```python
year = int(input("Enter the year: " ))
if year%4 == 0:  
  print("It is a leap year")
  if year < 2024:
    print("It is in the past")
  else:
    print("It is not in the past")
else:
  print("It is not a leap year")
  if year > 1997:
    print("Generation Z")
  else:
    print("Not Generation Z")
```
<details>
  <summary>
    🔎 Closer look:
  </summary>
  The user input year is converted to integer<br>
  % is an operator that calculates the remainder when two numbers are divided<br>
  So, if we want to know whether the year is leap year, it must be divisible by 4<br>
  That means the remainder must be zero when divided by 4<br>
  We check if the year is a leap year<br>
  If that is True, then we check if the year is less than 2024<br>
  If that is True, the print statement displays It is in the past<br>
  Otherwise, the print statement displays It is not in the past<br>
  If it is not a leap year<br>
  We check if the year is later than 1997<br>
  If True, the print statement displays Generation Z<br>
  Otherwise, the print statement displays Not Generation Z
</details>

<details>
  <summary>
    🖨 Output test cases:
  </summary>
  When we enter the year 2000,<br>
  Because, it is a leap year and is earlier than 2024, the output will be:<br>
  It is a leap year<br>
  It is in the past<br><br>
  When we enter the year 2028,<br>
  Because, it is a leap year and is later than 2024, the output will be:<br>
  It is a leap year<br>
  It is not in the past<br><br>
  When we enter the year 2001,<br>
  Because, it is not a leap year and is later than 1997, the output will be:<br>
  It is not a leap year<br>
  Not Generation Z<br><br>
  When we enter the year 1995,<br>
  Because, it is not a leap year and is earlier than 1997, the output will be:<br>
  It is not a leap year<br>
  Generation Z<br><br>
</details>


<details>
  <summary>
    👉 3-4. Try this
  </summary>
  Accept user's input for a number<br>
  Check if the number is an even number<br>
  If yes, check if the number is divisible by 3<br>
  If yes, print The number is divisible by 6<br>
  Otherwise, print The number is not divisible by 6<br><br>
  But if the number is not an even number<br>
  Print Odd number
</details>


<details>
  <summary>
    👀 Answer
  </summary>

  ```python
    num = int(input("Enter the number: " ))
    if num % 2 == 0:  
      if num % 3 == 0:
        print("The number is divisble by 6")
      else:
      print("The number is not divisble by 6")
    else:
      print("Odd number")
```
</details>

# 3-5. If-Elif-Else Statement
First the if statement condition is evaluated.  
If it is true, the if block is executed.  
If false, the elif condition is evaluated.  
If true, the elif block is executed.  
If false, the else block is executed.  
We can have multiple elif blocks.

### Syntax:
```
if condition:
  statement
elif condition:
  statement
else:
  statement
```

### Example:

```python
light = input("Enter the light color: ")
if light == "red":
  print("Stop")
elif light == "orange":
  print("Slow Down")
elif light == "green":
  print("Go")
else:
  print("Invalid color")
```

<details>
  <summary>
    🔎 Closer look:
  </summary>
  We accept the user input for light color<br>
  We check if the color is red<br>
  If that is True, the control goes to the print statement that displays Stop<br>
  If not, the control jumps to the elif that checks if the color is orange<br>
  If that is True, the control goes to the print statement that displays Slow Down<br>
  If not, the control jumps to the elif that checks if the color is green<br>
  If that is True, the control goes to the print statement that displays Go<br>
  If not, the control jumps to the else block that has the print statement to display Invalid color
</details>

<details>
  <summary>
    🖨 Output test cases:
  </summary>
  When we enter red,<br>
  the output will be Stop<br><br>
  When we enter orange,<br>
  the output will be Slow Down<br><br>
  When we enter green,<br>
  the output will be Go<br><br>
  When we enter pink/blue,<br>
  the output will be Invalid color<br><br>
</details>


<details>
  <summary>
    👉 3-5-1. Try this
  </summary>
  
  - Accept user's input and store in a variable called choice  
  - If choice is 1, print You entered 1  
  - If choice is 2 print You entered 2  
  - If choice is 3 print You entered 3  
  - If choice is 4 print You entered 4  
  - If choice is 5 print You entered 5  
  - If anything else is entered, print Invalid Choice
</details>


<details>
  <summary>
    👀 Answer
  </summary>

```python
choice = input("Enter your choice: " )
if choice == "1":  
  print("Your entered 1")
elif choice == "2":  
  print("Your entered 2")
elif choice == "3":  
  print("Your entered 3")
elif choice == "4":  
  print("Your entered 4")
elif choice == "5":  
  print("Your entered 5")
else:
  print("Invalid Choice")
```
</details>


<details>
  <summary>
    👉 3-5-2. Try this
  </summary>
  Accept user's input for score<br>
  If score is between 90 and 100, print A grade<br>
  If score is between 80 and 89, print B grade<br>
  If score is between 70 and 79, print C grade<br>
  If score is between 60 and 69, print D grade<br>
  If score is between 60 and 0, print F grade<br>
  If score is none of the above, print Invalid Score<br>
</details>


<details>
  <summary>
    👀 Answer
  </summary>

  ```python
    score = int(input("Enter your score: " ))
    if score >= 90 and score <= 100:  
      print("A grade")
    elif score >= 80 and score <= 89:
      print("B grade")
    elif score >= 70 and score <= 79:
      print("C grade")
    elif score >= 60 and score <= 69:
      print("D grade")
    elif score >= 0 and score <= 59:
      print("F grade")
    else:<br>
      print("Invalid Score Entered")
  ```
</details>
