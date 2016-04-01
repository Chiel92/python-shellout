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
from shellout import out

files=out(r'find . -name "*.cpp" -o -name "*.h" -print0')

for f in files.z if x:
    print(f)
    matches=out(r"grep -zZ 'some regex pattern' '{filename}'", filename=f)
    print(matches.z)
```
