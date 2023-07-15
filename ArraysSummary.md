## Array Methods

1. `push()` - Add elements to the end of an array.
    - Example: `[1, 2, 3].push(4, 5) // Output: [1, 2, 3, 4, 5]`
    - Explanation: Adds elements 4 and 5 to the end of the array.

2. `pop()` - Remove the last element from an array.
    - Example: `[1, 2, 3].pop() // Output: [1, 2]`
    - Explanation: Removes the last element (3) from the array.

3. `unshift()` - Add an element to the beginning of an array.
    - Example: `[1, 2, 3].unshift(4) // Output: [4, 1, 2, 3]`
    - Explanation: Adds element 4 to the beginning of the array.

4. `shift()` - Remove the first element from an array.
    - Example: `[1, 2, 3].shift() // Output: [2, 3]`
    - Explanation: Removes the first element (1) from the array.

5. `splice()` - Remove or insert elements at a specific position. and changes Main Array output is removed data and effects present in main array
    let array = [1, 2, 3]
    - Example 1: `output = array.splice(1, 1) // Output: output= [2], array = [1,3] `
    - Explanation: Removes 1 element at index 1 (element 2).
    - Example 2: `array.splice(1, 0, 4) // Output: output=[], array = [1,4,2,3]`
    - Explanation: Inserts element 4 at index 1 without removing any elements.
    - Example 3: `[1, 2, 3].splice(1, 1, 4) // Output: [1, 4, 3]`
    - Explanation: Replaces element at index 1 (element 2) with 4.

7. `slice()` - Extracts a section of an array.
    - Example 1: `[1, 2, 3].slice(1, 2) // Output: [2]`
    - Explanation: Returns elements from index 1 (inclusive) to index 2 (exclusive).
    - Example 2: `[1, 2, 3].slice(1) // Output: [2, 3]`
    - Explanation: Returns elements from index 1 to the end.

8. `concat()` - Merge two or more arrays.
    - Example: `[1, 2, 3].concat([4, 5]) // Output: [1, 2, 3, 4, 5]`
    - Explanation: Concatenates two arrays into a new array.

9. `indexOf()` - Find the index of an element in an array.
    - Example: `[1, 2, 3].indexOf(2) // Output: 1`
    - Explanation: Returns the index of the first occurrence of element 2.

10. `join()` - Join elements of an array into a string.
    - Example: `[1, 2, 3].join('') // Output: '123'`
    - Explanation: Joins the elements of the array into a string with no separator.

11. `reverse()` - Reverse the order of elements in an array.
    - Example: `[1, 2, 3].reverse() // Output: [3, 2, 1]`
    - Explanation: Reverses the order of elements in the array.

12. `sort()` - Sort the elements of an array.
    - Example: `[3, 2, 1].sort() // Output: [1, 2, 3]`
    - Explanation: Sorts the elements of the array in ascending order.

13. `map()` - Apply a function to each element in an array.
    - Example: `[1, 2, 3].map(x => x * 2) // Output: [2, 4, 6]`
    - Explanation: Applies the given function to each element and returns a new array.

14. `filter()` - Create a new array with elements that pass a condition.
    - Example: `[1, 2, 3].filter(x => x > 1) // Output: [2, 3]`
    - Explanation: Creates a new array with elements greater than 1.

15. `reduce()` - Apply a function to reduce the elements of an array to a single value.
    - Example: `[1, 2, 3].reduce((a, b) => a + b) // Output: 6`
    - Explanation: Applies the function to reduce the array to a single value (sum of elements).

16. `every()` - Check if all elements in an array satisfy a condition.
    - Example: `[1, 2, 3].every(x => x > 1) // Output: false`
    - Explanation: Returns true if all elements are greater than 1, otherwise false.

17. `some()` - Check if at least one element in an array satisfies a condition.
    - Example: `[1, 2, 3].some(x => x > 1) // Output: true`
    - Explanation: Returns true if at least one element is greater than 1, otherwise false.

18. `find()` - Find the first element in an array that satisfies a condition.
    - Example: `[1, 2, 3].find(x => x > 1) // Output: 2`
    - Explanation: Returns the first element greater than 1.

19. `findIndex()` - Find the index of the first element in an array that satisfies a condition.
    - Example: `[1, 2, 3].findIndex(x => x > 1) // Output: 1`
    - Explanation: Returns the index of the first element greater than 1.

20. `includes()` - Check if an array contains a specific element.
    - Example: `[1, 2, 3].includes(2) // Output: true`
    - Explanation: Returns true if the array contains the element 2, otherwise false.

21. `fill()` - Fill elements of an array with a specific value.
    - Example 1: `[1, 2, 3].fill(4) // Output: [4, 4, 4]`
    - Explanation: Fills the array with the value 4.
    - Example 2: `[1, 2, 3].fill(4, 1) // Output: [1, 4, 4]`
    - Explanation: Fills the array with the value 4 starting from index 1.
    - Example 3: `[1, 2, 3].fill(4, 1, 2) // Output: [1, 4, 3]`
    - Explanation: Fills the array with the value 4 from index 1 to index 2 (exclusive).

22. `copyWithin()` - Copy elements within an array to a specific position.
    - Example 1: `[1, 2, 3].copyWithin(1) // Output: [1, 1, 2]`
    - Explanation: Copies elements starting from index 1 and pastes them at index 1.
    - Example 2: `[1, 2, 3].copyWithin(1, 2) // Output: [1, 3, 3]`
    - Explanation: Copies elements starting from index 2 and pastes them at index 1.

23. `reduceRight()` - Apply a function to reduce the elements of an array from right to left.
    - Example: `[1, 2, 3].reduceRight((a, b) => a + b) // Output: 6`
    - Explanation: Applies the function to reduce the array from right to left.

24. `entries()` - Return an iterator of key/value pairs for an array.
    - Example: `[1, 2, 3].entries() // Output: [[0, 1], [1, 2], [2, 3]]`
    - Explanation: Returns an iterator that generates an array of key/value pairs.

25. `forEach()` - Iterate over each element in an array and perform a function.
    - Example: `[1, 2, 3].forEach(x => console.log(x)) // Output: 1 2 3`
    - Explanation: Executes a provided function once for each array element.

26. `keys()` - Return an iterator of keys for an array.
    - Example: `[1, 2, 3].keys() // Output: [0, 1, 2]`
    - Explanation: Returns an iterator that generates the keys of the array.

27. `values()` - Return an iterator of values for an array.
    - Example: `[1, 2, 3].values() // Output: [1, 2, 3]`
    - Explanation: Returns an iterator that generates the values of the array.

28. `flat()` - Flatten nested arrays.
    - Example 1: `[1, [2, 3], 4].flat() // Output: [1, 2, 3, 4]`
    - Explanation: Flattens the nested array.
    - Example 2: `[1, [2, [3, 4]]].flat(2) // Output: [1, 2, 3, 4]`
    - Explanation: Flattens the nested array up to 2 levels.

29. `flatMap()` - Apply a function to each element, flatten the result into a new array.
    - Example: `[1, 2, 3].flatMap(x => [x, x]) // Output: [1, 1, 2, 2, 3, 3]`
    - Explanation: Applies the function to each element and flattens the result.

30. `lastIndexOf()` - Find the last index of an element in an array.
    - Example: `[1, 2, 2, 3].lastIndexOf(2) // Output: 2`
    - Explanation: Returns the last index of the element 2 in the array.

31. `Array.from()` - Create a new array from an iterable object.
    - Example 1: `Array.from('abc') // Output: ['a', 'b', 'c']`
    - Explanation: Creates an array from a string.
    - Example 2: `Array.from([1, 2, 3]) // Output: [1, 2, 3]`
    - Explanation: Creates a new array from an existing array.

32. `Array.isArray()` - Check if a value is an array.
    - Example 1: `Array.isArray([1, 2, 3]) // Output: true`
    - Explanation: Returns true if the value is an array.
    - Example 2: `Array.isArray('abc') // Output: false`
    - Explanation: Returns false if the value is not an array.

33. `Array.of()` - Create a new array with the given arguments as elements.
    - Example: `Array.of(1, 2, 3) // Output: [1, 2, 3]`
    - Explanation: Creates a new array with the given arguments as elements.

34. `Array.prototype` - Prototype property of the Array object, which allows adding new methods to all arrays.
    - Example: `Array.prototype.customMethod = function() { // Custom code }`
    - Explanation: Adds a custom method to all arrays.

