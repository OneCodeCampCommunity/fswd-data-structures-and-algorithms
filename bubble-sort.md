```js
/*
  Bubble sort repeatedly compares adjacent elements and 
  swaps them if they are in the wrong order, 
  gradually "bubbling" larger elements to the end.

  Time Complexity: O(n^2)
*/

function bubbleSort(array) {
  // Outer Loop:
  //   Iterates over the array from the beginning to the second-to-last element.
  //   Determines the number of passes required to sort the list.
  for (let outerIndex = 0; outerIndex < array.length - 1; outerIndex++) {
    let isSwapped = false; // Indicate if any swaps occurred in the inner loop

    // Inner Loop:
    //   Iterates through a portion of the list in each pass.
    //   Compares adjacent elements and swaps them if they are in the wrong order.
    for (
      let innerIndex = 0;
      innerIndex < array.length - outerIndex - 1;
      innerIndex++
    ) {
      if (array[innerIndex] > array[innerIndex + 1]) {
        // Swap the adjacent elements
        let temp = array[innerIndex];
        array[innerIndex] = array[innerIndex + 1];
        array[innerIndex + 1] = temp;
        isSwapped = true;
      }
    }

    // If no swaps occurred in the inner loop, the array is already sorted
    if (!isSwapped) {
      break;
    }
  }
}

// Function calling
const numbers = [7, 6, 4, 3];

// Sort the array using bubble sort
bubbleSort(numbers);

console.log("Sorted array:", numbers);
```
