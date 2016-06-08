# python-shellout
Thin convenience wrappers for shelling out commands easily from python

## Installation

In shell with enough admin rights type

```bash
$ git clone https://github.com/Chiel92/python-shellout
$ cd python-shellout
$ python3 setup.py install
```

## Example Usage

```python
from shellout import get

files=get(r'find . -name "*.cpp" -o -name "*.h" -print0')

for f in files.z:
    print(f)
    matches=get(r"grep -zZ 'some regex pattern' '{filename}'", filename=f)
    print(matches.z)
```

A more elaborate example can be found on [this blog post about automatically archiving merged
git branches.][archive-git-branches]

[archive-git-branches]: http://ctenbrinke.net/2016/06/07/archiving-branches-with-git/
