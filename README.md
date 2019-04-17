# Gilded Rose Refactoring Exercise in JavaScript

> **TL;DR:**
> You inherited this NPM package for stock management. You are asked to add support for a new product. Feel free to refactor as you like.

If you want to get cracking:

```
git clone https://github.com/robinpokorny/gilded-rose-javascript.git
cd gilded-rose-javascript
yarn
yarn test
```

---

## Notes on this version

- Turned into an NPM package. Only the API of the whole package needs to preserved
- You can change the code, add dependencies, use tooling, create files or folders – whatever you find helpful
- [Jest](https://jestjs.io/), the unit testing framework, is provided for convinience – it is entirely optional
- The task now uses more modern naming and other conventions
- Part of the motivation was to make it functional programming friendly
- The original text was slighlty adjusted to reflect these changes

## Original text

Hi and welcome to team Gilded Rose.

As you know, we are a small inn with a prime location in a prominent city ran
by a friendly innkeeper named Allison. We also buy and sell only the finest
goods. Unfortunately, our goods are constantly degrading in quality as they
approach their sell by date.

We have a system in place that updates our inventory for us. It was developed
by a no-nonsense type named Leeroy, who has moved on to new adventures. Your
task is to add the new feature to our system so that we can begin selling a
new category of items.

First an introduction to our system:

- All items have a `sellIn` value which denotes the number of days we have to
  sell the item

- All items have a `quality` value which denotes how valuable the item is

- At the end of each day our system lowers both values for every item

Pretty simple, right? Well this is where it gets interesting:

- Once the `sellIn` days is less then zero, `quality` degrades twice as fast

- The `quality` of an item is never negative

- "Aged Brie" actually increases in `quality` the older it gets

- The `quality` of an item is never more than 50

- "Sulfuras", being a legendary item, never has to be sold nor does it
  decrease in `quality`

- "Backstage passes", like aged brie, increases in `quality` as it's `sellIn`
  value decreases; `quality` increases by 2 when there are 10 days or less
  and by 3 when there are 5 days or less but `quality` drops to 0 after the
  concert

We have recently signed a supplier of conjured items. This requires an update
to our system:

- "Conjured" items degrade in `quality` twice as fast as normal items

Feel free to make any changes to the package and add any new
code as long as everything still works correctly. However, do not alter the
interface of input and output of the package as this belongs to the goblin in the corner
who will insta-rage and one-shot you as he doesn't believe in shared code
ownership.

Just for clarification, an item can never have its `quality` increase above 50,
however "Sulfuras" is a legendary item and as such its `quality` is 80 and it
never alters.

### Sources:

- http://iamnotmyself.com/2011/02/13/refactor-this-the-gilded-rose-kata/
- https://github.com/professor/GildedRose
- https://github.com/guyroyse/gilded-rose-javascript

## Help

Please read those only after tring yourself first.

<details> <summary>I have no idea what I should do</summary>

Make sure you read the text properly. It asks you to add a support for a new type of product. However, the _real task_ is to refactor the current code first as it is uneasy to follow.

Most people would probably work in this order:

1. Write unit tests for all current product types and all edge cases
2. Refactor the code to be more understandable; the unit tests will help prevent regressions
3. Add unit tests for the new product, thinking about all edge cases
4. Update the code to handle the new product and make tests pass
   </details>

<details> <summary>How do I verify I fullfiled the task?</summary>

The task has many edge cases. It can be easy to think you are done, but there could be regressions. In fact, that happened to me the first time I tried this kata.

To be totaly sure you did a good job, I prepared a test, that will validate your solution.

It is strongly recommended to run the validation only when you think you are done and the systems supports "Conjured" items.

Run this command:

```
yarn validate
```

If it passed, congratulations! You did great!

If it fails, do not worry. I was there, too. You might want to test few more edge cases on the original code. The text above does not tell you everything. Resist reverse-engineering the validation test.

</details>
