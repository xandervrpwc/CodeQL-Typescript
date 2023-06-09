---
id: a2f1d72d9b908d0bd72bb9f6
title: Crea una persona
challengeType: 1
forumTopicId: 16020
dashedName: make-a-person
---

# --description--

Completa el constructor de objetos con los siguientes métodos:

```js
getFirstName()
getLastName()
getFullName()
setFirstName(first)
setLastName(last)
setFullName(firstAndLast)
```

Ejecuta las pruebas para ver el resultado esperado para cada método. Los métodos que toman un argumento deben aceptar sólo un argumento y tiene que ser una cadena. Estos métodos deben ser el único medio disponible para interactuar con el objeto.

# --hints--

No se deben agregar propiedades. `Object.keys(bob).length` siempre debe devolver 6.

```js
assert.strictEqual(
  Object.keys((function () {
    let bob = new Person('Bob Ross');
    bob.setFirstName('Haskell');
    bob.setLastName('Curry');
    bob.setFullName('John Smith');
    return bob;
  })()).length,
  6
 );
```

`bob instanceof Person` debe devolver `true`.

```js
assert.deepEqual(_test_bob instanceof Person, true);
```

`bob.firstName` debe devolver `undefined`.

```js
assert.deepEqual(_test_bob.firstName, undefined);
```

`bob.lastName` debe devolver `undefined`.

```js
assert.deepEqual(_test_bob.lastName, undefined);
```

`bob.getFirstName()` debe devolver la cadena `Bob`.

```js
assert.deepEqual(_test_bob.getFirstName(), 'Bob');
```

`bob.getLastName()` debe devolver la cadena `Ross`.

```js
assert.deepEqual(_test_bob.getLastName(), 'Ross');
```

`bob.getFullName()` debe devolver la cadena `Bob Ross`.

```js
assert.deepEqual(_test_bob.getFullName(), 'Bob Ross');
```

`bob.getFullName()` debe devolver la cadena `Haskell Ross` after `bob.setFirstName("Haskell")`.

```js
assert.strictEqual(
  (function () {
    _test_bob.setFirstName('Haskell');
    return _test_bob.getFullName();
  })(),
  'Haskell Ross'
);
```

`bob.getFullName()` debe devolver la cadena `Haskell Curry` después de `bob.setLastName("Curry")`.

```js
assert.strictEqual(
  (function () {
    var _bob = new Person('Haskell Ross');
    _bob.setLastName('Curry');
    return _bob.getFullName();
  })(),
  'Haskell Curry'
);
```

`bob.getFullName()` debe devolver la cadena `Haskell Curry` después de `bob.setFullName("Haskell Curry")`.

```js
assert.strictEqual(
  (function () {
    _test_bob.setFullName('Haskell Curry');
    return _test_bob.getFullName();
  })(),
  'Haskell Curry'
);
```

`bob.getFirstName()` debe devolver la cadena `Haskell` después de `bob.setFullName("Haskell Curry")`.

```js
assert.strictEqual(
  (function () {
    _test_bob.setFullName('Haskell Curry');
    return _test_bob.getFirstName();
  })(),
  'Haskell'
);
```

`bob.getLastName()` debe devolver la cadena `Curry` después de `bob.setFullName("Haskell Curry")`.

```js
assert.strictEqual(
  (function () {
    _test_bob.setFullName('Haskell Curry');
    return _test_bob.getLastName();
  })(),
  'Curry'
);
```

# --seed--

## --after-user-code--

```js
const _test_bob = new Person('Bob Ross');
```

## --seed-contents--

```js
const Person = function(firstAndLast) {
  this.getFullName = function() {
    return "";
  };
  return firstAndLast;
};

const bob = new Person('Bob Ross');
bob.getFullName();
```

# --solutions--

```js
const Person = function(firstAndLast) {

  let firstName, lastName;

  function updateName(str) {
    firstName = str.split(" ")[0];
    lastName = str.split(" ")[1];
  }

  updateName(firstAndLast);

  this.getFirstName = function(){
    return firstName;
  };

  this.getLastName = function(){
    return lastName;
  };

  this.getFullName = function(){
    return firstName + " " + lastName;
  };

  this.setFirstName = function(str){
    firstName = str;
  };


  this.setLastName = function(str){
    lastName = str;
  };

  this.setFullName = function(str){
    updateName(str);
  };
};

const bob = new Person('Bob Ross');
bob.getFullName();
```
