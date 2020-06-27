# JAVA CHEAT SHEET

## LAMBDA
```java
(parameters) -> expression      (int x, int y) -> x + y
(parameters) -> statement       () -> System.out.println("hi " + s)
(parameters) -> { statements }  (String s) -> { int n = s.length(); return n; }
```

## OPTIONAL
```java
Optional.empty(); 
Optional.of(o);
Optional.ofNullabe(o)
```

## STREAM
```java
int[] numbers = {1, 2, 3, 4, 5};
int sum = Arrays.stream(numbers).sum();
Stream<String> stream = Stream.of("Java8", "Lambdas", "In", "Action");
Stream<String> lines = Files.lines(Paths.get("data.txt"), Charset.defaultCharset());
/*
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
*/
List<Integer> integers = Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8);
integers.stream().filter(i -> i % 2 == 0).collect(Collectors.toList());
integers.stream().sorted().limit(5).collect(Collectors.toList());
integers.stream().map(i -> i * i).collect(Collectors.toList());
integers.stream().parallel().map(i -> i * i).collect(Collectors.toList());
list.stream().collect(Collectors.joining());

List<String> strings = Arrays.asList("A", "bb", "CC", "dd");
// Map the strings to UPPERCASE and join them with the : separator
String joined = strings.stream()
        .map(String::toUpperCase)
        .collect(Collectors.joining(":")); //"A:BB:CC:DD"
```

## COLLECTIONS
```java
Collections.sort(List<T> list, Comparator<? super T> c)
Collections.sort(values, (v1, v2) -> v1.name.compareTo(v2.name));
list.replaceAll(String::toUpperCase);
integers.reduce(0, Integer::sum);
```

## CALCULATE STATISTICS
```java
List<Integer> numbers = Arrays.asList(10, 3, 2, 5, 9, 4);
IntSummaryStatistics stats = numbers.stream().mapToInt(x -> x).summaryStatistics();
stats.getCount();    //6
stats.getMin();      //2
stats.getMax();      //10
stats.getSum();      //33
stats.getAverage();  //5.5
```

## EFFECTIVELY FINAL VARIABLES
```java
String s = "foo";
// s can be referenced in the lambda
Callable<String> callable = () -> s;
callable.call();
```

