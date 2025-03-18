```js
/*
  Selection sort repeatedly finds the minimum element from
  the unsorted part of the array and swaps it with the first element of the unsorted part.
  Time Complexity: 0(n^2)
*/

function swapElements(array, firstIndex, secondIndex) {
  const temp = array[firstIndex];
  array[firstIndex] = array[secondIndex];
  array[secondIndex] = temp;
}

function selectionSort(array) {
  /*
    Outer loop: (Focus on each pass (ex. First Pass, Second Pass...))
    - Iterate through the array from the beginning to the second-to-last element
    - For each iteration, it considers a new unsorted subarray starting from the current outerIndex.
  */
  for (let outerIndex = 0; outerIndex < array.length - 1; outerIndex++) {
    // Find the minimum element's index in the unsorted subarray

    /*
      Inner Loop: (Iterate over each element)
        - Iterates through the unsorted subarray, starting from the element after the current outerIndex.
        - Compares each element in the subarray with the current minimum element.
        - If a smaller element is found, it updates the minIndex to point to the new minimum element.
    */
    let minIndex = outerIndex;
    for (
      let innerIndex = outerIndex + 1;
      innerIndex < array.length;
      innerIndex++
    ) {
      if (array[innerIndex] < array[minIndex]) {
        minIndex = innerIndex;
      }
    }

    if (minIndex !== outerIndex) {
      swapElements(array, outerIndex, minIndex);
    }
  }
}

// Example usage
const numbers = [20, 12, 10, 15, 2];

// Sort the array using selection sort
selectionSort(numbers);

console.log("Sorted array:", numbers);
```
