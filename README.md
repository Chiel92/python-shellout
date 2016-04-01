# python-shellout
Thin convenience wrappers for shelling out commands easily from python

## Example

```python
files=out(r'find . -name "*.cpp" -o -name "*.h" -print0')

for f in files.z if x:
    print(f)
    matches=out(r"grep -zZ 'some regex pattern' '{filename}'", filename=f)
    print(matches.z)
```
