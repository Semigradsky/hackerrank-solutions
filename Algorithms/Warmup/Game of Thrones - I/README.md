# [Game of Thrones - I](https://www.hackerrank.com/challenges/game-of-thrones)

## Problem Statement

Dothraki are planning an attack to usurp King Robert from his kingdom. King Robert learns of this conspiracy from Raven and plans to lock the single door through which an enemy can enter his kingdom.

![door](https://cloud.githubusercontent.com/assets/1198848/5976610/f9f388b4-a8a0-11e4-99c7-53f75b8b6516.png)

But, to lock the door he needs a key that is an [anagram](https://en.wikipedia.org/wiki/Anagram) of a certain [palindrome](http://en.wikipedia.org/wiki/Palindrome) string.

The king has a string composed of lowercase English letters. Help him figure out if any anagram of the string can be a palindrome or not.

## Input Format 
A single line which contains the input string

## Constraints 

1<=length of string <= 10^5 

Each character of the string is a lowercase English letter.

## Output Format 
A single line which contains YES or NO in uppercase.

## Sample Input : 01
```
aaabbbb
```

## Sample Output : 01
```
YES
```

## Explanation 
A palindrome permutation of the given string is `bbaaabb`. 

## Sample Input : 02
```
cdefghmnopqrstuvw
```

## Sample Output : 02
```
NO
```

## Explanation 
You can verify that the given string has no palindrome permutation. 

## Sample Input : 03
```
cdcdcdcdeeeef
```

## Sample Output : 03
```
YES
```

## Explanation 
A palindrome permutation of the given string is `ddcceefeeccdd`.

## Solution

### JavaScript
```javascript
function isOdd(number) {
  return number % 2 === 1;
}

function isAnagram(input) {
  var letters = [].reduce.call(input, function(l, c) {
      !l[c] && (l[c] = 0);
      l[c]++;
      return l;
  }, {});

  var canBeOddNumber = isOdd(input.length),
      wasOddNumber = false;
  for (var letter in letters) {
    if (isOdd(letters[letter])) {
      if (!canBeOddNumber || wasOddNumber) {
        return false;
      }
      wasOddNumber = true;
    }
  }
  return true;
}

function processData(input) {
  process.stdout.write(isAnagram(input) ? 'YES' : 'NO');
} 
```