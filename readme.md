# Terrence Howard 1 * 1 = 2 explanation


## The problem start with square root of 2

The square root appear first in with pythagorean theorem:

![Alt text](Screenshot%20from%202024-05-20%2013-23-01.png)


```js
c * c = (a * a) + (a * a)

// if a = 1
c * c = (1 * 1) + (1 * 1)

// if 1 * 1 = 1
c * c === 1 + 1

c === Math.sqrt(2)
```

## What's the problem with `Math.sqrt(2)`

In the above equation, we calculate `1 * 1 === 1` which causes the result to be
`Math.sqrt(2)`.

But `Math.sqrt(2)` doesn't exist, see: [A Proof That The Square Root of Two Is Irrational](https://www.youtube.com/watch?v=LmpAntNjPj0).

## Propose solution: Use a numerical system that avoid `Math.sqrt(2)`

+ Taking `scale` into account

```ts
// We have

type Meter = {value: number}

const m = (i): Meter => ({value: i})

type MeterSquare = {value: number}

const m2 = (i): MeterSquare => ({value: i})
```

With above:
```js
(m 1) * 1 === (m 1) // 1 meter line multiply by 1 = still 1 meter line
```

refer a completely different thing from 

```js
(m 1) * (m 1) === (m2 1) // 1 meter line multiply by 1 meter line = a square with 1 meter width.
```

Terrence Howard propose that we should use something else for `(m 1) * (m 1) === ???` because `Math.sqrt(2)` doesn't make sense, and it appear a lot due to pythagorean theorem.


Assuming that we use a different numerical symbol for that refer to the same number but with different scale.

```
1, 2, 3, 4, 5, 6, 7, 8, 9, 0
===
one, two, three, four, five, six, seven, eight, nine, zero
```

Math operation on these 2 symbols stay the same, but they cannot cross each other. 
```js
1 + 1 = 2
one + one = two

// 1 is equivalent to `one`
// 2 is equivalent to `two`

1 + one !== 2 // (cannot cross each other system normally)
```

With this, we can assume

```js
(m 1) * (m 1) === (m2 one) 
// ^ allow crossing due to scale change from m => m2

=> c === Math.sqrt(two)
```

Using the same system, `Math.sqrt(two)` is the result, and we try to avoid that.

We can use this instead:

```js
(m 1) * (m 1) === (m2 two)
// ^ allow crossing due to scale change from m => m2

=> c === Math.sqrt(four)
```

`Math.sqrt(four) = two` terminate, as such we can use `(m 1) * (m 1) === (m2 two)`.

# Conclusion

Terrence Howard doesn't really propose that `1 * 1 = 2` but rather `(m 1) * (m 1)` should be equal to something else beside `(m2 1)`, such that we can avoid `Math.sqrt(2)`.

- `(m 1) * 1` should be still `(m 1)`.
- `(m 1) * (m 1)` should be `(m2 <something-else>)`.
- Assume that we can terminate `Math.sqrt(2)` to `1.41421356237...`
then we can propose a cross between the numerical system `(1, 2, ...)` and `(one, two, ...)` => `two = 1.41421356237`. (But these conversion make us lose information)

