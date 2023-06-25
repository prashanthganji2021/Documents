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
