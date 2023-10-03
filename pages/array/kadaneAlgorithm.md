[**<-Back**](/README.md)

# Kadane’s Algorithm

The task is to find the sum of the contiguous sub-array within a array with the largest sum.

   <img src="../../assets/kadane-Algorithm.png" width="600" height="300" />

The idea of **_kadane's algorithm_** is to maintain variable **_max_ending_here_** that stores the maximum sum contiguous sub-array ending at current index and a variable **_max_so_far_** stores the maximum sum of contiguous sub-array found so far, Everytime there is positive-sum value in **_max_ending_here_** compare it with **_max_so_far_** and update **_max_so_far_** if it is greater than max_so_far.

- ## So main _**Intuition**_ behind _**Kadane's algorithm**_ is

  - The sub-array with negative sum is discarded (By assigning max_ending_here=0 in code).
  - we carry sub-array till it gives positive sum

```
Initialize:
    max_ending_here = ARRAY[0]
    max_so_far = ARRAY[0]

Loop for each element of the array

  (a) max_ending_here = max_ending_here + ARRAY[index]
  (b) if(ARRAY[index] > max_ending_here)
            max_ending_here = ARRAY[index]
  (c) if(max_so_far < max_ending_here)
            max_so_far = max_ending_here
return max_so_far
```

## Example

```javascript
const arr = [5, -1, 2, -7, 10, -2, 5, -15, 4, 21, -4, -6, 10, -25];

// Use for-loop
let max_ending_here = arr[0];
let max_so_far = arr[0];

for (let i = 1; i < arr.length; i++) {
  max_ending_here = max_ending_here + arr[i];

  if (arr[i] > max_ending_here) {
    max_ending_here = arr[i];
  }

  if (max_ending_here > max_so_far) {
    max_so_far = max_ending_here;
  }
}
console.log("Maximum sub-array sum is:", max_so_far);

// output = Maximum sub-array sum is: 25

// Use while loop

let max_ending_here = arr[0];
let max_so_far = arr[0];

let i = 1;
while (i < arr.length) {
  max_ending_here = max_ending_here + arr[i];

  if (arr[i] > max_ending_here) {
    max_ending_here = arr[i];
  }

  if (max_ending_here > max_so_far) {
    max_so_far = max_ending_here;
  }
  i++;
}

console.log("Maximum subarray sum is:", max_so_far);

// output = Maximum sub-array sum is: 25
```
