---
id: 5a23c84252665b21eecc8013
title: Sorting algorithms/Strand sort
challengeType: 1
forumTopicId: 302319
dashedName: sorting-algorithmsstrand-sort
---

# --description--

The **Strand sort** creates sorted subsets that are merged to create the final result.

Consider an `unsortedArray = [3, 1, 4, 2]`. Pick the first item `3` and copy it into a separate array. Search for any bigger item following this item. When you find the a larger item, in this case `4`, copy it to the separate array, `[3, 4]`, and compare the following items to this new value, `4`.

After you have reached the end of the array, remove the items you copied, `[3, 4]`, and start again with the first item remaining in the `unsortedArray`, in this case `1`.

Following this process results in two sorted arrays, `[3, 4]` and `[1, 2]`. Merge these two arrays to create the `strandSortedArray`.

```js
const unsortedArray = [3, 1, 4, 2];
const strandsortedArray = [1, 2, 3, 4];
```

Write a function to sort an array using the **Strand sort**. The function should return the sorted array.


# --hints--

`strandSort` sollte eine Funktion sein.

```js
assert(typeof strandSort == 'function');
```

`strandSort([25, 32, 12, 7, 20])` sollte ein Array zurückgeben.

```js
assert(Array.isArray(strandSort([25, 32, 12, 7, 20])));
```

`strandSort([25, 32, 12, 7, 20])` sollte `[7, 12, 20, 25, 32]` zurückgeben.

```js
assert.deepEqual(strandSort([25, 32, 12, 7, 20]), [7, 12, 20, 25, 32]);
```

`strandSort([38, 45, 35, 8, 13])` sollte `[8, 13, 35, 38, 45]` zurückgeben.

```js
assert.deepEqual(strandSort([38, 45, 35, 8, 13]), [8, 13, 35, 38, 45]);
```

`strandSort([43, 36, 20, 34, 24])` sollte `[20, 24, 34, 36, 43]` zurückgeben.

```js
assert.deepEqual(strandSort([43, 36, 20, 34, 24]), [20, 24, 34, 36, 43]);
```

`strandSort([12, 33, 26, 18, 1, 16, 38])` sollte `[1, 12, 16, 18, 26, 33, 38]` zurückgeben.

```js
assert.deepEqual(strandSort([12, 33, 26, 18, 1, 16, 38]), [
  1,
  12,
  16,
  18,
  26,
  33,
  38
]);
```

`strandSort([3, 39, 48, 16, 1, 4, 29])` sollte `[1, 3, 4, 16, 29, 39, 48]` zurückgeben.

```js
assert.deepEqual(strandSort([3, 39, 48, 16, 1, 4, 29]), [
  1,
  3,
  4,
  16,
  29,
  39,
  48
]);
```

# --seed--

## --seed-contents--

```js
function strandSort(list) {

}
```

# --solutions--

```js
function strandSort(list) {
  function merge(left, right) {
    var result = [];
    while (left.length != 0 && right.length != 0) {
      if (left[0] <= right[0]) result.push(left.shift());
      else result.push(right.shift());
    }
    result.push.apply(result, left);
    result.push.apply(result, right);
    return result;
  }

  if (list.length <= 1) return list;
  var result = [];
  while (list.length > 0) {
    var sorted = [];
    sorted.push(list.shift());
    var len = list.length;
    for (var i = 1; i < len; i++) {
      var elem = list[i];
      if (sorted[i - 1] <= elem) {
        sorted.push(elem);
        sorted.splice(i, 1);
      }
    }

    result = merge(result, sorted);
  }
  return result;
}
```
