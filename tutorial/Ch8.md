# 8-0. Intro to Strings

1. A string is a textual data in Python. According to Python anything between a single or double or triple quotes is a string.
```python
string1 = 'Hello'
string2 = " my dear"
string3 = ''' Watson'''
```
<details>
  <summary>
    💡 Remember:
  </summary>
  Triple quotes let us print paragraphs of data
</details>

2. So far we have seen string operations primarily with print() and input()

<details>
  <summary>
    💡 Remember:
  </summary>
  print is a void function<br>
  input is a value-returning function which accepts one string and returns one string
</details>

3. Strings are immutable, you cannot modify a string once you create it.

4. Strings are a type of sequence (just like lists or tuples). So, many concepts we have seen so far with sequences also work on Strings

# 8-1. Using Operators with Strings

## a. + or concatenation operator
```python
# concatenate multiple strings to create one string
string1 = "Hello"
string2 = "World"
new_string = string1 + string2
print(new_string)
```

<details>
  <summary>
    💡 Remember:
  </summary>
  Every variable you concatenate must be a string. So if it is an int or float or bool, convert it to string using str()
</details>


## b. * or repetition operator
```python
# Repeat a string 5 times
string = "tick tock "
new_string = string * 5
print(new_string)
```

<details>
  <summary>
    💡 Remember:
  </summary>
  The number must be an int, floats or strings need to be converted to int using int()
</details>


# 8-2. String Modification Methods

<details>
  <summary>
   💡 Remember 
  </summary>
  We cannot actually modify a string. Strings are immutable.<br>
  We can create a copy of the string.
</details>

## a. lower()
- This creates a all lowercase version of the string
- Numbers and special characters remain unchanged
```python
string = 'HeLLO343'
new_string = string.lower()
```

## b. upper()
- This creates a all uppercase version of the string
- Numbers and special characters remain unchanged
```python
string = 'hello'
new_string = string.upper()
```

## c. lstrip()
- Strips all the leading characters specified in ()
- If the () are empty, it will strip leading spaces
```python
# To strip all the leading *
string1 = '    hello     '
string2 = '****hello****'
new_string = string1.lstrip()
new_string = string2.lstrip('*')
```

## d. rstrip()
- Strips all the trailing characters specified in ()
- If the () are empty, it will strip trailing spaces
```python
# To strip all the trailing *
string1 = '    hello    '
string2 = '****hello****'
new_string = string1.rstrip()
new_string = string2.rstrip('*')
```

## e. strip()
- Strips all the leading and trailing characters specified in ()
- If the () are empty, it will strip leading and trailing spaces
```python
# To strip all the leading and trailing *
string1 = '    hello    '
string2 = '****hello****'
new_string = string1.strip()
new_string = string2.strip('*')
```

## f: @TODO: Check out these methods and write down what they do
- title()
- join()
- center()
- capitalize()
- casefold()

# 8-3. Indexing in Strings

- This is similar to that of lists
- Indexing is using an integer index to access elements
- In strings, each character is an element
- Index always starts at 0

```python
# Print the fifth character in this string
string = "The Hunger Games"
fifth_char = string[4]
```

<details>
  <summary>💡 Remember</summary>If you try to access an index that doesn't exist, Python will raise an exception
</details>

# 8-4. len() function

Returns the number of characters in a string

```python
string = "Facing the Giants"
num_of_characters = len(string)
print(num_of_characters)
```

<details>
  <summary>💡 Remember</summary>len always returns an integer
</details>

# 8-5. in and not in operators

## a. in operator
This is used to check if a substring is present in a string
```python
string = "My dear Watson"

if "Watson" in string:
  print("Substring exists")
```

## b. not in operator
This is used to check if a substring is NOT present in a string
```python
string = "My dear Watson"

if "Dear" not in string:
  print("Substring doesn't exist")
```

<details>
  <summary>💡 Remember</summary>This will be a case-sensitive search
</details>

# 8-6. String Slicing

## a. Using List slicing method
Just like lists we can slice strings

Syntax: <string_name>[\<start\>:\<stop\>:\<step\>]

```python
string = "ULM Rocks!"
slice = string[:3]

```
<details>
  <summary> 
    👉 Try this:
  </summary>

In the string given in the code below:
- the first 7 chars is CWID
- next 50 is name
- next 4 is major
- next 4 is gpa
Can you get all of data elements in a comma separated string?
It should output -  <code>4231560,Wes Kinney,COSC,4.00</code>
```python
string = "4231560                    Wes Kinney                    COSC4.00"
```
</details>

<details>
  <summary>
    👀 Answer: 
  </summary>

```python
cwid = string[:7] # To get the first 7 characters
name = string[7:57].strip() # Get 8th to 56th character, and remove the spaces
major = string[57:61]
gpa = string[61:]
joined_string = cwid + "," + name + "," + major + "," + gpa
print(joined_string)

# or, do all the above in one statement
# print(string[:7] + "," + string[7:57].strip() + "," + string[57:61] + "," + string[61:])
  ```
</details>


<details>
  <summary>💡 Remember</summary>If you try to access an index that doesn't exist, Python will raise an exception
</details>


## b. Using slice() method
```python
string = "ULM Rocks!"
s1 = slice(0,3)
slice = string[s1]
```


# 8-7. String Testing Methods

## a. isalnum()
Tests if a string is alpha-numeric only, without any special characters
```python
# If string has any special characters, test fails
string = "heLlo1230"
test = string.isalnum()
```

## b. isalpha()
Tests if a string is alphabetic only, without any numbers or special characters
```python
# If string has any special characters or numbers, test fails
string = "James Ellis"
test = string.isalpha()
```

## c. isdigit()
Tests if a string is numeric only, without any alphabets or special characters
```python
# If string not strictly numeric, test fails (even decimal points will cause test to fail)
string = "3185627894"
test = string.isdigit()
```

### d. islower()
Tests if a string is all lowercase, it ignores numbers and special characters
```python
# If the string has even one upper-case character, test fails
string = "hello12*"
test = string.islower()
```

### e. isspace()
Tests if a string is all blank spaces
```python
# If the string is not ALL spaces, test fails
string = "         "
test = string.isspace()
```

### f. isupper()
Tests if a string is all uppercase, it ignores numbers and special characters
```python
# If the string has even one lower-case character, test fails
string = "ULM"
test = string.isupper()
```

<details>
  <summary>💡 Note</summary>They all start with is
</details>

# 8-8. Searching and Replacing

## a. endswith(substring)
Checks if a string ends with a specified substring
```python
substring = "00"
string = "45678200"
search_test = string.endswith(substring)
```

## b. startswith(substring)
Checks if a string starts with a specified substring
```python
substring = "400"
string = "4000045"
search_test = string.startswith(substring)
```

## c. find(substring)
- Checks to see if a given substring (needle) is present in the string (haystack)
- If found, it will return the index of the FIRST occurence
- If not found, it will return -1


```python
substring = "8"
string = "4000045"
search_test = string.find(substring)
```

<details>
  <summary>⚠️ Important Note:</summary>find() method will always return an integer
</details>

## d. replace(old, new)
Creates a copy of the original string after replacing _all occurences_ of a specified substring with a new substring

```python
string = "Univ of Louisiana Monroe"
find = "Univ"
replace = "University"
new_string = string.replace(find, replace)
```

<details>
  <summary>💡 Note:</summary>This will be a case-sensitive search
</details>

# 8-9. Looping Over a String

Using a for loop we can go over each character of a string

```python
# print each digit
string = "123456789"

for ch in string:
  print(ch)
```

# 8-10. String splitting

## split() method
split() method uses a delimiter to break a string down into list elements  
If no delimiter is specified, a space character is used as a delimiter

```python
from suchi_pretty_print import suchi_print

# with space as a delimiter
string = "My name is James Watson"
string_to_list = string.split()
suchi_print(string_to_list)

# with comma as a delimiter
string = "James Watson,1008976,COSC,4.0,watson@ulm.edu"
string_to_list = string.split(',')

```

<details>
  <summary>💡 Remember</summary>split() method always returns a list
</details>