# SHELL PROGRAMMING CHEAT SHEET

## VARIABLES
```
now=$(date)
now=`date`
```
## CONTROL STRUCTURES
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

## TEST FILE AND DIRECTORY
- `-d`: if a directory exists?
- `-f`: if a file exists?
- `-s`: is empty?

## DATE AND TIME
- [`date +"%A, %T, %B %d, %Y"`]: Friday, 10:10:00, June 30, 2016
- [`date --date="next month"`]: next month|last month|5 days ago|tomorrow|next Sunday|
- [`time <cmd>`]: timing

## THREAD
- `sleep 5s/5m/5h/5d`: waits 5 seconds/minutes/hours/days