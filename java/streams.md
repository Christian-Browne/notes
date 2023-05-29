# Streams

- Allow you to chain operations together
- Allows you to call stream operations:
- These are higher order functions

> Streams don't mutate original data source

`stream()` converts the data into s single stream so each element can be processed one at a time

When you're done with stream chain use tolist() to convert it back to a list if you're working with list.

`filter(Predicate<T> predicate)`

- Filters the elements of the stream based on a given predicate.

`map(Function<T, R> mapper)`

- Transforms each element of the stream using the provided mapper function.

`sorted()`

- Sorts the elements of the stream based on their natural order.

`distinct()`

- Returns a stream with distinct elements (removes duplicates).

`limit(long maxSize)`

- Returns a stream truncated to a maximum size.

`skip(long n)`

- Returns a stream after skipping the first n elements.
