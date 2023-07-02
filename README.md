# The Pythonic Way


***


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

OTHER ESCAPE CHARACTER!


### String Methods

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

<sub>A delimiter is the character that tells you how to separate the string, (",") , ("."), (" ")</sub>
<sub>when you put nothing, it defaults to spaces. (" ")</sub>

```
.split() example:

```

.replace() # replace all of the characters in a current string with whatever string you specify
# Then it will return a new string with all of the replaced characters.
s = "A,B,C,D"
s2 = s.replace("," , "|") # will return "A|B|C|D"
# s.replace() doesn't change the original variable. Instead it creates a new variable. So you might have trouble when using .replace() without assigning the returned value to a new variable.

.join() # used to build a new string from an iterable item (set, dictionary, list)
lst = ["d","a", "n"]
lst_string = "".join(lst) #takes all the items in the iterable together into the variable.
lst.string = "-".join(lst) # returns "d-a-n"
lst.string = "|".join(lst) # returns "d|a|n"

# F-Strings
# to help with the cumbersome nature of concatenation
# {can but any equation in here or variable name if it exists}
# You are a human on Earth who is receiving intel from Potsu about the aliens.

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
