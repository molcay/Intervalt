
# Intervalt

Interval tree implementation in Python.

Interval trees hold intervals in tree structure 
so that overlaps can be observed faster.

[![Build Status](https://travis-ci.org/Akaame/Intervalt.svg?branch=master)](https://travis-ci.org/Akaame/Intervalt)
[![codecov](https://codecov.io/gh/molcay/Intervalt/branch/master/graph/badge.svg)](https://codecov.io/gh/molcay/Intervalt)

## Version
0.1.1dev0

## Python Version
Python 3 is supported. 
Python 3.5.2 is tested on Linux 4.13.0-37-generic #42~16.04.1-Ubuntu.

Python 2 is supported.
Python 2.7.12 is tested on Linux 4.13.0-37-generic #42~16.04.1-Ubuntu.

## Installation

#### From PyPI
- Use PyPI to install this repository:
```bash
[sudo] pip install intervalt
```

#### From Source Code
- Download this repository. Then, use:
```bash
python setup.py install
```
- or
```bash
[sudo] pip install .
```
to install this module.

## Quickstart
```python
import intervalt
# import numpy as np 
from random import randrange

vals = [(randrange(0,10),randrange(11,20)) for i in range(10)]
intervals = [intervalt.Interval(i[0],i[1]) for i in vals]
nodes = [intervalt.Node(i) for i in intervals]

tree = intervalt.IntervalBSTree(nodes[0])

for node in nodes[1:]:
    tree.add(node)
print(tree.check_overlap(intervalt.Interval(0,10)))
```

## Features

- Interval, Node, IntervalTree Structures to encapsulate logic
- Binary Search Tree based IntervalTree structure is default
- Support Node add operation
- Bintrees conditional dependency addition
- Node remove operation
- Python 2 support
- Create setup file
- Overlap check operation
- Adapter classes for bintrees.BinaryTree, bintrees.RBTree, bintrees.AVL 
- CI with Travis

## TODO

- Make classes pickleable if they are not. Check it.
- Do a pickling example
- Do a UNIX time interval tree example.
- Create Strategy pattern for each tree backend
- Create StrategyFactory pattern for creating IntervalTrees
- Implement AVL
- Implement RB Tree
- Write further testing
- Set verbosity levels
- Backend options like keras.
- Try coverall instead of coverage.py

### Python 2 Support

- @property decorator is not the same as Python 3 version syntactically.
This can be solved via deriving classes from object. [DONE]
- Bintrees conditional dependency needs to check 
if bintrees is installed or not. Checking method differs in 
different versions. [DONE]

## Test Results
Ran 20 tests in 0.001s

OK.

## Coverage

If coverage.py is installed
```bash
coverage run tests.py
coverage report --omit=/usr/*
```
gives coverage results.

Current coverage on Intervalt is %80.

## Documentation
Documentation can be reached at docs/build/html/index.html.
