# RXJS exercises

## Before your start
I suggest you to use https://codesandbox.io/ or other online playground. In codesandbox, you can choose rxjs playground.


## 1
Create two observables$ with timer. 
```js
import { concat, interval } from "rxjs";
import { take } from "rxjs/operators";

const first$ = interval(1000).pipe(take(4));
const second$ = interval(200).pipe(take(5));

```
Now we want subscribe to those two observables, and return first obsFirst$ values, and when obsFirst$ is done, values from obsSecond$. 

## 2


