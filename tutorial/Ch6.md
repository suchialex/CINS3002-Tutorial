# 6-1. Files
Files are permanent storage for data  
The data is available even after the program stops running

## a. Types of files

### Text files
A text file contains data that has been encoded as text  
Even if the file contains numbers, those numbers are stored in the file as a series of characters.  
Such files may be opened and viewed in a text editor such as Notepad. 

### Binary files
A binary file contains data that has not been converted to text  
The data that is stored in a binary file is intended only for a program to read, like Word or Excel  
Contents of a binary file cannot be viewed with a text editor.

<details>
  <summary>
    💡 Note:
  </summary>
  For the scope of Chapters 6, 7, 8 we will be working with text files
</details>


## b. File Access Methods
### Sequential access 
Data is accessed from the beginning of the file to the end of the file  
If you want to read a piece of data that is stored at the very end of the file, you have to read all of the data that comes before it  
Similar to the way cassette tape players work

### Direct access or random access 
You can jump directly to any piece of data in the file without reading the data that comes before it  
Similar to the way a CD player or an MP3 player works

💡 For this class, we will use sequential access files.


## c. File Processing Steps
1. Open file
2. Read from or write to file
3. Close file - if we don't close the file,  any new data will not be written to the file

# 6-2. Writing to file
Before we can write to a file, we must open it in **w** mode  
When we open a file in write mode it is called an output file

**Syntax**: <file_pointer> = open("\<file_name\>", "w")

```python
fp = open('data.txt','w')
fp = open('files/data.txt','w') # the slash might be different in different operating systems
fp.close()
```
<details>
  <summary>
    🔍 Closer look
  </summary>
  fp is a variable and is called file pointer or file object<br>
  open() - is a built-in Python function to open a file<br>
  open takes atleast one required argument, file name (along with full path<br>
  file name must be specified in single or double quotes<br>
  second argument - mode is optional<br>
  if no mode is specified, the file is opened in read mode<br>
  if you want to specify the write mode, you must use "w" inside single or double quotes
</details>

In write mode, if the file doesn't exist Python will create the file 

## a. The write() method
```python
fp = open('states.txt', 'w')
fp.write('Alabama')
fp.write('Alaska')
fp.close()
```

In write mode the read position starts at 0, meaning each time, the data will be overwritten

<details>
  <summary>
    👉 Try this: 6-2a
  </summary>
  Open a file named products.csv in write mode, name the file pointer outfile<br>
  To this file write two values like this<br><br>
  Apples<br>
  Oranges<br><br>
  Close the file
</details>

<details>
  <summary>
    👀 Answer
  </summary>
  
  ```python
  outfile = open("products.csv", "w")
  outfile.write("Apples")
  outfile.write("Oranges")
  outfile.close()
  ```
</details>

## b. Using newline characters (and tab characters)
```python
fp = open('states.txt', 'w')
fp.write('Alabama\tMontgomery\n')
fp.write('Alaska\tJuneau\n')
# or
# fp.write('Alabama\tMontgomery\nAlaska\tJuneau\n')
fp.close()
```
<details>
  <summary>
    💡 Remember
  </summary>
  \n - newline character<br>
  \t - tab character
</details>


## c. Concatenating strings and writing to file
```python
infile = open('states.txt', 'w')
more = "y"
while more != "n":
  state = input("Enter state: ")
  capital = input("Enter capital: ")
  string = state + '\t' + capital + '\n'
  infile.write(string)
  more = input("Do you want to enter more? (y/n): ")
infile.close()
```

<details>
  <summary>
    👉 Try this: 6-2c
  </summary>
  Open a file named states.csv in write mode, name the file pointer of<br>
  Using two input statements, ask user to enter a state and a capital 
  Write those two values like this<br><br>
  Alaska,Juneau<br>
  Close the file
</details>

<details>
  <summary>
    👀 Answer
  </summary>

  ```python
  of = open("states.csv", "w")
  state = input("Enter state: ")
  capital = input("Enter capital: ")
  string = state + ',' + capital + '\n'
  of.write(string)
  of.close()
  ```
</details>

We can only write string data to file  
So we have to convert other datatypes to strings before we write to the file

## d. Writing other datatypes
Using for loop to write numbers from 1 to 20
```python
file = open('numbers.txt', 'w')
for num in range(1, 21):
  file.write(num) # will give error
  # file.write(str(num)) # we must convert to string
file.close()
```

<details>
  <summary>
    👉 Try this: 6-2b
  </summary>
  To a file named scores.txt write 30 random floats between 50 and 100<br>⏩ Tutorial 5-15e for random number generation
</details>

<details>
  <summary>
    👀 Answer
  </summary>

  ```python
  import random
  f = open("scores.txt", "w")
  for i in range(30):
    score = random.uniform(50, 100)
    f.write(str(score) + '\n')
  f.close()
  ```
</details>

## e. Writing data in append mode
In append mode
- the file is created if it doesn't exist
- read position starts at the end of the file  
- new data will be appended to old data

**Syntax**: <file_pointer> = open("\<file_name\>", "a")

```python
infile = open('products.txt', 'a')
done = "n"
while done != "y":
  product = input("Enter product: ")
  price = input("Enter price: ")
  string = product + '\n' + price + '\n'
  infile.write(string)
  done = input("Are you done? (y/n): ")
infile.close()
```

<details>
  <summary>
    👉 Try this
  </summary>
  Until the user presses n<br>
  Using three input statements, ask user for student cwid, name, major and gpa
  To a file named students.txt write these values in four separate lines. Open the file in append mode<br>
  # Test your code with these four values<br>
  267898, John Doe, HIST, 3.5
</details>

<details>
  <summary>
    👀 Answer
  </summary>
  
  ```python
  f = open("students.txt", "a")
  more = "y"
  while more != "n":
    cwid = input("Student CWID: ")
    name = input("Student Name: ")
    major = input("Student Major: ")
    gpa = input("Student GPA: ")
    string= cwid + '\n' + name + '\n' + major + '\n' + gpa + '\n'
    f.write(string)
    more = input("Enter more? (y/n): ")
  f.close()
  ```
</details>

# 6-3. Reading from files

Before reading from a file, we must open the file in "r" mode  
If no mode is specified, the default is read mode  
**Syntax**: <file_pointer> = open("\<file_name\>", "r")


<details>
  <summary>
    🚩 To remember
  </summary>
  When opening file in read mode, make sure the file exists, otherwise it will give an error (or in correct terms - raise an exception)
</details>

```python
fp = open('data.txt')
# fp = open('data.txt','r')
```
<details>
  <summary>
    🔍 Closer look
  </summary>
  fp is a variable and is called file pointer<br>
  open() - is a built-in Python function to open a file<br>
  open takes atleast one required argument, file name along with the full path<br>
  file name must be specified in single or double quotes<br>
  second argument - mode is optional<br>
  if you want to specify the read mode, you must use "r" inside single or double quotes
</details>

When a file is opened in read mode
- it is called an input file
- the read position is at the beginning of the file

<details>
  <summary>
    👉 Try this: 6-3
  </summary>
  Open a file named products.csv in read mode, name the file pointer infile
</details>

<details>
  <summary>
    👀 Answer
  </summary>

  ```python
  infile = open("products.csv", "r")
  ```
</details>

## a. read() method - without arguments

```python
fp = open("data.txt", "r")
contents = fp.read()
print(contents)
fp.close()
```

read() will read the **entire** file contents into the memory.  
This is not good when we are reading large files.

## b. read() - with integer argument
We can use read() method to read only specified number of characters

```python
fp = open("data.txt", "r")
print(fp.tell()) # this will tell us the current location of the read position
contents = fp.read(5)
print(contents)
print(fp.tell()) # this will tell us the current location of the read position
contents = fp.read(5)
print(contents)
print(fp.tell())
fp.seek(0)  # this will move the read position to 0
contents = fp.read(5)
print(contents)
print(fp.tell())
fp.close()
```

<details>
  <summary>
    🚩 To remember
  </summary>
  tell() gives the location of the read position<br>
  seek() will move the read position to the desired location
</details>

## c. readline()
Reads one line and advances the read position to the beginning of the next line

```python
fp = open("data.txt", "r")
line1 = fp.readline()
print(line1)

line2 = fp.readline()
print(line2)

# why is there an additional blank line?
# that is because of the newline we added
# so we need to remove it
fp.close()
```

<details>
  <summary>
    👉 Try this: 6-3c
  </summary>
  Open the students.txt and print the first four lines separated by |<br>
  For example: <br>
  267898|John|HIST|3.5
</details>

<details>
  <summary>
    👀 Answer
  </summary>

  ```python
  infile = open("students.txt", "r")
  name = infile.readline().rstrip("\n")
  major = infile.readline().rstrip("\n")
  gpa = infile.readline().rstrip("\n")
  print(name, major, gpa, sep="|")
  infile.close()
  ```
</details>

## d. Using for loop
For loop will read each line in the file until there are no more lines

```python
fp = open("data.txt", "r")
for line in fp:
  print(line.rstrip("\n"))
fp.close()
```

<details>
  <summary>
    🔍 Closer look
  </summary>
  When we use a for loop over a file pointer, the loop variable stores each line<br>
</details>


To make for loop read every other line (instead of every line) we can sneak in a readline()

```python
fp = open("data.txt", "r")
for line in fp:
  print(line.rstrip("\n"))
  fp.readline() # moves the pointer to the next line
fp.close()
```

<details>
  <summary>
    👉 Try this: 6-3d
  </summary>
  Using for loop print just the names and majors of the students in students.txt
</details>

<details>
  <summary>
   👀 Answer 
  </summary>
  
  ```python
  fp = open("data.txt", "r")
  for line in fp:
    print(line.rstrip("\n")) # print the first line
    fp.readline() # skip the second line
    print(fp.readline().rstrip("\n")) # print the third line
  fp.close()
  ```
</details>

## e. readlines() method
This method reads file contents into a list  
We won't go over this method for this class

```python
fp = open("data.txt", "r")
data_list = fp.readlines()
print(data_list)
fp.close()
```

# 6-5. Processing Records
A record is a complete set of data about an item, and a field is an individual piece of data within a record.  
For example:  

267898  
John Doe  
HIST  
3.5  

All four lines together is a student record, and each line is called a field

## a. Adding data to a record
If we want to add another record, we have to add four lines with a newline after each line  

```python
f = open("students.txt", "a")
cwid = input("Student CWID: ")
name = input("Student Name: ")
major = input("Student Major: ")
gpa = input("Student GPA: ")
f.write(name + '\n' + major + '\n' + gpa + '\n')
f.close()  
```

<details>
  <summary>
    👉 Try this: 6-5a
  </summary>
  In a while loop keep adding student records in the above format, until user doesn't want to add any more. Choose your loop variable and exit condition for the while loop
</details>

<details>
  <summary>
    👀 Answer:
  </summary>

  ```python
  f = open("students.txt", "a")
  done = "n"
  while done != "n":
    cwid = input("Student CWID: ")
    name = input("Student Name: ")
    major = input("Student Major: ")
    gpa = input("Student GPA: ")
    f.write(name + '\n' + major + '\n' + gpa + '\n')
    done = input("Enter more? (y/n): ")
  f.close()  
  ```  
</details>


## b. Looking up
If we want to search the student record for a given cwid, we must check every fourth line and match it with the user entered cwid  
We can use a for loop to go over the lines in the file  
But for loop goes over every line, so we must skip three lines

```python
user_input = input("Enter CWID to lookup: ")
found = False # Let's assume we won't find the student in the file
f = open("students.txt", 'r')
for each_line in f:
  stu_id = each_line
  name = f.readline().rstrip('\n') # we read the next line to get the name and remove the newline character
  major = f.readline().rstrip('\n') # we read the next line to get the major and remove the newline character
  gpa = f.readline().rstrip('\n') # we read the next line to get the gpa and remove the newline character
  if stu_id.rstrip("\n") == user_input:
    print("Name:",name)
    print("Major:", major)
    print("GPA:", gpa)
    found = True
    break # we found what we are looking for, so stop reading the file

# outside the for loop
f.close()
if found == False:
  print("Student Not Found")
```

<details>
  <summary>
    🔍 Closer look
  </summary>
  We open the file in read mode because we are just looking up data<br>
  When we use a for loop over a file pointer, the loop variable stores each line<br>
  when the for loop starts, the first line has the cwid so we strip newline character and store in cwid variable<br>
  since we know the next line is the name, we use the readline() method to get that value and strip the newline character from it<br>
  the next line is the major, we use the readline() method to get that value and strip the newline character from it<br>
  the next line is the gpa, we use the readline() method to get that value and strip the newline character from it<br>
  we check if the cwid from the file matches the user entered cwid<br>
  if it matches, we print the name, major and gpa<br>
  break statement stops the for loop from executing any further<br>
  if match is not found, the loop continues to execute<br>
  and since we have already read the gpa, the next line will be stored in the loop variable (which is the cwid)<br>
  and the process repeats until a break statement is encountered or all the lines in the file are read
</details>

## c. Displaying
To display all the data in a tabular format
```python
f = open("students.txt", 'r')
for each_line in f:
  stu_id = each_line.rstrip("\n")
  name = f.readline().rstrip('\n') # we read the next line to get the name
  major = f.readline().rstrip('\n') # we read the next line to get the major
  gpa = f.readline().rstrip('\n') # we read the next line to get the gpa
  print(f'{stu_id : ^8} | {name: <20} | {major: ^6} | {gpa: >5} |')
  
f.close()
```

## d. Modifying
Modifying any data in a record involves both reading from and writing to the file  
Since we don't have a file open mode to do both, we read from one file and write to another file
For example, if you want to modify the name of a student  
First you open the students file in a read mode  
Open another temporary file in write mode  
Ask the user to give the CWID of the student whose name needs to be modified   
Using the for loop, we will try to find that CWID in the first record,  
If that CWID is Not found, we write the whole record to a new file without making any changes  
If the cwid is found, then we ask the user to provide the new name  
Now we will write the old cwid, new name, old major and old gpa to the new file  
Outside the for loop, close both the input file and output file  
Using the os module, delete the students file and rename the temporary file to students file
```python
import os
user_input = input("Enter student ID: ")

infile = open("students.txt", 'r')
outfile = open("temp.txt", "w")
for stu_id in infile:
  name = f.readline()
  major = f.readline()
  gpa = f.readline()
  if stu_id.rstrip('\n') != user_input:
    outfile.write(stu_id + name + major + gpa)
  else:
    new_name = input("Enter new name: ")
    outfile.write(stu_id + new_name + "\n" + major + gpa)
infile.close()
outfile.close()

os.remove("students.txt")
os.rename("temp.txt", "students.txt")
```

## e. Deleting
To delete a student (4 lines from the file)
Deleting a record involves both reading from and writing to the file  
Since we don't have a file open mode to do both, we read from one file and write to another file
First you open the students file in a read mode  
Open another temporary file in write mode  
Ask the user to give the CWID of the student who needs to be deleted   
Using the for loop, we will try to find that CWID in the first record,  
If that CWID is Not found, we write the whole record to a new file  
If the cwid is found, then skip writing that entire record to the new file  
Outside the for loop, close both the input file and output file  
Using the os module, delete the students file and rename the temporary file to students file
```python
import os
user_input = input("Enter Student ID to delete: ")

infile = open("students.txt", 'r')
outfile = open("temp.txt", "w")
for stu_id in f:
  if stu_id.rstrip('\n') != user_input:
    outfile.write(stu_id + f.readline() + f.readline() + f.readline())
infile.close()
outfile.close()

os.remove("students.txt")
os.rename("temp.txt", "students.txt")
```

# 6-6. Exceptions
An exception is an error that occurs while a program is running  
In most cases, an exception causes a program to abruptly halt  
For example:


```python
def main():
  cookies = int(input('Enter number of cookies: '))
  people = int(input('Enter number of people: '))
  cookies_per_person = cookies/people
  
main()
```

<details>
  <summary>
    🔎 Closer look:
  </summary>
  The above code is syntactically and semantically correct<br>
  When you execute it and enter, say 10 cookies and 4 people<br>
  The program output is 2.5<br>
  But if you enter 10 cookies and 0 people<br>
  Then the program abruptly halts with mesage called "traceback" specifying that it is a "ZeroDivisionError"<br>
  Such errors happen only at run-time and are called Exceptions<br>
  There are many different types of exceptions<br>
  For example instead of a numeric value enter an alphabetic value for cookies or peopl<br>
  That causes a "ValueError" exception because we just tried to convert a string to int
</details>

A good programmer must prevent exceptions from being raised by careful coding.  
In the above program to prevent ZeroDivisionError, we can place an if statement.


```python
def main():
  cookies = int(input('Enter number of cookies: '))
  people = int(input('Enter number of people: '))
  if people > 0:
    cookies_per_person = cookies/people
  else:
    print("Invalid value for people, must be more than 0")

main()
```

But some exceptions cannot be avoided regardless of how carefully we write our program  
For example we cannot avoid the ValueError  
Python allows us to write code that responds to exceptions when they are raised  
Such code is called an exception handler and is written with the **try/except** statement  

There are several ways to write a try/except statement, but the following general format shows the simplest variation

## a. try/except statement

```python
try:
  # statement
  # statement
  except <Exception_Name>:
  # statement
```

<details>
  <summary>
    🔎 Closer look:
  </summary>
  First, the keyword try appears, followed by a colon<br>
  Next, a code block appears called the try suite<br>
  The try suite is one or more statements that can potentially raise an exception<br>
  After the try suite, an except clause appears<br>
  The except clause begins with the keyword except, optionally followed by the name of an exception, and ending with a colon<br>
  Beginning on the next line is a block of statements that is called a handler<br>
  When the try/except statement executes, the statements in the try suite begin to execute<br>
  The following describes what happens next:<br><br>

  If a statement in the try suite raises an exception that is specified by the ExceptionName in an except clause, then the handler that immediately follows the except clause executes. Then, the program resumes execution with the statement immediately following the try/except statement<br><br>

  If a statement in the try suite raises an exception that is not specified by the ExceptionName in an except clause, then the program will halt with a traceback error message<br><br>

  If the statements in the try suite execute without raising an exception, then any except clauses and handlers in the statement are skipped, and the program resumes execution with the statement immediately following the try/except statement
</details>

```python
try:
  fp = open('suchi.txt', 'r') # can potentially raise exception because this file doesn't exist, so place it in the try suite
  contents = fp.read()
  print(contents)
  fp.close()
except FileNotFoundError: # this handler handles the case when the file doesn't exist
  print("File doesn't exist")

```

## b. Handling Multiple Exceptions

```python
def main():
  try: # the three statements below can potentially raise exception(s), so place them in the try suite
    cookies = int(input('Enter number of cookies: '))
    people = int(input('Enter number of people: '))
    cookies_per_person = cookies/people
    print(f"Each person gets {cookies_per_person} cookies")
  except ZeroDivisionError: # this handler handles the case when people = 0
    print("Invalid value for people, cannot be 0")
  except ValueError: # this handler handles the case when cookies or people is not numeric
    print("Enter valid numeric value for cookies and people")

  # This statement executes whether or not an exception is raised
  print(f"Done with everything")

main()
```

<details>
  <summary>
    🚩 To remember:
  </summary>
  A try/except statement gracefully responds to exceptions
</details>

## c. Using One except Clause to Catch All Exceptions

```python
def main():
  try:
    cookies = int(input('Enter number of cookies: '))
    people = int(input('Enter number of people: '))
    cookies_per_person = cookies/people
    print(f"Each person gets {cookies_per_person} cookies")
  except: # generic handler
    print("An error occured")

main()
```

## d. Displaying an Exception’s Default Error Message

If you want to have just one except clause to catch all the exceptions that are raised in a try suite, you can specify Exception as the type

```python
def main():
  try:
    cookies = int(input('Enter number of cookies: '))
    people = int(input('Enter number of people: '))
    cookies_per_person = cookies/people
    print(f"Each person gets {cookies_per_person} cookies")
  except Exception as err: # storing the exception info in a variable called err
    print("An error occured", err)

main()
```

## e. The else clause

The try/except statement may have an optional else clause, which appears after all the except clauses. Here is the general format of a try/except statement with an else clause:

The block of statements that appears after the else clause is known as the else suite. The statements in the else suite are executed after the statements in the try suite, only if no exceptions were raised. If an exception is raised, the else suite is skipped

```python
try:
    statement
    statement
    etc.
 except ExceptionName:
    statement
    statement
    etc.
 else:
    statement
    statement
    etc.
```


```python
def main():
  try:
    cookies = int(input('Enter number of cookies: '))
    people = int(input('Enter number of people: '))
    cookies_per_person = cookies/people
  except Exception as err: # storing the exception info in a variable called err
    print("An error occured", err)
  else:
    print(f"Each person gets {cookies_per_person} cookies")

main()
```

## f. The finally Clause
The try/except statement may have an optional finally clause, which must appear after all the except clauses. Here is the general format of a try/except statement with a finally clause:

```python
try:
    statement
    statement
    etc.
except ExceptionName:
  statement
  statement
  etc.
finally:
  statement
  statement
  etc.
```

The block of statements that appears after the finally clause is known as the finally suite. The statements in the finally suite are always executed after the try suite has executed, and after any exception handlers have executed. The statements in the finally suite execute whether an exception occurs or not. The purpose of the finally suite is to perform cleanup operations, such as closing files or other resources. Any code that is written in the finally suite will always execute, even if the try suite raises an exception.


```python
try:
  fp = open('suchi.txt', 'r')
except Exception as err: # executes only if exception is raised
  print(err)
else: # executes only if no exception is raised
  contents = fp.read()
  print(contents)
  fp.close()
finally: # executes whether or not exception is raised
  print("Done with everything")
```