---
title: Find Sum Factors
tags: math, array
expertise: beginner
firstSeen: 2022-04-22T12:50:54+0000
---

Returns an array of all the numbers that add to the factor given an array of numbers.

```js
const findSumFactors = (arr, factor) => {
    let validNum = arr.filter(number => number < factor);
    let index1stNum = 0;
    let factors = []
    for (number of validNum){
        let index2ndNum = 0;
        for(num of validNum){
            if(index1stNum !== index2ndNum && !( (factors.flat()).includes(num) ) &&  !( (factors.flat()).includes(number) )){
                if(num + number === factor) {
                    factors.push([num, number])
                }
            }
            index2ndNum++
        }
        index1stNum++
    }
    return factors;
}
```

```js
findSumFactors([1,2,3,4,5], 8); // '[5, 3]'
```
