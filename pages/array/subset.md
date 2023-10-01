[**<-Back**](/README.md)

# Sub-Array

**_A Sub-set is a contiguous part of the array._**

**Sub-set may not be contiguous and may not be order.**

Formula _**n\*(n+1)/2**_ in sub-array length,
**n = array length**

```doc
    Example
    [1,2,3,4]
    This array sub-arrays
    [1]
    [1,2]
    [1,2,3]
    [1,2,3,4]
    [2]
    [2,3]
    [2,3,4]
    [3]
    [3,4]
    [4]
```

## Extract the sub-arrays of the array

```javascript
const array = [1, 2, 3, 4];

// 1. Using the for-loop
let subArrays = [];
for (let i = 0; i < array.length; i++) {
  for (let j = i; j < array.length; j++) {
    let subArray = [];
    for (let s = i; s <= j; s++) {
      subArray.push(array[s]);
    }
    subArrays.push(subArray);
  }
}
console.log(subArrays);

// Output
/*
 *[
 *   [1],
 *   [1,2],
 *   [1,2,3],
 *   [1,2,3,4],
 *   [2],
 *   [2,3],
 *   [2,3,4],
 *   [3],
 *   [3,4],
 *   [4],
 *]
 */

// 2. Using the while-loop
const array = [1, 2, 3, 4];
let subArrays = [];
let i = 0;
while (i < array.length) {
  let j = i;
  while (j < array.length) {
    var subArray = [];
    let s = i;
    while (s <= j) {
      subArray.push(array[s]);
      s++;
    }
    subArrays.push(subArray);
    j++;
  }
  i++;
}
console.log(subArrays);

// Output
/*
 *[
 *   [1],
 *   [1,2],
 *   [1,2,3],
 *   [1,2,3,4],
 *   [2],
 *   [2,3],
 *   [2,3,4],
 *   [3],
 *   [3,4],
 *   [4],
 *]
 */
```
