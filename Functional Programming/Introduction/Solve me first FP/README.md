# [Solve me first FP](https://www.hackerrank.com/challenges/fp-solve-me-first)

## Problem Statement

This is an introductory challenge. The purpose of this challenge is to give you a working I/O template in your preferred language. It includes scanning 2 integers from STDIN, calling a function, returning a value, and printing it to STDOUT.

Your task is to scan two numbers from STDIN, and print the sum A+B on STDOUT.

## Input Format 
Given A and B on two different lines.

## Output Format 
An integer that denotes Sum (A + B)

## Constraints 
1 ≤ A, B ≤ 1000

## Sample Input
```
2
3
```

## Sample Output
```
5
```

## Solution

### Haskell

```haskell
solveMeFirst a b = a + b

main = do
    val1 <- readLn
    val2 <- readLn
    let sum = solveMeFirst val1 val2
    print sum
```

### Clojure

```clojure
(defn solveMeFirst [x y]    
    (+ x y))

(def a (read-line))
(def b (read-line))

(println (solveMeFirst (Integer/parseInt a) (Integer/parseInt b)))
```
