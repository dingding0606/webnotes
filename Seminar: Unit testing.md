# Seminar: Unit testing

-   Requirements of unit tests:
    -   run automatically, without human input
    -   determine automatically whether the test is passed or failed, without human interpretation
    -   run in isolation, separate from other test cases, even if multiple cases test the same code



-   Unittest: Python's unit testing framework



-   Errors and exceptions: exceptions are not always fatal. they can be "handled" by the program without exiting, or they can be "raised".



-   Common build-in python exceptions
    -   IndexError
    -   KeyRrror
    -   NameError: use a variable that haven't defined yet
    -   SyntaxError
    -   TypeError: eg, expect a string, but get a int
    -   ValueError



-   Unittest assert methods
    -   assertEqual(a, b)
    -   assertNotEqual(a, b)
    -   assertTrue(x)
    -   assertFalse(x)
    -   assertIs(a, b)
    -   asserIsNot(a, b)
    -   assertIsNone(x)
    -   assertIsNotNone(x)
    -   assertIn(a, b)
    -   assertNotIn(a, b)
    -   assertRaises(e, func, *args): pass in a particular value for a func, and test the output

    

**ASCII:**

A: 65

a: 97

```python
In [2]: ord("a")
Out[2]: 97

In [3]: chr(65)
Out[3]: 'A'
```