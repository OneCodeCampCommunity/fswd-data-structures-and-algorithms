```js
/*
  Linear Search:
  Sequentially checks each element until a match is found or the list ends.
  Time complexity: O(n)
*/

function linearSearch(array, targetValue) {
  for (let index = 0; index < array.length; index++) {
    if (array[index] === targetValue) {
      return index;
    }
  }
  return -1;
}

const numbers = [10, 50, 30, 70, 20];
const target = 50;

const result = linearSearch(numbers, target);
console.log("Index:", result);
```
