# 5-1. Functions
- A function is a group of statements that exist within a program for the purpose of performing a specific task
- Most programs perform tasks are large enough to be broken down into several subtasks
- These subtasks in Python are called **Functions**
- These functions can be executed in the desired order to perform the overall task of the program  

<details>
  <summary>
    🤓 Example
  </summary>
  Think of a university<br>  
  Its functionality is so vast that it is divided into departments and each of these departments perform jobs that are specific to them<br><br>  
  &ensp; - Admissions handles all recruitment, prep etc<br><br>  
  &ensp; - Housing handles dorms etc<br>  
  &ensp; - Registrar handles are courses and add and drop etc<br>
  And many more <br>
  All these departments also pass information back and forth for their functioning
</details>

## Modularized Program
Any program that uses functions to accomplish a task is called a modularized program

### Without functions
```python
# Admissions
print("Admissions step 1")
print("Admissions step 2")
print("Admissions step 3")
print("Admissions step 4")

# Scholarship
print("Scholarship step 1")
print("Scholarship step 2")
print("Scholarship step 3")

# Enrollment
print("Enrollment step 1")
print("Enrollment step 2")
```

### With Functions

```python
# Admissions
def admissions():
  print("Admissions step 1")
  print("Admissions step 2")
  print("Admissions step 3")
  print("Admissions step 4")

# Scholarship
def scholarship():
  print("Scholarship step 1")
  print("Scholarship step 2")
  print("Scholarship step 3")

# Enrollment
def enrollment():
  print("Enrollment step 1")
  print("Enrollment step 2")



admissions()
scholarship()
enrollment()
```

## Benefits of using functions

1. Simpler Code
2. Code reuse
3. Better testing
4. Faster development
5. Easier facilitation of teamwork

# 5-2. main() function

It is important to have main() function in a modularized program  
main() is in main.py
The main function is called when the program starts    
The main function then calls other functions in the program as they are needed   
The main function contains a program’s **mainline logic**  
The main function is Python's in-built void function

<details>
  <summary>
    🤓 Analogy
  </summary>
  Think of main() as the conductor of an orchestra<br>
  While each instrument player plays his own notes, the conductor decides who plays at what time
</details>

## a. Defining a main() function
In main.py

```python
def main():  # This statement is called main definition or header
  print("Hello World")
```

<details>
  <summary>
    🔎 Closer Look:
  </summary>
  def is a keyword in Python and needs to be in that exact case<br><br>
  main is a built-in function name in Python and you cannot use Main or MAIN or any other case, except main in all lowercase<br><br>
  The open/close parentheses denote that this is a function<br><br>
  : denotes that a block of statements could be following<br>
  (Similar to IF or FOR statements)<br><br>
  
  Every statement after this should be one indent to the right<br>
  All statements are executed sequentially<br>
  For now, we have only one statement that prints Hello World
</details>

## b. Calling main()
Defining is a function is not enough  
We must "call it" for the statement(s) to be executed  
main() must be called outside its definition  

<details>
  <summary>
    👍 5-2a,b: Rule of thumb:
  </summary>
  main() function definition and call will ALWAYS be at zero indent
</details>


```python
# Outside the definition of main()
main()
```

<details>
  <summary>
    👉 5-2a,b Try this:
  </summary>
  Add another statement inside main() to print<br>
  I am in main
</details>


<details>
  <summary>
    👀 Answer:
  </summary>
  Inside main(),<br>
  &ensp;print("I am in main")
</details>


<details>
  <summary>
    🚩 5-2 To remember:
  </summary>
  Function must be defined before the function call
</details>

# 5-3. Writing Our First Void Function

A function that doesn't return any value to the calling after execution is called a void function.

## a. Defining the function
**Syntax:**  

def <function_name>():  

This is called a **function header**  
Set of statement(s) inside the function is called **function body**

<details>
  <summary>
    💡 Function naming conventions
  </summary>
  Same rules when naming variables apply here<br><br>
- cannot use Python’s keywords<br>
- cannot contain spaces<br>
- cannot use any special characters except underscore<br>
- can use numbers as long as it doesn't start with a number<br>
- uppercase and lowercase characters are distinct
</details>

```python
def first_function(): # function header or function signature
  # all statements must be indented and collectively called function body
  print("This is my first function!")
  print("Hip hip hooray")

```

<details>
  <summary>
    👍 5-3a Rule of thumb:
  </summary>
Always define a function at ZERO indent position<br>
  Until we get to chapter 10
</details>

## b. Calling a function
Remember, defining is not enough, we must call it  
We call a function by its name with parentheses next to it  
Function call will not be inside its definition (at least until chapter 12)

```python
def main():
  first_function()

main()
```


<details>
  <summary>
    👉 5-3a Try this:
  </summary>
  Define a function named second_function and inside the function body have two print statements to print<br><br>
  I am in second function<br>
  I will call third function
</details>


<details>
  <summary>
    👀 Answer:
  </summary>
def second_function():<br>
&ensp;print("I am in main")<br>
&ensp;print("I will call third function")
</details>


<details>
  <summary>
    👉 5-3b Try this:
  </summary>
  Call the second_function in main() after the call to first_function
</details>


<details>
  <summary>
    👀 Answer:
  </summary>
def main():<br>
&ensp;first_function()<br>
&ensp;second_function()<br><br>
main()
</details>

# 5-4. Execution Sequence
A Python program begins at the first statement and executes each statement sequentially  

## a. Using Functions
<details>
  <summary>
    🚩 Remember
  </summary>
  A good practice is to write a Python program in main.py
</details>

- The main() function is defined in main.py  
- Then, the main() function is called  
- All the statements in the program should be inside the main() definition  
- main() function can also call other functions  
- When a function call is encountered, the execution **"jumps to"** the function definition of that function  
- It will execute all the statements until there are no more or until a special keyword **return** is encountered  
- Then the control comes back to the calling function  
Any statement written after a **return** statement will not be executed

<details>
  <summary>
    🤓 Recipe book
  </summary>
  <a href="/.tutorial/cake.jpg">Recipe</a>
</details>

```python
# Write a program to make Recipe 1 from the cake recipe book

# Without functions

print('Chocolate cake with buttercream icing')
print('Prepare the batter')

# Chocolate Batter
print('Beat eggs and butter')
print('Add sugar and beat some more')
print('Mix in flour, chocolate powder and baking powder') 
      
print('Bake the batter at 350o for 30 min')    
print('Prepare icing')

# Buttercream icing
print('Take butter at room temperature')
print('Add powdered sugar and mix them together')

# Vanilla Flavor
print('Split open the vanilla bean')
print('Use the back of the knife to get the seeds out')
print('Crush the seeds to extract the vanilla flavor')

print('Mix in vanilla flavor')

print('Apply icing to cake')

## -----------------------------

# Let's transform the above program to use functions
# Write main function first

```

<details>
  <summary>
  🔎 Closer look
  </summary>
  First the main function is called when Python encounters main()<br>
  The control jumps to the first line inside the main definition<br>
  This prints Chocolate cake with buttercream icing<br>
  Next control goes to the next line, which prints Prepare the batter<br>
  The next line is a function call to chocolate_batter()<br>
  In other words main function is calling chocolate_batter function<br>
  So, the control jumps to the first line of the function body of chocolate_batter<br>
  Which prints Beat eggs and butter<br>
  The control then goes to the next line which prints Add sugar and beat some more<br>
  Then the control goes to the next line which prints Mix in flour, chocolate powder and baking powder<br>
  Since there are no more statements after this, the control jumps to the next line of the calling function (main function)<br>
  The next line after the function call prints Bake the batter at 350o for 30 min<br>
  And the control goes to the next line which prints Prepare icing<br>
  The next line is a function call to buttercream_icing or main is calling buttercream_icing<br>
  So the control jumps to the first line of the function body which prints Take butter at room temperature<br>
  The control moves to the next line which prints Add powdered sugar and mix them together<br>
  In the next line, buttercream_icing is calling the function vanilla_flavor<br>
  So the control jumps to the first line in that function, which prints Split open the vanilla bean<br>
  The control goes to the next line which prints Use the back of the knife to get the seeds out<br>
  The control goes to the next line which prints Crush the seeds to extract the vanilla flavor<br>
  After this there are no more statements to execute, so the control goes back to the calling function, buttercream_icing<br>
  The next line in this function prints Mix in vanilla flavor<br>
  After this, there are no more statements in buttercream_icing, so the control jumps to the calling function, main<br>
  The next line in main prints Apply icing to cake<br>
  There are no more statements in main function, so the programs ends its execution.
</details>

<details>
  <summary>
    Recipe 1 (Chocolate cake with buttercream icing) using functions
  </summary> 
  
  ```python
  def main():
    print('Chocolate cake with buttercream icing')
    print('Prepare the batter')
    chocolate_batter()
    print('Bake the batter at 350o for 30 min')
    print('Prepare icing')
    buttercream_icing()
    print('Apply icing to cake')

  def chocolate_batter():
    print('Beat eggs and butter')
    print('Add sugar and beat some more')
    print('Mix in flour, chocolate powder and baking powder')

  def buttercream_icing():
    print('Take butter at room temperature')
    print('Add powdered sugar and mix them together')
    vanilla_flavor()
    print('Mix in vanilla flavor')

  def vanilla_flavor():
    print('Split open the vanilla bean')
    print('Use the back of the knife to get the seeds out')
    print('Crush the seeds to extract the vanilla flavor')

  main()

  ```
</details>



<details>
  <summary>
  🚩 5-4a. Remember:
  </summary>
  The function definition MUST appear before main() function call<br>
  Cannot use the same function name for two functions defined in the same file
</details>

<details>
  <summary>
  👉 5-4a. Try this
  </summary>
  Write a program to make Recipe 2 from the cake recipe book with functions. Define function(s) as needed
</details>

<details>
  <summary>
  👀 Answer
  </summary>

  ```python
  
  def vanilla_flavor():  # We have already written this function
    print('Split open the vanilla bean')
    print('Use the back of the knife to get the seeds out')
    print('Crush the seeds to extract the vanilla flavor')
  
  def vanilla_batter():
    print('Beat eggs and butter')
    print('Add sugar and beat some more')
    vanilla_flavor()
    print('Mix in flour, vanilla flavor and baking powder')

  def creamcheese_icing():
    print('Take creamcheese and beat it')
    print('Add powdered sugar and beat some more')
    print('Mix in almond flavor')
  
  def main():
    print('Vanilla cake with creamcheese icing')
    print('Prepare the batter')
    vanilla_batter()
    print('Bake the batter at 350 degrees for 30 min')
    print('Prepare icing')
    creamcheese_icing()
    print('Apply icing to cake')
  ```
 
</details>

## b. Functions inside Modules
We can also place our functions in separate files  

For example, all functions related to   
- icings can be placed in icing.py aka icing **module**    
- batter can be placed in batter.py aka batter **module**
  
In such cases, we will have to import the functions in main.py using import statement

```python
# Using import

# Method 1: Using comma separated names to import only the functions we need
from icing import vanilla_icing, creamcheese_icing
from batter import chocolate_batter, vanilla_batter

# Method 2: Using * to import ALL the functions
from icing import *
from batter import *

# Method 3
import icing
import batter
# In this method, the function call will have a prefix of the filename it is located in

# For example:
icing.vanilla_icing()
batter.chocolate_batter()
```

[Check out recipes using modules](https://replit.com/@SuchiRodda/Modules)


# 5-5. Hierarchy Chart

As the program gets bigger it can get difficult to track all the functions and the relationships between them. So we use a hierarchy chart  

A hierarchy chart, shows boxes that represent each function in a program. The boxes are connected in a way that illustrates the functions called by each function  

The hierarchy chart for our program chocolate cake with buttercream icing will look like this:
![Image](images\hierarchy_chart.jpg)  

The file name where the function is defined is depicted outside the box

<details>
  <summary>
    👉 5-5 Try this
  </summary>
  Draw a hierarchy chart for vanilla cake with cream cheese icing
</details>

<details>
  <summary>
    👀 Answer
  </summary>
  <a href="hc55.draw">Vanilla Cake with Cream cheese icing</a>
</details>

# 5-6. Writing Skeletal Code - pass keyword

When we are initially writing a program’s code, we know the names of the functions but may not know all the details of the code that will be in those functions  
Then we use the **pass** keyword to create empty functions  

**For example**  
Given the hierarchy chart as follows, let us write the empty functions or skeletal code  

![Image](images\hierarchy_chart_for_pass.jpg)

```python
def step1():
  pass

def step2():
  step3()

def step3():
  pass
  
def main():
  step1()
  step2()
  step4()

main()
```

<details>
  <summary>
    💡 Note:
  </summary>
  pass can be used not just in empty functions, it can be used as placeholder in if statement or for or any blocks
</details>

# 5-7. Local Variables snd scope

When we assign a value to a variable inside a function, we create **a local variable**   
A local variable created inside a function cannot be accessed by statements that are outside the function  

<details>
  <summary>
    💡 5-7 Note:
  </summary>The term local is meant to indicate that the variable can be used only locally, within the function in which it is created
</details>

```python

def get_name():
  # name is assigned a value by the user input
  name = input('Enter your name: ')
  
def main():
  get_name()
  print(f'Hello {name}.')

main()
 ```
<details>
  <summary>
    🔎 Closer look
  </summary>
  This program has two functions: main and get_name. In the function get_name, the name variable is assigned a value that is entered by the user, so the name variable is local to that function. This means that the name variable cannot be accessed by statements outside the get_name function.<br><br>

  The main function calls the get_name function. Then, the statement after the function call tries to access the name variable. This results in an error because the name variable is local to the get_name function, and statements in the main function cannot access it.
</details>

<details>
  <summary>
    🚩 5-7a To remember
  </summary>
  A local variable cannot be accessed by code at a point before the variable has been created.
</details>



## b. Scope
A variable’s scope is the part of a program in which the variable may be accessed. In the above example the scope of the variable name is the function get_name()  

<details>
  <summary>
    🚩 5-7b To remember
  </summary>
  A variable is visible only to statements in the variable’s scope.
</details>

# 5-8. Local Variables With Same Name

Different functions can have local variables with the same names because the functions cannot see each other's local variables

```python

def main():
  texas() # Call the texas function
  california() # Call the california function

# Definition of the texas function
def texas():
  birds = 5000  # a local variable named birds
  print(f'texas has {birds} birds.')

# Definition of the california function
def california():
  birds = 8000  # a local variable named birds
  print(f'california has {birds} birds.')

# Call the main function
main()
```

<details>
  <summary>
    🔎 Closer Look
  </summary> 
  Although there are two separate variables named birds in this program, only one of them is visible at a time because they are in different functions<br>
  When the texas function is executing, the birds variable with value 5000 is visible <br>
  When the california function is executing, the birds variable with value 8000 is visible
</details>

# 5-9. Passing Arguments to Functions

Sometimes it is useful not only to call a function, but also to send one or more pieces of data into the function<br>
Pieces of data that are sent into a function are known as **arguments**<br>
The function can use its arguments in calculations or other operations<br>

```python
def show_double(number):
 result = number * 2
 print(result)

def main():
  value = 5
  show_double(value)

main()
```

<details>
  <summary>
    🔎 Closer look
  </summary>
  When this program runs, the main function is called<br>
  Inside the main function definition<br>
  a local variable named value created and assigned the integer value 5<br>
  Then the show_double function is called, with value in parentheses<br>
  Or, in correct words, show_double function is called with value as an argument<br>
  In the show_double function definition, the number variable will be assigned the same value as the value variable<br>
  Then a local variable named result is assigned the value of the expression number * 2<br>
  Because number references the value 5, this statement assigns 10 to result.<br>
  Then the result variable is displayed
</details>

## Passing multiple values
If you want to pass more arguments, you can do so by using comma separated variables in the function call  
Also, you must accept the same number of comma separated variables in the function definition  
These two sets of variables may or may not have the same names  
The first argument is passed to the first parameter variable, the second argument is passed to the second parameter variable and so on
 
<details>
  <summary>
    🚩 To remember
  </summary>
  The variables inside the parentheses in a function call are called arguments or argument list<br>
  The variables inside the parentheses in a function definition are called parameters or parameter list<br>
  The number of arguments and parameters MUST match
</details>


<details>
  <summary>
    👉 Try this
  </summary>
  Define a function called create_multiple which accepts two parameters named, number and multiple<br>
  Inside the function body,<br>
  1. Create a local variable named resultant and assign it a value of expression number times multiple<br>
  2. Print the resultant variable
</details>


<details>
  <summary>
    👀 Answer
  </summary>
  def create_multiple(number, multiple):<br>
  &ensp;resultant = number * multiple<br>
  &ensp;print(resultant)
</details>


<details>
  <summary>
    👉 Try this
  </summary>
  In main() definition<br>
  1. Assign a local variable called n a value entered by the user input converted to integer<br>
  2. Assign another local variable called m, a value entered by the user input converted to integer<br>
  3. Call the create_multiple function with the arguments n and m in that order<br>
  4. Outside main() definition call the main() function
</details>


<details>
  <summary>
    👀 Answer
  </summary>
  def main():<br>
  &ensp;n = int(input("Enter number: "))<br>
  &ensp;m = int(input("Enter multiple: "))<br>
  &ensp;create_multiple(n, m)<br><br>
  main()
</details>

# 5-10. Making Changes to Parameters

We have seen that when an argument is passed to a function, the function parameter variable will reference the argument’s value<br><br>
But, any changes that are made to the parameter variable inside the function will not affect the argument

```python

def main():
  value = 99
  print(f'Before change me call: {value}')
  change_me(value)
  print(f'After change me call: {value}')

def change_me(arg):
  arg = 0
  print(f'Inside change me function: {arg}')
 
main()
```

<details>
  <summary>
    🔎 Closer look
  </summary>
The main function creates a local variable named value with value 99<br>
The print statement 'Before change me call: 99'<br>
The value variable is passed as an argument to the change_me function<br>
This means that in the change_me function, the arg parameter will also reference the value 99<br>
Inside the change_me function, the arg parameter is assigned the value 0<br>
This reassignment changes arg, but it does not affect the value variable in main<br>
The two variables now reference different values in memory. The print statement  'Inside change me function: 0'<br>
And the function ends<br>
Control of the program then returns to the main function<br>
The print statement displays 'After change me call: 99'<br>
This proves that even though the parameter variable arg was changed in the change_me function, the argument (the value variable in main) was not modified.
</details>

<details>
  <summary>
    🚩 5-10 To remember
  </summary>
  This form of argument passing, where a function cannot change the value of an argument that was passed to it, is called pass by value
</details>


So far we have seen that the calling function can communicate with the called function, but the called function cannot use the argument to communicate with the calling function.<br><br>
Later in this chapter, we will see how to write a function that can communicate with the part of the program that called it by returning a value

# 5-11. Keyword Arguments
We have seen how arguments are passed by position to parameter variables in a function.<br>
In addition to this form of argument passing, we can specify which parameter variable the argument should be passed to<br>

`parameter_name=value`<br>

parameter_name is the name of a parameter variable<br>
value is the value being passed to that parameter<br><br>
An argument that is written in accordance with this syntax is known as a **keyword argument**

### Let us see our Try this example:

```python
def create_multiple(number, multiple):
  resultant = number * multiple
  print(resultant)

def main():
  n = int(input("Enter number: "))
  m = int(input("Enter multiple: "))
  
  # Passing by position
  create_multiple(n, m)

  # Passing by keyword - one way
  create_multiple(number = n, multiple = m)

  # Passing by keyword - another way
  create_multiple(multiple = m, number = n)

main()
```

<details>
  <summary>
    🔎 Closer look
  </summary>
When we called create_multiple using positional arguments, n was passed to number and m was passed to multiple, simply based on their respective positions<br>
But, when we use keyword arguments we can specify, which argument can be passed to which parameter<br>
In this case, we don't have to follow the same order<br>
</details>

# 5-12. Mixing Keyword and Positional Arguments

It is possible to mix positional arguments and keyword arguments in a function call<br>
But the positional arguments must appear first, followed by the keyword arguments

```python

def display_student(first_name, last_name, major, email):
  print(f'Name: {last_name}, {first_name}\nMajor: {major}\nEmail: {email}')

def main():
  f = input("First Name: ")
  l = input("Last Name: ")
  m = input("Major: ")
  e = input("Email: ")

  # Mixing positional and keyword arguments
  display_student(f, l, email = e, major = m)

  # or
  display_student(f, l, major = m, email = e)
```

# 5-13. Globals

## a. Global Variables
A global variable is created outside all the functions   
It is accessible to **ALL** the functions in a program

```python
var = 10  # Create a global variable

def function1():
  print(var)

def function2():
  print(var)

function1()
function2()
```

To assign a value to a global variable

```python
var = 0  

def function1():
  print(f'The global variable is {var}.')

def function2():
  global var  # global keyword tells the interpreter to assign a value to the global variable var
  var = int(input('Enter a number: '))

function1()
function2()
function1()
```

## Issues with global variables:

### Global variables make debugging difficult
Any statement in a program file can change the value of a global variable. If you find that the wrong value is being stored in a global variable, you have to track down every statement that accesses it to determine where the bad value is coming from. In a program with thousands of lines of code, this can be difficult.

### Global variable dependency makes code portability difficult
Functions that use global variables are usually dependent on those variables. If you want to use such a function in a different program, most likely you will have to redesign it so it does not rely on the global variable.

### Global variables make a program hard to understand
A global variable can be modified by any statement in the program. If you are to understand any part of the program that uses a global variable, you have to be aware of all the other parts of the program that access the global variable.


## b. Global Constants
A global constant is a global name that references a value that cannot be changed.  

```python
INTEREST_RATE = 3.4

```

<details>
  <summary>
    👍 5-a: Rule of Thumb:
  </summary>
  Global variables and global constants are created at ZERO indent position
</details>

# 5-14. Value-Returning Functions
A value-returning function is a function that returns a value back to the part of the program that called it

```python
def function():
  number = input("Enter a number: ")
  return int(number)

def main():
  a = function()
  print(a)
  b = a*a
  print(b)

main()
```

<details>
  <summary>
    🔎 Closer look
  </summary>
  A value-returning function is a special type of function<br>
  It is a group of statements that perform a specific task<br>
  When you want to execute the function, you call it<br>
  When a value-returning function finishes, it returns a value back to the part of the program that called it.<br>
  The value that is returned from a function can be used like any other value: it can be assigned to a variable, displayed on the screen, used in a mathematical expression (if it is a number), and so on.
</details>

Value-returning functions can be
- Standard Library Functions
- User-defined Functions

# 5-15. Standard Library Functions
Python comes with a standard library of functions that have already been written for us  
These functions, also known as library functions, make a programmer’s job easier 

<details>
  <summary>
    💡 Remember
  </summary>
  We have used some Python’s library functions<br>
  print() - void function that takes arguments
  input() - value returning function that returns a string<br>
  range() - value returning function, returns a range
</details>

## Modules
- Many of the library functions are stored in files called modules   
- To be able to call a function stored in a module, we write an import statement at the top of the program  
- An import statement tells the interpreter the name of the module that contains the function 

## b. math Module:
One of the Python standard modules is named math    
It contains various mathematical functions that work with floating-point numbers  
To the math module’s functions we write an import statement at the top of the program  
This statement loads the contents of the math module into memory and makes all the functions in the math module available to the program

```python
import math
# to calculate the square root of a number
number = 35
square_root = math.sqrt(number)
print(square_root)
```

<details>
  <summary>
    🔎 Closer look
  </summary>
  sqrt() function is needed to calculate the square root of a number<br>
  this function is available in the math module<br>
  so, we import the math module<br>
  But to be able to call sqrt(), we must use the module name as a prefix<br>
  sqrt() returns a float, that is why we are able to store the value in a variable called square_root<br>
</details>

#### Because the internal workings of library functions cannot be seen, they are called black boxes

## Random module - Generating Random Numbers

## c. randint()
Random numbers are useful for lots of different programming tasks.  
Computer games that let the player roll dice use random numbers to represent the values of the dice 
Programs that show cards being drawn from a shuffled deck use random numbers to represent the face values of the cards


Python provides several library functions for working with random numbers.  
These functions are stored in a module named random in the standard library. 

```python
import random
# To generate a random integer between 1 and 100
number = random.randint (1, 100)
print(number)
```

<details>
  <summary>
    🔎 Closer look
  </summary>
  The randint function is in the random module, so we import it<br>
  when calling randint<br>
  - we must prefix the module name before the function name using a dot<br>
  - we must pass two integer arguments, that tell the function to give an integer random number in the range of 1 through 100<br>
  randint returns an integer, that can be assigned to a variable called number<br>
  to display a random number, it is not necessary to assign the random number to a variable, it can be sent to the  print function<br>
  print(random.randint (1, 100))
</details>


<details>
  <summary>
    👉 Try this
  </summary>
  Generate a random integer between two values that the user enters<br>
  Hint: When user enters data using input function, that data is a string, we must convert it to integer
</details>


<details>
  <summary>
    👀 Answer
  </summary>

```python
num1 = int(input("Enter first number: "))<br>
num2 = int(input("Enter second number: "))<br>
rand = random.randint(num1, num2)<br>
print(rand)<br>
# Assume that the user will enter numeric values and that the first number will be smaller than the second one
```
</details>


## d. randrange()
The randrange function takes the same arguments as the range function.  
It returns a randomly selected value from a sequence of values. 

```python
number = random.randrange(10)
print(number)
# The function will randomly select a number from [0,1,2,3,4,5,6,7,8,9]
```

```python
number = random.randrange(5,10)
print(number)
# The function will randomly select a number from [5,6,7,8,9]
```

```python
number = random.randrange(0, 101, 10)
print(number)
# The function will select a number from [0, 10, 20, 30, 40, 50, 60, 70, 80, 90, 100]
```

<details>
  <summary>
    🚩 To remember
  </summary>
  randint and randrange return an integer
</details>


<details>
  <summary>
    👉 Try this
  </summary>
  Generate a random number between 1 and 13 and if it is 1, print Ace, 2 print Two.. , 3 print Three, so on, 11, print Jack, 12 print Queen and 13 print King
</details>


<details>
  <summary>
    👀 Answer
  </summary>
  rand = random.randrange(1, 14)<br>
  if rand == 1:<br>
  &ensp;print("Ace")<br>
  elif rand == 2:<br>
  &ensp;print("Two")<br>
  elif rand == 3:<br>
  &ensp;print("Three")<br>
  elif rand == 4:<br>
  &ensp;print("Four")<br>
  elif rand == 5:<br>
  &ensp;print("Five")<br>
  elif rand == 6:<br>
  &ensp;print("six")<br>
  elif rand == 7:<br>
  &ensp;print("Seven")<br>
  elif rand == 8:<br>
  &ensp;print("Eight")<br>
  elif rand == 9:<br>
  &ensp;print("Nine")<br>
  elif rand == 10:<br>
  &ensp;print("Ten")<br>
  elif rand == 11:<br>
  &ensp;print("Jack")<br>
  elif rand == 12:<br>
  &ensp;print("Queen")<br>
  elif rand == 13:<br>
  &ensp;print("King")<br>
</details>

## e. uniform() function
The uniform returns a random floating-point number between two specified floats

```python
number = random.uniform(1.0, 10.0)
print(number)
```

<details>
  <summary>
    👉 Try this
  </summary>
  Generate a random float between two values that the user enters<br>
  Hint: When user enters data using input function, that data is a string, we must convert it to float
</details>


<details>
  <summary>
    👀 Answer
  </summary>

```python
num1 = float(input("Enter first number: "))<br>
num2 = float(input("Enter second number: "))<br>
rand = random.uniform(num1, num2)<br>
print(rand)<br>
# Assume that the user will enter numeric values and that the first number will be smaller than the second one
```
</details>


# 5-16. User-defined functions
We can write our own functions that return values to the calling function

```python
def validate_gpa():
  gpa = input("Enter the GPA: ")
  gpa = float(gpa)
  if gpa >= 0.0 and gpa <= 4.0:
    return gpa
  else:
    print("Invalid GPA entered")

def main():
  correct_gpa = validate_gpa()
  print(correct_gpa)

main()
```

Because the function is returning a value, we can collect it in a variable for future printing or other mathematical calculations

```python
def get_values():
  name = input("Enter the student name: ")
  major = input("Enter the student major: ")
  return name, major

def main():
  student_name, student_major = get_values()
  print(student_name)
  print(student_major)

main()
```

Because the function is returning two value, we are collecting them in two variables  

<details>
  <summary>
    💡 Note
  </summary>
  When we get to Chapter 7: Lists and Tuples, we will collect all returned values in one variable and that would be a tuple
</details>
