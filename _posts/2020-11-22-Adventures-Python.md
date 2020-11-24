# Adventures in Python
I'm trying to learn python because it might come in handy to know at some point in the future. The way I'm learning is by using this [online python interpreter]( https://www.tutorialspoint.com/execute_python3_online.php) along with [this tutorial](https://www.programiz.com/python-programming/tutorial).

### Begin Again
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
### Data Structures
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
Next up, "Dictionaries"!  
**PROGRAM**
```python3
dict = {"wine": "quite a lovely drink", "PI": 3.14, (1, 2, 3): 100}
print(dict["wine"])
print(dict["PI"])
print(dict[(1, 2, 3)])
dict[(1, 2, 3)] = "this is quite odd"
print(dict)
del dict[(1, 2, 3)]
print(dict)
```
**OUTPUT**
```
quite a lovely drink
3.14
100
{'wine': 'quite a lovely drink', 'PI': 3.14, (1, 2, 3): 'this is quite odd'}
{'wine': 'quite a lovely drink', 'PI': 3.14}
```
As you can see, dictionaries are quite friendly in python as well! I was curious if you could use any value as a key in a dictionary and, as you can see above, you can! Deleting keys is easy too!  
The next task is to get familiar with the `range` function.  
**PROGRAM**
```python3
# define a range
r = range(1, 6)
# use a range to create a list, tuple, set, or dictionary!
print(list(r))
print(tuple(r))
print(set(r))
print(dict.fromkeys(r, "test"))
print(dict.fromkeys(range(90, 100, 2)))
```
**OUTPUT**
```
[1, 2, 3, 4, 5]
(1, 2, 3, 4, 5)
{1, 2, 3, 4, 5}
{1: 'test', 2: 'test', 3: 'test', 4: 'test', 5: 'test'}
{90: None, 92: None, 94: None, 96: None, 98: None}
```
Lists, tuples, sets, and dictionaries can all be instantiated from a range. You can choose the amount to "step" by as the third argument to the `range` function. As you can see in the code above, creating a dictionary from a range where the value of each dictionary item is not specified is totally valid as well!  
### Control Flow
`if...else` in python:  
**PROGRAM**
```python3
if 5 > 6:
    print('Hi')
elif 100 <= 99:
    print('Why me?')
else:
    print("Well you're here now.")
    
print(not(True and False))
print(not True)
```
**OUTPUT**
```
Well you're here now.
True
False
```
So, we can control program flow with an `if` statement and use all the usual logical (`and`, `or`, `not`) and comparison (`==`, `<=`, `>=`, `<`, `>`, `!=`) operators.  
Here's a `while` loop:  
**PROGRAM**
```python3
keepLooping = True
loopTimes = 0
while keepLooping:
    loopTimes += 1
    print("I am looping",loopTimes,"times!")
    if loopTimes == 10:
        keepLooping = False
```
**OUTPUT**
```
I am looping 1 times!
I am looping 2 times!
I am looping 3 times!
I am looping 4 times!
I am looping 5 times!
I am looping 6 times!
I am looping 7 times!
I am looping 8 times!
I am looping 9 times!
I am looping 10 times!
```
Simple enough. The loop continues to execute as long as the conditional expression evaluates to `True`.  
Traversing over any iterable sequence (list, tuple, set, dictionary, or range) using a `for` loop:  
**PROGRAM**
```python3
breakfast = ["eggs", "bacon", "hashbrowns"]

for item in breakfast:
    print(item)
    
for i in range(2, 5):
    print(i)

dict = {"one": 1, "two": 2, "three": 3}
for key in dict:
    print("key:", key, "value:", dict[key]))
 ```
 **OUTPUT**
```
eggs
bacon
hashbrowns
2
3
4
key: one value: 1
key: two value: 2
key: three value: 3
```
Sweet.  
On to Functions!  
**PROGRAM**
```python3
def func():
    pass

def func1(one, two):
    return one + two

print(func())
print(func1(8, 6))
```
**OUTPUT**
```
None
14
```
Functions in python can return values, accept arguments, and execute arbitrary code. It is interesting to note that we can use the `pass` keyword to basically make a block of python code do nothing. Python also has a concept of something called a "lambda" function. We can use it on a `filter` or `map` operation.
**PROGRAM**
```python3
l = [101, 89.6, 3j, 4.5, 2, 14 / 3]
integers = list(filter(lambda i: type(i) is int, l))
print(integers)
l1 = list(map(lambda i: i / 2, l))
print(l1)
```
**OUTPUT**
```
[101, 2]
[50.5, 44.8, 1.5j, 2.25, 1.0, 2.3333333333333335]
```
I defined a list called `l` and assigned some values to it. I then used the `filter` function, only selecting items that were of the type `int`. I also called the `map` function to return a list of all the items of `l` divided by 2! Lambda functions aren't strictly necessary here but I'm assuming it's good practice to use them in this case.  
Python also has support for object orientation.  
**PROGRAM**
```python3
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
        
    def tostring(self):
        return "This person's name is: " + self.name + " and their age is: " + str(self.age) + "!"

p = Person("Kelan", 28)
print(p.tostring())
```
**OUTPUT**
```
This person's name is: Kelan and their age is: 28!
```
Here I've defined a simple `Person` class that has two attributes, a `name` and an `age` and I've defined a method of that class that uses those attributes.
### A Project
There is of course more to learn in regards to Python but I think we have a good basis on which to build out a project from. I've taken inspiration for a problem to work on with Python from a book I possess from my college days: *Data Structures and Algorithms* by Michael Goodrich, Roberto Tamassia, and Michael Goldwasser. Problem P-2.31 on page 100 reads:  
> Write a Java program to simulate an ecosystem containing two types of creatures, ***bears*** and ***fish***. The ecosystem consists of a river, which is modeled as a relatively large array. Each cell of the array should contain an `Animal` object, which can be a `Bear` object, a `Fish` object, or **null**. In each time step, based on a random process, each animal either attempts to move into an adjacent array cell or stay where it is. If two animals of the same type are about to collide in the same cell, then they stay where they are, but they create a new instance of that type of animal, which is placed in a random empty (i.e., previously **null**) cell in the array. If a bear and a fish collide, however, then the fish dies (i.e., it disappears). Use actual object creation, via the **new** operator, to model the creation of new objects, and provide a visualization of the array after each time step.  

This problem was intended to be solved ind Java but we can adapt it for learning Python as well. As you can see, the authors are trying to hammer home object orientation as well, so we will use some object oriented features of the Python language in our solution.  
So, we need to simulate the river that the bears and fish live in, so we can create a `River`, `Animal`, `Fish`, and `Bear` class. We can use that handy `pass` keyword to avoid having to define bodies for these classes for the time being.  
```python3
class River:
    class Animal:
        pass
    
    class Bear(Animal):
        pass
    
    class Fish(Animal):
        pass
    
    def __init__(self):
        self.river_array = []
```
You can run this code and it executes just fine. In Python you can easily define a class within another class. Here I'm defining the `Animal`, `Bear`, and `Fish` class within the `River` class because only the `River` should need access to new instances of `Fish` and `Bear`. Now to begin with, we should probably be able to instantiate a `River` object by passing the `River`'s size as an argument to the constructor method. Here I added some code to do that. I'm using a list to represent the river and instantiating all the elements as either `Bear`, `Fish`, or the special `None` objects, based off a random number generator.  
**PROGRAM**
```python3
import random

class Animal:
    pass
            
class Bear(Animal):
    def __repr__(self):
        return "Bear"

class Fish(Animal):
    def __repr__(self):
        return "Fish"
                    
def getAnimal(i):
    r = random.randint(0, 2)
    if r == 0:
        return Bear()
    elif r == 1:
        return Fish()
    else:
        return None

def make_river(river_size):
    return list(map(getAnimal, range(0, river_size)))
        
# TESTING
print(make_river(5))
print(make_river(10))
print(make_river(2))
print(make_river(8))
```
**OUTPUT**
```
[Bear, Bear, Bear, Fish, None]
[None, Bear, Bear, Bear, None, None, Fish, Fish, Fish, None]
[None, Bear]
[None, Bear, None, Bear, Bear, Fish, None, Bear]
```
So, now that I can generate randomly sized "rivers" populated with different `Animal` or `None` objects, I think the next thing to do is code what happens when the animals start moving around and breeding or eating each other.  
**PROGRAM**
```python3
import random

class Animal:
    pass
            
class Bear(Animal):
    def __repr__(self):
        return "Bear"

class Fish(Animal):
    def __repr__(self):
        return "Fish"
                    
def getAnimal(i):
    r = random.randint(0, 2)
    if r == 0:
        return Bear()
    elif r == 1:
        return Fish()
    else:
        return None

def make_river(river_size):
    return list(map(getAnimal, range(0, river_size)))
    
def none_indexes(l):
    index = 0
    none_list = []
    for i in l:
        if i == None:
            none_list.append(index)
        index += 1
    return none_list
    
def choose_random_item(l):
    if len(l) > 1:
        return l[random.randint(0, len(l) - 1)]
    elif len(l) == 1:
        return l[0]
    return None

def move_animals(river):
    i = 0
    while i < len(river):
        if issubclass(type(river[i]), Animal):
            if random.randint(0, 1) == 0:
                if random.randint(0, 1) == 0:
                    if i < len(river) - 1:
                        if type(river[i]) == type(river[i + 1]):
                            print(river[i], "at index:", i, "met another", river[i + 1], "while moving right. Time to breed!")
                            rni = choose_random_item(none_indexes(river))
                            if rni != None:
                                if type(river[i]) == Bear:
                                    river[rni] = Bear()
                                    print(river[rni], "spawned at index:", str(rni) + ".")
                                else:
                                    river[rni] = Fish()
                                    print(river[rni], "spawned at index:", str(rni) + ".")
                            else:
                                print("There is no more room to spawn new animals in the river!")
                        elif type(river[i]) == Bear and type(river[i + 1]) == Fish:
                            river[i + 1] = river[i]
                            river[i] = None
                            print("Bear moved right from index:", i, "and ate Fish at index:", str(i + 1) + ".")
                            i += 1
                        elif type(river[i]) == Fish and type(river[i + 1]) == Bear:
                            river[i] = None
                            print("Fish swam right from index:", i, "and was eaten by Bear at index:", str(i + 1) + ".")
                        else:
                            print(river[i], "at index:", i, "moved right.")
                            river[i + 1] = river[i]
                            river[i] = None
                            i += 1
                            
                    else:
                        print(river[i],"at index:", i, "tried to move right but is out of space, so they stayed put.")
                else:
                    if i > 0:
                        if type(river[i]) == type(river[i - 1]):
                            print(river[i], "at index:", i, "met another", river[i - 1], "while moving left. Time to breed!")
                            rni = choose_random_item(none_indexes(river))
                            if rni != None:
                                if type(river[i]) == Bear:
                                    river[rni] = Bear()
                                    print(river[rni], "spawned at index:", str(rni) + ".")
                                else:
                                    river[rni] = Fish()
                                    print(river[rni], "spawned at index:", str(rni) + ".")
                            else:
                                print("There is no more room to spawn new animals in the river!")
                        elif type(river[i]) == Bear and type(river[i - 1]) == Fish:
                            river[i - 1] = river[i]
                            river[i] = None
                            print("Bear moved left from index:", i, "and ate fish at index:", str(i - 1) + ".")
                        elif type(river[i]) == Fish and type(river[i - 1]) == Bear:
                            river[i] = None
                            print("Fish swam left from index:", i, "and was eaten by Bear at index:", str(i - 1) + ".")
                        else:
                            print(river[i], "at index:", i, "moved left.")
                            river[i - 1] = river[i]
                            river[i] = None
                    else:
                        print(river[i],"at index:", i, "tried to move left but is out of space, so they stayed put.")
            else:
                print(river[i],"at index:", i, "chose not to move.")
        i += 1
    
        
time_steps = 10
river_size = 20
river = make_river(river_size)
for i in range(0, time_steps):
    print("River state:")
    print(river)
    move_animals(river)
print(river)
```
**OUTPUT**
```
River state:
[Fish, Bear, None, None, Fish, Fish, Bear, None, None, Bear, Fish, None, Bear, Bear, Bear, Fish, None, Bear, None, Fish]
Fish at index: 0 chose not to move.
Bear at index: 1 chose not to move.
Fish at index: 4 chose not to move.
Fish at index: 5 chose not to move.
Bear at index: 6 chose not to move.
Bear at index: 9 chose not to move.
Fish swam left from index: 10 and was eaten by Bear at index: 9.
Bear at index: 12 chose not to move.
Bear at index: 13 met another Bear while moving left. Time to breed!
Bear spawned at index: 2.
Bear at index: 14 chose not to move.
Fish at index: 15 chose not to move.
Bear at index: 17 chose not to move.
Fish at index: 19 chose not to move.
River state:
[Fish, Bear, Bear, None, Fish, Fish, Bear, None, None, Bear, None, None, Bear, Bear, Bear, Fish, None, Bear, None, Fish]
Fish at index: 0 chose not to move.
Bear at index: 1 met another Bear while moving right. Time to breed!
Bear spawned at index: 18.
Bear at index: 2 chose not to move.
Fish at index: 4 moved left.
Fish at index: 5 moved left.
Bear at index: 6 moved right.
Bear at index: 9 moved right.
Bear at index: 12 moved left.
Bear at index: 13 chose not to move.
Bear moved right from index: 14 and ate Fish at index: 15.
Bear at index: 17 chose not to move.
Bear at index: 18 chose not to move.
Fish at index: 19 chose not to move.
River state:
[Fish, Bear, Bear, Fish, Fish, None, None, Bear, None, None, Bear, Bear, None, Bear, None, Bear, None, Bear, Bear, Fish]
Fish swam right from index: 0 and was eaten by Bear at index: 1.
Bear at index: 1 chose not to move.
Bear at index: 2 chose not to move.
Fish at index: 3 chose not to move.
Fish at index: 4 chose not to move.
Bear at index: 7 chose not to move.
Bear at index: 10 chose not to move.
Bear at index: 11 chose not to move.
Bear at index: 13 chose not to move.
Bear at index: 15 moved left.
Bear at index: 17 chose not to move.
Bear at index: 18 chose not to move.
Fish at index: 19 chose not to move.
River state:
[None, Bear, Bear, Fish, Fish, None, None, Bear, None, None, Bear, Bear, None, Bear, Bear, None, None, Bear, Bear, Fish]
Bear at index: 1 chose not to move.
Bear at index: 2 met another Bear while moving left. Time to breed!
Bear spawned at index: 16.
Fish at index: 3 chose not to move.
Fish at index: 4 chose not to move.
Bear at index: 7 moved right.
Bear at index: 10 met another Bear while moving right. Time to breed!
Bear spawned at index: 5.
Bear at index: 11 chose not to move.
Bear at index: 13 met another Bear while moving right. Time to breed!
Bear spawned at index: 0.
Bear at index: 14 met another Bear while moving left. Time to breed!
Bear spawned at index: 6.
Bear at index: 16 moved left.
Bear at index: 17 chose not to move.
Bear at index: 18 met another Bear while moving left. Time to breed!
Bear spawned at index: 7.
Fish at index: 19 tried to move right but is out of space, so they stayed put.
River state:
[Bear, Bear, Bear, Fish, Fish, Bear, Bear, Bear, Bear, None, Bear, Bear, None, Bear, Bear, Bear, None, Bear, Bear, Fish]
Bear at index: 0 chose not to move.
Bear at index: 1 chose not to move.
Bear at index: 2 chose not to move.
Fish at index: 3 met another Fish while moving right. Time to breed!
Fish spawned at index: 12.
Fish swam right from index: 4 and was eaten by Bear at index: 5.
Bear at index: 5 met another Bear while moving right. Time to breed!
Bear spawned at index: 4.
Bear at index: 6 met another Bear while moving right. Time to breed!
Bear spawned at index: 16.
Bear at index: 7 met another Bear while moving right. Time to breed!
Bear spawned at index: 9.
Bear at index: 8 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 9 met another Bear while moving right. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 10 chose not to move.
Bear at index: 11 chose not to move.
Fish at index: 12 chose not to move.
Bear moved left from index: 13 and ate fish at index: 12.
Bear at index: 14 moved left.
Bear at index: 15 chose not to move.
Bear at index: 16 chose not to move.
Bear at index: 17 met another Bear while moving right. Time to breed!
Bear spawned at index: 14.
Bear moved right from index: 18 and ate Fish at index: 19.
River state:
[Bear, Bear, Bear, Fish, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, None, Bear]
Bear at index: 0 chose not to move.
Bear at index: 1 met another Bear while moving left. Time to breed!
Bear spawned at index: 18.
Bear at index: 2 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Fish at index: 3 chose not to move.
Bear at index: 4 met another Bear while moving right. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 5 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 6 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 7 chose not to move.
Bear at index: 8 met another Bear while moving right. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 9 chose not to move.
Bear at index: 10 met another Bear while moving right. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 11 chose not to move.
Bear at index: 12 chose not to move.
Bear at index: 13 chose not to move.
Bear at index: 14 chose not to move.
Bear at index: 15 chose not to move.
Bear at index: 16 chose not to move.
Bear at index: 17 chose not to move.
Bear at index: 18 met another Bear while moving right. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 19 chose not to move.
River state:
[Bear, Bear, Bear, Fish, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear]
Bear at index: 0 tried to move left but is out of space, so they stayed put.
Bear at index: 1 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 2 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Fish at index: 3 chose not to move.
Bear moved left from index: 4 and ate fish at index: 3.
Bear at index: 5 chose not to move.
Bear at index: 6 met another Bear while moving right. Time to breed!
Bear spawned at index: 4.
Bear at index: 7 met another Bear while moving right. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 8 chose not to move.
Bear at index: 9 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 10 chose not to move.
Bear at index: 11 chose not to move.
Bear at index: 12 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 13 met another Bear while moving right. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 14 met another Bear while moving right. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 15 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 16 chose not to move.
Bear at index: 17 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 18 met another Bear while moving right. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 19 chose not to move.
River state:
[Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear]
Bear at index: 0 met another Bear while moving right. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 1 chose not to move.
Bear at index: 2 chose not to move.
Bear at index: 3 chose not to move.
Bear at index: 4 chose not to move.
Bear at index: 5 chose not to move.
Bear at index: 6 met another Bear while moving right. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 7 chose not to move.
Bear at index: 8 met another Bear while moving right. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 9 chose not to move.
Bear at index: 10 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 11 met another Bear while moving right. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 12 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 13 met another Bear while moving right. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 14 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 15 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 16 chose not to move.
Bear at index: 17 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 18 chose not to move.
Bear at index: 19 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
River state:
[Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear]
Bear at index: 0 chose not to move.
Bear at index: 1 chose not to move.
Bear at index: 2 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 3 chose not to move.
Bear at index: 4 chose not to move.
Bear at index: 5 met another Bear while moving right. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 6 chose not to move.
Bear at index: 7 chose not to move.
Bear at index: 8 met another Bear while moving right. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 9 met another Bear while moving right. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 10 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 11 met another Bear while moving right. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 12 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 13 chose not to move.
Bear at index: 14 chose not to move.
Bear at index: 15 met another Bear while moving right. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 16 met another Bear while moving right. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 17 chose not to move.
Bear at index: 18 chose not to move.
Bear at index: 19 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
River state:
[Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear]
Bear at index: 0 met another Bear while moving right. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 1 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 2 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 3 chose not to move.
Bear at index: 4 chose not to move.
Bear at index: 5 chose not to move.
Bear at index: 6 met another Bear while moving right. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 7 met another Bear while moving right. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 8 chose not to move.
Bear at index: 9 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 10 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 11 chose not to move.
Bear at index: 12 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 13 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 14 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 15 chose not to move.
Bear at index: 16 met another Bear while moving right. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 17 met another Bear while moving left. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 18 met another Bear while moving right. Time to breed!
There is no more room to spawn new animals in the river!
Bear at index: 19 tried to move right but is out of space, so they stayed put.
[Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear, Bear]
```
As you can see, because bears can eat fish but not vice-versa, as the simulation plays out the bears eventually outbreed and eat all the fish!  
Of course there is more to learn in regards to python, but I think solving this problem gives us a good basis to starting coding from.  
Happy coding!
