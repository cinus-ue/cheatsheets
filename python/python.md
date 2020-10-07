# PYTHON CHEAT SHEET

## FORMAT
```python
<str> = f'{<el_1>}, {<el_2>}'
<str> = '{}, {}'.format(<el_1>, <el_2>)
```
## LAMBDA
```python
<function> = lambda: <return_value>
<function> = lambda <argument_1>, <argument_2>: <return_value>
```

## READ FILE
```python
def read_file{(ilename):
    with open(filename,encoding='utf-8') as file:
        return file.readlines()
```        

## WRITE TO FILE
```python
def write_to_file(filename,text):
    with open(filename,'w',encoding='utf-8') as file:
        file.write(text)
```

## HASHLIB
```python
hashlib.md5(<str>.encode()).hexdigest()
```

## PRINT
```python
print(<el_1>, ..., sep=' ', end='\n', file=sys.stdout, flush=False)

from pprint import pprint
pprint(<collection>, width=80, depth=None, compact=False, sort_dicts=True)
```

## EXCEPTION
```python
class MyError(Exception):
    pass
class MyInputError(MyError):
    pass

raise <exception>
raise <exception>()
raise <exception>(<el> [, ...])

try:
    <code>
except <exception>:
    <code>

```

## TERNARY CONDITIONAL OPERATOR
```python
<expression1> if <condition> else <expression2>
```

## DATACLASS
```python
from dataclasses import dataclass, field

@dataclass(order=False, frozen=False)
class <class_name>:
    <attr_name_1>: <type>
    <attr_name_2>: <type> = <default_value>
    <attr_name_3>: list/dict/set = field(default_factory=list/dict/set)
```

## COPY
```python
from copy import copy, deepcopy
<object> = copy(<object>)
<object> = deepcopy(<object>)
```