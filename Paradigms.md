# Functional programming
https://probablydance.com/2016/02/27/functional-programming-is-not-popular-because-it-is-weird/
https://blog.devgenius.io/object-oriented-vs-functional-programming-with-typescript-6b2243bb8c4b

- pure functions (no side effect)
- immutable data (inputs/outputs) (Object.freeze)
- input parameter can be function
- return value can be function
- side effects taken in some command queue
- monad: defines two operators: one to wrap a value in the monad type, and another to compose together functions
- pro: multi thread safe

```
const appendEmoji = (fixed) => (dynamic) => fixed + dynamic;
const rain = appendEmoji('🌧️');
const sun = appendEmoji('️🌞');
console.log(rain(' today'))  // ️🌧️ ️️today
console.log(sun(' tomorrow'))  // ️🌞 tomorrow
```

# Reactive programming

## Change propagation algorithms
- pull
- push
- push-pull

## Concurrency glitch

## Cyclic dependencies

```
a=1;
b=2;
c=a+b;
b=10;
console.log({c});
```

```
$a=1;
$b=2;
$c=$a+$b;
$b=10;
console.log({$c});
```
