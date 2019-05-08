# Shell Programming Cheat Sheet

## Variables
```
now=$(date)
now=`date`
```
## Control structures
- if/then/else/fi
- case/in/esac

- pattern matching
```
case $str in
    a*) # matches anything starting with "a"
		foo
		;;    
    b?) # matches any two-character string starting with "b"
		bar
		;;    
    c[de]) # matches "cd" or "ce"
		baz
		;;    
    me?(e)t) # matches "met" or "meet"
		qux
		;;    
    @(a|e|i|o|u)) # matches one vowel
		fuzz
		;;   
	*)
		;;
esac
```
- while/do/done

## Test file and directory
- `-d`: if a directory exists?
- `-f`: if a file exists?
- `-s`: is empty?

## Date and Time
- [`date +"%A, %T, %B %d, %Y"`]: Friday, 10:10:00, June 30, 2016
- [`date --date="next month"`]: next month|last month|5 days ago|tomorrow|next Sunday|
- [`time <cmd>`]: timing

## Threads
- `sleep 5s/5m/5h/5d`: waits 5 seconds/minutes/hours/days