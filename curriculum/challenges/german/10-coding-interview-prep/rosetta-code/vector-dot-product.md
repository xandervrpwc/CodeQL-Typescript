---
id: 594810f028c0303b75339ad3
title: Vector dot product
challengeType: 1
forumTopicId: 302343
dashedName: vector-dot-product
---

# --description--

A vector can have one or more values represented by an ordered collection. Beispiele könnten (x), (x, y) oder (x, y, z) sein.

# --instructions--

Write a function that takes two vectors (represented as one-dimensional arrays) as input and computes their dot product. Your function should return `null` on invalid inputs such as vectors of different lengths or passing anything other than two vectors.

# --hints--

`dotProduct` sollte eine Funktion sein.

```js
assert.equal(typeof dotProduct, 'function');
```

`dotProduct()` sollte `null` zurückgeben.

```js
assert.equal(dotProduct(), null);
```

`dotProduct([1], [1])` sollte `1` zurückgeben.

```js
assert.equal(dotProduct([1], [1]), 1);
```

`dotProduct([1], [1, 2])` sollte `null` zurückgeben.

```js
assert.equal(dotProduct([1], [1, 2]), null);
```

`dotProduct([1, 3, -5], [4, -2, -1])` sollte `3` zurückgeben.

```js
assert.equal(dotProduct([1, 3, -5], [4, -2, -1]), 3);
```

`dotProduct([3, 2, 1], [2, 4, 2], [5, 3, 1])` sollte `null` zurückgeben.

```js
assert.equal(dotProduct([3, 2, 1], [2, 4, 2], [5, 3, 1]), null);
```

`dotProduct([ 0, 3, 6, 9, 12 ], [ 0, 4, 8, 12, 16 ])` sollte `360` zurückgeben.

```js
assert.equal(dotProduct([ 0, 3, 6, 9, 12 ], [ 0, 4, 8, 12, 16 ]), 360);
```

# --seed--

## --seed-contents--

```js
function dotProduct(...vectors) {

}
```

# --solutions--

```js
function dotProduct(...vectors) {
  if (!vectors || !vectors.length || vectors.length > 2 || vectors[0].length !== vectors[1].length) {
    return null;
  }
  const vectorLen = vectors[0].length;

  let prod = 0;
  let sum = 0;
  let j = vectorLen;
  let i = 2;
  // Sum terms
  while (j--) {
    i = 2;
    prod = 1;

    while (i--) {
      prod *= vectors[i][j];
    }
    sum += prod;
  }
  return sum;
}
```
