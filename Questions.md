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

