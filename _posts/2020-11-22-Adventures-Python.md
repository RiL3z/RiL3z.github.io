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
What's interesting to note is that Python has native operators for floor division (`\\`) and exponents (`**`), which I think is quite nice, because we don't have to go running off writing our own functions for these operations. Of course we can do a re-assignment of a variable while performing some operation in one concise step as well:  
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
