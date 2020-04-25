# JAVA CHEAT SHEET

# STREAM
```java
 int[] numbers = {1, 2, 3, 4, 5};
 int sum = Arrays.stream(numbers).sum();
 Stream<String> stream = Stream.of("Java8", "Lambdas", "In", "Action");
 Stream<String> lines = Files.lines(Paths.get("data.txt"), Charset.defaultCharset());
```

## COLLECTIONS
```java
 Collections.sort(List<T> list, Comparator<? super T> c)
 list.replaceAll(String::toUpperCase);
 integers.reduce(0, Integer::sum);
```

## COLLECTORS
```java
 List<Integer> integers = Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8);
 integers.stream().filter(i -> i % 2 == 0).collect(Collectors.toList());
 integers.stream().sorted().limit(5).collect(Collectors.toList());
 integers.stream().map(i -> i * i).collect(Collectors.toList());
 integers.stream().parallel().map(i -> i * i).collect(Collectors.toList());
 list.stream().collect(Collectors.joining());
```
