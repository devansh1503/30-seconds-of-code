---
title: CountingSort
tags: algorithm,array,beginner
firstSeen: 2021-11-2
lastUpdated: 2021-11-2
---
Counting sort algorithm works by counting distinct objects, and then calculating their position in the output.
1. The array containing count operates between the minimum and maximum value of given array.
2. The output contains the elements with count more than 0 and thus decrements its count.
3. This algorithm is efficient for handling duplicates. And has a time complexity of n+k.
```js
const countingSort = (arr, min, max) => {
    const count = {};
    for (let i = min; i <= max; i++) {
        count[i] = 0;
    }
    for (let i = 0; i < arr.length; i++) {
        count[arr[i]] += 1;
    }
    const sortedArray = [];
    for (let i = min; i <= max; i++) {
        while (count[i] > 0) {
            sortedArray.push(i);
            count[i]--;
        }
    }
    return sortedArray;
};
```
```js
countingSort([2,7,8,3,6,6],2,8);//2,3,6,6,7,8
```
