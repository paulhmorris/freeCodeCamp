---
id: ab306dbdcc907c7ddfc30830
title: Steamroller
isRequired: true
challengeType: 5
forumTopicId: 16079
---

## Description
<section id='description'>
Flatten a nested array. You must account for varying levels of nesting.
Remember to use <a href='https://www.freecodecamp.org/forum/t/how-to-get-help-when-you-are-stuck-coding/19514' target='_blank'>Read-Search-Ask</a> if you get stuck. Try to pair program. Write your own code.
</section>

## Instructions
<section id='instructions'>

</section>

## Tests
<section id='tests'>

```yml
tests:
  - text: <code>steamrollArray([[["a"]], [["b"]]])</code> should return <code>["a", "b"]</code>.
    testString: assert.deepEqual(steamrollArray([[["a"]], [["b"]]]), ["a", "b"]);
  - text: <code>steamrollArray([1, [2], [3, [[4]]]])</code> should return <code>[1, 2, 3, 4]</code>.
    testString: assert.deepEqual(steamrollArray([1, [2], [3, [[4]]]]), [1, 2, 3, 4]);
  - text: <code>steamrollArray([1, [], [3, [[4]]]])</code> should return <code>[1, 3, 4]</code>.
    testString: assert.deepEqual(steamrollArray([1, [], [3, [[4]]]]), [1, 3, 4]);
  - text: <code>steamrollArray([1, {}, [3, [[4]]]])</code> should return <code>[1, {}, 3, 4]</code>.
    testString: assert.deepEqual(steamrollArray([1, {}, [3, [[4]]]]), [1, {}, 3, 4]);
  - text: Your solution should not use the <code>Array.prototype.flat()</code> or <code>Array.prototype.flatMap()</code> methods.
    testString: assert(!code.match(/\.flat\([\s\S]*?\)/) && !code.match(/\.flatMap\([\s\S]*?\)/));
```

</section>

## Challenge Seed
<section id='challengeSeed'>

<div id='js-seed'>

```js
function steamrollArray(arr) {
  // I'm a steamroller, baby
  return arr;
}

steamrollArray([1, [2], [3, [[4]]]]);
```

</div>



</section>

## Solution
<section id='solution'>


```js
function steamrollArray(arr) {
  if (!Array.isArray(arr)) {
    return [arr];
  }
  var out = [];
  arr.forEach(function(e) {
    steamrollArray(e).forEach(function(v) {
      out.push(v);
    });
  });
  return out;
}
```

</section>
