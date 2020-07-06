# RXJS exercises

## Before your start
I suggest you to use https://codesandbox.io/ or other online playground. In codesandbox, you can choose rxjs playground. Stars shows, how difficult is execise. 

All operations, should be done inside pipe().

General setup:
```js
const obs$ = of('hello')
  .pipe(
    // here your operators
  )
  .subscribe(item => console.log(item));
```
Please remember to unsubscribe from streams. 

## 1 *
Create two observables$ with timer. 
```js
import { concat, interval } from "rxjs";
import { take } from "rxjs/operators";

const first$ = interval(1000).pipe(take(4));
const second$ = interval(200).pipe(take(5));

```
Now we want subscribe to those two observables, and return first obsFirst$ values, and when obsFirst$ is done, values from obsSecond$. 

## 2 *

Create observable from given array:

```js
['lorem', 'ipsum', 'dolor']
```
but first returned value should be "veni" and last - "vici"

expected result
```
veni 
lorem
ipsum
dolor
vici
``` 

## 3 *

Create observable from given array:

```js
['lorem', 'ipsum', 'dolor']
```
return values, but uppercase every first char.

expected result:
```
Lorem
Ipsum
Dolor
```

## 4 **

Create observable from given array:
```js
['b', 'g', 'a', 'd', 'e']
```
return values, but sorted

expected result:
```
a 
b
d
e
g 
```

## 5 

Create one http request. When is done, create second http request. 
You can mock http request like this:
```
const reqFirst$ = of('hello').pipe(delay(3000));
const reqSecond$ = of('world').pipe(delay(500));
```
Print also timestamp for every request.

## 6

This is the same like 5, but you don't need wait for first request. Just run two request and don't worry about order.

## 7
So you have observable stream of booleans like this 
```
[true, false, true, false]
```
Please make some action in your code, when at some point of time, value from observable is true. Make sure, that you takes only first value and that your stream will not receive values forever. You can imagine, that this stream is service value, that get give you some information and you must use this information for make proper action.

## 8 
Setup is the same like in 7, but you have two streams. For example, first is information that you are in readonly mode, and second, that you can edit or not.
```
canEdit$ = [true, false, false, true];
```
If first stream gives value false, and second stream gives you value of true, please log info - 'you can edit'.