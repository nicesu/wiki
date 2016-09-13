## Promise [Back](./../es6.md)

Promise is used for asynchronous calculating, which is an object which means that it will be done in the future.

```js
var promiseObj = new Promise(function (resolve, reject)) {
    /** calling resolve when the job is done */
    resolve();
    
    /** calling reject when the job failed */
    reject();
};
```

A Promise object will only have **three states**:

- pending: the initial state
- fulfilled: successful state
- rejected: failed state

### Prototype functions

There are 2 prototype functions: `then()` and `catch()`, which both will return a Promise object (So we can use chain operations).

When a Promise object has changed its state, `Promise.prototype.then()` will be called according to the state:

```js
promiseObj.then(function () {
    /** fulfilled state */
}, function () {
    /** rejected state */
});
```

In comparison with `then()`, `catch()` will only handle rejected state:

```js
promiseObj.catch(function () {
    /** rejected state */
});
```

### Other functions

#### all()

`Promise.all(iterator)` should return a promise, which can **be only resolved until all promises in the iterator have been resolved**, same as rejected.

#### race()

`Promise.all(iterator)` should return a promise, which will **be resolved or rejected once one of the iterator has been resoved and rejected**.

#### reject()

`Promise.reject(reason)` will return a promise, which has been rejected with the reason.

#### resolve()

`Promise.resolve(reason)` will return a promise, which has been resolved with the reason.

### Compatibility

**Q / Bluebird / Async / co / then / Babel** has supported asynchronous programming.