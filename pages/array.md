[**< Back**](/README.md)

# Array

- **It is a linear data structure**

The most basic yet important data structure is the array.An array is collection of same data types where the elements are allocated contiguous memory.Because of the contiguous allocation of memory, any element of an array can be accessed in constant time.
Each array element has a cor-responding index number.

```
    Array = 2  6  7  9
    Index = 0  1  2  3
```

- **Some topic array**

  - **_Reverse Array_** - Reverse array means shifting the element of an array in a reverse manner,i.e.,the last element becomes the first element, second last element becomes the second element, and so on.

    ```
    Input  = 1  2  3  4
    Output = 4  3  2  1
    ```

    - **Javascript**

    ```javascript
    const array = [1, 2, 3, 4];

    // First Solution while loop
    function reverseArray(arr) {
      let start = 0;
      let end = arr.length - 1;
      while (start < end) {
        const temp = arr[start];
        arr[start] = arr[end];
        arr[end] = arr[temp];
        start++;
        end--;
      }
    }
    reverseArray(array);
    console.log(array);
    // Output: [4,3,2,1]

    // Second Solution for loop
    let newArray = [];

    for (let i = array.length - 1; i >= 0; i--) {
      newArray.push(array[i]);
    }
    console.log(newArray);
    // Output: [4,3,2,1]

    // Three Solution Recursive
    function reverseArray(arr, start, end) {
      var temp = arr[start];
      arr[start] = arr[end];
      arr[end] = temp;

      if (start + 1 < end - 1) {
        reverseArray(arr, start + 1, end - 1);
      }
    }

    reverseArray(array, 0, array.length - 1);
    console.log(array);
    // Output: [4,3,2,1]
    ```
