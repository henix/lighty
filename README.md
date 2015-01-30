# fundef: Function combinators for ES5

Based on ES5 and inspired by Scala, fundef aims at adding comfortable syntax for functional programming in JavaScript.

## Example

ex 1: Split a string, then trim each string, then filter the non-empty strings.

How things are done in vanilla ES5:

```js
var urls = value.split("\n").map(function(s) { return s.trim(); }).filter(function(s) { return s.length > 0; });
```

This is how to do it in Scala:

```scala
val urls = value.split("\n").map(_.trim).filter(_.length > 0);
```

With fundef, you can write JS code in Scala-style:

```js
var urls = value.split("\n").map(_.trim()).filter(_.$length.gt(0));
```

ex2: Sum an array

Scala:

```scala
val sum = List(1, 2, 3, 4).fold(0)(_ + _); // 10
```

fundef:

```js
var sum = [1, 2, 3, 4].reduce(_.add(_), 0); // 10
```

more example: see test.js
