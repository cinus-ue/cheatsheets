# JMAP CHEAT SHEET

## OPTIONS FOR YHE JMAP COMMAND
```
-clstats pid
Connects to a running process and prints class loader statistics of Java heap.

-finalizerinfo pid
Connects to a running process and prints information on objects awaiting finalization.

-histo[:live] pid
Connects to a running process and prints a histogram of the Java object heap. If the live suboption is specified, it then counts only live objects.

-dump:dump_options pid
Connects to a running process and dumps the Java heap. The dump_options include:

live — When specified, dumps only the live objects; if not specified, then dumps all objects in the heap.

format=b — Dumps the Java heap,. in hprof binary format

file=filename — Dumps the heap to filename

Example: jmap -dump:live,format=b,file=heap.bin pid
```