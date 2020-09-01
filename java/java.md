# JAVA CHEAT SHEET

## LAMBDA
```java
(parameters) -> expression      (int x, int y) -> x + y
(parameters) -> statement       () -> System.out.println("hi " + s)
(parameters) -> { statements }  (String s) -> { int n = s.length(); return n; }
```

## STREAM
```
filter    I  Stream<T>  Predicate<T> 
distinct  I  Stream<T> 
skip      I  Stream<T>  long
limit     I  Stream<T>  Long
map       I  Stream<R>  Function<T,R>
flatMap   I  Stream<R>  Function<T,Stream<R>>
sorted    I  Stream<T>  Comparator<T>
forEach   T  Void  Consumer<T>
collect   T  R     Collector<T,A,R>
reduce    T  Optional<T>  BinaryOperator<T>
count     T  Long
iterate   I  Void  Stream<T>
generate  I  Void  Stream<T>
anyMatch,noneMatch, allMatch,  T  Bool  Predicate<T>
findAny,findFirst              T  Optional<T>
```

## EFFECTIVELY FINAL VARIABLES
```java
String s = "foo";
// s can be referenced in the lambda
Callable<String> callable = () -> s;
callable.call();
```

