# [Flipping bits](https://www.hackerrank.com/challenges/flipping-bits)

## Problem Statement

You will be given a list of 32-bits unsigned integers. You are required to output the list of the unsigned integers you get by flipping bits in its binary representation (i.e. unset bits must be set, and set bits must be unset).

## Input Format

The first line of the input contains the list size *T*. T lines follow each line having an integer from the list.

## Constraints

1 ≤ T ≤ 100

## Output Format

Output one line per element from the list with the requested result.

## Sample Input
```
3 
2147483647 
1 
0
```

## Sample Output
```
2147483648 
4294967294 
4294967295
```

## Explanation

Take `1` for example, as unsigned 32-bits is `00000000000000000000000000000001` and doing the flipping we get `11111111111111111111111111111110` which in turn is `4294967294`

## Solution

### JavaScript
```javascript
function to32Bit(number) {
    var zeroes = new Array(32).join(0);
    return (zeroes + Number(number).toString(2)).slice(-32);
}

function reverseBit(bit) {
    return 1 - bit;
}

function reverseBits(number) {
    return parseInt(to32Bit(number).split('').map(reverseBit).join(''), 2);
}

function processData(input) {
    var data = input.split('\n').slice(1);
    data = data.map(reverseBits);
    process.stdout.write(data.join('\n'));
}
```
