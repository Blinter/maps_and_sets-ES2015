# Maps and Sets Exercise
### Quick Question #1
What does the following code return?
```javascript
new Set([1,1,2,2,3,4])
```
+ `new Set([1,1,2,2,3,4])`
    - returns `Set(4) { 1, 2, 3, 4 }`
---
### Quick Question #2
What does the following code return?
```javascript
[...new Set("referee")].join("")
```
+ `[...new Set("referee")].join("")`
    - returns `"ref"`
---
# Quick Questions #3
What does the Map m look like after running the following code?
```javascript
let m = new Map();
m.set([1,2,3], true);
m.set([1,2,3], false);
```
+ `m`
    - returns `Map(2) {Array(3) => true, Array(3) => false}`
---
### hasDuplicate
Write a function called hasDuplicate which accepts an array and returns true or false if that array contains a duplicate
```javascript
hasDuplicate([1,3,2,1]) // true
hasDuplicate([1,5,-1,4]) // false
```
```javascript
const hasDuplicate = a => new Set(a).size !== a.length;
```
---
### vowelCount
Write a function called vowelCount which accepts a string and returns a map where the keys are numbers and the values are the count of the vowels in the string.
```javascript
vowelCount('awesome') // Map { 'a' => 1, 'e' => 2, 'o' => 1 }
vowelCount('Colt') // Map { 'o' => 1 }
```
```javascript
const vowelCount = str => str.toLowerCase().split("").reduce((a, v) => {
    if ("aeiou".includes(v))
        a.has(v) ? a.set(v, a.get(v) + 1) : a.set(v, 1);
    return a;
}, new Map());
```
