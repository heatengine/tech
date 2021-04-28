# RxJS - Reactive Extensions for JavaScript

## What is RxJS
- RxJS (Reactive Extensions for JavaScript) is a library for reactive programming using observables that makes it easier to compose asynchronous or callback-based code. The library also provides utility functions for creating and working with observables.

## Concepts
- Observable: represents the idea of an invokable collection of future values or events.
- Observer: is a collection of callbacks that knows how to listen to values delivered by the Observable.
- Subscription: represents the execution of an Observable, is primarily useful for cancelling the execution.
- Operators: are pure functions that enable a functional programming style of dealing with collections with operations like map, filter, concat, reduce, etc.
- Subject: is the equivalent to an EventEmitter, and the only way of multicasting a value or event to multiple Observers.
- Schedulers: are centralized dispatchers to control concurrency, allowing us to coordinate when computation happens on e.g. setTimeout or requestAnimationFrame or others.

## Subjects
- A Subject is a special type of Observable which shares a single execution path among observers.

## Operators
- Combination
    - combineLatest ⭐
    - concat ⭐⭐
    - merge ⭐
    - startWith ⭐
    - withLatestFrom ⭐
- Creation
    - ajax ⭐
    - from ⭐⭐
    - of ⭐⭐
- Error Handling
    - catch / catchError ⭐⭐
- Filtering
    - debounceTime ⭐
    - filter ⭐⭐
    - take ⭐
- Multicasting
    - share ⭐
    - shareReplay ⭐
    - bufferTime ⭐
    - concatMap ⭐
    - map ⭐⭐
    - scan ⭐
    - switchMap ⭐
- Utility
    - tap / do ⭐
