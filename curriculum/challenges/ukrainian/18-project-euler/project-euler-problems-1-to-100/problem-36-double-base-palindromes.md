---
id: 5900f3901000cf542c50fea3
title: 'Problem 36: Double-base palindromes'
challengeType: 1
forumTopicId: 302020
dashedName: problem-36-double-base-palindromes
---

# --description--

The decimal number, 585 = 1001001001<sub>2</sub> (binary), is palindromic in both bases.

Find the sum of all numbers, less than `n`, whereas 1000 ≤ `n` ≤ 1000000, which are palindromic in base 10 and base 2.

(Please note that the palindromic number, in either base, may not include leading zeros.)

# --hints--

`doubleBasePalindromes(1000)` має повернути число.

```js
assert(typeof doubleBasePalindromes(1000) === 'number');
```

`doubleBasePalindromes(1000)` має повернути 1772.

```js
assert(doubleBasePalindromes(1000) == 1772);
```

`doubleBasePalindromes(50000)` має повернути 105795.

```js
assert(doubleBasePalindromes(50000) == 105795);
```

`doubleBasePalindromes(500000)` має повернути 286602.

```js
assert(doubleBasePalindromes(500000) == 286602);
```

`doubleBasePalindromes(1000000)` має повернути 872187.

```js
assert(doubleBasePalindromes(1000000) == 872187);
```

# --seed--

## --seed-contents--

```js
function doubleBasePalindromes(n) {

  return n;
}

doubleBasePalindromes(1000000);
```

# --solutions--

```js
// solution required
```
