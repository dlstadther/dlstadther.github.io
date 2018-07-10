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





Python3 features:
* f-strings
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
>>> x = 2
>>> print(f"{x} + {x} is {x+x} minus {3} that's {x+x-3}. Quick Maths")
"2 + 2 is 4 minus 1 that's 3. Quick Maths"
```

* dict concatentation
* dict insertion order preservation
* integar division
* packaged venv (no more system python-virtualenv installation)
* static type checking (mypy)


Python2 / Python3 Cheatsheet
http://python-future.org/compatible_idioms.html
