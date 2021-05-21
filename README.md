[![PyPI version](https://badge.fury.io/py/pyshellout.svg)](https://badge.fury.io/py/pyshellout)

# python-shellout
Thin convenience wrappers for shelling out commands easily from python

## Installation

In shell with enough admin rights type

```bash
$ git clone https://github.com/Chiel92/python-shellout
$ cd python-shellout
$ python3 setup.py install
```

Or to obtain the version from PyPI do

```bash
$ pip install pyshellout
```

## Example Usage

```python
from pyshellout import get

files=get('find . -name "*.cpp" -o -name "*.h" -print0')

for f in files.z: # Iterate filenames separated by null bytes
    print('Current file: ' + f)
    matches=get("grep -zZ 'some multiline regex pattern' '{}'", f)  # Allows string formatting
    print(matches.z)
```

A more elaborate example can be found on [this blog post about automatically archiving merged
git branches.][archive-git-branches]
Or on this [this blog post about automatically delete merged local git branches.][delete-git-branches].

[delete-git-branches]: http://ctenbrinke.net/2016/06/16/deleting-merged-local-branches-in-git/
[archive-git-branches]: http://ctenbrinke.net/2016/06/07/archiving-branches-with-git/
