
## Array
- `toString(): string`: Converts the array to a string by concatenating all the elements using a comma separator.
- `toLocaleString(): string`: Converts the array to a localized string by calling `toLocaleString()` on each element and concatenating the results using a comma separator.
- `pop(): T | undefined`: Removes the last element from the array and returns it. If the array is empty, `undefined` is returned.
- `push(...items: T[]): number`: Appends new elements to the end of the array and returns the new length of the array.
- `concat(...items: ConcatArray<T>[]): T[]`: Returns a new array that combines the elements of the original array with additional arrays or values.
- `join(separator?: string): string`: Converts all the elements of the array into a string and concatenates them using the specified separator. If no separator is provided, a comma is used as the default separator.
- `reverse(): T[]`: Reverses the order of the elements in the array in place.
- `shift(): T | undefined`: Removes the first element from the array and returns it. If the array is empty, `undefined` is returned.
- `slice(start?: number, end?: number): T[]`: Returns a shallow copy of a portion of the array into a new array. The new array contains elements from the `start` index up to, but not including, the `end` index.
- `sort(compareFn?: (a: T, b: T) => number): this`: Sorts the elements of the array in place. If a compare function is provided, it determines the order of the elements during sorting.
- `splice(start: number, deleteCount?: number): T[]`: Changes the content of an array by removing existing elements and/or adding new elements at the specified index. Returns the deleted elements.
- `unshift(...items: T[]): number`: Inserts new elements at the beginning of the array and returns the new length of the array.
- `indexOf(searchElement: T, fromIndex?: number): number`: Returns the first index at which a given element can be found in the array, or -1 if it is not present. The search starts from the `fromIndex` if provided.
- `lastIndexOf(searchElement: T, fromIndex?: number): number`: Returns the last index at which a given element can be found in the array, or -1 if it is not present. The search starts from the `fromIndex` if provided.
- `every(predicate: (value: T, index: number, array: T[]) => boolean, thisArg?: any): boolean`: Tests whether all elements in the array pass the test implemented by the provided predicate function.
- `some(predicate: (value: T, index: number, array: T[]) => boolean, thisArg?: any): boolean`: Tests whether at least one element in the array passes the test implemented by the provided predicate function.
- `forEach(callbackfn: (value: T, index: number, array: T[]) => void, thisArg?: any): void`: Executes a provided callback function once for each array element.
- `map<U>(callbackfn: (value: T, index: number, array: T[]) => U, thisArg?: any): U[]`: Creates a new array by calling a provided callback function on each element in the array.
- `filter(predicate: (value: T, index: number, array: T[]) => boolean, thisArg?: any): T[]`: Creates a new array with all elements that pass the test implemented by the provided predicate function.
- `reduce(callbackfn: (previousValue: T, currentValue: T, currentIndex: number, array: T[]) => T, initialValue?: T): T`: Applies a function against an accumulator and each element in the array to reduce it to a single value.
- `reduceRight(callbackfn: (previousValue: T, currentValue: T, currentIndex: number, array: T[]) => T, initialValue?: T): T`: Applies a function against an accumulator and each element in the array (from right to left) to reduce it to a single value.

### `DateTimeFormatOptions`

- `localeMatcher?: "best fit" | "lookup"`: Specifies the algorithm used to match locale tags.
- `weekday?: "long" | "short" | "narrow"`: Specifies the weekday formatting style.
- `era?: "long" | "short" | "narrow"`: Specifies the era formatting style.
- `year?: "numeric" | "2-digit"`: Specifies the year formatting style.
- `month?: "numeric" | "2-digit" | "long" | "short" | "narrow"`: Specifies the month formatting style.
- `day?: "numeric" | "2-digit"`: Specifies the day formatting style.
- `hour?: "numeric" | "2-digit"`: Specifies the hour formatting style.
- `minute?: "numeric" | "2-digit"`: Specifies the minute formatting style.
- `second?: "numeric" | "2-digit"`: Specifies the second formatting style.
- `timeZoneName?: "short" | "long" | "shortOffset" | "longOffset" | "shortGeneric" | "longGeneric"`: Specifies the time zone name formatting style.
- `formatMatcher?: "best fit" | "basic"`: Specifies the format matching style.
- `hour12?: boolean`: Specifies whether 12-hour time format should be used.
- `timeZone?: string`: Specifies the time zone to use.

### `ResolvedDateTimeFormatOptions`

- `locale: string`: The actual locale used.
- `calendar: string`: The calendar used.
- `numberingSystem: string`: The numbering system used.
- `timeZone: string`: The time zone used.
- `hour12?: boolean`: Indicates whether 12-hour time format is used.
- `weekday?: string`: The weekday formatting style used.
- `era?: string`: The era formatting style used.
- `year?: string`: The year formatting style used.
- `month?: string`: The month formatting style used.
- `day?: string`: The day formatting style used.
- `hour?: string`: The hour formatting style used.
- `minute?: string`: The minute formatting style used.
- `second?: string`: The second formatting style used.
- `timeZoneName?: string`: The time zone name formatting style used.

## Functions

- `eval(x: string): any`: Evaluates and executes JavaScript code provided as a string parameter.
- `parseInt(string: string, radix?: number): number`: Converts a string to an integer using the specified radix (base).
- `parseFloat(string: string): number`: Converts a string to a floating-point number.
- `isNaN(number: number): boolean`: Returns `true` if a value is `NaN` (not a number), otherwise `false`.
- `isFinite(number: number): boolean`: Returns `true` if a value is a finite number, otherwise `false`.
- `decodeURI(encodedURI: string): string`: Decodes an encoded Uniform Resource Identifier (URI).
- `decodeURIComponent(encodedURIComponent: string): string`: Decodes an encoded component of a URI.
- `encodeURI(uri: string): string`: Encodes a text string as a valid URI.
- `encodeURIComponent(uriComponent: string | number | boolean): string`: Encodes a text string as a valid URI component.
- `escape(string: string): string`: Computes a new string with certain characters replaced by a hexadecimal escape sequence (deprecated).
- `unescape(string: string): string`: Computes a new string with hexadecimal escape sequences replaced by the corresponding characters (deprecated).


### Object

Provides methods and properties common to all JavaScript objects.

- `constructor: Function`: The initial value of `Object.prototype.constructor` is the standard built-in `Object` constructor.
- `toString(): string`: Returns a string representation of an object.
- `toLocaleString(): string`: Returns a date converted to a string using the current locale.
- `valueOf(): Object`: Returns the primitive value of an object.
- `hasOwnProperty(v: PropertyKey): boolean`: Determines whether an object has a property with the specified name.
- `isPrototypeOf(v: Object): boolean`: Determines whether an object exists in another object's prototype chain.
- `propertyIsEnumerable(v: PropertyKey): boolean`: Determines whether a specified property is enumerable.

### ObjectConstructor

Represents the constructor function for the `Object` class.

- `new(value?: any): Object`: Creates a new object with an optional initial value.
- `getPrototypeOf(o: any): any`: Returns the prototype of an object.
- `getOwnPropertyDescriptor(o: any, p: PropertyKey): PropertyDescriptor | undefined`: Gets the own property descriptor of the specified object.
- `getOwnPropertyNames(o: any): string[]`: Returns the names of the own properties of an object.
- `create(o: object | null): any`: Creates an object with the specified prototype or `null` as the prototype.
- `create(o: object | null, properties: PropertyDescriptorMap & ThisType<any>): any`: Creates an object with the specified prototype and additional properties.
- `defineProperty<T>(o: T, p: PropertyKey, attributes: PropertyDescriptor & ThisType<any>): T`: Adds or modifies a property on an object.
- `defineProperties<T>(o: T, properties: PropertyDescriptorMap & ThisType<any>): T`: Adds or modifies multiple properties on an object.
- `seal<T>(o: T): T`: Prevents the modification of attributes of existing properties and the addition of new properties.
- `freeze<T extends Function>(f: T): T`: Prevents the modification of existing property attributes and values, and the addition of new properties to a function object.
- `freeze<T extends { [idx: string]: U | null | undefined | object }, U extends string | bigint | number | boolean | symbol>(o: T): Readonly<T>`: Prevents the modification of existing property attributes and values, and the addition of new properties to an object.
- `freeze<T>(o: T): Readonly<T>`: Prevents the modification of existing property attributes and values, and the addition of new properties to an object.
- `preventExtensions<T>(o: T): T`: Prevents the addition of new properties to an object.
- `isSealed(o: any): boolean`: Returns `true` if existing property attributes cannot be modified and new properties cannot be added to an object.
- `isFrozen(o: any): boolean`: Returns `true` if existing property attributes and values cannot be modified, and new properties cannot be added to an object.
- `isExtensible(o: any): boolean`: Returns `true` if new properties can be added to an object.
- `keys(o: object): string[]`: Returns the names of the enumerable string properties and methods of an object.


## Interface: Function

- `apply(this: Function, thisArg: any, argArray?: any): any`: Calls the function, substituting the specified object for the this value of the function, and the specified array for the arguments of the function.
- `call(this: Function, thisArg: any, ...argArray: any[]): any`: Calls a method of an object, substituting another object for the current object.
- `bind(this: Function, thisArg: any, ...argArray: any[]): any`: For a given function, creates a bound function that has the same body as the original function. The this object of the bound function is associated with the specified object, and has the specified initial parameters.
- `toString(): string`: Returns a string representation of a function.
- `prototype: any`: Represents the prototype object of a function.
- `length: number`: Represents the number of arguments expected by a function.
- `arguments: any`: Non-standard extension that represents the arguments passed to a function.
- `caller: Function`: Non-standard extension that represents the calling function of the current function.

## Interface: String

- `toString(): string`: Returns a string representation of a string.
- `charAt(pos: number): string`: Returns the character at the specified index.
- `charCodeAt(index: number): number`: Returns the Unicode value of the character at the specified location.
- `concat(...strings: string[]): string`: Returns a string that contains the concatenation of two or more strings.
- `indexOf(searchString: string, position?: number): number`: Returns the position of the first occurrence of a substring.
- `lastIndexOf(searchString: string, position?: number): number`: Returns the last occurrence of a substring in the string.
- `localeCompare(that: string): number`: Determines whether two strings are equivalent in the current locale.
- `match(regexp: string | RegExp): RegExpMatchArray | null`: Matches a string with a regular expression, and returns an array containing the results of that search.
- `replace(searchValue: string | RegExp, replaceValue: string): string`: Replaces text in a string, using a regular expression or search string.
- `replace(searchValue: string | RegExp, replacer: (substring: string, ...args: any[]) => string): string`: Replaces text in a string, using a regular expression or search string.
- `search(regexp: string | RegExp): number`: Finds the first substring match in a regular expression search.
- `slice(start?: number, end?: number): string`: Returns a section of a string.
- `split(separator: string | RegExp, limit?: number): string[]`: Splits a string into substrings using the specified separator and returns them as an array.
- `substring(start: number, end?: number): string`: Returns the substring at the specified location within a String object.
- `toLowerCase(): string`: Converts all the alphabetic characters in a string to lowercase.
- `toLocaleLowerCase(locales?: string | string[]): string`: Converts all alphabetic characters to lowercase, taking into account the host environment's current locale.
- `toUpperCase(): string`: Converts all the alphabetic characters in a string to uppercase.
- `toLocaleUpperCase(locales?: string | string[]): string`: Returns a string where all alphabetic characters have been converted to uppercase, taking into account the host environment's current locale.
- `trim(): string`: Removes the leading and trailing whitespace and line terminator characters from a string.
- `length: number`: Returns the length of a String object.
- `substr(from: number, length?: number): string`: Gets a substring beginning at the specified location and having the specified length.
- `valueOf(): string`: Returns the primitive value of the specified object.


## Interface: Number

- `toString(radix?: number): string`: Returns a string representation of a number.
- `toFixed(fractionDigits?: number): string`: Returns a string representing a number in fixed-point notation.
- `toExponential(fractionDigits?: number): string`: Returns a string containing a number represented in exponential notation.
- `toPrecision(precision?: number): string`: Returns a string containing a number represented either in exponential or fixed-point notation with a specified number of digits.
- `valueOf(): number`: Returns the primitive value of the specified object.

## Interface: NumberConstructor

- `new(value?: any): Number`: Creates a new Number object.
- `(value?: any): number`: Creates a new number.
- `prototype: Number`: Represents the prototype object of the Number constructor.
- `MAX_VALUE: number`: The largest number that can be represented in JavaScript.
- `MIN_VALUE: number`: The closest number to zero that can be represented in JavaScript.
- `NaN: number`: A value that is not a number.
- `NEGATIVE_INFINITY: number`: A value that is less than the largest negative number that can be represented in JavaScript.
- `POSITIVE_INFINITY: number`: A value greater than the largest number that can be represented in JavaScript.


## Interface: Math

- `E: number`: The mathematical constant e.
- `LN10: number`: The natural logarithm of 10.
- `LN2: number`: The natural logarithm of 2.
- `LOG2E: number`: The base-2 logarithm of e.
- `LOG10E: number`: The base-10 logarithm of e.
- `PI: number`: Pi, the ratio of the circumference of a circle to its diameter.
- `SQRT1_2: number`: The square root of 0.5.
- `SQRT2: number`: The square root of 2.
- `abs(x: number): number`: Returns the absolute value of a number.
- `acos(x: number): number`: Returns the arc cosine of a number.
- `asin(x: number): number`: Returns the arcsine of a number.
- `atan(x: number): number`: Returns the arctangent of a number.
- `atan2(y: number, x: number): number`: Returns the angle from the X axis to a point.
- `ceil(x: number): number`: Returns the smallest integer greater than or equal to a number.
- `cos(x: number): number`: Returns the cosine of a number.
- `exp(x: number): number`: Returns e (the base of natural logarithms) raised to a power.
- `floor(x: number): number`: Returns the largest integer less than or equal to a number.
- `log(x: number): number`: Returns the natural logarithm (base e) of a number.
- `max(...values: number[]): number`: Returns the largest value among a set of numbers.
- `min(...values: number[]): number`: Returns the smallest value among a set of numbers.
- `pow(x: number, y: number): number`: Returns the value of a base expression raised to a specified power.
- `random(): number`: Returns a pseudorandom number between 0 and 1.
- `round(x: number): number`: Returns the value of a number rounded to the nearest integer.
- `sin(x: number): number`: Returns the sine of a number.
- `sqrt(x: number): number`: Returns the square root of a number.
- `tan(x: number): number`: Returns the tangent of a number.


# Date Interface

The `Date` interface enables basic storage and retrieval of dates and times.

- `toString(): string`: Returns a string representation of a date.
- `toDateString(): string`: Returns a date as a string value.
- `toTimeString(): string`: Returns a time as a string value.
- `toLocaleString(): string`: Returns a value as a string value appropriate to the host environment's current locale.
- `toLocaleDateString(): string`: Returns a date as a string value appropriate to the host environment's current locale.
- `toLocaleTimeString(): string`: Returns a time as a string value appropriate to the host environment's current locale.
- `valueOf(): number`: Returns the stored time value in milliseconds since midnight, January 1, 1970 UTC.
- `getTime(): number`: Returns the stored time value in milliseconds since midnight, January 1, 1970 UTC.
- `getFullYear(): number`: Gets the year using local time.
- `getUTCFullYear(): number`: Gets the year using Universal Coordinated Time (UTC).
- `getMonth(): number`: Gets the month using local time.
- `getUTCMonth(): number`: Gets the month of a Date object using Universal Coordinated Time (UTC).
- `getDate(): number`: Gets the day of the month using local time.
- `getUTCDate(): number`: Gets the day of the month using Universal Coordinated Time (UTC).
- `getDay(): number`: Gets the day of the week using local time.
- `getUTCDay(): number`: Gets the day of the week using Universal Coordinated Time (UTC).
- `getHours(): number`: Gets the hours in a date using local time.
- `getUTCHours(): number`: Gets the hours value in a Date object using Universal Coordinated Time (UTC).
- `getMinutes(): number`: Gets the minutes of a Date object using local time.
- `getUTCMinutes(): number`: Gets the minutes of a Date object using Universal Coordinated Time (UTC).
- `getSeconds(): number`: Gets the seconds of a Date object using local time.
- `getUTCSeconds(): number`: Gets the seconds of a Date object using Universal Coordinated Time (UTC).
- `getMilliseconds(): number`: Gets the milliseconds of a Date using local time.
- `getUTCMilliseconds(): number`: Gets the milliseconds of a Date object using Universal Coordinated Time (UTC).
- `getTimezoneOffset(): number`: Gets the difference in minutes between the time on the local computer and Universal Coordinated Time (UTC).
- `setTime(time: number): number`: Sets the date and time value in the Date object.
- `setMilliseconds(ms: number): number`: Sets the milliseconds value in the Date object using local time.
- `setUTCMilliseconds(ms: number): number`: Sets the milliseconds value in the Date object using Universal Coordinated Time (UTC).
- `setSeconds(sec: number, ms?: number): number`: Sets the seconds value in the Date object using local time.
- `setUTCSeconds(sec: number, ms?: number): number`: Sets the seconds value in the Date object using Universal Coordinated Time (UTC).
- `setMinutes(min: number, sec?: number, ms?: number): number`: Sets the minutes value in the Date object using local time.
- `setUTCMinutes(min: number, sec?: number, ms?: number): number`: Sets the minutes value in the Date object using Universal Coordinated Time (UTC).
- `setHours(hours: number, min?: number, sec?: number, ms?: number): number`: Sets the hour value in the Date object using local time.
- `setUTCHours(hours: number, min?: number, sec?: number, ms?: number): number`: Sets the hours value in the Date object using Universal Coordinated Time (UTC).
- `setDate(date: number): number`: Sets the numeric day-of-the-month value of the Date object using local time.
- `setUTCDate(date: number): number`: Sets the numeric day of the month in the Date object using Universal Coordinated Time (UTC).
- `setMonth(month: number, date?: number): number`: Sets the month value in the Date object using local time.
- `setUTCMonth(month: number, date?: number): number`: Sets the month value in the Date object using Universal Coordinated Time (UTC).
- `setFullYear(year: number, month?: number, date?: number): number`: Sets the year of the Date object using local time.
- `setUTCFullYear(year: number, month?: number, date?: number): number`: Sets the year value in the Date object using Universal Coordinated Time (UTC).
- `toUTCString(): string`: Returns a date converted to a string using Universal Coordinated Time (UTC).
- `toISOString(): string`: Returns a date as a string value in ISO format.
- `toJSON(key?: any): string`: Used by the JSON.stringify method to enable the transformation of an object's data for JavaScript Object Notation (JSON) serialization.

