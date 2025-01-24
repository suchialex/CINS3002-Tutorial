# 9-1,2. Creating Dictionary

## 9-1. Create an empty dictionary

Syntax: <dictionary_name> = {} or <dictionary_name> = dict()
```python
student = {}
student = dict()  
```
<details>
  <summary>
    💡 Remember this for future
  </summary>
  In the above code, we created student as an object of the class dict
</details>

## 9-2. Creating a dictionary with values
- Dictionary keys can be of any datatype that is immutable
- Values can be of any datatype, including a dictionary
### a. Method 1:
```python
student = {"name": "Mary Kay",
            "cwid": "1007845",
            "major": "CINS",
            3 : 3,
            "gpa" : 4.0
          }
suchi_print(student)
```

### b. Method 2: Using {} and keys in []
```python
student = {}
student["name"] = "Mary Kay"
student["cwid"] = "1007845"
suchi_print(student)
```

### c. Method 3: dict method and list of tuples
```python
name_tuple = ("name", "Mary Kay")
cwid_tuple = ("cwid", "1007845")
major_tuple = ("major", "CINS")
student_list = [name_tuple, cwid_tuple, major_tuple]
           
suchi_print(student_list)

# student = dict(student_list)
# suchi_print(student)
```
<details>
  <summary>
    💡 Note
  </summary>
  Each tuple should have exactly two elements
</details>

# 9-3. Accessing Dictionary elements
Syntax: \<value\> = <dictionary_name>[\<key\>]
```python
student = {"name": "John Decker", 
            "cwid": "1007845"}
value = student["cwid"]
print(value)   
```
<details>
  <summary>
    💡 Note
  </summary>
  If the key is not found, Python raises an exception
</details>

## Three ways to do address this key error

### a. Exception Handling
```python
try:
  print(student["major"])
except:
  print("Key not found")
```

### b. Using in operator
```python
if "major" in student:
  print(student["major"])
else:
  print("Key not found")
```

### c. get() method
```python
major = student.get("major")
# print(major)
```

# 9-4. Modifying Dictionary Elements

## a. Modifying dictionary elements given the key
```python
student = {"name": "John Decker", 
            "cwid": "1007845"}
student["name"] = "Josh Decker"
student["major"] = "COSC"
suchi_print(student)
```

## b. Modifying dictionary elements given the value

For modifying elements using the value we must use a for loop

```python
student = {"name": "John Decker", 
            "cwid": "1007845"}

old_name = input("Whose name do you want to change? : ")
new_name = input("What do you want to change it to? : ")

# suchi_print(student)

for key, value in student.items():
  if value == old_name:
    student[key] = new_name
    
# suchi_print(student)
```
- We will see more such examples later on
  
<details>
  <summary>
    💡 Note:
  </summary>
  We will see more on items() method later on
    
</details>

# 9-5. len() Function

Returns the number of key:value pairs in a dictionary

```python
student = {"name": "Mary Kay", 
           "cwid": "1007845", 
           "major":"COSC", 
           "gpa": 4.0,
           "color":["purple", "red", "yellow"],
           "hobby" : ("badminton", "ping pong")
          }
print(len(student))
```

<details>
  <summary>
    💡 Note:
  </summary>
  len function will always return an int
</details>

# 9-6. Deleting Dictionary Elements

## a. Method 1 - using del statement
```python
student = {"name": "Suchi Rodda", "cwid": "1007845", "major": "COSC"}
suchi_print(student)
del student["major"]
# suchi_print(student)
```

## b. Method 2 - using pop() method
```python
student = {"name": "Suchi Rodda", "cwid": "1007845", "major": "COSC"}
student.pop('phone')
```
- Can we delete if the key doesn't exist?
```python
student = {"name": "Suchi Rodda", "cwid": "1007845", "major": "COSC"}
del student["phone"]
# student.pop('phone')
```

<details>
  <summary>
    💡 Note:
  </summary>
  Both del and pop() will raise an exception if the key is not found
</details>

# 9-6c. Using in Operator On Dictionary

We can use **in** operator to check if a key exists in a dictionary  
**Syntax**: if <key> in <dictionary_name>:  

```python
student = {"name": "Suchi Rodda", 
           "cwid": "1007845", 
           "major": "COSC"}

if "name" in student:
  print("Key exists")
else:
  print("Key Not Found")

# 9-7. Complex Dictionary

- Dictionary values can be str, int, float, bool, lists, tuples, dictionaries, and even nested dictionaries
- Dictionary keys can be any immutable datatype, including tuples

```python
student = {
  "age" : 29,
  "gpa" : 3.45,
  "name" : "John",
  "colors" : ["red", "black", "yellow"],
  "sports" : ("tennis", "badminton", "ping pong"),
  "favorites" : ["apple", "orange", "banana"],
  "courses" : {"fall": ["math 101", 'engl 101'],
               "winter" : ["math 201", 'engl 201'],
               "spring" : ["math 201", 'engl 201'],
               "summer" : ["math 201", 'engl 201'],
              }
          }
```

<details>
  <summary>
   🔍 Closer look 
  </summary>
  
  - student is a dictionary
  - student has seven key/value pairs
    - first key is a string age and value is an int 29
    - second key is a string gpa and value is a float 3.45
    - third key is a string name and value is a string John
    - fourth key is a string colors and value is a list with three elements
    - fifth key is a string sports and value is a tuple with three elements
    - sixth key is a string favorites and value is a list with three elements
    - seventh key is a string courses and value is a dictionary with four key/value pairs
      - first key is a string fall and its value is a list with two elements
      - second key is a string winter and its value is a list with two elements
      - third key is a string spring and its value is a list with two elements
      - fourth key is a string summer and its value is a list with two elements<br>    
</details>

## Some Examples
### Example 1: 
<details>
  <summary>
    Add blue to student's colors
  </summary>

  ```python
  student["colors"].append("blue")
  ```

<details>
  <summary>
   🔍 Closer look 
  </summary>
  
  - Students colors are in the key "colors"
  - But that element is a list
  - To add a new color to the existing list we use append() method
</details>

</details>



<details>
  <summary>
   👉 Try this: 9-7a 
  </summary>
  Add the color green at index 2 to the student's colors

<details>
  <summary>
   👀 Answer 
  </summary>

  ```python
  student["colors"].insert(2, "green")
  ```
</details>
</details>

### Example 2:
<details>
  <summary>
    Delete the color red from the student's colors
  </summary>

  ```python
  student["colors"].remove("red")
  ```
  But this will raise an exception if red is not in the student's colors, so check before you delete

  ```python
  if "red" in student["colors"]:
    student["colors"].remove("red")
  ```
</details>


### Example 3:
<details>
  <summary>
    Add a maymester term with acct 101 as a course
  </summary>
  
```python
student["courses"]["maymester"] = ["acct 101"]
```

<details>
  <summary>
   🔍 Closer look 
  </summary>
  
  - Students courses are in the key "courses"
  - But that element is a dictionary
  - To add a new course we must create a new key value pair
  - The key is a string maymester and the value is a list with one element acct 101     
</details>
</details>

### Example 4:
<details>
  <summary>
    Drop the math 101 in fall
  </summary>
  
```python
student["courses"]["fall"].remove("math 101")
```
</details>

<details>
  <summary>
   👉 Try this 
  </summary>
  
  Drop the course engl 201 from summer

<details>
  <summary>
   👀 Answer 
  </summary>

  ```python
  student["courses"]["summer"].remove("engl 201")
  ```
</details>
</details>


### Example 5:

<details>
<summary>
  Add a user entered course for winter
</summary>
  
```python
course = input("Enter the course to add: ")
student["courses"]["winter"].append(course)
```
</details>

<details>
  <summary>
   👉 Try this 
  </summary>
  Add a user entered course for spring<br>
  
  ```python
  course = input("Enter the course to add: ")
  ```

<details>
  <summary>
   👀 Answer 
  </summary>

  ```python
  student["courses"]["spring"].append(course)
  ```
</details>
</details>

### Example 6:

<details>
  <summary>
    Ask user for a term and a course and delete that course from that term
  </summary>

```python
term = input("Enter a term: (fall/winter/spring/summer) ")
if term in student["courses"]:
  course = input("Enter course to delete: ")
  if course in student["courses"][term]:
    student["courses"][term].remove(course)
  else:
    print("Student not enrolled in this course")
else:
  print("Student not enrolled for this term")
```
</details>


### Example 7:

<details>
<summary>
  Ask user for a term and a course and add that course to that term
</summary>

```python
term = input("Enter a term: (fall/winter/spring/summer) ")
course = input("Enter course to add: ")
if term in student["courses"]:
  if course not in student["courses"][term]:
    student["courses"][term].append(course)
  else:
    print("Student already enrolled in this course")
else:
  student["courses"][term] = course
```
</details>

# 9-8. Looping Through Dictionary

```python
student = {"name" : "John",
         "age" : 29,
         "gpa" : 3.45,
         "courses" : {"fall": ["math 101", 'engl 101'],
                      "winter" : ["math 201", 'engl 201'],
                      "spring" : ["math 201", 'engl 201'],
                      "summer" : ["math 201", 'engl 201'],
                      },
         "sports" : ("tennis", "badminton", "ping pong"),
         "colors" : ["red", "black", "yellow"],
         "favorites" : {"apple", "orange", "banana"}
         }

for key in student:
  print(f'{key} : {student[key]}')
```

<details>
  <summary>
    💡 Remember: In Lists
  </summary>
  When using a for loop on a lists, the loop variable stored the value
</details>

```python
import time

list = ["Mary Kay", "1007845", "CINS", 4.0]
for element in list:
  print(element)
  time.sleep(2)
```

<details>
  <summary>
    💡 Note: In Dictionaries
  </summary>
  When using a for loop on a dictionary, the loop variable stores the key
</details>

  
```python
import time

student = {"name": "Mary Kay",
               "cwid": "1007845",
               "major": "CINS",
               "gpa" : 4.0
             }
for element in student:
  print(element)
  time.sleep(2)
```

# 9-9. Dictionary Methods

## a. copy()
Creates a copy of the dictionary

```python
student = {"name": "Suchi Rodda", "cwid": "1007845", "major":"COSC", "gpa":4.5}
new_student = student.copy()
suchi_print(new_student)
```

## b. clear()
Deletes all the elements in a dictionary

```python
student.clear()
suchi_print(student)
```

## c. get()
Gets the value associated with specified key
```python
name = student.get("name")

```

## d. update()
Adds new key-value pair or modify existing value in a dictionary

```python
# using dictionary
new_dictionary = {"gpa":4.0, 
                  "email":"rodda@ulm.edu"}
student.update(new_dictionary)
suchi_print(student)

# using a list of tuples
list_of_tuples = [("gpa", 4.0), 
                  ("email",  "rodda@ulm.edu")
                 ]
suchi_print(student)
```

## e. items()
Returns all the dictionary's keys and associated values

```python
print(student.items())
```

## f. keys()
Returns all the dictionaries keys as a sequence
```python
k = student.keys()
# suchi_print(k)
```

## g. values()
Returns all the dictionaries values as a sequence
```python
v = student.values()
suchi_print(v)
```

## h. pop()
Returns value associated with specified key and removes that key-value pair from the dictionary
```python
popped = student.pop("name")
suchi_print(student)
# raises exception is key not present
```

## i. popitem()
Returns the last key-value pair and removes that key-value pair from the dictionary

```python
popped_item = student.popitem()
# print(popped_item)
print(student)
```

# 9-10, 9-11. Pickling and Unpickling Dictionaries

Serializing an object is the process of converting an object to a stream of bytes that can be saved to a file for later retrieval.  
In Python, object serialization is called **pickling**.  
We need to import the pickle module for pickling and unpickling

## 10. Pickling a dictionary
Must open file in wb mode - write in binary
  
```python
import pickle

student1 = {
  "name" : "John",
  "age" : 29,
  "gpa" : 3.45,
  "courses" : {"fall": ["math 101", 'engl 101'],
               "winter" : ["math 201", 'engl 201'],
               "spring" : ["math 201", 'engl 201'],
               "summer" : ["math 201", 'engl 201']
              },
  "sports" : ("tennis", "badminton", "ping pong"),
  "colors" : ["red", "black", "yellow"],
  "favorites" : ["apple", "orange", "banana"]
  }
  
with open("student.txt", "wb") as fp:
  pickle.dump(student, fp)
```

<details>
  <summary>
    💡 Note
  </summary>
  When you open a file that doesn't exist, in wb mode, Pyhton creates it
</details>


## 9-11. Unpickle a dictionary
Must open file in rb mode - read in binary

```python
with open("student.txt", "rb") as fp:
  student = pickle.load(fp)

suchi_print(student)
```

<details>
  <summary>
    💡 Note
  </summary>
  We can pickle and unpickle lists and tuples too
</details>

# 9-12. Sets

## Characteristcs:
- Sets store a collection of data
- Sets are unordered
- Sets are mutable
- Sets do not have duplicate values
  
## 1. Create an empty set

```python
my_set = set() 
print(my_set)
print(type(my_set))
```

<details>
  <summary>
    💡 Remember
  </summary>
  lists was []<br>
  tuple was (,)<br>
  dict was {}
</details>

## 2a. Creating a set with values

```python
colors = {"blue", "red", "yellow"}
suchi_print(colors)
```

## 2b. convert other iterables to a set
### a. list
```python
my_list = [25, 30, 25, 40]
my_set = set(my_list)
suchi_print(my_set)
```

### b. tuple
```python
my_tuple = (25, 30, 25, 40)
my_set = set(my_tuple)
suchi_print(my_set)
```

### c. dictionary
```python
my_dict = {1:25, 2:30, 3:25, 4:40, 5:25}
my_set = set(my_dict)
suchi_print(my_set)
```

### d. string
```python
my_string = "Hello"
my_set = set(my_string)
suchi_print(my_set)
```

## 3. len()
```python
my_set = {"blue", "red", "yellow"}
suchi_print(len(my_set))
```

## 4. modifying set elements

### a. add()
Adds element to a set
```python
my_set = {"blue", "red", "yellow"}
my_set.add("purple")
suchi_print(my_set)
```

### b. update()
Adds elelments of iterable to set
```python
my_set = {"blue", "red", "yellow"}

my_set.update({"green", "pink"})
# my_set.update([25,35, "pink"])
# my_set.update((25,30))
# my_set.update({1:25, 2:30, 3:25, 4:40, 5:25})
# my_set.update('hello')

suchi_print(my_set)
```

### c. remove()
Removes an element, raises an exception if not found
```python
my_set = {"blue", "red", "yellow"}
my_set.remove("green")
suchi_print(my_set)
```

### d. discard()
Removes an element, doesn't raise exception
```python
my_set = {"blue", "red", "yellow"}
my_set.discard("green")
suchi_print(my_set)
```

## 5. Loop through a set
```python
colors = {"blue", "red", "yellow"}
for val in colors:
  print(val)
```

## 6. Some set methods
### a. copy()
Creates a copy of our student
```python
colors = {"blue", "red", "yellow"}
new_colors = colors.copy()
print(new_colors)
```

### b. clear()
Removes all the elements of the set
```python
my_set = {"blue", "red", "yellow"}
my_set.clear()
print(my_set)
```

### c. pop()
Removes the first element and returns the first element
```python
my_set = {"blue", "red", "yellow"}
print(my_set.pop())
print(my_set)
```

## 7. Set Union
Returns a set that contains all the elements of both sets
```python
set1 = {"blue", "red", "yellow"}
set2 = {"purple", "red", "green"}
print(set1.union(set2))
print(set1 | set2) # Using operator
```

## 8. Set Intersection
Returns a set that contains only the elements found in both sets
```python
set1 = {"blue", "red", "yellow"}
set2 = {"purple", "red", "green"}
print(set1.intersection(set2))
print(set1 & set2) # Using operator
```

## 9. Set Difference
Returns a set that contains the elements that appear in the first set but do not appear in the second set
```python
set1 = {"blue", "red", "yellow"}
set2 = {"purple", "red", "green"}
diff1 = set1.difference(set2)
# diff1 = set1 - set2  # Using operator

diff2 = set2.difference(set1)
# diff2 = set2 - set1   # Using operator
 
```

## 10. Set Symmetric Difference
Returns a set that contains the elements that are not shared by the two sets
```python
set1 = {"blue", "red", "yellow"}
set2 = {"purple", "red", "green"}
print(set1.symmetric_difference(set2))
print(set2.symmetric_difference(set1))
print(set1 ^ set2) # Using operator
print(set2 ^ set1) # Using operator
```

## 11. Finding subset
set1 is subset of set2 if all the elements in set1 are included in set2
```python
student_courses = {"acct101","acct501"}
courses_offered = {"acct101","acct201","acct301","acct401","acct501"}
print(student_courses.issubset(courses_offered))
```

## 12. Finding superset
set1 is superset of set2 if all the elements in set2 are included in set1
```python
student_courses = {"acct601","acct401"}
courses_offered = {"acct101","acct201","acct301","acct401","acct501"}
print(courses_offered.issuperset(student_courses))
```

