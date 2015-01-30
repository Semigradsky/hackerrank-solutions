# [Is Fibo](https://www.hackerrank.com/challenges/is-fibo)

## Problem Statement

You are given an integer, N. Write a program to determine if N is an element of the Fibonacci Sequence.

The first few elements of fibonacci sequence are 0,1,1,2,3,5,8,13,⋯ A fibonacci sequence is one where every element is a sum of the previous two elements in the sequence. The first two elements are 0 and 1.

Formally:

![formula](https://cloud.githubusercontent.com/assets/1198848/5976669/8d9aa21e-a8a1-11e4-80fd-8778abceb8c2.png)

## Input Format 
The first line contains T, number of test cases. 

T lines follows. Each line contains an integer N.

## Output Format 
Display IsFibo if N is a fibonacci number and IsNotFibo if it is not a fibonacci number. The output for each test case should be displayed in a new line.

## Constraints 

1≤T≤105 

1≤N≤1010

## Sample Input
```
3
5
7
8
```

## Sample Output
```
IsFibo
IsNotFibo
IsFibo
```

## Explanation 
5 is a Fibonacci number given by ** fib<sub>5</sub> = 3 + 2 **

7 is not a Fibonacci number 

8 is a Fibonacci number given by ** fib<sub>6</sub> = 5 + 3 **

## TimeLimit 
Time limit for this challenge is given [here](https://www.hackerrank.com/environment)

## Solution

### JavaScript
```javascript
var fibo = [0, 1, 1, 2, 3, 5, 8];

function isFibo(number) {
  number = +number;
  var lastCalculated = fibo.slice(-1)[0];

  if (!!~fibo.indexOf(number)) { 
    return true;
  } else {
    if (lastCalculated > number) {
      return false;
    }
  }

  var countCalculated = fibo.length;
  while (lastCalculated < number) {
    fibo.push(fibo[countCalculated - 1] + fibo[countCalculated - 2]);
    lastCalculated = fibo[countCalculated];
    countCalculated++;
  }

  return lastCalculated === number;
}

function processData(input) {
  var data = input.split('\n').slice(1);
  data = data.map(isFibo).map(function(x) { return x ? 'IsFibo' : 'IsNotFibo'; });
  process.stdout.write(data.join('\n'));
} 
```