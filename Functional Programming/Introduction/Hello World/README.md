# [Hello World](https://www.hackerrank.com/challenges/fp-hello-world)

## Problem Statement

A "Hello World" program has been widely adopted as the introductory program for learning programming. So let's start with functional programming by writing the same program.

## Sample Input
```
(Nil)
```

## Sample Output
```
Hello World
```

## Method Signature
```
Number Of Parameters: 0
Parameters: []
Returns: nil
Behavior: Prints "Hello World"
```

## Solution

### Haskell
```haskell
hello_world =
    putStrLn "Hello World"

main = do
    hello_world
```

### Clojure
```clojure
(print "Hello World")
```
