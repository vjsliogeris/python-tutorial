# Python basics!

This will cover the basics of python.
I may have forgotten to include some shit,
so if something does not make sense - ask, I may have missed it.

## How python works/reads code

Python has loads of stuff that makes it less autistic than other programming languages.
It does not demand any boilerplate-preamble bullshit.
You can open up a text file, put some code (any code), and feed it to python,
and it 'just works (tm)'.
- It reads the code line by line, trying to do whatever is in that line.
- What belongs where is generally shown in indentation, which is usually 4 spaces or a tab per level. It'll make more sense later on.
- You do not need to "declare variables". Where as some autistic languages demand an "This thing `x` is an integer and I'll only put integers there", in python you can just say `x = "kiausai" in one line, then later on say "x = 4", and it won'd bitch.
    - It will bitch if you try to do `x + 5` when `x = "kiausai"` was last run - you can't add numbers to text. A small price to pay.


## Running python
I have created a file called `bibys.txt`.
In the terminal, type
```bash
python3 bibys.txt
```
Some text should show up, akin to this
```
zsh/4 32  (git)-[main]-% python3 bibys.txt
You're supposed to put stuff here to run!
```
Ignore the `zsh/4 32  (git)-[main]-` bit - this is my specific linux bullshit.
Otherwise congratulations, you just ran python.

### On file extensions
I deliberately named the file `bibys.txt`.
There is a belief that the `.txt`, `.exe` and `.jpg` (extensions) are meaningful.
However, they are usually only meaningful to people.
Computers at most use those extensions to choose _where_ to put that file.
Windows, when you double-click a file, looks at the extension, and:
- Gives it to vlc or something if it's an `.mp3`
- Gives it to notepad if it's a `.txt`
- Gives it to python if it's a `.py`
- et cetera

Text editors also use the extensions to guess what the code is so it can properly colour text.

Since we already tell the computer to use `python3`, the extension is meaningless.
The only thing that matter is that the contents of the file is text,
and that the text is valid python.

You can now rename the file to `bibys.py` if you want to stop confusing windows
or the text editor.

## Variables

Variables are those proverbial buckets where you put data in.
As mentioned before, python does not need you to declare them explicitly.
If you have some text, an equals sign and _something_, then it's good to go.
It looks like this:
```python
finger = 12
```
The spaces are not necessary,
and instead of `finger` you can have any string of letters.
Don't put numbers in variable names - it's in bad taste and may not work.

Note that you can't assign _variables to values_.
What I mean is that
```python
12 = finger
```
is bad and will not work.

You can also assign variables values of other variables.
```python
butt = finger
```
For this to work, `finger` needs to be assigned a value beforehand,
i.e. a line
```python
finger = 12
```
must exist before the butt finger line.
Otherwise the computer won't know what value to put in butt.


### But what _are_ the things we can put in those buckets?

There are four building blocks in python:
- integers
- float
- string
- boolean

Everything in python is either one of those four,
or a bigger structure built up of those four.

#### Integers and Floats
They are numbers.
For now we don't care about the difference between them.
They take the form of digits, maybe some minus signs,
maybe some periods (no commas).
They are to do math with.
```python
finger = 12
bubu = -1.54
```
If you do
```python
gaga = finger + bubu
```
It will add the two values together, and save the result in `gaga`.
Analogous with multiplication (`*`), division(`\`), etc..
The variables there hold numbers. Yippee.

#### Bool
These are just `True`/`False` statements.
Capitalization matters in those,
because the interpreter does not know what a `true` is.
```python
plays_poe = True
drives_sober = False
```
These are used later on to do things based on conditions :)

#### String
This handles text.
Text handling is big and important and cool.
Do do a string, just surround _literally anything_ with either `"` or `'`.
```python
evaldas_word = "Big, thing, something, ass"
monkey = 'I like banana'
```
You can join them with a plus sign.
```python
som = evaldas_word + "cock" + monkey
```
Would result in the variable `som` having value `Big, thing, something, asscockI like banana`.

At this point you should be able to create basic things,
and give them names!

## Functions

Functions are smaller bits of code that we reuse.
They are denoted by parentheses after some text, as such:

```python
value = function(arguments)
```

The `function` is the name of the code.
It should describe what it does.
`arugments` are the things that the function takes and does stuff with.
`value` is the result of the function.
It is not mandatory, and if the function does not return anything,
it will have value `None`.
Funcitons that don't return a value can be called as such:
```python
function(arguments)
```

Python is very liberal with calling functions.
If a function returns a thing, but you write it as such:
```python
function(arguments)
```
It will work - you just won't have the result of the function handy at a variable.


## Input/output
Finally something that does stuff!

We generally wanna give stuff to programs so they can work on the stuff.
We also want it to give us the results back.
Usually people make python scripts read files and produce files,
but for now we'll just use the basic terminal functions.
There are two funcitons that are used for this: `print()` and `input()`.

### Printing
Printing is done via a function `print(thing)`.
The `thing` there should be a stirng,
but it's not stupid - if you give it a number it'll make it into the text of the number
and print it just as fine.
It does not return anything.
Try printing.
Type the following into a file (like `bibys.txt`, or create a new one, idc.),
```python
print('Hello world!')
```
Run the file as told beforehand
```bash
python3 namefile.py
```
And `Hello world!` should show up in you're console.
Congratulations!

### Inputs

Now we want to give things to programs.
It is done via the function called `input()`.
It takes no arguments.
When python reaches this line, the terminal waits for an input and an `enter` press.
Then it takes whatever's been typed into the terminal, and returns it.
```python
x = input()
```
This would take whatever you've typed, and put it into the variable `x` as a string.

### Putting it all together.

You can put the two of the functions together like this:

```python
print('What is your name?')
name = input()
print('Hello, ' + name)
```

The first line prints the text `What is your name?` into the terimnal.
The second line waits for the user to type something,
and puts it in the variable called `name`.
The third line does some magic --
it joins the string `Hello, ` with the user input, and prints it.

Printer suvalge popieri.

## Casting

[Inspiration lol](https://www.w3schools.com/python/python_casting.asp)

"Casting" is a computer term for "converting one datatype into another".
`print()` does that when you tell it to print a number - behind the scenes
it converts the integer/float into a string, and then puts it on your terminal.

You may need to do that in some occasion, e.g. when you want to input numbers from the terminal.
Casting is done via these three functions:
- `int(thing)` tries to convert `thing` into an integer
- `str(thing)` tries to convert `thing` into a string
- `float(thing)` tries to convert `thing` into a float.
Just be careful - if you try to convert text to a number,
it will crash.

### Joining Inputs/Ouptuts with numbers

In the following code:
```python
print('What is your name?')
name = input()
print('Hello, ' + name)
```
If you type in a digit instead of text,
the program will not crash.
Let's try making a program which returns a larger number.

```python
print('Give me a number')
number = input()
print(number + 1)
```

This program will not work.
This is because `input()` returns a string.
Conerting things into strings is usually easy.
Convertings strings into things is ass.
That's why it's not the default,
and when you try to add a number to a string,
it doesn't even try and just crashes.
In the third line it tries to add the number 1 to the text of a number.
For this we need casting.

Just modify the code as such:

```python
print('Give me a number')
number = int(input())
print(number + 1)
```
And it works!
Just don't type any text.

Congratulations, you can now write the most basic programs that can cover a lot of things!
Checkout the `homework/` folder for homework so you know you've done did it.
