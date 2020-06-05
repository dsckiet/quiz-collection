# quiz-collection

###### 1. What's the output?

```javascript
const shape = {
  radius: 10,
  diameter() {
    return this.radius * 2;
  },
  perimeter: () => 2 * Math.PI * this.radius,
};

console.log(shape.diameter());
console.log(shape.perimeter());
```

- A: `20` and `62.83185307179586`
- B: `20` and `NaN`
- C: `20` and `63`
- D: `NaN` and `63`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

Note that the value of `diameter` is a regular function, whereas the value of `perimeter` is an arrow function.

With arrow functions, the `this` keyword refers to its current surrounding scope, unlike regular functions! This means that when we call `perimeter`, it doesn't refer to the shape object, but to its surrounding scope (window for example).

There is no value `radius` on that object, which returns `undefined`.

</p>
</details>

---

###### 2. What's the output?

```python
s = 'foo'
t = 'bar'
print('barf' in 2 * (s + t))
```

<details><summary><b>Answer</b></summary>
<p>

#### Answer: True

`s + t` gives `'foobar'`
`2 * (s + t)` gives `'foobarfoobar'`

and since, `'barf'` is present in `'foobarfoobar'`,
we can find that using the `in` operator
in python which finds `'barf'` in the given string.

</p>
</details>

---

###### 3. What's the output?

```javascript
const arr = [
  x => x * 1,
  x => x * 2,
  x => x * 3,
  x => x * 4
];
console.log(arr.reduce((agg, el) => agg + el(agg), 1));
```

- A: `96`
- B: `24`
- C: `120`
- D: `144`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: C

With `array.reduce`, the initial value of the aggregator (here, named `agg`) is given in the second argument. In this case, that's `1`. We can then iterate over our functions as follows:

###### 1 + 1 * 1 = 2
###### 2 + 2 * 2 = 6
###### 6 + 6 * 3 = 24
###### 24 + 24 * 4 = 120

Since array reduce is use to flatten or change the array to something we want

</p>
</details>

---

