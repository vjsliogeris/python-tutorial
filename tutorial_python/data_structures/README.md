# Python complexs!

Now that we know the basics of python, we can move up.

## Data Structures

Data structures are the larger things that are built up of python primitives.
There are quite a lot of those, but we will stay with the essentials for now:

- lists
- dictionaries

### Lists
[Documentation](https://docs.python.org/3/tutorial/datastructures.html#more-on-lists)

Lists are like "arrays" in other languages - they hold multiple things
(a list of things).
Here are the ways that you can build lists.
```python
bitches = []
sins = ['lust', 'greed', 'gaming']
grades = [8, 9, 9, 5]
trash = ['thing', 5, -0.72, False]
```
They are very pythonic (lazy):
- They can hold a myriad of different retarded things, as outlined in line 4.
- They don't have to be initialised befure usage.
Yada yada.

These are the basic funcitons of working with lists.

#### Adding to a list
Adding to a list is very common and useful.

##### Append
`append(thing)` adds a `thing` to the end of the list.

```python
mylist = []
mylist.append('homo')
```
Now `mylist` is `['homo']`.
You can repeat this to add more things to the list.

Remember when I said that a list can hold _anything_?
Yea, you can add other lists to a list.

```python
mylist = []
retards = ['vycka', 'pofke', 'rolke']
mylist.append('homo')
mylist.append(retards)
```
You get some godforsaken list that has values `['homo', ['vycka', 'pofke', 'rolke']]`.
While this works, you should not abuse this.
It's cool to have lists of lists (essentially making a matrix of things),
but having lists of mixed types (numbers, strings, lists) make it very difficult to work with later on.
Types are like races - they souldn't mix.


##### Extend
> Ok, but what if I want to add values of one list to another?
You can do it with loops (we'll go over it later in this document),
but this is so common that pyton has a function for it: `extend()`.
`extend(thing)` takes a list of things (`thing` **must** be a list),
and then it adds the elements of `things` and adds it to our list.

```python
mylist = []
retards = ['vycka', 'pofke', 'rolke']
mylist.append('homo')
mylist.extend(retards)
```
`mylist` will now be `['homo', 'vycka', 'pofke', 'rolke']`.
This is no longer an abomination :smile:.

##### Insert

There may be cases where you want to add an element,
but _in a particular position_.
It is usually ill-advised to abuse this - focusing on element positions is often difficult to reason about.
Not impossible, but may cause headaches.

To add an element to  particular position, there is a function called `insert()`.
`insert(position, thing)` adds `thing` to a list at position `position`.


```python
mylist = ['vycka', 'pofke', 'rolke']
mylist.insert(1, 'homo')
```
`mylist` is now `['vycka', 'homo', 'pofke', 'rolke']`.


#### Retrieving values from a list

Ok, we have lists of things.
But we want to do stuff with them!

Two ways of doing this - using special python grammar or using stupid function.
For getting values you should _almost always_ use the special python grammar.

##### Special python list grammar (slicing)
`list[position]` returns the element of `list` which is at position `position`.

```python
mylist = ['vycka', 'homo', 'pofke', 'rolke']
x = mylist[0]
y = mylist[1]
```
`x` has value `'vycka'`, `y` - `'homo'`.

But there's magic and syntactic sugar that will make it very easy to work with lists when you get the hang of it.
For example.

```python
mylist = ['vycka', 'homo', 'pofke', 'rolke']
z = mylist[-1]
a = mylist[-2]
```
`z` will have value `'rolke'`, and `a`: `'pofke'`!
When the index is negative, it wraps around the other way of the list.
Using `list[-1]` is a very common way to access the final / last added element of the list.
###### Slicing!
[Documentation](https://www.geeksforgeeks.org/python-list-slicing/)
Final bit of magic!

```python
mylist = ['vycka', 'homo', 'pofke', 'rolke']
yourlist = mylist[1:]
hislist = mylist[:2]
herlist = mylist[:-1]
theirlist = mylist[1:3]
```
If there's a colon `:` in the index - it selects multiple values!
The grammar is such: `list[start:finish]`.
So `yourlist` will be `['homo', 'pofke', 'rolke']`,
`hislist`: `['vycka', 'homo', ]`,
`herlist`: `['vycka', 'homo', 'pofke']`,
`theirlist`: `['homo', 'pofke']`.

The index mangling can get confusing,
but it's generally usefull to get all elements except first/last elements.

#### Deleting items from a list

This is an extension of getting values from lists.
There is one function that is cool and may work nicely:
`pop(position)`.
The function takes the value of the lists at `position` _out_ of the list,
and **also** returns it.


```python
mylist = ['vycka', 'homo', 'pofke', 'rolke']
x = mylist.pop(2)
```
`mylist` is `['vycka', 'homo', 'rolke']`,
and `x` is `'pofke'`.

##### A TALE OF CAUTION

DELETING THINGS FROM LISTS IS A SURE FIRE WAY TO SHIT PANT.
When you delete an element from a list - indexes of further values get shifted back.
It makes it **super easy** to lose trach of element positions and fuck up.
If you ever thing of removing elements from the list - reconsider.
It is most often way easier and better to just re-build a list without including some values,
instead of taking values _out_ of the list.

#### List properties

##### List length
We may want to know some things about lists.
For now the only one I recall is the length of the list.
There exists a function `len(thing)`.
`thing` must be a list.
It will return the length of the list as an integer.

```python
mylist = ['vycka', 'homo', 'pofke', 'rolke']
x = len(mylist)
```
`x` will be `4`.

##### List sums

There is another thingy!
Sums.
A similar function to `len` exists: `sum(thing)`.
`thing` must be a list, and it sums up all of the elements in `thing`.
So:
```python
mylist = [4, 3, 18, -1.2]
x = sum(mylist)
```
`x` will be 3 + 4 + 18 - 1.2 = `23.8` I thing.
```python
mylist = ['vycka', 'homo', 'pofke', 'rolke']
x = sum(mylist)
```
This will crash at the second line.
You can't add letters.

#### List mangling

There are two functions that may be cool for handling lists.

##### Reversing
You may want to reverse a list.
`reverse()` does not return a thing - it reverses the list "in place".
```python
mylist_a = ['vycka', 'homo', 'pofke', 'rolke']
mylist_b = [4, 3, 18, -1.2]
mylist_a.reverse()
mylist_b.reverse()
```
`mylist_a` will be `['rolke', 'pofke', 'homo', 'vycka']`,
`mylist_b`: `[-1.2, 18, 3, 4]`.

##### Sorting
Sorting is usually great.
This has similar grammar to reversing a list, but it sorts elements.
It can sort numbers _and_ strings (just not mixed lists).
It sorts numbers in ascending order by their value,
and it sorts strings alphabetically in ascending order.
```python
mylist_a = ['vycka', 'homo', 'pofke', 'rolke']
mylist_b = [4, 3, 18, -1.2]
mylist_a.sort()
mylist_b.sort()
```
`mylist_a` will be `['homo', 'pofke', 'rolke', 'vycka']`,
`mylist_b`: `[-1.2, 3, 4, 18]`.

Be a tiny bit careful - sorting is sort of maybe a bit expensive,
but you'll usually not notice.
You'll only notice if you have lists with _millions_ of elements.


### Dictionaries
[Documentation](https://docs.python.org/3/tutorial/datastructures.html#dictionaries)

Dictionaries are like lists, but slightly cooler
- instead of being held at positions denoted by numbers,
they're accessed by _names_, otherwise referred to as `keys`.

This is what dictionaries look like:
```python
enis = {}
benis = {
    "john": [1,43,"thing"],
    "hess": 123,
    }
```
There `enis` is an empty dictionary,
and `benis` is a dictionary with two values.
One value of `benis` has key `"john"` and value of a list of random shit: `[1,43,"thing"]`.
The other value has key `"hess"` and value `123`.

They can hold literally any shit as value - lists, other dictionaries, whatver.
Keys have _some_ restrictions - for now let's limit them to either numbers or strings.

#### Adding to dictionaries
It's like magic.
```python
benis = {
    "john": [1,43,"thing"],
    "hess": 123,
    }
benis["burger"] = "skanus"
```
`benis` will now be
```python
benis = {
    "john": [1,43,"thing"],
    "hess": 123,
    "burger": "skanus",
    }
```
Great!

#### Accessing things in dictionaries
```python
benis = {
    "john": [1,43,"thing"],
    "hess": 123,
    "burger": "skanus",
    }
x = benis["john"]
y = benis["hess"]
z = benis["burger"]
```
`x` will have value `[1,43,"thing"]`,
`y` - `123` and
`z` - `"skanus"`

##### ADVANCED SHIT

There are three functions we may like if we wanna work on entire dictionaries.
- `dictionary.keys()`
- `dictionary.values()`
- `dictionary.items()`

`keys()` returns a list of all the keys.
```python
benis = {
    "john": [1,43,"thing"],
    "hess": 123,
    "burger": "skanus",
    }
x = benis.keys()
```
`x` will have value `["john", "hess", "burger"]`.

`values()` returns a list of all the values.
```python
benis = {
    "john": [1,43,"thing"],
    "hess": 123,
    "burger": "skanus",
    }
x = benis.values()
```
`x` will have value `[[1,43,"thing"], 123, "skanus"]`.

`items()` returns _a list key-value pairs_.
```python
benis = {
    "john": [1,43,"thing"],
    "hess": 123,
    "burger": "skanus",
    }
x = benis.items()
```
`x` will have value `[("john", [1,43,"thing"]), ("hess", 123), ("burger", "skanus")]`.

#### Deleting

Don't.

#### Mangling

Usually no need.
While order in lists usually matters,
dictionaries are looser in that sense,
as we usually access them by keys.

## Loops

Okay, now I'll introduce you to for loops.
This is gonna be the main way of working with lists and dictionaries.

The basic grammar of the for loop is such:
```python
# We're not in loop yet
for value in list:
    #do thing with value
    #do another thing with value
    #...
    #do final thing with value
# We're out of the loop
```
### Looping lists
The indentation denotes whether line of code belongs within the loop.
Let's show us an actual example:
```python
things = [1, 4, -1, 2.5]
new_things = []
for bubu in things:
    new_bubu = bubu + 1
    new_things.append(new_bubu)
    print(new_bubu)
print(new_things)
```
Let's go line by line.
The first line initializes one list with some numbers.
The second line initializes an empty list.
The third line starts a `for` loop,
noting that we're iterating over the list `things`,
with each value being temporarily assigned to `bubu`.
Then likes 4-6 are the contents of the loop.
For each element it assins the value to another variable `new_bubu`,
which is 1 larger than `bubu`.
Line 5 adds the new value `new_bubu`.
The 6th line prints the value to the terminal.
The line 7 prints the new list after we're done iterating the list.

When run it'll produce the following
```bash
<renamorcen@salomeike:~/education/python-tutorial/tutorial_python/data_structures>
zsh/4 13  (git)-[feature/data_structures]-% python test.py
2
5
0
3.5
[2, 5, 0, 3.5]
```
The first four lines come from within the for loop,
and the final line is the `new_things` new list.
All the numbers from the input are incremented by one,
and added to the new list.
Ta-da!

### Looping dictionaries.
I say we're going to loop dictionaries,
but that's a slight lie.
The functions `keys`, `values` and `items` return **lists** that correspond to the dicitonary.

```python
retard_elo = {
    "rolke": 4,
    "vycka": 900,
    "nojus": 1500,
    "efkas": 2000,
}

print("Printing old elos")
for name, elo in retard_elo.items():
    print('Person:' + name)
    print(elo)

print("Computing new elos")
new_elo = {}
for name in retard_elo.keys():
    elo = retard_elo[name]
    new_elo[name] = elo+100
print("New elos")
print(new_elo)
```

This produces the following.
```bash
<renamorcen@salomeike:~/education/python-tutorial/tutorial_python/data_structures>
zsh/4 19 [1]  (git)-[feature/data_structures]-% python test.py
Printing old elos
Person:rolke
4
Person:vycka
900
Person:nojus
1500
Person:efkas
2000
Computing new elos
New elos
{'rolke': 104, 'vycka': 1000, 'nojus': 1600, 'efkas': 2100}
```
I believe this makes sense.

## Functions

Slight detour to funcitons since we got into loops already.
Functions are reusable bits of code, and now we'll try making our own functions.

You create a function like this:

```python
def funtction_name(argument):
    # Do thing with argument.
```

This creates a function with the name and the argument :).
Let's create a function that takes a number, and increments it!

```python
def increment_number(number):
    new_number = number + 1
    return new_number
```

This function takes number, increases it by one, and returns it :).
You can call it like this
```python
x = increment_number(5)
```
`x` will have value `6`.

You can also make a funciton that increments all numbers in a list.

```python
def increment_list(old_list):
    new_list = []
    for old_value in old_list
        new_value = increment_number(old_value)
        new_list.append(new_value)
    return new_list
```

Using it:
```python
list = [1, 5, 6]
new_list = increment_list(list)
```
`new_list` will be `[2, 6, 7]`

### Philosophy

It is usually a very good idea to make the funcitons _as simple as possible_.
Functions should usually do only one thing very well so it will be easier to understand/debug.
If you want a function to do a complicated thing,
instead of writing complicated code,
break it up into simpler tasks.
Those simpler tasks have simple functions,
and the complicated funciton calls the simpler functions.
This will pay dividends.
