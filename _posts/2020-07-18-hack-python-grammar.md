---
title: Hack Python Grammar
layout: post
---

This is a quick post about how you can hack the Python grammar and define your own constructs.

In this short tutorial we'll be seeing how you can define your own words to replace the `pass` statement in Python.

Here's what you'll need to do:

1. Start by cloning the CPython repository and installing the dev version of Python3

    ```bash
    git clone https://github.com/python/cpython.git
    cd cpython
    ./configure
    make -j2 -s
    ```

2. Edit the `Grammar/Grammar`, and add to the `pass_stmt` directive as follows:

    ```code
    ...
    pass_stmt: 'pass' | 'proceed' | 'anythingyouwant'
    ...
    ```

3. Regenerate the grammar by running:

    ```bash
    make regen-grammar
    ```

4. Recompile the Python source code

    ```bash
    make -j2 -s
    ```

5. Run the Python interpreter

    ```bash
    ./python.exe -X oldparser
    ```

6. Use the pass statement in your code and verify that it works, and feel proud!

    ```python
    def foo():
        proceed

    foo()
    ```

That's it! Pretty amazing isn't it? 😃

## References

- Take a look at this amazing book on [CPython internals by Anthony Shaw](https://realpython.com/products/cpython-internals-book/) for more details
- [Talk by Pablo Salgado at EuroPython 2019](https://www.youtube.com/watch?v=1_23AVsiQEc) explaining everything about the Python parser generator
