---
title: Decorator Factory - How to pass arguments to decorators
layout: post
---
_Skip to [pass arguments to decorators](#pass-arguments-to-decorators) if you already know what a decorator is_

## What is a decorator?

A decorator allows the user to add functionality to an existing function without modifying its structure. 

For example, 
We might need a way to authenticate an API call, and only then allow some data to be returned. We can streamline the authentication process by abstracting it into a decorator function.

Consider the following function that needs to be authenticated,

```python
def foo(user_id):
   # perform some DB calls
   # perform some DB writes
   pass
```

We can use a decorator as follows,

```python
def authenticate(func):
   def wrapper(*args, **kwargs):
       # perform auth checks
       if auth:
          return func(*args, **kwargs)
       else:
          raise Exception('not authenticated')

   return wrapper
```

And hence, authenticating `foo` is as simple as,

```python
@authenticate
def foo(user_id):
   # perform some DB calls
   # perform some DB writes
   pass
```
<hr>

## Pass arguments to decorators

Now that we have some knowledge of decorators, let us proceed to something more interesting. How would we pass arguments to decorators?

This is where it gets a little confusing - we will need to create a decorator factory that returns a particular decorator based on the arguments passed.

A simple use case could be when we want to **call a function multiple times**, but we do not want to write it in an explicit for loop, and neither do we want to use a for loop inside the function itself.

For example, we would want to call the function `foo` below, 10 times:

```python
def foo():
   print("Hello World")
```

In this scenario, we can create a decorator factory that takes in a `number` and returns a decorator that calls a function a `number` of times.

```python
def call(number):  # Decorator factory
    def decorator(func):
        def wraps(*args, **kwargs):
            for i in range(number):
                func(*args, **kwargs)

        return wraps

    return decorator
```

And to use the decorator factory above,

```python
@call(10)
def foo():
   print("Hello World")
```

When we call `foo` now,

```
>>> foo()
Hello World
Hello World
Hello World
Hello World
Hello World
Hello World
Hello World
Hello World
Hello World
Hello World
```

Thanks for reading! Please hit me up at sanjay.rohit2@gmail.com for any feedback :)
