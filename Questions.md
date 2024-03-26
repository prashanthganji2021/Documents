## 1. Find a peak element which is not smaller than its neighbours

``` javascript
// Given an array arr[] of integers. Find a peak element i.e. an element that is not smaller than its neighbors. 
// Note: For corner elements, we need to consider only one neighbor. 
// Example:
// Input: array[]= {5, 10, 20, 15}
// Output: 20
// Explanation: The element 20 has neighbors 10 and 15, both of them are less than 20.
// let arr = [5, 10, 20, 15]
let arr = [5, 10, 20, 15]

let outputOne = arr.filter((x,i) => x > arr[i-1] && x > arr[i+1])  
// filter will return an array of elements that pass the condition - in this case, x > arr[i-1] && x > arr[i+1] - which is the same as the forEach loop below but in one line of code
// x: the current element being processed in the array, i: the index of the current element being processed in the array
// 5 > arr[-1] = undefined --> false && 5 > arr[1] = 10 --> false, so 5 is not pushed into the output array , 
// 10 > arr[-1] = 5 --> true && 10 > arr[1] = 20 --> false, so 10 is not pushed into the output array, 
// 20 > arr[-1] = 10 --> true && 20 > arr[1] = 15 --> true, so 20 is pushed into the output array, 
// 15 > arr[-1] = 20 --> false && 15 > arr[1] = undefined --> false, so 15 is not pushed into the output array
let outputTWO = arr.map((x,i) => x > arr[i-1] && x > arr[i+1] ? x : null).filter(x => x !== null)
// map will return an array of elements that pass the condition - in this case, x > arr[i-1] && x > arr[i+1] - which is the same as the forEach loop below but in one line of code
// x: the current element being processed in the array, i: the index of the current element being processed in the array
// after the map function --> [null, null, 20, null] --> filter will return an array of elements that are not null, so [20] is returned
let outputFour = arr.reduce((acc, x, i) => x > arr[i-1] && x > arr[i+1] ? acc.push(x) : acc, [])
// acc: the accumulator accumulates the callback's return values; it is the accumulated value previously returned in the last invocation of the callback, or initialValue, if supplied (see below).
// x: the current element being processed in the array, i: the index of the current element being processed in the array
// [], 5, 0 --> [], 10, 1 --> [], 20, 2 --> [20], 15, 3 --> [20] --> outputFour = [20]
let outputFive = []
arr.forEach((x,i) => { 
  if (x > arr[i-1] && x > arr[i+1]) {
    outputFive.push(x)
  }
})
// x: the current element being processed in the array, i: the index of the current element being processed in the array
// 5 > arr[-1] = undefined --> false && 5 > arr[1] = 10 --> false, so 5 is not pushed into the output array , 
// 10 > arr[-1] = 5 --> true && 10 > arr[1] = 20 --> false, so 10 is not pushed into the output array,
// 20 > arr[-1] = 10 --> true && 20 > arr[1] = 15 --> true, so 20 is pushed into the output array,
// 15 > arr[-1] = 20 --> false && 15 > arr[1] = undefined --> false, so 15 is not pushed into the output array
let outputSix = []
for (let i = 0; i < arr.length; i++) {
  if (arr[i] > arr[i-1] && arr[i] > arr[i+1]) {
    outputSix.push(arr[i])
  }
}
// i = 0 --> 5 > arr[-1] = undefined --> false && 5 > arr[1] = 10 --> false, so 5 is not pushed into the output array ,
// i = 1 --> 10 > arr[0] = 5 --> true && 10 > arr[2] = 20 --> false, so 10 is not pushed into the output array,
// i = 2 --> 20 > arr[1] = 10 --> true && 20 > arr[3] = 15 --> true, so 20 is pushed into the output array,
// i = 3 --> 15 > arr[2] = 20 --> false && 15 > arr[4] = undefined --> false, so 15 is not pushed into the output array
```

## 2. Program to find the minimum (or maximum) element of an array
``` javascript
// Given an array, write functions to find the minimum and maximum elements in it. 

// The most simplest way to find min and max value of an element 

let arrayTest = [5, 10, 20, 15]

let min = Math.min(...arrayTest)
// The spread operator allows an expression to be expanded in places where multiple arguments (for function calls) or multiple elements (for array literals) are expected.
// Math.min(5, 10, 20, 15) --> 5
let max = Math.max(...arrayTest)
// Math.max(5, 10, 20, 15) --> 20

// method 2
let minTwo = arrayTest.reduce((acc, x) => acc < x ? acc : x)
// acc: the accumulator accumulates the callback's return values; it is the accumulated value previously returned in the last invocation of the callback, or initialValue, if supplied (see below).
// x: the current element being processed in the array
// 5, 10 --> 5, 20 --> 5, 15 --> minTwo = 5
let maxTwo = arrayTest.reduce((acc, x) => acc > x ? acc : x)
// acc: the accumulator accumulates the callback's return values; it is the accumulated value previously returned in the last invocation of the callback, or initialValue, if supplied (see below).
// x: the current element being processed in the array
// 5, 10 --> 10, 20 --> 20, 15 --> maxTwo = 20

// method 3
let minThree = arrayTest.sort((a,b) => a - b)[0]
// sort will sort the array in ascending order
// a - b --> 5 - 10 = -5 --> -5 - 20 = -25 --> -25 - 15 = -40

let maxThree = arrayTest.sort((a,b) => b - a)[0]
// sort will sort the array in descending order
// b - a --> 10 - 5 = 5 --> 20 - 5 = 15 --> 15 - 5 = 10

// method 4
let minFour = arrayTest.sort((a,b) => a > b ? 1 : -1)[0]
// sort will sort the array in ascending order
// a > b ? 1 : -1 --> 5 > 10 ? 1 : -1 --> -1 --> 10 > 20 ? 1 : -1 --> -1 --> 20 > 15 ? 1 : -1 --> 1

let maxFour = arrayTest.sort((a,b) => a > b ? -1 : 1)[0]
// sort will sort the array in descending order
// a > b ? -1 : 1 --> 5 > 10 ? -1 : 1 --> 1 --> 10 > 20 ? -1 : 1 --> 1 --> 20 > 15 ? -1 : 1 --> -1

// method 5
let minFive = arrayTest.sort((a,b) => a - b).shift()
// sort will sort the array in ascending order
// a - b --> 5 - 10 = -5 --> -5 - 20 = -25 --> -25 - 15 = -40
// shift will remove the first element of the array and return that element
// 5, 10, 15, 20 --> 10, 15, 20 --> 15, 20 --> 20 --> minFive = 5

let maxFive = arrayTest.sort((a,b) => b - a).shift()

// sort will sort the array in descending order
// b - a --> 10 - 5 = 5 --> 20 - 5 = 15 --> 15 - 5 = 10
// shift will remove the first element of the array and return that element
// 5, 10, 15, 20 --> 10, 15, 20 --> 15, 20 --> 20 --> maxFive = 20
```


## 3. Write a program to reverse an array or string
``` javascript
// Given an array (or string), the task is to reverse the array/string.
// Examples : 
// Input  : arr[] = {1, 2, 3}  
// Output : arr[] = {3, 2, 1}  
let arrayTestTwo = [1, 2, 3]
// method 1
let outputSeven = arrayTestTwo.reverse()
// reverse will reverse the array
// [1, 2, 3] --> [3, 2, 1] --> outputSeven = [3, 2, 1]

// method 2
let outputEight = arrayTestTwo.reduce((acc, x) => [x, ...acc], [])
// acc: the accumulator accumulates the callback's return values; it is the accumulated value previously returned in the last invocation of the callback, or initialValue, if supplied (see below).
// x: the current element being processed in the array
// [], 1 --> [1] --> [2, 1] --> [3, 2, 1] --> outputEight = [3, 2, 1]

// method 3
let outputNine = []
for (let i = arrayTestTwo.length - 1; i >= 0; i--) {
  outputNine.push(arrayTestTwo[i])
}

// i = 2 --> outputNine = [3] --> i = 1 --> outputNine = [3, 2] --> i = 0 --> outputNine = [3, 2, 1] --> outputNine = [3, 2, 1]

// method 4
let outputTen = []
arrayTestTwo.forEach(x => outputTen.unshift(x))
// x: the current element being processed in the array
// 1 --> [1] --> 2 --> [2, 1] --> 3 --> [3, 2, 1] --> outputTen = [3, 2, 1]

// method 5
let outputEleven = []
for (let i = 0; i < arrayTestTwo.length; i++) {
  outputEleven.unshift(arrayTestTwo[i])
}
```

## 4 program to sort an array in ascending order
![image](https://github.com/prashanthganji2021/Documents/assets/111948535/c9b0e9ad-498a-43c8-8e7c-86186c618017)

``` javascript

// Given an array arr[] of size N, the task is to sort this array in ascending order in C.
// Examples: 

// Input: arr[] = {0, 23, 14, 12, 9}
// Output: {0, 9, 12, 14, 23}

// Input: arr[] = {7, 0, 2}
// Output: {0, 2, 7}
// Recommended: Please try your approach on {IDE} first, before moving on to the solution.
// Approach: 
// There are many ways by which the array can be sorted in ascending order, like:  

// Selection Sort
// Bubble Sort
// Merge Sort
// Radix Sort
// Insertion Sort, etc

// method 1 : Selection Sort
let arrayTestThree = [0, 23, 14, 12, 9]
let outputTwelve = []
for (let i = 0; i < arrayTestThree.length; i++) {
  let min = Math.min(...arrayTestThree)
  outputTwelve.push(min)
  arrayTestThree.splice(arrayTestThree.indexOf(min), 1)
}

// i = 0 --> min = 0 --> outputTwelve = [0] --> arrayTestThree = [23, 14, 12, 9]
// i = 1 --> min = 9 --> outputTwelve = [0, 9] --> arrayTestThree = [23, 14, 12]
// i = 2 --> min = 12 --> outputTwelve = [0, 9, 12] --> arrayTestThree = [23, 14]
// i = 3 --> min = 14 --> outputTwelve = [0, 9, 12, 14] --> arrayTestThree = [23]
// i = 4 --> min = 23 --> outputTwelve = [0, 9, 12, 14, 23] --> arrayTestThree = []

// method 2 : Bubble Sort
let arrayTestFour = [0, 23, 14, 12, 9]
let outputThirteen = []
for (let i = 0; i < arrayTestFour.length; i++) {
  for (let j = 0; j < arrayTestFour.length; j++) {
    if (arrayTestFour[j] > arrayTestFour[j+1]) {
      let temp = arrayTestFour[j]
      arrayTestFour[j] = arrayTestFour[j+1]
      arrayTestFour[j+1] = temp
    }
  }
}
// i = 0, j = 0 --> 0 > 23 --> false --> j = 1 --> 23 > 14 --> true --> temp = 23 --> arrayTestFour = [0, 14, 23, 12, 9]
// i = 0, j = 1 --> 14 > 23 --> false --> j = 2 --> 23 > 12 --> true --> temp = 23 --> arrayTestFour = [0, 14, 12, 23, 9]
// i = 0, j = 2 --> 12 > 23 --> false --> j = 3 --> 23 > 9 --> true --> temp = 23 --> arrayTestFour = [0, 14, 12, 9, 23]
// i = 0, j = 3 --> 9 > 23 --> false --> j = 4 --> 23 > undefined --> false --> arrayTestFour = [0, 14, 12, 9, 23]

// i = 1, j = 0 --> 0 > 14 --> false --> j = 1 --> 14 > 12 --> true --> temp = 14 --> arrayTestFour = [0, 12, 14, 9, 23]
// i = 1, j = 1 --> 12 > 14 --> false --> j = 2 --> 14 > 9 --> true --> temp = 14 --> arrayTestFour = [0, 12, 9, 14, 23]
// i = 1, j = 2 --> 9 > 14 --> false --> j = 3 --> 14 > 23 --> false --> arrayTestFour = [0, 12, 9, 14, 23]
// i = 1, j = 3 --> 14 > 23 --> false --> j = 4 --> 23 > undefined --> false --> arrayTestFour = [0, 12, 9, 14, 23]

// i = 2, j = 0 --> 0 > 12 --> false --> j = 1 --> 12 > 9 --> true --> temp = 12 --> arrayTestFour = [0, 9, 12, 14, 23]
// i = 2, j = 1 --> 9 > 12 --> false --> j = 2 --> 12 > 14 --> false --> arrayTestFour = [0, 9, 12, 14, 23]
// i = 2, j = 2 --> 12 > 14 --> false --> j = 3 --> 14 > 23 --> false --> arrayTestFour = [0, 9, 12, 14, 23]
// i = 2, j = 3 --> 14 > 23 --> false --> j = 4 --> 23 > undefined --> false --> arrayTestFour = [0, 9, 12, 14, 23]

// i = 3, j = 0 --> 0 > 9 --> false --> j = 1 --> 9 > 12 --> false --> arrayTestFour = [0, 9, 12, 14, 23]
// i = 3, j = 1 --> 9 > 12 --> false --> j = 2 --> 12 > 14 --> false --> arrayTestFour = [0, 9, 12, 14, 23]
// i = 3, j = 2 --> 12 > 14 --> false --> j = 3 --> 14 > 23 --> false --> arrayTestFour = [0, 9, 12, 14, 23]
// i = 3, j = 3 --> 14 > 23 --> false --> j = 4 --> 23 > undefined --> false --> arrayTestFour = [0, 9, 12, 14, 23]

// i = 4, j = 0 --> 0 > 9 --> false --> j = 1 --> 9 > 12 --> false --> arrayTestFour = [0, 9, 12, 14, 23]
// i = 4, j = 1 --> 9 > 12 --> false --> j = 2 --> 12 > 14 --> false --> arrayTestFour = [0, 9, 12, 14, 23]
// i = 4, j = 2 --> 12 > 14 --> false --> j = 3 --> 14 > 23 --> false --> arrayTestFour = [0, 9, 12, 14, 23]
// i = 4, j = 3 --> 14 > 23 --> false --> j = 4 --> 23 > undefined --> false --> arrayTestFour = [0, 9, 12, 14, 23]


// method 3 : Merge Sort
let arrayTestFive = [0, 23, 14, 12, 9]
let outputFourteen = []
for (let i = 0; i < arrayTestFive.length; i++) {
  for (let j = 0; j < arrayTestFive.length; j++) {
    if (arrayTestFive[j] > arrayTestFive[j+1]) {
      let temp = arrayTestFive[j]
      arrayTestFive[j] = arrayTestFive[j+1]
      arrayTestFive[j+1] = temp
    }
  }
}
// i = 0, j = 0 --> 0 > 23 --> false --> j = 1 --> 23 > 14 --> true --> temp = 23 --> arrayTestFive = [0, 14, 23, 12, 9]
// i = 0, j = 1 --> 14 > 23 --> false --> j = 2 --> 23 > 12 --> true --> temp = 23 --> arrayTestFive = [0, 14, 12, 23, 9]
// i = 0, j = 2 --> 12 > 23 --> false --> j = 3 --> 23 > 9 --> true --> temp = 23 --> arrayTestFive = [0, 14, 12, 9, 23]
// i = 0, j = 3 --> 9 > 23 --> false --> j = 4 --> 23 > undefined --> false --> arrayTestFive = [0, 14, 12, 9, 23]
// i = 0, j = 4 --> 23 > undefined --> false --> arrayTestFive = [0, 14, 12, 9, 23]

// i = 1, j = 0 --> 0 > 14 --> false --> j = 1 --> 14 > 12 --> true --> temp = 14 --> arrayTestFive = [0, 12, 14, 9, 23]
// i = 1, j = 1 --> 12 > 14 --> false --> j = 2 --> 14 > 9 --> true --> temp = 14 --> arrayTestFive = [0, 12, 9, 14, 23]
// i = 1, j = 2 --> 9 > 14 --> false --> j = 3 --> 14 > 23 --> false --> arrayTestFive = [0, 12, 9, 14, 23]
// i = 1, j = 3 --> 14 > 23 --> false --> j = 4 --> 23 > undefined --> false --> arrayTestFive = [0, 12, 9, 14, 23]
// i = 1, j = 4 --> 23 > undefined --> false --> arrayTestFive = [0, 12, 9, 14, 23]

// i = 2, j = 0 --> 0 > 12 --> false --> j = 1 --> 12 > 9 --> true --> temp = 12 --> arrayTestFive = [0, 9, 12, 14, 23]
// i = 2, j = 1 --> 9 > 12 --> false --> j = 2 --> 12 > 14 --> false --> arrayTestFive = [0, 9, 12, 14, 23]
// i = 2, j = 2 --> 12 > 14 --> false --> j = 3 --> 14 > 23 --> false --> arrayTestFive = [0, 9, 12, 14, 23]
// i = 2, j = 3 --> 14 > 23 --> false --> j = 4 --> 23 > undefined --> false --> arrayTestFive = [0, 9, 12, 14, 23]
// i = 2, j = 4 --> 23 > undefined --> false --> arrayTestFive = [0, 9, 12, 14, 23]

// i = 3, j = 0 --> 0 > 9 --> false --> j = 1 --> 9 > 12 --> false --> arrayTestFive = [0, 9, 12, 14, 23]
// i = 3, j = 1 --> 9 > 12 --> false --> j = 2 --> 12 > 14 --> false --> arrayTestFive = [0, 9, 12, 14, 23]
// i = 3, j = 2 --> 12 > 14 --> false --> j = 3 --> 14 > 23 --> false --> arrayTestFive = [0, 9, 12, 14, 23]
// i = 3, j = 3 --> 14 > 23 --> false --> j = 4 --> 23 > undefined --> false --> arrayTestFive = [0, 9, 12, 14, 23]
// i = 3, j = 4 --> 23 > undefined --> false --> arrayTestFive = [0, 9, 12, 14, 23]

// i = 4, j = 0 --> 0 > 9 --> false --> j = 1 --> 9 > 12 --> false --> arrayTestFive = [0, 9, 12, 14, 23]
// i = 4, j = 1 --> 9 > 12 --> false --> j = 2 --> 12 > 14 --> false --> arrayTestFive = [0, 9, 12, 14, 23]
// i = 4, j = 2 --> 12 > 14 --> false --> j = 3 --> 14 > 23 --> false --> arrayTestFive = [0, 9, 12, 14, 23]
// i = 4, j = 3 --> 14 > 23 --> false --> j = 4 --> 23 > undefined --> false --> arrayTestFive = [0, 9, 12, 14, 23]
// i = 4, j = 4 --> 23 > undefined --> false --> arrayTestFive = [0, 9, 12, 14, 23]

// method 4 : Insertion Sort
let arrayTestSix = [0, 23, 14, 12, 9]
let outputFifteen = []
for (let i = 0; i < arrayTestSix.length; i++) {
  let temp = arrayTestSix[i]
  let j = i - 1
  while (j >= 0 && arrayTestSix[j] > temp) {
    arrayTestSix[j+1] = arrayTestSix[j]
    j--
  }
  arrayTestSix[j+1] = temp
}
// i = 0 --> temp = 0 --> j = -1 --> -1 >= 0 --> false --> arrayTestSix = [0, 23, 14, 12, 9]
// i = 1 --> temp = 23 --> j = 0 --> 0 >= 0 --> true --> arrayTestSix = [0, 23, 14, 12, 9]
// i = 1 --> temp = 23 --> j = -1 --> -1 >= 0 --> false --> arrayTestSix = [0, 23, 14, 12, 9]
// i = 2 --> temp = 14 --> j = 1 --> 1 >= 0 --> true --> arrayTestSix = [0, 23, 23, 12, 9]
// i = 2 --> temp = 14 --> j = 0 --> 0 >= 0 --> true --> arrayTestSix = [0, 14, 23, 12, 9]
// i = 2 --> temp = 14 --> j = -1 --> -1 >= 0 --> false --> arrayTestSix = [0, 14, 23, 12, 9]
// i = 3 --> temp = 12 --> j = 2 --> 2 >= 0 --> true --> arrayTestSix = [0, 14, 23, 23, 9]
// i = 3 --> temp = 12 --> j = 1 --> 1 >= 0 --> true --> arrayTestSix = [0, 14, 14, 23, 9]
// i = 3 --> temp = 12 --> j = 0 --> 0 >= 0 --> true --> arrayTestSix = [0, 12, 14, 23, 9]
// i = 3 --> temp = 12 --> j = -1 --> -1 >= 0 --> false --> arrayTestSix = [0, 12, 14, 23, 9]
// i = 4 --> temp = 9 --> j = 3 --> 3 >= 0 --> true --> arrayTestSix = [0, 12, 14, 23, 23]
// i = 4 --> temp = 9 --> j = 2 --> 2 >= 0 --> true --> arrayTestSix = [0, 12, 14, 14, 23]
// i = 4 --> temp = 9 --> j = 1 --> 1 >= 0 --> true --> arrayTestSix = [0, 12, 12, 14, 23]
// i = 4 --> temp = 9 --> j = 0 --> 0 >= 0 --> true --> arrayTestSix = [0, 9, 12, 14, 23]
// i = 4 --> temp = 9 --> j = -1 --> -1 >= 0 --> false --> arrayTestSix = [0, 9, 12, 14, 23]
```


## 5. Longest alternating subsequence
``` javascript
// A sequence {X1, X2, .. Xn} is an alternating sequence if its elements satisfy one of the following relations : 
//   X1 < X2 > X3 < X4 > X5 < …. xn or 
//   X1 > X2 < X3 > X4 < X5 > …. xn
// Input: arr[] = {10, 22, 9, 33, 49, 50, 31, 60}
// Output: 6
// Explanation: The subsequences {10, 22, 9, 33, 31, 60} or
// {10, 22, 9, 49, 31, 60} or {10, 22, 9, 50, 31, 60}
// are longest subsequence of length 6

function longestAlternatingSubsequence(arr) {
  const length = arr.reduce((acc, _, index) => {
    if (
      (index > 1 && arr[index] > arr[index - 1] && arr[index - 1] < arr[index - 2]) ||
      (index > 1 && arr[index] < arr[index - 1] && arr[index - 1] > arr[index - 2])
    ) {
      acc.push(arr[index]);
    }
    return acc;
  }, []).length;

  return length + 2; // Add 2 for the initial two elements
}

// Example usage:
// acc: the accumulator accumulates the callback's return values; it is the accumulated value previously returned in the last invocation of the callback, or initialValue, if supplied (see below).
// x: the current element being processed in the array no use so _ is used instead
// , i: the index of the current element being processed in the array
// [], 10, 0 --> [], 22, 1 --> [], 9, 2 --> [9], 33, 3 --> [9, 33], 49, 4 --> [9, 33, 49], 50, 5 --> [9, 33, 49, 50], 31, 6 --> [9, 33, 49, 50, 31], 60, 7 --> [9, 33, 49, 50, 31, 60] --> length = 6


// Example usage:
const arrl = [10, 22, 9, 33, 49, 50, 31, 60];
const length = longestAlternatingSubsequence(arrl);
console.log(length); // Output: 6
```

## 6. Given an integer array of coins[ ] of size N representing different types of currency and an integer sum, The task is to find the number of ways to make sum by using different combinations from coins[].  

``` javascript

// Note: Assume that you have an infinite supply of each type of coin. 

// Examples: 

// Input: sum = 4, coins[] = {1,2,3}, 
// Output: 4
// Explanation: there are four solutions: {1, 1, 1, 1}, {1, 1, 2}, {2, 2}, {1, 3}. 


// Input: sum = 10, coins[] = {2, 5, 3, 6}
// Output: 5
// Explanation: There are five solutions: 
// {2,2,2,2,2}, {2,2,3,3}, {2,2,6}, {2,3,5} and {5,5}.

function countCoinChangeWays(sum, coins) {
  const dp = new Array(sum + 1).fill(0); // Create an array to store the number of ways for each sum
  dp[0] = 1; // Base case: There is one way to make sum 0 (by not selecting any coin)

  for (const coin of coins) { // Iterate over each coin in the coins array
    for (let i = coin; i <= sum; i++) { // Iterate from coin value to the target sum
      dp[i] += dp[i - coin]; // Update the number of ways at index i by adding the number of ways at index (i - coin)
    }
  }
 // [ 1, 1, 2, 3, 4 ]   [ 1, 0, 1, 1, 1, 2, 3, 2, 4, 4, 5 ]
  return dp[sum]; // Return the total number of ways to make the given sum
}

// Example usage:
const sum = 4;
const coins = [1, 2, 3];
const ways = countCoinChangeWays(sum, coins);
console.log(ways); // Output: 4

const sum2 = 10;
const coins2 = [2, 5, 3, 6];
const ways2 = countCoinChangeWays(sum2, coins2);
console.log(ways2); // Output: 5



function countCoinChangeWaysP(sum, coins) {
  const dp = new Array(sum + 1).fill(0); // Create an array to store the number of ways for each sum
  dp[0] = 1; // Base case: There is one way to make sum 0 (by not selecting any coin)

  for (const coin of coins) { // Iterate over each coin in the coins array
    for (let i = coin; i <= sum; i++) { // Iterate from coin value to the target sum
      dp[i] += dp[i - coin]; // Update the number of ways at index i by adding the number of ways at index (i - coin)
    }
  }
  return dp
}

// Example usage:
const sumP = 4;
const coinsP = [1, 2, 3];
const waysP = countCoinChangeWaysP(sumP, coinsP);
console.log(waysP); // Output: [ 1, 1, 2, 3, 4 ]
```

## 7. Find the smallest positive integer value that cannot be represented as sum of any subset of a given array
``` javascript

// Given an array of positive numbers, find the smallest positive integer value that cannot be represented as the sum of elements of any subset of a given set. 

function findSmallestInteger(arr) {
  arr.sort((a, b) => a - b); // Sort the array in ascending order
  let result = 1; // Initialize the smallest positive integer that cannot be represented

  for (const num of arr) {
    if (num > result) {
      return result; // Found the smallest positive integer that cannot be represented
    }
    result += num;
  }

  return result;
}

// Examples:
const arr1 = [1, 10, 3, 11, 6, 15];
console.log(findSmallestInteger(arr1)); // Output: 2
// explanation:
//  sort the array in ascending order --> [1, 3, 6, 10, 11, 15]
//  result = 1 , num = 1 --> 1 > 1 --> false --> result = 1 + 1 = 2
//  result = 2 , num = 3 --> 3 > 2 --> true --> return result = 2


const arr2 = [1, 1, 1, 1];
console.log(findSmallestInteger(arr2)); // Output: 5

const arr3 = [1, 1, 3, 4];
console.log(findSmallestInteger(arr3)); // Output: 10
// explanation:
//  sort the array in ascending order --> [1, 1, 3, 4]
//  result = 1 , num = 1 --> 1 > 1 --> false --> result = 1 + 1 = 2
//  result = 2 , num = 1 --> 1 > 2 --> false --> result = 2 + 1 = 3
//  result = 3 , num = 3 --> 3 > 3 --> false --> result = 3 + 3 = 6
//  result = 6 , num = 4 --> 4 > 6 --> false --> result = 6 + 4 = 10
//  result = 10 , num = undefined --> false --> result = 10

const arr4 = [1, 2, 5, 10, 20, 40];
console.log(findSmallestInteger(arr4)); // Output: 4
// explanation:
//  sort the array in ascending order --> [1, 2, 5, 10, 20, 40]
//  result = 1 , num = 1 --> 1 > 1 --> false --> result = 1 + 1 = 2
//  result = 2 , num = 2 --> 2 > 2 --> false --> result = 2 + 2 = 4
//  result = 4 , num = 5 --> 5 > 4 --> true --> return result = 4

const arr5 = [1, 2, 3, 4, 5, 6];
console.log(findSmallestInteger(arr5)); // Output: 22
// explanation:
//  sort the array in ascending order --> [1, 2, 3, 4, 5, 6]
//  result = 1 , num = 1 --> 1 > 1 --> false --> result = 1 + 1 = 2
//  result = 2 , num = 2 --> 2 > 2 --> false --> result = 2 + 2 = 4
//  result = 4 , num = 3 --> 3 > 4 --> false --> result = 4 + 3 = 7
//  result = 7 , num = 4 --> 4 > 7 --> false --> result = 7 + 4 = 11
//  result = 11 , num = 5 --> 5 > 11 --> false --> result = 11 + 5 = 16
//  result = 16 , num = 6 --> 6 > 16 --> false --> result = 16 + 6 = 22
//  result = 22 , num = undefined --> false --> result = 22
```

## 8. [1, [2, [3, 4]]] --> [1, 2, 3, 4]

```javascript
let arr = [1, [2, [3, 4]]]
let res = []
function flat(arr) {
  for (let i = 0; i < arr.length; i++) {
    if (Array.isArray(arr[i])) {
      flat(arr[i])
    } else {
      res.push(arr[i])
    }
  }
}
```

