## How to implement a chainable Add function to calculate the sum of numbers?

## Problem Statement:
You are required to write an add function such that it allows chained addition of numbers and returns the sum of all the added numbers when the sum() method is called. Each call to add() should store the given number and return an object that allows chaining of further add() calls. The sum() method should return the total sum of all the numbers added in the chain.

## Arguments
- n (Number): A number to be added.

## Returns
- sum (Number): The total sum of all the numbers after calling sum().

Examples
```
const value = add(4).add(2).add(3).sum();
console.log(value); // Outputs: 9

const anotherValue = add(10).add(20).sum();
console.log(anotherValue); // Outputs: 30
```


## Solution
```
function add(n = 0) {
  if (isNaN(n)) {
    throw Error("error");
  }
  let total = n;

  return {
    add: function (val = 0) {
      if (isNaN(val)) {
        throw Error("error");
      }
      total += val;
      return this;
    },
    sum: function () {
      return total;
    }
  }
}
```
