# [Hello World N Times](https://www.hackerrank.com/challenges/fp-hello-world-n-times)

## Problem Statement

Print "Hello World" N times. The input portion will be handled automatically. You need to write a function with the recommended method signature.

## Input Format
An Integer N which is the number of times we need to print "Hello World".

## Output Format
N lines, each containing "Hello World".

## Constraints
0<=N<=50

## Sample Input
```
4
```

## Sample Output
```
Hello World
Hello World
Hello World
Hello World
```

## Recommended Method Signature
```
Number Of Parameters: 1
Parameters: [n]
Returns: nil
```

## Solution

### Haskell
```haskell
hello_worlds n =
    sequence_ [putStrLn "Hello World" | i <- [1..n]]

main = do
    n <- readLn :: IO Int
    hello_worlds n
```

### Clojure
```clojure
(fn[n] (dotimes [_ n] (println "Hello World")))
```
