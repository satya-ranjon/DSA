[**<-Back**](/README.md)

# Sub-Array

**_Sub-sequence may not be contiguous but maintain the relative order._**

Formula _**$(2^n-1)$**_ in sub-sequence length,
**n = array length**

```doc
    Example
    [1,2,3,4]
    This array sub-sequence
    [1]
    [2]
    [1,2]
    [3]
    [1,3]
    [2,3]
    [1,2,3]
    [4]
    [1,4]
    [2,4]
    [1,2,4]
    [3,4]
    [1,3,4]
    [2,3,4]
    [1,2,3,4]
```

## Extract the sub-sequence of the array

```javascript
const array = [1, 2, 3, 4];

// 1. Using the for-loop

let subSqSize = parseInt(Math.pow(2, array.length));

// Run from counter 000..1 to 111..1
for (let counter = 1; counter < subSqSize; counter++) {
  let subSequence = [];
  for (let j = 0; j < array.length; j++) {
    // Check if jth bit in the counter is set
    // If set then print jth element from arr[]
    if ((counter & (1 << j)) != 0) {
      subSequence.push(array[j]);
    }
  }
  console.log(subSequence);
}

// Output
/*
 *[
 *   [1],
 *   [2],
 *   [1,2],
 *   [3],
 *   [1,3],
 *   [2,3],
 *   [1,2,3],
 *   [4],
 *   [1,4],
 *   [2,4],
 *   [3,4],
 *   [1,2,4],
 *   [1,3,4],
 *   [2,3,4],
 *   [1,2,3,4],
 *]
 */

// 2. Using the while-loop
const arr = [1, 2, 3, 4];

const subSqSiz = parseInt(Math.pow(2, arr.length));

let counter = 1;
while (counter < subSqSiz) {
  let subSquence = [];
  let i = 0;
  while (i < arr.length) {
    if ((counter & (1 << i)) !== 0) {
      subSquence.push(arr[i]);
    }
    i++;
  }
  console.log(subSquence);
  counter++;
}

// Output
/*
 *[
 *   [1],
 *   [2],
 *   [1,2],
 *   [3],
 *   [1,3],
 *   [2,3],
 *   [1,2,3],
 *   [4],
 *   [1,4],
 *   [2,4],
 *   [3,4],
 *   [1,2,4],
 *   [1,3,4],
 *   [2,3,4],
 *   [1,2,3,4],
 *]
 */
```
