var array1 = [5, 12, 8, 130, 44];

function isLargeNumber(element) {
  return element > 44;
}

console.log(array1.findIndex(isLargeNumber));
// expected output: -1