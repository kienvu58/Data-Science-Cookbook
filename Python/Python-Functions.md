
> Written with [StackEdit](https://stackedit.io/).

# Python Functions Tutorial

### References

- [Python Functions Tutorial](https://bit.ly/2DDlBsF)

Functions are an essential part of the Python programming language: you might have already encountered and used some of the many fantastic functions that are built-in in the Python language or that come with its library ecosystem. However, as a Data Scientist, you’ll constantly need to write your own functions to solve problems that your data poses to you.

That’s why this post will introduce you to functions in Python. You’ll cover the following topics:

## Functions in Python

You use functions in programming to bundle a set of instructions that you want to use repeatedly or that, because of their complexity, are better self-contained in a sub-program and called when needed. That means that a function is a piece of code written to carry out a specified task. To carry out that specific task, the function might or might not need multiple inputs. When the task is carried out, the function can or can not return one or more values.

There are three types of functions in Python:
- Built-in functions, such as  `help()`  to ask for help,  `min()`  to get the minimum value,  `print()`to print an object to the terminal,… You can find an overview with more of these functions  [here](https://docs.python.org/3/library/functions.html).
-   User-Defined Functions (UDFs), which are functions that users create to help them out; And
-   Anonymous functions, which are also called lambda functions because they are not declared with the standard  `def`  keyword.

### Functions vs Methods

A method refers to a function which is part of a class. You access it with an instance or object of the class. A function doesn’t have this restriction: it just refers to a standalone function. This means that all methods are functions, but not all functions are methods.

Consider this example, where you first define a function `plus()` and then a `Summation` class with a `sum()` method:

```python
# Define a function `plus()`
def plus(a,b):
  return a + b
  
# Create a `Summation` class
class Summation(object):
  def sum(self, a, b):
    self.contents = a + b
    return self.contents 
```
If you now want to call the `sum()` method that is part of the `Summation` class, you first need to define an instance or object of that class. So, let’s define such an object:

```python
# Instantiate `Summation` class to call `sum()`
sumInstance = Summation()
sumInstance.sum(1,2)
```
Output:
```
3
```
Remember that this instantiation not necessary for when you want to call the function `plus()`! You would be able to execute `plus(1,2)`:

```python
plus(1,2)
```
Output:
```
3
```
### Parameters vs Arguments

Parameters are the names used when defining a function or a method, and into which arguments will be mapped. In other words, arguments are the things which are supplied to any function or method call, while the function or method code refers to the arguments by their parameter names.

Consider the following example and look back to the above chunk: you pass two  _arguments_  to the  `sum()`  method of the  `Summation`  class, even though you previously defined three  _parameters_, namely,  `self`,  `a`  and  `b`.

What happened to  `self`?

The first argument of every class method is always a reference to the current instance of the class, which in this case is  `Summation`. By convention, this argument is called  `self`.

This all means that you don’t pass the reference to  `self`  in this case because  `self`  is the parameter name for an implicitly passed argument that refers to the instance through which a method is being invoked. It gets inserted implicitly into the argument list.

## How To Define A Function: User-Defined Functions (UDFs)

The four steps to defining a function in Python are the following:

1.  Use the keyword  `def`  to declare the function and follow this up with the function name.
2.  Add parameters to the function: they should be within the parentheses of the function. End your line with a colon.
3.  Add statements that the functions should execute.
4.  End your function with a return statement if the function should output something. Without the return statement, your function will return an object  `None`.

```python
def hello():
  print("Hello World") 
  return 

hello()
```
Output:
```
Hello World
```
Of course, your functions will get more complex as you go along: you can add for loops, flow control, … and more to it to make it more finegrained:

```python
def hello():
  name = str(input("Enter your name: "))
  if name:
    print ("Hello " + str(name))
  else:
    print("Hello World") 
  return 
  
hello()
```
In the above function, you ask the user to give a name. If no name is given, the function will print out “Hello World”. Otherwise, the user will get a personalized “Hello” response.

**Remember**  also that you can define one or more function parameters for your UDF. You’ll learn more about this when you tackle the Function Arguments section. Additionally, you can or can not return one or multiple values as a result of your function.

### The  `return`  Statement

Note that as you’re printing something in your UDF  `hello()`, you don’t really need to return it. There won’t be any difference between the function above and this one:

```py
def hello_noreturn():
  print("Hello World") 
```


<!--stackedit_data:
eyJoaXN0b3J5IjpbNDczNjY3MzczLC0xOTE4NDkxMzk1LC0xNz
M0MjMxMjA2XX0=
-->