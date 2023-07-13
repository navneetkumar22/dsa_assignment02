# PPT - DSA Assignment 2

## Answer 1:
```js
const pairArrays = (nums) => {
    nums.sort((a, b) => a - b)
    let sum = 0;
    for (let i = 0; i < nums.length; i += 2) {
        sum += nums[i]
    }
    return sum;
};
```

<br/>

## Answer 2:
```js
const candiesTypes = (candies) => {
    const set = new Set();
    for (const type of candies) {
        set.add(type)
    }
    return Math.min(set.size, candies.length / 2)
};
```

<br/>

## Answer 3:
```js
const findLHS = (numbers) => {
    let fmap = new Map(), ans = 0
    for (let num of numbers)
        fmap.set(num, (fmap.get(num) || 0) + 1)
    for (let [key, val] of fmap)
        if (fmap.has(~~key + 1))
            ans = Math.max(ans, val + fmap.get(~~key + 1))
    return ans
};
```

<br/>

## Answer 4:
```js
const canPlaceFlowers = (flowerbed, n) => {
    let count = 0;
    let j = 0;
    while (j < flowerbed.length) {
        const flower = flowerbed[j];

        if (flowerbed[j] === 0  // current 
            && (j == 0 || flowerbed[j - 1] == 0) // prev 
            && (j === flowerbed.length - 1 || flowerbed[j + 1] == 0)) { // next 
            flowerbed[j++] = 1;
            count++;
        }
        if (count >= n) {   // if we are able to plant all flowers then it must stop and return true 
            return true;
        }
        j = j + 1
    }
    // if we are not able plant the flowers then it must rreturn false  
    return false;
};
```

<br/>

## Answer 5:
```js
const maxProduct = (arr) => {

    let n = arr.length;

    // if size is less than 3, no triplet exists
    if (n < 3)
        return -1;

    // will contain max product
    let max_product = Number.MIN_VALUE;

    for (let i = 0; i < n - 2; i++) {
        for (let j = i + 1; j < n - 1; j++) {
            for (let k = j + 1; k < n; k++) {
                max_product = Math.max(max_product,
                    arr[i] * arr[j] * arr[k]);
            }
        }
    }

    return max_product;
};
```

<br/>

## Answer 6:
```js
const searchTarget = (nums, target) => {
    return nums.indexOf(target)
};
```

<br/>

## Answer 7:
```js
const isMonotonic = (nums) => {
    let isIncr = false;
    let isDecr = false;
    for (let i = 1; i < nums.length; ++i) {
        if (nums[i] < nums[i - 1]) {
            isIncr = true;
        }
        if (nums[i] > nums[i - 1]) {
            isDecr = true;
        }
        if (isIncr && isDecr) {
            return false;
        }
    }
    return true;
};
```

<br/>

## Answer 8:
```js
const smallestRangeI = (nums, k) => {
    let min = Infinity, max = -Infinity
    for (let e of nums) {
        min = Math.min(min, e)
        max = Math.max(max, e)
    }
    return max - k >= min + k ? max - k - (min + k) : 0
};
```