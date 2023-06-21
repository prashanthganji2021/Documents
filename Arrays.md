
1. Find the maximum element in an array:
```javascript
function findMaxElement(arr) {
  return Math.max(...arr);
}

// Example usage
const array = [5, 8, 3, 2, 10];
const maxElement = findMaxElement(array);
console.log(maxElement); // Output: 10
```

2. Find the minimum element in an array:
```javascript
function findMinElement(arr) {
  return Math.min(...arr);
}

// Example usage
const array = [5, 8, 3, 2, 10];
const minElement = findMinElement(array);
console.log(minElement); // Output: 2
```

3. Calculate the sum of all elements in an array:
```javascript
function calculateSum(arr) {
  return arr.reduce((sum, element) => sum + element, 0);
}

// Example usage
const array = [5, 8, 3, 2, 10];
const sum = calculateSum(array);
console.log(sum); // Output: 28
```

4. Calculate the average of all elements in an array:
```javascript
function calculateAverage(arr) {
  const sum = arr.reduce((sum, element) => sum + element, 0);
  return sum / arr.length;
}

// Example usage
const array = [5, 8, 3, 2, 10];
const average = calculateAverage(array);
console.log(average); // Output: 5.6
```

5. Reverse an array:
```javascript
function reverseArray(arr) {
  return arr.reverse();
}

// Example usage
const array = [5, 8, 3, 2, 10];
const reversedArray = reverseArray(array);
console.log(reversedArray); // Output: [10, 2, 3, 8, 5]
```

6. Check if an array is sorted in ascending order:
```javascript
function isAscending(arr) {
  for (let i = 0; i < arr.length - 1; i++) {
    if (arr[i] > arr[i + 1]) {
      return false;
    }
  }
  return true;
}

// Example usage
const array1 = [2, 4, 6, 8];
console.log(isAscending(array1)); // Output: true

const array2 = [5, 2, 9, 1];
console.log(isAscending(array2)); // Output: false
```

7. Check if an array is sorted in descending order:
```javascript
function isDescending(arr) {
  for (let i = 0; i < arr.length - 1; i++) {
    if (arr[i] < arr[i + 1]) {
      return false;
    }
  }
  return true;
}

// Example usage
const array1 = [8, 6, 4, 2];
console.log(isDescending(array1)); // Output: true

const array2 = [1, 9, 2, 5];
console.log(isDescending(array2)); // Output: false
```

8. Find the second largest element in an array:
```javascript
function findSecondLargest(arr) {
  const uniqueArray = **Array.from(new Set(arr)); // Remove duplicates
  if (unique**Array.length < 2) {
    return null;
  }
  unique**Array.sort((a, b) => b - a);
  return uniqueArray[1];
}

// Example usage
const array = [5, 8, 3, 2, 10];
const secondL

argest = findSecondLargest(array);
console.log(secondLargest); // Output: 8
```

9. Find the second smallest element in an array:
```javascript
function findSecondSmallest(arr) {
  const uniqueArray = **Array.from(new Set(arr)); // Remove duplicates
  if (unique**Array.length < 2) {
    return null;
  }
  unique**Array.sort((a, b) => a - b);
  return uniqueArray[1];
}

// Example usage
const array = [5, 8, 3, 2, 10];
const secondSmallest = findSecondSmallest(array);
console.log(secondSmallest); // Output: 3
```

10. Remove duplicate elements from an array:
```javascript
function removeDuplicates(arr) {
  return **Array.from(new Set(arr));
}

// Example usage
const array = [5, 8, 3, 2, 10, 5, 3];
const uniqueArray = removeDuplicates(array);
console.log(uniqueArray); // Output: [5, 8, 3, 2, 10]
```


11. Find the kth largest element in an array:
```javascript
function findKthLargest(arr, k) {
  if (k <= 0 || k > arr.length) {
    return null;
  }
  const sortedArray = arr.sort((a, b) => b - a);
  return sortedArray[k - 1];
}

// Example usage
const array = [5, 8, 3, 2, 10];
const kthLargest = findKthLargest(array, 3);
console.log(kthLargest); // Output: 5
```

12. Find the kth smallest element in an array:
```javascript
function findKthSmallest(arr, k) {
  if (k <= 0 || k > arr.length) {
    return null;
  }
  const sortedArray = arr.sort((a, b) => a - b);
  return sortedArray[k - 1];
}

// Example usage
const array = [5, 8, 3, 2, 10];
const kthSmallest = findKthSmallest(array, 3);
console.log(kthSmallest); // Output: 5
```

13. Find the sum of all even numbers in an array:
```javascript
function sumOfEvenNumbers(arr) {
  return arr.filter(num => num % 2 === 0).reduce((sum, num) => sum + num, 0);
}

// Example usage
const array = [1, 2, 3, 4, 5, 6];
const sumOfEven = sumOfEvenNumbers(array);
console.log(sumOfEven); // Output: 12
```

14. Find the sum of all odd numbers in an array:
```javascript
function sumOfOddNumbers(arr) {
  return arr.filter(num => num % 2 !== 0).reduce((sum, num) => sum + num, 0);
}

// Example usage
const array = [1, 2, 3, 4, 5, 6];
const sumOfOdd = sumOfOddNumbers(array);
console.log(sumOfOdd); // Output: 9
```

15. Count the number of occurrences of a specific element in an array:
```javascript
function countOccurrences(arr, element) {
  return arr.reduce((count, num) => (num === element ? count + 1 : count), 0);
}

// Example usage
const array = [1, 2, 3, 4, 1, 1];
const occurrences = countOccurrences(array, 1);
console.log(occurrences); // Output: 3
```

16. Find the index of a specific element in an array:
```javascript
function findElementIndex(arr, element) {
  return arr.indexOf(element);
}

// Example usage
const array = [5, 8, 3, 2, 10];
const index = findElementIndex(array, 3);
console.log(index); // Output: 2
```

17. Find the frequency of all elements in an array:
```javascript
function findElementFrequency(arr) {
  const frequencyMap = {};
  arr.forEach(element => {
    frequencyMap[element] = (frequencyMap[element] || 0) + 1;
  });
  return frequencyMap;
}

// Example usage
const array = [1, 2, 3, 2, 1, 2, 4];
const frequency = findElementFrequency(array);
console.log(frequency);
// Output: { 1: 2, 2: 3,

 3: 1, 4: 1 }
```

18. Find the missing number in an array of consecutive numbers:
```javascript
function findMissingNumber(arr) {
  const n = arr.length + 1;
  const expectedSum = (n ** (n + 1)) / 2;
  const actualSum = arr.reduce((sum, num) => sum + num, 0);
  return expectedSum - actualSum;
}

// Example usage
const array = [1, 2, 3, 5, 6];
const missingNumber = findMissingNumber(array);
console.log(missingNumber); // Output: 4
```

19. Find the common elements between two arrays:
```javascript
function findCommonElements(arr1, arr2) {
  const set1 = new Set(arr1);
  const commonElements = arr2.filter(element => set1.has(element));
  return commonElements;
}

// Example usage
const array1 = [1, 2, 3, 4, 5];
const array2 = [3, 4, 5, 6, 7];
const commonElements = findCommonElements(array1, array2);
console.log(commonElements); // Output: [3, 4, 5]
```

20. Find the union of two arrays:
```javascript
function findArrayUnion(arr1, arr2) {
  const set = new Set([...arr1, ...arr2]);
  const union = **Array.from(set);
  return union;
}

// Example usage
const array1 = [1, 2, 3, 4, 5];
const array2 = [4, 5, 6, 7, 8];
const unionArray = findArrayUnion(array1, array2);
console.log(unionArray); // Output: [1, 2, 3, 4, 5, 6, 7, 8]
```

21. Find the intersection of two arrays:
```javascript
function findArrayIntersection(arr1, arr2) {
  const set1 = new Set(arr1);
  const intersection = arr2.filter(element => set1.has(element));
  return intersection;
}

// Example usage
const array1 = [1, 2, 3, 4, 5];
const array2 = [4, 5, 6, 7, 8];
const intersectionArray = findArrayIntersection(array1, array2);
console.log(intersectionArray); // Output: [4, 5]
```
22. Merge two arrays without duplicates:

```javascript
function mergeArraysWithoutDuplicates(arr1, arr2) {
  const set = new Set([...arr1, ...arr2]);
  const mergedArray = **Array.from(set);
  return mergedArray;
}

// Example usage
const array1 = [1, 2, 3, 4, 5];
const array2 = [4, 5, 6, 7, 8];
const mergedArray = mergeArraysWithoutDuplicates(array1, array2);
console.log(mergedArray); // Output: [1, 2, 3, 4, 5, 6, 7, 8]
```

23. Find the difference between two arrays:
```javascript
function findArrayDifference(arr1, arr2) {
  const set1 = new Set(arr1);
  const difference = arr2.filter(element => !set1.has(element));
  return difference;
}

// Example usage
const array1 = [1, 2, 3, 4, 5];
const array2 = [4, 5, 6, 7, 8];
const differenceArray = findArrayDifference(array1, array2);
console.log(differenceArray); // Output: [6, 7, 8]

// explanation: [4, 5] is the intersection of the two arrays. So, [6, 7, 8] is the difference.
```

24. Find the largest sum of any two elements in an array:
```javascript
function findLargestSum(arr) {
  const sortedArray = arr.sort((a, b) => b - a);
  return sortedArray[0] + sortedArray[1];
}

// Example usage
const array = [5, 8, 3, 2, 10];
const largestSum = findLargestSum(array);
console.log(largestSum); // Output: 18
```

25. Find the smallest sum of any two elements in an array:
```javascript
function findSmallestSum(arr) {
  const sortedArray = arr.sort((a, b) => a - b);
  return sortedArray[0] + sortedArray[1];
}

// Example usage
const array = [5, 8, 3, 2, 10];
const smallestSum = findSmallestSum(array);
console.log(smallestSum); // Output: 5
```


<!-  from all about javascript Q&A  concept Covered are - >

- **Array.push()** :  The push() method adds one or more elements to the end of an array and returns the new length of the array.   
Example: [1,2,3].push(4,5) // [1,2,3,4,5] -  push to the end of the array

- **Array.pop()** : The pop() method removes the last element from an array and returns that element. This method changes the length of the array.
Example: [1,2,3].pop() // [1,2] -  pop the last element from the array

- **Array.shift()** : The shift() method removes the first element from an array and returns that removed element. This method changes the length of the array.
Example: [1,2,3].shift() // [2,3] -  shift the first element from the array

- **Array.unshift()** : The unshift() method adds one or more elements to the beginning of an array and returns the new length of the array.
Example: [1,2,3].unshift(4,5) // [4,5,1,2,3] -  unshift to the beginning of the array

- **Array.slice()** : The slice() method returns a shallow copy of a portion of an array into a new array object selected from start to end (end not included) where start and end represent the index of items in that array. The original array will not be modified.
Example: [1,2,3,4,5].slice(1,3) // [2,3] -  slice from index 1 to index 3 (not included)

- **Array.splice()** : The splice() method changes the contents of an array by removing or replacing existing elements and/or adding new elements in place.
Example: [1,2,3,4,5].splice(1,3) // [2,3,4] -  splice from index 1 to index 3 (not included)

- **Array.concat()** : The concat() method is used to merge two or more arrays. This method does not change the existing arrays, but instead returns a new array.
Example: [1,2,3].concat([4,5]) // [1,2,3,4,5] -  concat two arrays


- **Array.reduce()** : The reduce() method executes a reducer function (that you provide) on each element of the array, resulting in a single output value.
Example: [1,2,3].reduce((sum, num) => sum + num, 0) // 6 -  sum of all elements in the array

- **Array.filter()** : The filter() method creates a new array with all elements that pass the test implemented by the provided function.
Example: [1,2,3,4,5].filter(num => num % 2 === 0) // [2,4] -  filter even numbers from the array

- **Array.map()** : The map() method creates a new array populated with the results of calling a provided function on every element in the calling array.
Example: [1,2,3,4,5].map(num => num ** 2) // [2,4,6,8,10] -  multiply each element by 2

- **Array.forEach()** : The forEach() method executes a provided function once for each array element.
Example: [1,2,3,4,5].forEach(num => console.log(num)) // 1 2 3 4 5 -  print each element

- **Array.every()** : The every() method tests whether all elements in the array pass the test implemented by the provided function. It returns a Boolean value.
Example: [1,2,3,4,5].every(num => num > 0) // true -  check if all elements are greater than 0

- **Array.some()** : The some() method tests whether at least one element in the array passes the test implemented by the provided function. It returns a Boolean value.
Example: [1,2,3,4,5].some(num => num > 3) // true -  check if at least one element is greater than 3

- **Array.find()** : The find() method returns the value of the first element in the provided array that satisfies the provided testing function.
Example: [1,2,3,4,5].find(num => num > 3) // 4 -  find the first element greater than 3

- **Array.findIndex()** : The findIndex() method returns the index of the first element in the array that satisfies the provided testing function. Otherwise, it returns -1, indicating that no element passed the test.
Example: [1,2,3,4,5].findIndex(num => num > 3) // 3 -  find the index of the first element greater than 3

- **Array.includes()** : The includes() method determines whether an array includes a certain value among its entries, returning true or false as appropriate.
Example: [1,2,3,4,5].includes(3) // true -  check if the array includes 3

- **Array.reverse()** : The reverse() method reverses an array in place. The first array element becomes the last, and the last array element becomes the first.
Example: [1,2,3,4,5].reverse() // [5,4,3,2,1] -  reverse the array

- **Array.join()** : The join() method creates and returns a new string by concatenating all of the elements in an array (or an array-like object), separated by commas or a specified separator string.
Example: [1,2,3,4,5].join() // "1,2,3,4,5" -  join the array elements with a comma

- **Array.toString()** : The toString() method returns a string representing the specified array and its elements.
Example: [1,2,3,4,5].toString() // "1,2,3,4,5" -  convert the array to a string

- **Array.indexOf()** : The indexOf() method returns the first index at which a given element can be found in the array, or -1 if it is not present.
Example: [1,2,3,4,5].indexOf(3) // 2 -  find the index of 3

- **Array.lastIndexOf()** : The lastIndexOf() method returns the last index at which a given element can be found in the array, or -1 if it is not present. The array is searched backwards, starting at fromIndex.
Example: [1,2,3,4,5].lastIndexOf(3) // 2 -  find the last index of 3

- **Array.fill()** : The fill() method fills (modifies) all the elements of an array from a start index (default zero) to an end index (default array length) with a static value. It returns the modified array.
Example: [1,2,3,4,5].fill(0) // [0,0,0,0,0] -  fill the array with 0

- **Array.flat()** : The flat() method creates a new array with all sub-array elements concatenated into it recursively up to the specified depth.
Example: [1,2,[3,4,[5,6]]].flat(2) // [1,2,3,4,5,6] -  flatten the array

- **Array.flatMap()** : The flatMap() method first maps each element using a mapping function, then flattens the result into a new array. It is identical to a map() followed by a flat() of depth 1, but flatMap() is often quite useful, as merging both into one method is slightly more efficient.
Example: [1,2,3,4,5].flatMap(num => [num ** 2]) // [2,4,6,8,10] -  multiply each element by 2 and flatten the array

- **Array.from()** : The **Array.from() static method creates a new, shallow-copied Array instance from an array-like or iterable object.
Example: **Array.from("hello") // ["h","e","l","l","o"] -  convert a string to an array

- **Array.isArray()** : The **Array.isArray() method determines whether the passed value is an **Array.
Example: **Array.isArray([1,2,3]) // true -  check if the value is an array

- **Array.of()** : The **Array.of() method creates a new Array instance from a variable number of arguments, regardless of number or type of the arguments.
Example: **Array.of(1,2,3) // [1,2,3] -  create an array from the arguments

- **Array.keys()** : The keys() method returns a new Array Iterator object that contains the keys for each index in the array.
Example: [1,2,3].keys() // Array Iterator {} -  get the keys of the array

- **Array.values()** : The values() method returns a new Array Iterator object that contains the values for each index in the array.
Example: [1,2,3].values() // Array Iterator {} -  get the values of the array

- **Array.entries()** : The entries() method returns a new Array Iterator object that contains the key/value pairs for each index in the array.
Example: [1,2,3].entries() // Array Iterator {} -  get the key/value pairs of the array

- **Array.copyWithin()** : The copyWithin() method shallow copies part of an array to another location in the same array and returns it without modifying its length.
Example: [1,2,3,4,5].copyWithin(0,3) // [4,5,3,4,5] -  copy the elements from index 3 to the start of the array

- **Array.sort()** : The sort() method sorts the elements of an array in place and returns the sorted array. The default sort order is ascending, built upon converting the elements into strings, then comparing their sequences of UTF-16 code units values.
Example: [1,2,3,4,5].sort((a,b) => a-b) // [1,2,3,4,5] -  sort the array in ascending order
Example: [1,2,3,4,5].sort((a,b) => b-a) // [5,4,3,2,1] -  sort the array in descending order






1. **Question:** Given an array `[1, 2, 3, 4, 5]`, create a new array that contains only the even numbers and then reverse the order of the elements.
   **Concepts Covered:** Array.filter(), Array.reverse()
   **Answer:** 
   ```javascript
   const array = [1, 2, 3, 4, 5];
   const filteredArray = array.filter(num => num % 2 === 0);
   const reversedArray = filteredArray.reverse();
   ```

2. **Question:** Convert the array `[1, 2, 3, 4, 5]` to a string where each element is separated by a dash ("-") and then find the index of the first occurrence of the number 3.
   **Concepts Covered:** Array.join(), Array.indexOf()
   **Answer:**
   ```javascript
   const array = [1, 2, 3, 4, 5];
   const joinedString = array.join("-");
   const indexOfThree = array.indexOf(3);
   ```

3. **Question:** Given two arrays `[1, 2, 3]` and `[4, 5, 6]`, merge them into a single array and then find the sum of all elements in the merged array.
   **Concepts Covered:** Array.concat(), Array.reduce()
   **Answer:**
   ```javascript
   const array1 = [1, 2, 3];
   const array2 = [4, 5, 6];
   const mergedArray = array1.concat(array2);
   const sum = mergedArray.reduce((total, num) => total + num, 0);
   ```

4. **Question:** Given an array `[1, 2, 3, 4, 5]`, create a new array where each element is multiplied by 2 and then remove all even numbers from the new array.
   **Concepts Covered:** Array.map(), Array.filter()
   **Answer:**
   ```javascript
   const array = [1, 2, 3, 4, 5];
   const multipliedArray = array.map(num => num * 2);
   const filteredArray = multipliedArray.filter(num => num % 2 !== 0);
   ```

5. **Question:** Given an array `[1, 2, 3, 4, 5]`, create a new array where each element is squared and then find the index of the first element that is greater than 10.
   **Concepts Covered:** Array.map(), Array.findIndex()
   **Answer:**
   ```javascript
   const array = [1, 2, 3, 4, 5];
   const squaredArray = array.map(num => num ** 2);
   const index = squaredArray.findIndex(num => num > 10);
   ```

6. **Question:** Given an array `[1, 2, 3, 4, 5]`, create a new array where each element is multiplied by 2, and then check if all elements in the new array are greater than 0.
   **Concepts Covered:** Array.map(), Array.every()
   **Answer:**
   ```javascript
   const array = [1, 2, 3, 4, 5];
   const multipliedArray = array.map(num => num * 2);
   const allGreaterThanZero = multipliedArray.every(num => num > 0);
   ```

7. **Question:** Given an array `[1, 2, 3, 4, 5]`, create a new array where each element is squared, and then calculate the sum of all elements in the new array.
   **Concepts Covered:** Array.map(), Array.reduce()
   **Answer:**
   ```javascript
   const array = [1, 2, 3, 4, 5];
   const squaredArray = array.map(num => num ** 2);
   const sum = squaredArray.reduce((total, num) => total + num, 0);
   ```

8. **Question:** Given an array `[1, 2, 3, 4, 5]`, remove the last two elements and then add the numbers 6 and 7 to the end of the array.
   **Concepts Covered:** Array.splice(), Array.push()
   **Answer:**
   ```javascript
   const array = [1, 2, 3, 4, 5];
   array.splice(-2);
   array.push(6, 7);
   ```

9. **Question:** Given an array `[1, 2, 3, 4, 5]`, create a new array that contains the square root of each element and then remove any non-integer numbers from the new array.
   **Concepts Covered:** Array.map(), Array.filter()
   **Answer:**
   ```javascript
   const array = [1, 2, 3, 4, 5];
   const squareRootArray = array.map(num => Math.sqrt(num));
   const filteredArray = squareRootArray.filter(num => Number.isInteger(num));
   ```

10. **Question:** Given an array `[1, 2, 3, 4, 5]`, check if any element is divisible by 3, and if so, create a new array that contains only those elements.
    **Concepts Covered:** Array.some(), Array.filter()
    **Answer:**
    ```javascript
    const array = [1, 2, 3, 4, 5];
    const divisibleByThree = array.filter(num => num % 3 === 0);
Apologies for the oversight. Here are revised questions with four concepts covered for each problem:

1. **Question:** Given an array of numbers, find the sum of all even numbers, square the result, and convert it to a binary string.
   **Concepts Covered:** Array.reduce(), Math.pow(), Number.toString(), Number.parseInt()
   **Answer:**
   ```javascript
   const array = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
   const sumOfEvens = array.reduce((sum, num) => num % 2 === 0 ? sum + num : sum, 0);
   const squaredSum = Math.pow(sumOfEvens, 2);
   const binaryString = Number.parseInt(squaredSum, 10).toString(2);
   ```

2. **Question:** Given an array of strings, convert all strings to uppercase, remove any duplicates, and sort them in descending order.
   **Concepts Covered:** Array.map(), Array.filter(), Array.from(), Array.sort(), String.toUpperCase()
   **Answer:**
   ```javascript
   const array = ['apple', 'banana', 'cherry', 'apple', 'date', 'banana'];
   const uniqueUppercaseArray = Array.from(new Set(array.map(str => str.toUpperCase())));
   const sortedArray = uniqueUppercaseArray.sort((a, b) => b.localeCompare(a));
   ```

3. **Question:** Given an array of objects representing students, filter out all students with a grade below 80, calculate their average age, and round it to the nearest whole number.
   **Concepts Covered:** Array.filter(), Array.map(), Math.round(), Array.reduce()
   **Answer:**
   ```javascript
   const students = [
     { name: 'John', age: 20, grade: 75 },
     { name: 'Jane', age: 19, grade: 85 },
     { name: 'Mark', age: 21, grade: 90 },
     { name: 'Alice', age: 18, grade: 70 },
   ];
   const filteredStudents = students.filter(student => student.grade >= 80);
   const averageAge = Math.round(filteredStudents.map(student => student.age).reduce((sum, age) => sum + age, 0) / filteredStudents.length);
   ```

4. **Question:** Given an array of numbers, create a new array that contains only prime numbers, calculate their product, and convert it to a hexadecimal string.
   **Concepts Covered:** Array.filter(), Array.reduce(), Number.isInteger(), Number.toString()
   **Answer:**
   ```javascript
   const array = [2, 3, 4, 5, 6, 7, 8, 9, 10];
   const primeNumbers = array.filter(num => {
     if (num < 2) return false;
     for (let i = 2; i <= Math.sqrt(num); i++) {
       if (num % i === 0) return false;
     }
     return true;
   });
   const product = primeNumbers.reduce((product, num) => product * num, 1);
   const hexadecimalString = product.toString(16);
   ```
:

5. **Question:** Given an array of strings, remove any duplicates, convert them to uppercase, and concatenate them into a single string separated by commas.
   **Concepts Covered:** Array.filter(), Array.map(), Array.join(), String.toUpperCase()
   **Answer:**
   ```javascript
   const array = ['apple', 'banana', 'cherry', 'apple', 'date', 'banana'];
   const uniqueArray = array.filter((value, index, self) => self.indexOf(value) === index);
   const uppercaseStrings = uniqueArray.map(str => str.toUpperCase());
   const result = uppercaseStrings.join(', ');
   ```

6. **Question:** Given an array of numbers, find the maximum value, calculate its square root, and convert it to a binary string.
   **Concepts Covered:** Array.reduce(), Math.max(), Math.sqrt(), Number.toString()
   **Answer:**
   ```javascript
   const array = [4, 9, 16, 25, 36, 49];
   const max = array.reduce((prev, curr) => Math.max(prev, curr));
   const squareRoot = Math.sqrt(max);
   const binaryString = squareRoot.toString(2);
   ```

7. **Question:** Given an array of objects representing students, calculate the average grade for female students, round it to the nearest whole number, and convert it to a binary string.
   **Concepts Covered:** Array.filter(), Array.reduce(), Math.round(), Number.toString()
   **Answer:**
   ```javascript
   const students = [
     { name: 'John', gender: 'Male', grade: 85 },
     { name: 'Jane', gender: 'Female', grade: 90 },
     { name: 'Mark', gender: 'Male', grade: 80 },
     { name: 'Alice', gender: 'Female', grade: 95 },
   ];
   const femaleStudents = students.filter(student => student.gender === 'Female');
   const averageGrade = Math.round(femaleStudents.reduce((sum, student) => sum + student.grade, 0) / femaleStudents.length);
   const binaryString = averageGrade.toString(2);
   ```

8. **Question:** Given two arrays of numbers, find the common elements between them, calculate their sum, and check if it is a prime number.
   **Concepts Covered:** Array.filter(), Array.reduce(), Number.isInteger(), Math.sqrt()
   **Answer:**
   ```javascript
   const array1 = [2, 3, 4, 5, 6, 7, 8];
   const array2 = [4, 5, 6, 7, 8, 9, 10];
   const commonElements = array1.filter(num => array2.includes(num));
   const sum = commonElements.reduce((acc, num) => acc + num, 0);
   const isPrime = isNumberPrime(sum);

   function isNumberPrime(num) {
     if (num < 2) return false;
     for (let i = 2; i <= Math.sqrt(num); i++) {
       if (num % i === 0) return false;
     }
     return true;
   }
   ```



9. **Question:** Given an array of strings, find the longest word, convert it to uppercase, and reverse its characters.
   **Concepts Covered:** Array.reduce(), String.length, String.toUpperCase(), String.split(), Array.reverse(), Array.join()
   **Answer:**
   ```javascript
   const words = ['apple', 'banana', 'cherry', 'date', 'elephant'];
   const longestWord = words.reduce((prev, curr) => (curr.length > prev.length ? curr : prev));
   const uppercase = longestWord.toUpperCase();
   const reversed = uppercase.split('').reverse().join('');
   ```

10. **Question:** Given an array of numbers, find all the even numbers, square them, and calculate their sum.
    **Concepts Covered:** Array.filter(), Array.map(), Array.reduce()
    **Answer:**
    ```javascript
    const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
    const evenNumbers = numbers.filter(num => num % 2 === 0);
    const squaredNumbers = evenNumbers.map(num => num ** 2);
    const sum = squaredNumbers.reduce((prev, curr) => prev + curr, 0);
    ```

11. **Question:** Given an array of strings, remove any duplicates, sort them in alphabetical order, and concatenate them into a single string separated by a hyphen.
    **Concepts Covered:** Array.filter(), Array.sort(), Array.join()
    **Answer:**
    ```javascript
    const strings = ['banana', 'apple', 'cherry', 'date', 'apple', 'banana'];
    const uniqueStrings = strings.filter((value, index, self) => self.indexOf(value) === index);
    const sortedStrings = uniqueStrings.sort();
    const result = sortedStrings.join('-');
    ```

12. **Question:** Given an array of numbers, calculate the sum of the even-indexed elements and the product of the odd-indexed elements.
    **Concepts Covered:** Array.reduce(), Array.every(), Array.some()
    **Answer:**
    ```javascript
    const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
    const sumOfEven = numbers.reduce((prev, curr, index) => (index % 2 === 0 ? prev + curr : prev), 0);
    const productOfOdd = numbers.reduce((prev, curr, index) => (index % 2 !== 0 ? prev * curr : prev), 1);
    ```

13. **Question:** Given an array of strings, remove any empty strings, convert the remaining strings to uppercase, and concatenate them into a single string separated by a space.
    **Concepts Covered:** Array.filter(), String.length, String.toUpperCase(), Array.join()
    **Answer:**
    ```javascript
    const strings = ['', 'apple', '', 'banana', 'cherry', '', 'date'];
    const nonEmptyStrings = strings.filter(str => str.length > 0);
    const uppercaseStrings = nonEmptyStrings.map(str => str.toUpperCase());
    const result = uppercaseStrings.join(' ');
    ```

14. **Question:** Given two arrays of numbers, find the common elements between them, square each element, and calculate their sum.
    **Concepts Covered:** Array.filter(), Array.includes(), Array.map(), Array.reduce()
    **Answer:**
    ```javascript
    const arr1 = [1, 2, 3, 4, 5];
    const arr2 = [3, 4, 5, 6, 7];
    const commonElements = arr1.filter(num => arr2.includes(num));
    const squaredElements = commonElements.map(num => num ** 2);
    const sum = squaredElements.reduce((prev, curr) => prev + curr, 0);
    ```

15. **Question:** Given an array of numbers, find the maximum and minimum values, calculate their difference, and check if it is divisible by a specific number.
    **Concepts Covered:** Array.reduce(), Math.max(), Math.min(), Arithmetic Operators (%)
    **Answer:**
    ```javascript
    const numbers = [12, 34, 56, 78, 90];
    const max = Math.max(...numbers);
    const min = Math.min(...numbers);
    const difference = max - min;
    const isDivisible = difference % 5 === 0;
    ```

16. **Question:** Given an array of strings, find the longest word, calculate its length, and check if it is a palindrome.
    **Concepts Covered:** Array.reduce(), String.length, String.split(), Array.reverse(), Array.join()
    **Answer:**
    ```javascript
    const words = ['apple', 'banana', 'cherry', 'racecar', 'date', 'elephant'];
    const longestWord = words.reduce((prev, curr) => (curr.length > prev.length ? curr : prev));
    const length = longestWord.length;
    const reversed = longestWord.split('').reverse().join('');
    const isPalindrome = longestWord === reversed;
    ```

17. **Question:** Given an array of numbers, find the average of all the positive numbers, round it to the nearest integer, and return the result.
   **Concepts Covered:** Array.filter(), Array.reduce(), Math.round()
   **Answer:**
   ```javascript
   const numbers = [-2, 5, 8, -3, 10, 4, -6, 7];
   const positiveNumbers = numbers.filter(num => num > 0);
   const sum = positiveNumbers.reduce((prev, curr) => prev + curr, 0);
   const average = sum / positiveNumbers.length;
   const result = Math.round(average);
   ```

18. **Question:** Given an array of names, sort them alphabetically, convert them to uppercase, and return the resulting array.
   **Concepts Covered:** Array.sort(), String.toUpperCase()
   **Answer:**
   ```javascript
   const names = ['John', 'Alice', 'Mark', 'Emily', 'David'];
   const sortedNames = names.sort();
   const uppercaseNames = sortedNames.map(name => name.toUpperCase());
   ```

19. **Question:** Given an array of numbers, remove any duplicates, calculate the square of each number, and return the resulting array in descending order.
   **Concepts Covered:** Array.filter(), Array.indexOf(), Array.map(), Array.sort()
   **Answer:**
   ```javascript
   const numbers = [2, 4, 3, 1, 4, 2, 5, 3, 6];
   const uniqueNumbers = numbers.filter((num, index) => numbers.indexOf(num) === index);
   const squaredNumbers = uniqueNumbers.map(num => num ** 2);
   const sortedNumbers = squaredNumbers.sort((a, b) => b - a);
   ```

20. **Question:** Given an array of strings, count the number of occurrences of each string, sort them in descending order of occurrence, and return the resulting array of objects.
   **Concepts Covered:** Array.reduce(), Object.entries(), Array.sort()
   **Answer:**
   ```javascript
   const strings = ['apple', 'banana', 'cherry', 'apple', 'date', 'banana', 'apple'];
   const occurrenceCount = strings.reduce((count, str) => {
     count[str] = (count[str] || 0) + 1;
     return count;
   }, {});
   const sortedOccurrences = Object.entries(occurrenceCount).sort((a, b) => b[1] - a[1]);
   ```


21. **Question:** Given an array of numbers, remove all even numbers, double the remaining numbers, and return the resulting array in ascending order.
   **Concepts Covered:** Array.filter(), Array.map(), Array.sort()
   **Answer:**
   ```javascript
   const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
   const oddNumbers = numbers.filter(num => num % 2 !== 0);
   const doubledNumbers = oddNumbers.map(num => num * 2);
   const sortedNumbers = doubledNumbers.sort((a, b) => a - b);
   ```

22. **Question:** Given an array of strings, find the longest string, convert it to uppercase, and return the result.
   **Concepts Covered:** Array.reduce(), String.length, String.toUpperCase()
   **Answer:**
   ```javascript
   const strings = ['apple', 'banana', 'cherry', 'date', 'elderberry'];
   const longestString = strings.reduce((longest, current) => {
     if (current.length > longest.length) {
       return current;
     }
     return longest;
   }, '');
   const uppercaseLongest = longestString.toUpperCase();
   ```

23. **Question:** Given two arrays of numbers, merge them into a single array, remove any duplicates, square each number, and return the resulting array in descending order.
   **Concepts Covered:** Array.concat(), Array.filter(), Array.map(), Array.sort()
   **Answer:**
   ```javascript
   const arr1 = [2, 4, 6, 8];
   const arr2 = [1, 3, 5, 7];
   const mergedArray = arr1.concat(arr2);
   const uniqueNumbers = mergedArray.filter((num, index) => mergedArray.indexOf(num) === index);
   const squaredNumbers = uniqueNumbers.map(num => num ** 2);
   const sortedNumbers = squaredNumbers.sort((a, b) => b - a);
   ```

24. **Question:** Given an array of objects representing students, filter out the students whose age is below 18, sort them alphabetically by name, and return the resulting array of student names.
   **Concepts Covered:** Array.filter(), Array.sort(), Object property access
   **Answer:**
   ```javascript
   const students = [
     { name: 'Alice', age: 20 },
     { name: 'Bob', age: 17 },
     { name: 'Charlie', age: 19 },
     { name: 'David', age: 16 },
     { name: 'Emily', age: 18 }
   ];
   const filteredStudents = students.filter(student => student.age >= 18);
   const sortedStudents = filteredStudents.sort((a, b) => a.name.localeCompare(b.name));
   const studentNames = sortedStudents.map(student => student.name);
   ```


25. **Question:** Given an array of numbers, remove all negative numbers, square the remaining numbers, and return the result in ascending order.
   **Concepts Covered:** Array.filter(), Array.map(), Array.sort()
   **Answer:**
   ```javascript
   const numbers = [2, -5, 1, -3, 4, -2];
   const positiveNumbers = numbers.filter(num => num >= 0);
   const squaredNumbers = positiveNumbers.map(num => num ** 2);
   const sortedNumbers = squaredNumbers.sort((a, b) => a - b);
   ```

26. **Question:** Given an array of strings, remove any empty strings, convert the remaining strings to uppercase, and return the result in reverse order.
   **Concepts Covered:** Array.filter(), Array.map(), Array.reverse(), String.length, String.toUpperCase()
   **Answer:**
   ```javascript
   const strings = ['', 'apple', '', 'banana', 'cherry', '', 'date'];
   const nonEmptyStrings = strings.filter(str => str.length > 0);
   const uppercaseStrings = nonEmptyStrings.map(str => str.toUpperCase());
   const reversedStrings = uppercaseStrings.reverse();
   ```

27. **Question:** Given an array of numbers, find the average of the even numbers, round it to the nearest integer, and return the result.
   **Concepts Covered:** Array.filter(), Array.reduce(), Math.round(), Number.isInteger()
   **Answer:**
   ```javascript
   const numbers = [2, 4, 6, 3, 5, 7];
   const evenNumbers = numbers.filter(num => num % 2 === 0);
   const sum = evenNumbers.reduce((acc, num) => acc + num, 0);
   const average = sum / evenNumbers.length;
   const roundedAverage = Math.round(average);
   ```

28. **Question:** Given an array of strings, find the first string that starts with 'a', convert it to lowercase, and return the result. If no such string exists, return 'Not found'.
   **Concepts Covered:** Array.find(), String.startsWith(), String.toLowerCase()
   **Answer:**
   ```javascript
   const strings = ['apple', 'banana', 'cherry', 'date', 'elderberry'];
   const foundString = strings.find(str => str.startsWith('a'));
   const result = foundString ? foundString.toLowerCase() : 'Not found';
   ```



29. **Question:** Given an array of numbers, find the sum of the numbers that are divisible by 3, square the result, and return it.
   **Concepts Covered:** Array.filter(), Array.reduce(), Math.pow()
   **Answer:**
   ```javascript
   const numbers = [2, 3, 6, 9, 12, 15];
   const divisibleByThree = numbers.filter(num => num % 3 === 0);
   const sum = divisibleByThree.reduce((acc, num) => acc + num, 0);
   const squaredSum = Math.pow(sum, 2);
   ```

30. **Question:** Given two arrays of numbers, merge them together, remove any duplicates, and return the result in ascending order.
   **Concepts Covered:** Array.concat(), Array.filter(), Array.sort()
   **Answer:**
   ```javascript
   const arr1 = [1, 2, 3, 4, 5];
   const arr2 = [3, 4, 5, 6, 7];
   const mergedArray = arr1.concat(arr2);
   const uniqueArray = mergedArray.filter((value, index, self) => self.indexOf(value) === index);
   const sortedArray = uniqueArray.sort((a, b) => a - b);
   ```

31. **Question:** Given an array of strings, count the number of strings that have a length greater than 5 and start with a capital letter.
   **Concepts Covered:** Array.filter(), String.length, String.charAt(), String.toUpperCase()
   **Answer:**
   ```javascript
   const strings = ['Apple', 'banana', 'Cherry', 'Date', 'elderberry', 'Fig'];
   const count = strings.filter(str => str.length > 5 && str.charAt(0) === str.charAt(0).toUpperCase()).length;
   ```

32. **Question:** Given an array of numbers, find the maximum value, multiply it by 2, and return the result.
   **Concepts Covered:** Array.reduce(), Math.max()
   **Answer:**
   ```javascript
   const numbers = [5, 8, 2, 10, 3];
   const maxNumber = numbers.reduce((max, num) => Math.max(max, num), -Infinity);
   const result = maxNumber * 2;
   ```



33. **Question:** Given an array of strings, convert all the strings to uppercase and remove any strings that contain numbers. Then, sort the resulting array in descending order.
   **Concepts Covered:** Array.map(), Array.filter(), Array.sort(), String.toUpperCase(), String.includes()
   **Answer:**
   ```javascript
   const strings = ['apple', 'Banana', 'Cherry', 'Date', 'Fig', 'Grape123'];
   const filteredArray = strings
     .map(str => str.toUpperCase())
     .filter(str => !str.includes('1') && !str.includes('2') && !str.includes('3'));
   const sortedArray = filteredArray.sort((a, b) => b.localeCompare(a));
   ```

34. **Question:** Given an array of numbers, remove the duplicates, square each number, and return the sum of all the squared numbers.
   **Concepts Covered:** Array.filter(), Array.reduce(), Math.pow()
   **Answer:**
   ```javascript
   const numbers = [2, 3, 2, 4, 5, 3, 6, 7, 5];
   const uniqueNumbers = numbers.filter((value, index, self) => self.indexOf(value) === index);
   const squaredNumbers = uniqueNumbers.map(num => Math.pow(num, 2));
   const sum = squaredNumbers.reduce((acc, num) => acc + num, 0);
   ```

35. **Question:** Given two arrays of objects representing students, merge the arrays, filter out any students with a grade below 70, and return the names of the remaining students sorted in alphabetical order.
   **Concepts Covered:** Array.concat(), Array.filter(), Array.map(), Array.sort(), Object.property access
   **Answer:**
   ```javascript
   const students1 = [{ name: 'John', grade: 85 }, { name: 'Alice', grade: 72 }, { name: 'Bob', grade: 90 }];
   const students2 = [{ name: 'Mary', grade: 68 }, { name: 'Tom', grade: 80 }, { name: 'Emma', grade: 95 }];
   const mergedStudents = students1.concat(students2);
   const passingStudents = mergedStudents.filter(student => student.grade >= 70);
   const sortedNames = passingStudents.map(student => student.name).sort();
   ```

36. **Question:** Given an array of numbers, find the sum of the numbers that are divisible by 2 or 3, square the result, and return it.
   **Concepts Covered:** Array.reduce(), Math.pow(), Logical operators (OR)
   **Answer:**
   ```javascript
   const numbers = [2, 3, 4, 5, 6, 7, 8, 9];
   const sum = numbers.reduce((acc, num) => {
     if (num % 2 === 0 || num % 3 === 0) {
       return acc + num;
     }
     return acc;
   }, 0);
   const squaredSum = Math.pow(sum, 2);
   ```



37. **Question:** Given an array of strings, remove any duplicate strings, convert all the strings to uppercase, and concatenate them into a single string separated by a comma. Then, reverse the resulting string and return it.
   **Concepts Covered:** Array.filter(), Array.reduce(), Array.join(), Array.reverse(), String.toUpperCase(), String.includes(), String.split(), String.trim(), String.length, String.concat()
   **Answer:**
   ```javascript
   const strings = ['apple', 'banana', 'cherry', 'Apple', 'date', 'apple'];
   const uniqueStrings = strings.filter((value, index, self) => self.indexOf(value) === index);
   const uppercaseStrings = uniqueStrings.map(str => str.toUpperCase());
   const concatenatedString = uppercaseStrings.join(', ');
   const reversedString = concatenatedString.split('').reverse().join('').trim();
   ```

38. **Question:** Given an array of numbers, find the sum of all the even numbers, square the sum, and return it as a string with the word "Result:" appended at the beginning.
   **Concepts Covered:** Array.reduce(), Math.pow(), String concatenation, Array.every(), Arithmetic operators (%), String template literals
   **Answer:**
   ```javascript
   const numbers = [2, 5, 8, 10, 15, 6];
   const sum = numbers.reduce((acc, num) => {
     if (num % 2 === 0) {
       return acc + num;
     }
     return acc;
   }, 0);
   const squaredSum = Math.pow(sum, 2);
   const resultString = `Result: ${squaredSum.toString()}`;
   ```

39. **Question:** Given an array of objects representing students, find the average grade of all the students whose names start with the letter 'J', round the average to the nearest integer, and return it as a string.
   **Concepts Covered:** Array.filter(), Array.map(), Array.reduce(), Math.round(), Object.property access, Arithmetic operators (+), String template literals
   **Answer:**
   ```javascript
   const students = [
     { name: 'John', grade: 85 },
     { name: 'Alice', grade: 72 },
     { name: 'Bob', grade: 90 },
     { name: 'Jack', grade: 95 },
     { name: 'Jane', grade: 88 }
   ];
   const filteredStudents = students.filter(student => student.name.charAt(0) === 'J');
   const sumGrades = filteredStudents.reduce((acc, student) => acc + student.grade, 0);
   const averageGrade = Math.round(sumGrades / filteredStudents.length);
   const averageString = `Average Grade: ${averageGrade.toString()}`;
   ```



**Question:** Given an array of objects representing employees, calculate the total salary of all employees whose years of experience are greater than 5, and whose job titles include the word "Engineer". Then, find the average salary of these employees and return it as a formatted string with two decimal places.
 
The employee objects have the following structure:
```javascript
const employees = [
  { name: 'John', title: 'Software Engineer', yearsOfExperience: 8, salary: 80000 },
  { name: 'Alice', title: 'Data Engineer', yearsOfExperience: 6, salary: 75000 },
  { name: 'Bob', title: 'Software Developer', yearsOfExperience: 3, salary: 60000 },
  { name: 'Jane', title: 'Software Engineer', yearsOfExperience: 7, salary: 85000 },
  { name: 'Mike', title: 'DevOps Engineer', yearsOfExperience: 4, salary: 70000 }
];
```
**Concepts Covered:** Array.filter(), Array.reduce(), Array.map(), Arithmetic operators (+), Object.property access, String.includes(), Math.round(), Template literals, String formatting

**Answer:**
```javascript
const employees = [
  { name: 'John', title: 'Software Engineer', yearsOfExperience: 8, salary: 80000 },
  { name: 'Alice', title: 'Data Engineer', yearsOfExperience: 6, salary: 75000 },
  { name: 'Bob', title: 'Software Developer', yearsOfExperience: 3, salary: 60000 },
  { name: 'Jane', title: 'Software Engineer', yearsOfExperience: 7, salary: 85000 },
  { name: 'Mike', title: 'DevOps Engineer', yearsOfExperience: 4, salary: 70000 }
];

const filteredEmployees = employees.filter(employee => employee.yearsOfExperience > 5 && employee.title.includes('Engineer'));
const totalSalary = filteredEmployees.reduce((sum, employee) => sum + employee.salary, 0);
const averageSalary = totalSalary / filteredEmployees.length;
const formattedSalary = averageSalary.toFixed(2);

console.log(`Average Salary: $${formattedSalary}`);
```

This solution filters the employees based on the given conditions using `Array.filter()`. Then, it calculates the total salary of the filtered employees using `Array.reduce()`. Finally, it calculates the average salary by dividing the total salary by the number of filtered employees and formats it to two decimal places using `toFixed()`. The result is logged to the console in the desired format.


**Question:** Given an array of strings, write a function that takes the array as input and returns a new array containing the lengths of all the strings that have more than three vowels and are palindromes. The returned array should be sorted in descending order based on the lengths of the strings.

**Concepts Covered:** Array.filter(), Array.map(), Array.sort(), String manipulation, Regular expressions, Palindrome checking, Sorting numbers in descending order

**Answer:**
```javascript
function getSortedPalindromeLengths(arr) {
  const vowelsRegex = /[aeiou]/i;
  const palindromeRegex = /^(.{0,})(.?)(\2)(\1)$/i;
  
  const filteredStrings = arr.filter(str => {
    const vowelCount = str.match(vowelsRegex)?.length || 0;
    const isPalindrome = palindromeRegex.test(str);
    return vowelCount > 3 && isPalindrome;
  });
  
  const lengthsArray = filteredStrings.map(str => str.length);
  lengthsArray.sort((a, b) => b - a);
  
  return lengthsArray;
}

const strings = ["level", "hello", "racecar", "open", "stats", "engineer"];
const result = getSortedPalindromeLengths(strings);
console.log(result);
```


1. **Question:** What will be the output of the following code snippet?
```javascript
console.log(1 + "1" - 1);
```
**Answer:** The output will be `"10"`. JavaScript performs automatic type coercion, so the expression `"1" - 1` is interpreted as subtracting a number from a string. JavaScript converts the string to a number, resulting in the calculation `1 - 1 = 0`. The final result is converted back to a string when concatenated with the initial `"1"`, resulting in the string `"10"`.

2. **Question:** What will be the output of the following code snippet?
```javascript
console.log([] + []);
```
**Answer:** The output will be an empty string `""`. When JavaScript encounters the `+` operator between two arrays, it converts them to strings using the `toString()` method. An empty array, when converted to a string, results in an empty string. Concatenating two empty strings together gives an empty string as the final result.

3. **Question:** What will be the output of the following code snippet?
```javascript
console.log(2 ** 3 ** 2);
```
**Answer:** The output will be `512`. In JavaScript, the exponentiation operator (`**`) has right-to-left associativity. So, `3 ** 2` is evaluated first, resulting in `9`. Then, `2 ** 9` is evaluated, giving the final result of `512`.

4. **Question:** What will be the output of the following code snippet?
```javascript
console.log(0.1 + 0.2 === 0.3);
```
**Answer:** The output will be `false`. Floating-point arithmetic in JavaScript can sometimes lead to precision errors. In this case, the sum of `0.1 + 0.2` is not exactly equal to `0.3` due to rounding errors. Therefore, the expression `0.1 + 0.2 === 0.3` evaluates to `false`.

5. **Question:** What will be the output of the following code snippet?
```javascript
console.log(NaN === NaN);
```
**Answer:** The output will be `false`. In JavaScript, `NaN` (Not-a-Number) is a special value that represents an unrepresentable or undefined value. Surprisingly, `NaN` is not equal to itself, so the expression `NaN === NaN` evaluates to `false`.

6. **Question:** What will be the output of the following code snippet?
```javascript
console.log("hello" instanceof String);
```
**Answer:** The output will be `false`. The `instanceof` operator in JavaScript checks whether an object belongs to a specific class. In this case, the string `"hello"` is a primitive string, not an instance of the `String` class. Therefore, the expression `"hello" instanceof String` evaluates to `false`.

7. **Question:** What will be the output of the following code snippet?
```javascript
console.log(1 < 2 < 3);
```
**Answer:** The output will be `true`. JavaScript performs left-to-right evaluation, so `1 < 2` is evaluated first, resulting in `true`. Then, `true < 3` is evaluated as `1 < 3`, which is `true`. Therefore, the expression `1 < 2 < 3` evaluates to `true`.

8. **Question:** What will be the output of the following code snippet?
```javascript
console.log(3 + 4 + "5");
```
**Answer:** The output will be `"75

"`. JavaScript performs left-to-right evaluation, so `3 + 4` is evaluated first, resulting in `7`. Then, `7 + "5"` is evaluated as concatenating the string `"5"` to the number `7`, resulting in the string `"75"`.

9. **Question:** What will be the output of the following code snippet?
```javascript
console.log(typeof null);
```
**Answer:** The output will be `"object"`. In JavaScript, the `typeof` operator returns `"object"` for the value `null`, which is a known language quirk.

10. **Question:** What will be the output of the following code snippet?
```javascript
console.log(+"42");
```
**Answer:** The output will be the number `42`. The unary plus operator `+` converts a string to a number. In this case, the string `"42"` is converted to the number `42`.


1. **Question:** What will be the output of the following code snippet?
```javascript
console.log(typeof []);
```
**Answer:** The output will be `"object"`. In JavaScript, arrays are considered objects. The `typeof` operator returns `"object"` for arrays.

2. **Question:** What will be the output of the following code snippet?
```javascript
console.log(2 + "2" - 1);
```
**Answer:** The output will be `21`. JavaScript performs automatic type coercion in this expression. The addition operator concatenates the number `2` with the string `"2"`, resulting in the string `"22"`. Then, the subtraction operator converts the string `"22"` to a number and subtracts `1`, resulting in the number `21`.

3. **Question:** What will be the output of the following code snippet?
```javascript
console.log(1 < 2 < 2);
```
**Answer:** The output will be `true`. JavaScript evaluates the expression from left to right. `1 < 2` is `true`, and then `true < 2` is also `true`. This is because `true` is implicitly converted to the number `1` in the comparison operation.

4. **Question:** What will be the output of the following code snippet?
```javascript
console.log(0 == false);
```
**Answer:** The output will be `true`. In JavaScript, the `==` operator performs type coercion if the operands have different types. In this case, `0` is considered falsy, so it is coerced to `false` before the comparison. Therefore, `0 == false` evaluates to `true`.

5. **Question:** What will be the output of the following code snippet?
```javascript
console.log([] == ![]);
```
**Answer:** The output will be `true`. JavaScript performs type coercion in this comparison. The right side `![]` is evaluated as `false` because an empty array `[]` is considered truthy. Then, `[]` is converted to an empty string, which is falsy. Therefore, `"" == false` evaluates to `true`.
