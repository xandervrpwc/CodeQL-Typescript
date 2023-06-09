---
id: 5dfb5ecbeacea3f48c6300b1
title: Schritt 21
challengeType: 0
dashedName: step-21
---

# --description--

Use list item (`li`) elements to create items in a list. Here is an example of list items in an unordered list:

```html
<ul>
  <li>milk</li>
  <li>cheese</li>
</ul>
```

Within the `ul` element nest three list items to display three things cats love:

`cat nip` `laser pointers` `lasagna`

# --hints--

Du solltest drei `li`-Elemente haben. Each `li` element should have its own opening and closing tag.

```js
assert($('li').length === 3 && code.match(/<\/li\>/g).length === 3);
```

Du solltest drei `li`-Elemente mit dem Text `cat nip`, `laser pointers` und `lasagna` in beliebiger Reihenfolge haben. Du hast entweder etwas Text weggelassen oder einen Tippfehler gemacht.

```js
assert.deepStrictEqual(
  [...document.querySelectorAll('li')]
    .map((item) => item.innerText.toLowerCase())
    .sort((a, b) => a.localeCompare(b)),
  ['cat nip', 'lasagna', 'laser pointers']
);
```

The three `li` elements should be located between the `ul` element's opening and closing tags.

```js
assert(
  [...document.querySelectorAll('li')].filter(
    (item) => item.parentNode.nodeName === 'UL'
  ).length === 3
);
```

# --seed--

## --seed-contents--

```html
<html>
  <body>
    <main>
      <h1>CatPhotoApp</h1>
      <section>
        <h2>Cat Photos</h2>
        <!-- TODO: Add link to cat photos -->
        <p>See more <a target="_blank" href="https://freecatphotoapp.com">cat photos</a> in our gallery.</p>
        <a href="https://freecatphotoapp.com"><img src="https://cdn.freecodecamp.org/curriculum/cat-photo-app/relaxing-cat.jpg" alt="A cute orange cat lying on its back."></a>
      </section>
      <section>
        <h2>Cat Lists</h2>
        <h3>Things cats love:</h3>
--fcc-editable-region--
        <ul>

        </ul>
--fcc-editable-region--
      </section>
    </main>
  </body>
</html>
```

