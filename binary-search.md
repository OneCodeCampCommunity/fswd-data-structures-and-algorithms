```js
/*
  Binary Search:
  An efficient algorithm for finding a target value in a sorted array.
  It works by repeatedly dividing the search space in half.

  Key Steps:
  1. Initialize pointers:
    - left: Points to the leftmost index.
    - right: Points to the rightmost index.
  2. Find the middle index:
    - mid = (left + right) / 2
  3. Compare the middle element with the target value:
    - If equal, return the index.
    - If less than the target, search the right half.
    - If greater than the target, search the left half.
  4. Repeat steps 2 and 3 until the target is found or the search space is empty.
*/

function binarySearch(sortedArray, targetValue) {
  let leftIndex = 0;
  let rightIndex = sortedArray.length - 1;
  let middleIndex;

  while (rightIndex >= leftIndex) {
    middleIndex = leftIndex + Math.floor((rightIndex - leftIndex) / 2);

    // If the target value is at the middle index
    if (sortedArray[middleIndex] === targetValue) {
      return middleIndex;
    }

    // If the target value is smaller than the middle value,
    // search the left half of the array
    if (sortedArray[middleIndex] > targetValue) {
      rightIndex = middleIndex - 1;
    } else {
      // Otherwise, search the right half of the array
      leftIndex = middleIndex + 1;
    }
  }

  // If the target value is not found
  return -1;
}

// Example usage
const numbers = [10, 20, 30, 40, 50, 60];
const target = 40;

const result = binarySearch(numbers, target);
console.log("Result:", result);
```
