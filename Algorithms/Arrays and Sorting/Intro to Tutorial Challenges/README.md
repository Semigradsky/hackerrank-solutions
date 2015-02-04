# [Intro to Tutorial Challenges] (https://www.hackerrank.com/challenges/tutorial-intro)

## Problem Statement

### About Tutorial Challenges 
Many of the challenges on HackerRank are difficult and assume that you already know the relevant algorithms very well. These tutorial challenges are different. They break down algorithmic concepts into smaller challenges, so that, you can learn the algorithm by solving the challenges.

These challenges are intended for those who know some programming and now want to learn some algorithms. You could be a student majoring in Computers, a self-taught programmer, or an experienced developer who wants an active algorithms review!

The first series of challenges covers sorting. The challenges are listed below:

#### Tutorial Challenges - Sorting

Insertion Sort challenges

- [Insertion Sort 1 - Inserting](https://www.hackerrank.com/challenges/insertionsort1)
- [Insertion Sort 2 - Sorting](https://www.hackerrank.com/challenges/insertionsort2)
- [Correctness and loop invariant](https://www.hackerrank.com/challenges/correctness-invariant)
- [Running Time of Algorithms](https://www.hackerrank.com/challenges/runningtime)

Quicksort challenges

- [Quicksort 1 - Partition](https://www.hackerrank.com/challenges/quicksort1)
- [Quicksort 2 - Sorting](https://www.hackerrank.com/challenges/quicksort2)
- [Quicksort In-place (advanced)](https://www.hackerrank.com/challenges/quicksort3)
- [Running time of Quicksort](https://www.hackerrank.com/challenges/quicksort4)

Counting sort challenges

- [Counting Sort 1 - Counting](https://www.hackerrank.com/challenges/countingsort1)
- [Counting Sort 2 - Simple sort](https://www.hackerrank.com/challenges/countingsort2)
- [Counting Sort 3 - Preparing](https://www.hackerrank.com/challenges/countingsort3)
- [Full Counting Sort (advanced)](https://www.hackerrank.com/challenges/countingsort4)

There will also be some challenges, where you'll get to apply your learnings.

### About the Challenges 
The challenges will describe some topic and then ask you to code a solution. As you progress through the challenges, you will learn some important concepts in algorithms. In each challenge, you will receive input on STDIN and you will need to print the correct output to STDOUT.

For many challenges, helper methods (like an array) will be provided for you to process the input into a useful format. You can use these methods to get started with your program, or you can write your own input methods if you want. Your code just needs to print the right output to each test case.

### Sample Challenge 
This is a simple challenge to get things started. Given a sorted array (ar) and a number (V), can you print the index location of V in the array?

*{The next section describes the input format. You can often skip it, if you are using included methods. }*

## Input Format 
There will be three lines of input:

V - the value that has to be searched.

n - the size of the array.

ar - n numbers that make up the array.

## Output Format 
Output the index of V in the array.

*{The next section describes the constraints and ranges of the input. You should check this section to know the range of the input. }*

## Constraints 
1<=n<=1000 

-1000 <=x <= 1000 , x ∈ ar

*{This "sample" shows the first input test case. It is often useful to go through the sample to understand a challenge. }*

## Sample Input
```
4
6
1 4 5 7 9 12
```

## Sample Output
```
1
```

## Explanation 
V = 4. The value 4 is located at the 1st index in the array, so the answer is 1.

## Solution

### JavaScript
```javascript
function binaryFindPos(el, arr, start, end) {
  if (start > end) { return -1; }

  var middle = Math.floor((start + end)/2);
  if (arr[middle] === el) { return middle; }

  if (arr[middle] < el) {
    return binaryFindPos(el, arr, middle+1, end);
  } else {
    return binaryFindPos(el, arr, start, middle-1);
  }
}

function findPos(el, arr) {
  return binaryFindPos(el, arr, 0, arr.length-1);
}

function processData(input) {
  input = input.split('\n');
  var el = +input.shift();
  var data = input.pop().split(' ').map(function (x) {
    return parseInt(x, 10);
  });

  var pos = findPos(el, data);
  process.stdout.write(pos);
} 
```