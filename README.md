# The Pythonic Way


***

# SLICES

### What is a slice?
A slice is an operator we can use on a collection data type:
- String
- List
- Tuple

It'll create a new tuple, list, or string as the sliced version.
It creates a new object that contains the result of the slice.

slice = [start : stop : step]
```
lst = [1,2,3,4,5]
new_lst = lst[0:2] 
return new_list  # [1,2]
```
- Starting (inclusively) at the first indexed number.
- Ending (exclusively) at the second indexed number.
- Slicing up or down the collection based on the step.

The only parameter that is actually required is the "stop" parameter.
If the first and last parameters are empty, it will default: lst[0 : STOP : 1]
    - To start at the first index and only step up by 1. 
```
lst = [1,2,3,4,5]
new_lst = lst[:]  # This will simply return the list.
return new_list  # [1,2,3,4,5]
```

- Just including a start value (input an example here)

- [::2]

  
You can slice positively, and negatively. 

***

# NEGATIVE NUMBERS IN COLLECTION DATA TYPES

...

***

lst = ["a", "b", "c", "d"]
new_lst = lst[::-1] 
return new_list  # ["d", "c", "b", "a"]
This will return the list backwards, since we are slicing negatively. 




# STRINGS

### What is a string?

A string *(str)* is a data type represents a sequence of characters in Python. They start with
quotations: ("") , (''), ("""), or (''')

The following are examples of valid strings: 
"hello" || "2.0" || 'str' || \"""False\""" || \'''true\''' || "Wow the moon is so bright tonight!"

### Escape Characters
**The New Line Character**: <sub>\n</sub> is an invisible character that tells the computer to move the cursor to the next line in the console.

*<sub>Invisible meaning, the computer ignores it besides it function to move the cursor to the next line.</sub>*

For Example:
```
print("hello\nworld\n!")

    returns: hello
             world
             !
```

**Backslash** ( \\ )
Backslash: used to escape itself or other characters
```
Example of \\ escape character
```

**Single Quotes** ( \' )
Single Quotes: used to represent a single quotes.
```
Example of \' escape character
```

**Double Quotes** ( \" )
Double quote (used to represent a double quote)
```
pass
```

**Tab** ( \t )
Tab: used as a tab in a string
```
Pass
```

**Carriage Return** ( \r	)
Carriage return: (used to return to the beginning of the line)
```
pass
```

**Backspace** ( \b	)
Backspace: (used to move the cursor one position backward)
```
pass
```

You can use these escape characters in Python strings to represent special characters or characters that cannot be directly included in the string. For example, "\n" represents a newline character, and "\t" represents a tab character.

There are several other escape characters such as:
- \f
- \v
- \ooo
- \xhh
- \uhhhh
- \uhhhhhhhh
I didn't write them all here because they are less used. However, I want to help educate as much as I can so knowing they exist is probably good. If you are so inclined, feel free to look them up.


### String Methods

### upper() lower() title() capitalize()
```
name = "Kam"
print(name.upper())      # KAM
print(name.lower())      # kam
print(name.capitalize()) # Kam
print(name.title())      # Kam

# The difference between .capitalize() and .title() methods in Python is that they are both used to capitalize strings, but they do so in different ways.
# The title() method capitalizes the first letter of every word in the string.
# The capitalize() method only capitalizes the first letter of the first word in the string.

str = "The moon is beautiful tonight!"
print(str.capitalize())  # The moon is beautiful tonight!
print(str.title())       # The Moon Is Beautiful Tonight!
```


### .split()
.split() separates your string into an array using a **delimiter** to separate the words.

    <sub> - A delimiter is the character that tells you how to separate the string, (",") , ("."), (" ")</sub>
    <sub> - when you put nothing, it defaults to spaces. (" ")</sub>

**.split() Parameter Values**
separator:	        (Optional.) Specifies the separator to use when splitting the string. By default any whitespace is a separator
maxsplit:	        (Optional.) Specifies how many splits to do. Default value is -1, which is "all occurrences"
<sub>When maxsplit is specified, the list will contain the specified number of elements plus one.</sub>

```
sentence = "The International Space Station is in dire need!"

lst = sentence.split()
print(lst) # ["The", "International", "Space", "Station", "is", "in", "dire", "need!"]

# by default, since no second, optional, parameter was added, it defaulted to the delimiter of a " " (space)

                                        ----------
                                        
sentence = "Hello, this is captain Berk of the ISS, we have a grave status report."
lst = sentence.split(", ")
print(lst) # ["Hello", "this is captain Berk of the ISS", "we have a grave status report."]

# in this example the original sentence is broken into an array based on the separator parameter we specified above. In this case: (", ")

                                        ----------
                                        
sentence = "Moments after the ISS emergency broadcast. Looking up, you can see that the moon has been shattered and is now falling towards the Earth. Tweet #alieninvasion, #resistthem, or #moonshattering to spread awareness."
lst = sentence.split("#", 1)
print(lst) # ['Moments after the ISS emergency broadcast. Looking up, you can see that the moon has been shattered and is now falling towards the Earth. Tweet ', 'alieninvasion, #resistthem, or #moonshattering to spread awareness.']

# in this final example, the original sentence will be split by the (#) marking, but it will only be split by the second parameter, maxsplit, times. Which in this case is 1 time.
```

### .replace()
.replace() method replaces a specified phrase with another specified phrase.
- It replaces all of the characters in a current string with whatever string you specify.
- Then it will return a NEW string with all of the replaced characters.
(string.replace(oldvalue, newvalue, count))


**.split() Parameter Values**
old value:	        (Required.) The string to search for
new value:	        (Required.) The string to replace the old value with
count:	            (Optional.) A number specifying how many occurrences of the old value you want to replace. Default is all occurrences
<sub>All occurrences of the specified phrase will be replaced, if nothing else is specified.</sub>

```
s = "A,B,C,D"
s2 = s.replace("," , "|") # will return "A|B|C|D"
# s.replace() doesn't change the original variable. Instead it creates a new variable. So you might have trouble when using .replace() without assigning the returned value to a new variable.
```


```
.join() # used to build a new string from an iterable item (set, dictionary, list)
lst = ["d","a", "n"]
lst_string = "".join(lst) #takes all the items in the iterable together into the variable.
lst.string = "-".join(lst) # returns "d-a-n"
lst.string = "|".join(lst) # returns "d|a|n"
```


### F-Strings

Purpose: to help with the cumbersome nature of concatenation.
Concatenation is usually like: 
```
name = "Dr. Potsu"
mission = "To deliver human embyros in-vitro to the seven standing human planetary civilizations making sure all goes smoothly."
date = xx/xx/xxxx
concat = "Hey control. This is " + name + "and my objective is " + mission + "by " + date + ". Out."
f_string = f"Hey control. This is {name} and my objective is {mission} by {date}. Out."
```
As you can see above, concatenating is a little difficult and complicated to type and I find it more time consuming.
Luckily, Python and many other languages have a way around this:
*f-strings*
F-strings can be utilized like: 
```
name = "Dr. Potsu"
mission = "To deliver human embyros in-vitro to the seven standing human planetary civilizations making sure all goes smoothly."
date = xx/xx/xxxx
f_string = f"Hey control. This is {name} and my objective is {mission} by {date}. Out."
```
I think you can decided for yourself which one is a little faster or more effecient for your work flow.

# F-Strings: It's important to note
- The {} that we use to input variables. There are many other things we can put in there.
```
about_me = "hi! my name is Potsu and I am {50 - 20} years old.
# will return: "hi! my name is Potsu and I am 30 years old.
```
Essentially: anything inside the {} will be computed as normal and added as part of the string.

**You are a human on Earth who is receiving intel from Potsu about the aliens.**

# String multiplication
# multiple strings
name = input("name: ")
print(name * 5)

# also possible:
print("name " * 5) # will return "name name name name name "

# Multi-line strings
# multi-line strings are exactly the same as multi-line comments
# the difference is that you assign multi-line strings to a variable.

string = """There is some stuff here
            on multiple
            lines"""

strings = '''There is some stuff here
            on multiple
            lines
'''

# ESCAPE CHARACTERS
# Lets say I wanted to have an apostrophe ('s)
# Normally you'd have to be careful with the quotations you use
# If you use single quotes ('') the computer would assume you were closing the quotations.
# That's why this works below: We encase the quotes in double quotes.
string2 = f"{name}'s" # this is valid because

# However, let's assume for a second we couldn't do this.
# There's a way around this:
# You can use an escape character to avoid this issue.
string2 = f'{name}\s'
# The \ escapes the next character so that the computer ignores it's functionality if it has any.



s = "algoexpert"
contains = "a" in s
print(contains) #True

# We can convert strings to numbers but the string has to be solely numbers
s = "nineteen" # Would not work
s = "19"
q = int(s)

# however, we can check if a string is a digit with the isdigit() method.
s = "19"
is_digit = s.isdigit() #returns True

# Remember the string has to be an INTEGER. A floating point number would return False.
s = "19.6"
is_digit = s.isdigit() #returns False

# We can also check this on inputs
num = input("Integer: ")
if num.isdigit():
    print("It's a integer!")
    num = int(num)
    print(num + 10)
else:
    print("This is not an integer.")


greeting = "Hello " + name
print(greeting)
print(len(greeting))

if name in greeting:
    print("The name is contained in the greeting!")

print(f"The first character of the name is {name[0]}")


# Tuples

### What is a tuple?
Pronounced Tuple *(Cup-il)*

A tuple is a collection data type that stores a collection of elements like a list.
- A tuple is any element inside of a parentheses.
- Tuples are Immutable
```
t = (1,2,3,4)
t[2] = 10    # raises an exception because tuples cannot be changed.
t.append(10) # also raises an exception because tuples are immutable.
```

- All items are accessible using indices
```
t = (1,2,3,4)
print(t[0]) # prints 1
print([-1]) # prints 4
```

- Valid Tuple Examples:
t1 = (4, 4, 5, (3,2), True, [])
- Nested Tuples is possible


- Combining Tuples
t1 = (1, 2)
t2 = (3, 4)
combined = t1 + t2  # prints(1, 2, 3, 4)


- Multiplying Tuples
t1 = (1, 2)
multiplied = t1 * 2
print(multiplied)   # prints (1, 2, 1, 2)


- Creating Tuples
x = 1, 2, 3, 4 # A valid tuple by default
print(x)  # returns (1, 2, 3, 4)
- You don't actually need the parentheses when you define tuples.

- One Element Tuples
t1 = (1)
This won't work. It will just be an int.
If you want to make a one item tuple, you need to do this...
t1 = (1, )

- Changing a Tuple. | You can't change a Tuple but you can make a new one.
t1 = (1, 2, 3)
t2 = (t1[0], 4, t1[2])

# LISTS

### What is a list?

A list is a Data Structure. A data structure that stores a collection of data in sequential order.

Lists can contain almost any other data type. Numbers. Strings. Booleans. Even other lists.

EXAMPLES OF LISTS:
- [True, True [False, False]]
- [1, 2, 3, 4, 5.0, 43.2, "Help!"]

Lists are 0 - indexed. What does this mean?
- Let's say we have a List called "planets_on_route_to_our_destination"

planets_on_route_to_our_destination["Jupiter", "Planet X", "hu123bfo", "Cool Planet 77"]

| Planet    | Index |
| -------- | ------- |
| Jupiter  | 0   |
| Planet X | 1     |
| hu123bfo    | 2   |
| Cool Planet 77    | 3   |


lst = [1,2,3,4,5]
print(lst[4/2]) # will return print(lst[2])


NEGATIVE INDEXING
| Planet    | Index |
| -------- | ------- |
| Jupiter  | -4   |
| Planet X | -3     |
| hu123bfo    | -2   |
| Cool Planet 77    | -1   |



- You can use + on lists

YES: list_one += list_two
NO: list_one = [5,4,7]
    list_one += 6
    - If we want to add a single element to a list, we need to do something like this: 
        lst = [1,2,3,4]
        lst += [5]
        # lst will be: [1,2,3,4,5]

YES:
    in_my_garden = ["tomatoes", "strawberries", "carrots", "potatoes"]
    new_in_my_garden = in_my_garden + ["apples", "lemons", "garlic", "corn"]
    # will become: ["tomatoes", "strawberries", "carrots", "potatoes", "apples", "lemons", "garlic", "corn"]


RE-ASSIGNING INDEXES
```
friends = ["Tom", "Matt", Erin", "Danny", "Kurt"]
friends[0] = "Juan"
# this will change "Tom" -> "Juan"
# ["Juan", "Matt", Erin", "Danny", "Kurt"]

we can also do this with negative indexes
friends[-4] = "Chip"
# this will change "Matt" -> "Chip"
# ["Juan", "Chip", Erin", "Danny", "Kurt"]

```

TWO DIMENSIONAL LISTS:

We will often find that a two-dimensional list is a very good structure for representing grids such as games like tic-tac-toe.

#A 2d list with three lists in each of the indices. 
tic_tac_toe =   [
                    ["X","O","X"], 
                    ["O","X","O"], 
                    ["O","O","X"]
                ]

ADD TO A TWO-DIMENSIONAL LIST

heights = [["Jenny", 61], ["Alexus", 70], ["Sam", 67], ["Grace", 64]]

heights += [["Vik", 68]]

ages = [["Aaron", 15], ["Dhruti", 16]]

dhruti_age = ages[1][1] 
print(dhruti_age) # 16



### List Methods:

- append()
          Adds an item to end of the list.
- remove()
          The .remove() method removes an item from a list by passing in the value of the item to be removed as an argument.
```
customer_data = [["Ainsley", "Small", True], ["Ben", "Large", False], ["Chani", "Medium", True], ["Depak", "Medium", False]]

print(customer_data)

customer_data[2][-1] = False

customer_data[1].remove(False)
#[["Ainsley", "Small", True], ["Ben", "Large"], ["Chani", "Medium", True], ["Depak", "Medium", False]]
```


# For Loops
names = ["Dan", "Paul", "Andrew"]
for name in names:
    print(f"Name in list: {name}")


for i in range(1, 10, 2):
    print(f"i = {i}")



range()
len(lst) is better
if an object is an ITERABLE object we can:
iterable = "hello" | ["h", "e", "l", "l", "o"] | etc...
for element in iterable:
    print(element)

for i, element in enumerate(lst):
#has access to the index of the element and the element itself.

ITERATE THROUGH TUPLES
tup = (1,2,3,4, "hello", "tim", True)
for i in range (len(tup)):
    element = tup[i]
    print(element)

for i, element in enumerate(tup):
    print(i, element)

for element in tup:
    print(element)

STRINGS
s = "my string"

for i in range(len(s)):
    print(s[i])

for i in range(0, len(s), 2)
prints every other char

for num in lst:
    if num == 4:
        break # stops the for loop
    print(num)

for num in lst:
    if num == 4:
        continue # skips the current iteration but continues the loop
    print(num)

pass keyword: doesn't do anything. It's a placeholder we can put somewhere that we don't know what to code yet.
if i == 0:
    pass
else:
    print("something")


nested for loops
for i in range(10):
    for j in range(10):
        print(j)

        j will run each iteration of i 
        so j will run 10 times for each one iteration of i

for i in range(10):
    for j in range(10):
        for w in range(2):
            print(i,j,w)
            prints: 
            0 0 0
            0 0 1
            0 1 0
            0 1 1
            0 2 0
            0 2 1
            0 3 0
            0 3 1
            0 4 0
            0 4 1
            0 5 0
            0 5 1
            0 6 0
            0 6 1
            0 7 0
            0 7 1
            0 8 0
            0 8 1
            0 9 0
            0 9 1
            1 0 0
            1 0 1
            1 1 0
            1 1 1
            1 2 0
            1 2 1
            1 3 0
            1 3 1
            1 4 0
            1 4 1
            1 5 0
            1 5 1
            1 6 0
            1 6 1
            1 7 0
            1 7 1
            1 8 0
            1 8 1
            1 9 0
            1 9 1
            2 0 0
            2 0 1
            2 1 0
            2 1 1
            2 2 0
            2 2 1
            2 3 0
            2 3 1
            2 4 0
            2 4 1
            2 5 0
            2 5 1
            2 6 0
            2 6 1
            2 7 0
            2 7 1
            2 8 0
            2 8 1
            2 9 0
            2 9 1
            3 0 0
            3 0 1
            3 1 0
            3 1 1
            3 2 0
            3 2 1
            3 3 0
            3 3 1
            3 4 0
            3 4 1
            3 5 0
            3 5 1
            3 6 0
            3 6 1
            3 7 0
            3 7 1
            3 8 0
            3 8 1
            3 9 0
            3 9 1
            4 0 0

### Exmaple of nested for loops
```
# Use nested for loops to iterate through the provided list, which contains other lists, and print the respective
# sums of the inner lists, each on a separate line.

lst = [[2, 3, 4], [-2, -4, 0], [1, 2], [1, 1, 1, 5, 6], [0, 9, 8, 7]]

# Write your code here.
for i in range(len(lst)):
    interior_lst = lst[i]
    sum = 0
    for j in range(len(interior_lst)):
        sum += interior_lst[j]
    print(sum)


"""
OUTPUT: 
9
-6
3
14
24
"""
```

The below example will 
lst = [[1,2], [3,4], [5,6], [7,8]]

for i in range(len(lst)):
    interior_list = lst[i]
    for j in range(len(interior_lst)):
        print(interiot_lst[j])
    
st = "hello world"
for i, char in enumerate(st):
    if char == "w":
        print(i)
        # 6

what is this enumerate thing? 

Ask for a number a specific amount of times

nums = []
for i in range(5):
    num = input("Enter a number: ")
    nums.append(int(num)) // we need int() because input() always yields a string.
    
.find()? 

**FOR ELSE**:


words = ("hello", "name", "this")
target = "name"

for word in words:
    if word == target:
        print("I found the word!")
else:
    print("I didn't find the word")

If we loop through the entire words looking for target and it's not found. The else statement will run.
The entire for loop will run first and then the else statement will run if the for loop doesn't execute it's intended effect.



# While Loops
a = 1
while a != 42:
    print("a is still not 42")
    a += 1

# Anything you can do with a for loop, you can do with a while loop
# The difference in use case comes from "Not knowing how much you have to loop."

# text adventure example:
num = input("Enter an integer: ")
while not num.isdigit():
    num = input("Enter an integer: ")

# We need to be careful of infinite loops
while True:
    num = input("Enter an integer: ")

# more correct version of code: 
while True:
    num = input("Enter an integer: ")    
    if num.isdigit():
        break # will immediately break out of current loop.

lst = [2,3,3,-2,-2,-1]

result = 0
i = 0 # we need to keep track of and compare to the list indices

while result < 9 and i < len(lst):
    num = lst[i]
    result += num
    i += 1 # to make sure it does not make an infinite loop.

    print(num)


# while else
lst = [1,2,3,3,45,5]
i = 0
while i < len(lst):
    if lst[i] == -2:
        print("found it")
        break
    i += 1 # make sure no infinite loop happens.
else:
    print("didn't find it.")
    
 <hr>

# Dictionaries
In Python, a dictionary (or dict) is a collection that associates immutable keys
with values of any type.
    The values do not need to be similar throughout the dict.
    They can be differet with every key.
For example, the following code creates and accesses a dictionary
that stores the age of each person according to their names:

An unordered collection of key-value pairs.
Dictionaries are really good for frequency counting.

Dictionary BIG O calculations happen instantly. They are fast.
```
ages = {
    "Simon": 27",
    "Alex": 30
}

print("Alex is", ages["Alex"], "years old.")
# will return: Alex is 30 years old.
# The spaces are inherent considering the syntax is comma based.
```
```
d = {}  # an empty dict
d["key"] = "value"  # establishing a value to the key.
print(d["key"])  # RETURNS: "value"

# If you try to add a value into a dictionary when the key already exists:
    # The key will stay the same but it's value will change.
d["key"] = "VALUES"
print(d["key"])  # returns: "VALUES"
```

You will get a traceback error when trying to access a dictionary value
that does not exist. KeyError:
```
x = dict()  # this will create and intiatlize a brand new, empty dictionary

x = {
    1: 1, 2:2, 3:3
}

contains = 1 in x  # here we are checking if the key 1 exists, not the value
return contains #  True

x.keys()  # will return all the keys (1,2,3,4)
```
however, if you want to use something like x.keys(), you need to convert it to a list first.
y = list(x.keys())

items = x.items()  # we get a list of tuples of all the keys and values together.
items = list(x.items())

## GETTING THE LENGTH OF A DICTIONARY
print(len(x)) # will return the number of items. Each key + value are considered 1 item.

## LOOPING THROUGH A DICTIONARY
A dictionary is an unordered object.
The items we insert into a dictionary doesn't mean the order will be maintained.

- Cannot access indices.

for key in x: #  will loop through by key.
    value = x[key]
    print(key, value)

for key, value in x.items():
    print(key, value)

# both of the above will do the same thing.
## .get method

Access the key 4 and add 1 to it's value
but what if there is no key 4?
We want to add the key 4 and give it a value


x[4] = x.get(4,0) + 1
x[4] is trying to access the key 4
x.get(4,0) + 1 is going to make a new key of 4 if one does not exist.
# will return: {1:1, 2:2, 3:3, 4:4} (with an added 4)

You use a dictionary when you care about the presence of something.
You also use a dictionary when you don't care about the order.


In Python, trying to access a key that doesn't exist in a dictionary raises an exception.

To avoid this, you should use the .get(key, default=None) method, which will return None if the key doesn't exist in the dictionary that the method is called on.

Example:

string = "hello world"

for char in string:
    characters[char] = characters.get(char, 0) + 1

# will return: {'h': 1, 'e': 1, 'l': 3, 'o': 2, ' ':1. 'w': 1, 'r':1, 'd': 1}
    


salaries = {
    "Brad": 10,
    "Lucy": 12,
    "John": 6.5,
}

for name in salaries:
    salary = salaries[name]
    print(f"{name} makes ${salary} an hour")


for name, salary in salaries.items():
    weekly_salary = salary * 40
    print(f"{name} makes ${weekly_salary} an week")


<hr>

# Sets
An unordered collection of unique elements.

When you insert items into a set, the order is not maintained.
No elements inside of a set can be duplicated within.
If you want to see something exists, it's similar to a dict as it happens almost immediately. Much faster than a list.
```
y = {} # an empty set (but it makes a dictionary)
# a set is represented by curly braces.
# However, a dictionary is also denoted by {} 
# So when we make an empty set we have to do it as so...
x = set()

# furthermore,

y = {2,3} # this is no longer a dictionary. It's now a set. 
#Because we put something inside the curly braces.
```

s = {1,1,1,2,2,2} will only return {1,2} because sets disregard
elements that are duplicated

### METHODS

y = {1,2,2,1,1}
y.add(3) this will add 3
y.remove(2) will remove an element from the set
y.clear() it will remove all elements from a set
len(y) it will tell the length of the set

- All data types can be mixed and matched inside a set.
- You cannot add a list inside a set
- But you can add tuples
- Inside sets you can only add immutable objects.

### Check if something exists inside a set
```
contains = 1 in y
print(contains) prints True
```

### Combine sets together
x = {1,2}
y = {2,3}

UNION: combine to sets together

z = x.union(y)
print(z) this will print {1,2,3} however this doesn't change x or y original variables.
Another way to write this:
Union Shortcut: z = x | y ... This will perform the union function the same way

### Intersection of sets, items contained within both sets
x = {1,2,3}
y = {1,2,4}
z = x.intersection(y) will return {1,2} because both sets share {1,2}
Intersection shortcut: z = y & x

### Difference of two sets, all the elements contained in one set but not in the other.
x = {1,2,3}
y = {1,2,4}
z = x.difference(y) will return 3
The order we call difference matters.
z = y.difference(x) will return 4

this is because {3} inside x is what y doesn't have
and
{4} insiIntersection shortcut: z = y & xde y is what x doesn't have
Difference shortcut: z = y - x or z = x - y

### Symmetric difference, gives you all elements that are not shared between the two sets
x = {1,2,3}
y = {1,2,4}
z = x.symmetric_difference(y): will return {3,4}
x = {1,2,3}
y = {1,2,4,3}
z = x.symmetric_difference(y): will return {4}

difference only gives us the items in one set that aren't in the other
symmetic_difference gives us the differences in both
Symmetric difference shortcut: z = y ^ x

### Update
Update is a method that will completely update a new set
x = {1,2,3}
y = {1,2,4,3}
x.update(y) - This will not update y but it WILL update x
Will print out: x = {1,2,3,4}

### .difference_update()
x = {1,2,3}
y = {1,2,4}
x.difference_update(y)
x will be equal to the difference between them x and y where x is the dominant set
x = {3}
y.difference_update(x) = {4}

### symmetric_difference_update()
x = {1,2,3}
y = {1,2,4}
y = symmetric_difference_update(x) will return {3,4}

###Subset
This set contains the same items as another set that has more items than itself.
x = {1,2,3}
y = {1,2,3,4}
here x is a subset of y because even though y is a longer set, x still shares every item with y that x contains.

x.issubset(y)) True
Shortcut: x <= y True

x = {1,2,3,8}
y = {1,2,3,4}
Here though x would not be a subset because ALL of x is not contained inside of y

x.issubset(y)) False
Shortcut: x <= y False

###Superset
This set contains all of the elements and MAYBE even more than the other set
x = {1,2,3}
y = {1,2,3,4}
Here y is a superset of x because y contains everything that x contains.

y.issuperset(x) True
Shortcut: x >= y True

###Set Theory (discrete math)
- A proper super set / subset, means that the set we are talking about is not equal to the other set
???

### Convert List to set
x = [1,2,2,2,3,4,5,3,4]
set_x = set(x)
print(set_x) will return: {1,2,3,4,5}

- You can use it for strings too.

### When to use Dictionary or Set
Only use a set when you care about if something is in or not inside of a set
If you just want to see if something exists, you don't care about the order or frequency, then you would use a set.



sentence = (
    "This is a regular sentence with words inside. Some words are unique within the sentence, "
    + "while some are duplicates."
)
words_with_duplicates = sentence.split(" ")
unique_words = set(words_with_duplicates)

print(words_with_duplicates)
print(unique_words)
print(f"The sentence contains {len(unique_words)} unique words, but {len(words_with_duplicates)} words total.")


 <hr>


### Tuple Methods

Tuple()
```
tuple() ???
```

len()
count()
.index()


### Immutable
- Tuple
- String
- Int
- Float
- Bool

### Mutable
- List


### CS Resources
- https://github.com/mtdvio/every-programmer-should-know
- https://github.com/kdeldycke/awesome-falsehood
- https://roadmap.sh/computer-science
- https://github.com/ossu/computer-science
- https://github.com/ForrestKnight/open-source-cs
- https://github.com/PKUFlyingPig/Self-learning-Computer-Science







ERRORS:
Traceback : means the program stopped. Something went wrong.
IndexError: list index out of range: YOU are trying to access an index within a list that doesn't exist.
ValueError: list.remove(x): x not in list

# Exceptions
An exception in python, is raised when something unexpected happens
during the execution of your program.
For example: If you try to convert "hello" to an integer.
x = int("Hello") -- Will raise a "ValueError"

However, we can anticipate when an error will be raised.
If you do anticipate that a part of your code might, in some cases
raise an exception, you can surround that part of the code
with a try/except block and prevent your program from crashing.

```
digits = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

try:
    if len(digits) != 10:
        raise Exception("There should be exactly 10 digits!")
except Exception as e:
    print(e)
finally:
    print("Goodbye!")
```

```
try:
    int("hello")
except:
    print("Exception!")
```

This will print "Exception"

You can also code for specific exceptions.
- Heading Specific Exceptions

```
try:
    int("hello")
except ValueError as e:
    #store the error as a variable
    print("Exception!", e)
```

```
try:
    int("hello")
except ZeroDivisionError as e:
    #The value specific error will only print out "e" if it's the type of error we are looking for.
    print("Exception!", e)
```

- We can also accept multiple different exceptions:
```
try:
    x = 2/0
except ZeroDivisionError as e:
    print("Zero Div Exception!", e)
except ValueError as e:
    print("Val Exception!", e)
```

- If you don't know what exception you are looking for, you can accept a "general" exception type:
```
try:
    x = 2/0
except Exception as e:
    print("General Exception!", e)
```

### Finally Block
- Clean up operations
- Finally block will always run no matter what
```
try:
    x = 2/0
except Exception as e:
    print("General Exception!", e)
finally:
    print("Done")
```
- Even if an exception does NOT occur, the finally section will still run

IndexError
ValueError
Zero Division Error
Invalid Syntax

### Raise our own errors
```
raise ValueError("This is an error!")

```
```
raise Exception("This is an error!")

```

What's the point of raising our own errors?
- We can also create our own exceptions and errors?
    - How?

```
num = input("Enter a number: ")

if not num.isdigit():
    raise ValueError("this is not a valid number!")
```

```
while True:
    num = input("Enter a number: ")

    try:
        num = float(num)
        break
    except ValueError:
        print("Not a valid float, try again.")
```

- Only when you know an error can occur should we use try/except blocks
- And usually when you are expecting a specific error
- Looking for general exceptions isn't a best practice in Python

Runtime vs compile time Error:

Compile Time: Refers to the time when the code will be converted into Bytecode
- An error occurs before the computer can read the code.
Byte Code: Interpreted and ran by computer

Runetime error: A error that occurs while the code is executed.
```
num = input("Enter a float: ")
num = float(num)
# num = "hello"

#The first line will run fine, but the second line will crash because the input can't be converted to a float.
```

Run time errors are harder to detect










NOTES:
- If you're concerned with the presence or the frequency of items in a collection but don't care about their order, you should use a dictionary
- If you're concerned with the order in which items are added to a collection and would like to modify these items, you should use a list







# CLASSES

### STATIC METHODS

A static method is a method that sits inside of a class but does not 
have access to the CLS or self key word.

```
class Student:
    STATIC ATTRIBUTES / CLASS ATTRIBUTES
    num_of_grades = 3
    num_of_students = 20
    grade_bump = 2.0

    def __init__(self, name, grades=[]):
        self.name = name
        self.grades = grades

    # INSTANCE METHOD
    def average(self):
        return sum(self.grades) / len(self.grades)

    @classmethod
    def average_from_grades_plus_bump(cls, grades):
        average = cls.average_from_grades(grades)
        return min(average + cls.grade_bump, 100)

    @staticmethod
    def average_from_grades(grades):
        return sum(grades) / len(grades)

s1 = Student("Dan", [80,75,90,99])

How to call the static method:
    print(s1.average_from_grades(s1.grades))
```






```
import math


class Geometry:
    @staticmethod
    def perimeter_of_square(side_length):
        return 4 * side_length

    @staticmethod
    def area_of_square(side_length):
        return side_length ** 2

    @staticmethod
    def perimeter_of_circle(radius):
        return 2 * math.pi * radius

    @staticmethod
    def area_of_circle(radius):
        return math.pi * (radius ** 2)


print("Perimeter of square with side of length 7:", Geometry.perimeter_of_square(7))
print("Area of square with side of length 7:", Geometry.area_of_square(7))

print("Perimeter of circle with radius of length 3:", Geometry.perimeter_of_circle(3))
print("Perimeter of circle with radius of length 3:", Geometry.area_of_circle(3))
```

















