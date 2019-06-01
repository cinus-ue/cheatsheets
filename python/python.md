# PYTHON CHEAT SHEET

## REGEX
```python
import re
<str>   = re.sub(<regex>,new,text,count=0)
<list>  = re.findall(<regex>,text)
<list>  = re.split(<regex>,text,maxsplit=0)
<Match> = re.search(<regex>,text)
<Match_iter> = re.finditer(<regex>,text)
```
## MATCH OBJECT
```python
<str> = <Match>.group()  #whole match
<str> = <Match>.group(1) #part in first bracket
<int> = <Match>.start()  #start index of a match
<int> = <Match>.end()    #excusive end index of a match
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
>>>hashlib.md5(<str>.encode()).hexdigest()
```
