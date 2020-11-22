# Adventures in Python
I'm trying to learn python because it might come in handy to know at some point in the future. The way I'm learning is by using this [online python interpreter]( https://www.tutorialspoint.com/execute_python3_online.php) along with [this tutorial](https://www.programiz.com/python-programming/tutorial).

### To Begin With
Every programming tutorial conventionally starts with the "Hello, World!" program. Here it is in Python:  
**PROGRAM**
```python3
print("Hello World!")
```
**OUTPUT**
```
Hello World!
```
Makes sense so far. So, the next thing you might wonder is how do we assign a value to a variable in Python? It is quite simple, here's an example of assigning the literal string value of `"Hello World!"` to a variable called `testVar`: `testVar = "Hello World!"`.  
The next thing to learn is how to operate with values. Here's an example of that:  
**PROGRAM**
```python3
print(5 + 8)
print("14" + " the string")
print(13//2)
print(9756 % 10)
print(2 ** 3)
```
**OUTPUT**
```
13
14 the string
6
6
8
```
What's interesting to note is that Python has native operators for floor division (`\\`) and exponents (`**`), which I think is quite nice because we don't have to go running off writing our own functions for these operations. Of course we can do a re-assignment of a variable while performing some operation in one concise step as well:  
**PROGRAM**
```python3
test = 8
test **= 2
print(test)
```
**OUTPUT**
```
64
```
Interestingly, there's no `++` or `--` operators like there is in most languages:  
**PROGRAM**
```python3
test = 0
test ++
print(test)
```
**OUTPUT**
```
  File "main.py", line 2
    test ++
          ^
SyntaxError: invalid syntax
```
Of course we can get around this easily by using the `+=` operator:  
**PROGRAM**
```python3
test = 0
test += 1
print(test)
```
**OUTPUT**
```
1
```
The next thing [the tutorial](https://www.programiz.com/python-programming/tutorial) introduces us to is a method for accepting and working with user input:  
**PROGRAM**
```python3
someInput = input("Enter some text here:")
print("\n" + someInput)
```
Entering the string `this is some input` for STDIN:  
**OUTPUT**
```
Enter some text here:
this is some input
```
To make a single line comment in the source code we can use `#` (the pount sign). We can also make multi-line comments:  
**PROGRAM**
```python3
# hey there I'm a sexy one-line comment

'''
This comment
is spread
over multiple lines
and ignored by the interpreter
'''
print("The bastard","took all my m&ms!")
```
**OUTPUT**
```
The bastard took all my m&ms!
````
The next thing introduced is implicit type conversion:  
**PROGRAM**
```python3
someInt = 2
someReal = 2.3
print(someInt + someReal)
result = someInt + someReal
print(type(result))
```
**OUTPUT**
```
4.3
<class 'float'>
```
As we can see, adding an integer and a float together results in a float.  
We can do explict type conversion as well:  
**PROGRAM**
```python3
print(bool("I wonder what will happen"))
print(bool(''))
print(float("2.657"))
```
**OUTPUT**
```
True
False
2.657
```
As you can see, I was curious about what would happen if I converted an empty and non-empty string value to a boolean. Python won't throw an error, but will return `True` for any non-emtpy string value and `False` for an empty string. Neato.  
Python has your regular `integer` and `float` types but also has a `complex` numeric type for the more mathematically inclined:  
**PROGRAM**
```python3
print(2j + 3j)
print(complex("5j"))
```
**OUTPUT**
```
5j
5j
```
# Data Structures
After learning the basics of the language, the tutorial moves us on to learn about the data structures that are native to Python. The first one we learn about is the "list" structure:  
**PROGRAM**
```python3
list = [1, 2, 3, "this is a list"]
print(list)
list[2] = 4.5
print(list[-2])
print(list[1])
```
**OUTPUT**
```
[1, 2, 3, 'this is a list']
4.5
2
```
One interesting thing to note is that we can go backwards in a list starting from the last item of the list using the index `-1`.  
The next structure that we are introduced to is similar to a list, however, unlike a list, it's immutable. This type of data structure is called a "tuple".  
**PROGRAM**
```python3
tuple = (1, 2, 3)
print(tuple[1])
tuple[0] = "haha"
print(tuple)
```
**OUTPUT**
```
2
Traceback (most recent call last):
  File "main.py", line 3, in <module>
    tuple[0] = "haha"
TypeError: 'tuple' object does not support item assignment
```
As you can see, trying to assign a value to an element in a tuple results in a run-time error.  
This section of the tutorial introduces the interesting operator `del`.  
**PROGRAM**
```python3
num = 10.0
string = "This is a test string"
t1 = (3, 8, 12, 69)
l1 = ["apples", "tofu", "oranges", "tea"]

print(num, string, t1, l1)

del num
del string
del t1
del l1

print(num)
```
**OUTPUT**
```
10.0 This is a test string (3, 8, 12, 69) ['apples', 'tofu', 'oranges', 'tea']
Traceback (most recent call last):
  File "main.py", line 13, in <module>
    print(num)
NameError: name 'num' is not defined
```
I played around with `del` to see if it could delete things like numbers, strings, tuples, and lists, and it can certainly handle that. I'm not sure what `del` is really good for yet but I'm sure it has it's uses.  
Next up is the good old programming standyby: the string.  
**PROGRAM**
```python3
test = "here there be dragons"
test1 = '''this
is
another
string'''

print(test1)
print(test[3] + test[-1])
# slicing in python
print(test[1:4])
list = ["this", "is", "cool"]
print(list[:-1])
print("the thing" * 5)
```
**OUTPUT**
```
this
is
another
string
es
ere
['this', 'is']
the thingthe thingthe thingthe thingthe thing
```
We can define, concatenate, and slice strings! I was curious if the slicing syntax worked for lists as well and it does, so I'm assuming it works for tuples as well. I also like the ability to repeat a string by using the `*` operator. Cool.  
"Sets" are next. Here's some cool stuff we can do with them:  
**PROGRAM**
```python3
set1 = {1, 2, 3}
set2 = {3, 4, 5}

# union operation
print(set1 | set2)
# subtraction
print(set2 - set1)
# intersection
print(set1 & set2)

# add multiple elements at once
set1.update([4, 10, 12])
print(set1)
# add one element
set2.add("ComPuTeR")
print(set2)
# remove one element
set1.remove(1)
print(set1)
```
**OUTPUT**
```
{1, 2, 3, 4, 5}
{4, 5}
{3}
{1, 2, 3, 4, 10, 12}
{3, 4, 5, 'ComPuTeR'}
{2, 3, 4, 10, 12}
```
I am really enjoying the fact that sets are so readily available to be worked with in Python. Most often we don't directly deal with the notion of a set in a programming language (and we use arrays as a substitute) so the fact that python supports this is very awesome indeed!  
