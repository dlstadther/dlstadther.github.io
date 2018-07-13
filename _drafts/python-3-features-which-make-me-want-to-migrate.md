---
layout: post
title: "Python 3 Features Which Make Me Want to Migrate"
date: 2018-06-13
categories: python code
---

I understand that Python3 was released nearly 10 years ago. However, I'm still on the Python 2.7 train.

My experience with Python came out of nowhere, with no strong reason (at least that I can recall).

As it's not the point of this post, I'll summarize my Python experieneces in bullet form.

* Summer 2014 - needed scripting language for file scraping and data processing for [static Android manifest analysis](https://ieeexplore.ieee.org/document/7035780/) (2.7.7)
* Spring 2015 - CISS 423: Survery of Programming Languages (2.7.9)
* Summer 2015 - inherited existing ETL processes (2.7.8)
* Spring 2016 : Current - assisted in maintenance and development of spotify/luigi.git (2.7, 3.3, 3.4, 3.5, 3.6)
* Summer 2018 : Current - authored republicwireless/webmercator (2.7, 3.5, 3.6, 3.7)

With the end of Python 2.7 support quickly approaching, I recognize the need to migrate all my work and personal work to be Python 3 compatible. Perhaps "need" is a bit extreme - mostly just a desire. Python 3 brings improved function and new features - some of which I've found myself wishing I could currently use in existing development.





## Python3 features:

### f-strings
There are many methods of string formatting in Python 2:

String Concatenation
```python
>>> print(str(2) + " + " + str(2) + " is " + str(4) + " minus " + str(1) + " that's " + str(3) + ". Quick Maths")
"2 + 2 is 4 minus 1 that's 3. Quick Maths"
```

Printf-Style
```python
>>> print("%d + %i is %i minus %d that's %i. Quick Maths" % (2, 2, 4, 3, 1))
"2 + 2 is 4 minus 1 that's 3. Quick Maths"
```

str.format
```python
>>> print("{} + {} is {} minus {} that's {}. Quick Maths".format(2, 2, 4, 3, 1))
"2 + 2 is 4 minus 1 that's 3. Quick Maths"

>>> print("{1} + {1} is {3} minus {2} that's {0}. Quick Maths".format(1, 2, 3, 4))
"2 + 2 is 4 minus 1 that's 3. Quick Maths"

>>> nums = {'one': 1, 'two': 2, 'three': 3, 'four': 4}
>>> print("{two} + {two} is {four} minus {three} that's {one}. Quick Maths".format(**nums))
"2 + 2 is 4 minus 1 that's 3. Quick Maths"
```

But Python 3.6 released a new string formatting method, called formatted string literals (or f-strings). This new way allows for the use of embedded Python expressions and variables inside string constaints.

f-strings
```python
Python 3.6+
>>> x = 2
>>> print(f"{x} + {x} is {x+x} minus {3} that's {x+x-3}. Quick Maths")
"2 + 2 is 4 minus 1 that's 3. Quick Maths"
```

### Dict Merging (3.5+)

Python 3.5+ allows the merging of multiple dictionaries using intuitive dictionary declaration curly braces (PEP 448):

```python
Python 3.5+
>>> x = {'foo': 123, 'bar': 'abc'}
>>> y = {'bar': 456}
>>> z = {**x, **y}
>>> print(z)
{'foo': 123, 'bar': 456}

>>> a = {**y, **x}
>>> print(a)
{'bar': 'abc', 'foo': 123}

>>> b = {'doge': 'wow', **z}
>>> print(b)
{'doge': 'wow', 'foo': 123, 'bar': 456}
```

Currently, in Python 2 (or 3.4-) a few additional lines are required

```python
def merge_dicts(*dicts):
    z = {}
    for d in dicts:
        z.update(d)
    return z

>>> w = {'foo': 'zyx'}
>>> x = {'foo': 123, 'bar': 'abc'}
>>> y = {'bar': 456}
>>> z = merge_dicts(w, x, y)
>>> print(z)
{'foo': 123, 'bar': 456}
```


### Dict Keeps Insertion Order (3.6+)

Python 3.5- does not guantee the key order of a normal dictionary:

```python
Python 3.5-
>>> x = {'foo': 123, 'bar': 'abc'}
>>> print(x)
{'bar': 'abc', 'foo': 123}

>>> a = {}
>>> a['foo'] = 1
>>> a['bar'] = 2
>>> a['doge'] = 3
>>> print(a)
{'wow': 3, 'foo': 1, 'bar': 2}
```

However, in Python 3.6+ the standard behavior of dictionaries is to maintain insertion order

```python
Python 3.6+
>>> x = {'b': 1, 'c': 2}
>>> x['a': 0]
>>> print(x)
{'b': 1, 'c': 2, 'a': 0}
```


### Default Float Division

When starting out with Python 2.x, everyone gets bitten by the following:

```python
Python 2.x
>>> print(3 / 2)
1
```

and we quickly learn that the `/` operator in Python 2.x performs integer division (also referred to as floor division).

In order to perform floating division in Python 2.x, we learn to cast at least one of the operands to a float.

```python
Python 2.x
>>> a = 3 / float(2)
>>> b = float(3) / 2
>>> c = float(3) / float(2)
>>> d = 3.0 / 2
>>> e = 3 / 2.0
>>> f = 3.0 / 2.0

>>> print(set((a, b, c, d, e, f)))
set(1.5)
```

While this is easy, it's annoying. Python 3.x switched the default division operator, `/`, to perform floating division such that:

```python
Python 3.x
>>> print(3 / 2)
1.5
```

So now if you want integer division (for whatever reason), you use the operator `//`.

```python
Python 3.x
>>> print(3 // 2)
1
```

It's worth noting that Python 2.x includes the Python 3.x division functionality within its `__future__` import such that Python 2.x can be compatible with Python 3.x division.

```python
Python 2.x
>>> from __future__ import division
>>> print(3 / 2)
1.5
```


### packaged venv (no more system python-virtualenv installation)

Python 2
```shell
sudo pip install virtualenv
virtualenv /path/to/venv
```

Python 3
```shell
python3 -m venv /path/to/venv
```

### static type checking (mypy)


Python2 / Python3 Cheatsheet
http://python-future.org/compatible_idioms.html
