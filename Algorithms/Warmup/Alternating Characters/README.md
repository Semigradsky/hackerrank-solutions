# [Alternating Characters](https://www.hackerrank.com/challenges/alternating-characters)

## Problem Statement

Shashank likes strings in which consecutive characters are different. For example, he likes ABABA, while he doesn't like ABAA. Given a string containing characters A and B only, he wants to change it into a string he likes. To do this, he is allowed to delete the characters in the string.

Your task is to find the minimum number of required deletions.

## Input Format 
The first line contains an integer T i.e. the number of test cases. Next T lines contain a string each.

## Output Format 
For each test case, print the minimum number of deletions required.

## Constraints
1≤T≤10 

1≤lengthofString≤105 

## Sample Input
```
5
AAAA
BBBBB
ABABABAB
BABABA
AAABBB
```

## Sample Output
```
3
4
0
0
4
```

## Explanation

AAAA => A, 3 deletions
BBBBB => B, 4 deletions
ABABABAB => ABABABAB, 0 deletions
BABABA => BABABA, 0 deletions
AAABBB => AB, 4 deletions

## Solution

### JavaScript
```javascript
function getCountDeleting(word) {
  var count = 0,
      previousSymbol = word[0];

  for (var i = 1, l = word.length; i < l; i++) {
    if (word[i] === previousSymbol) {
      count++;
    } else {
      previousSymbol = word[i];
    }
  }

  return count;
}

function processData(input) {
  var data = input.split('\n').slice(1);
  data = data.map(getCountDeleting);
  process.stdout.write(data.join('\n'));
}
```