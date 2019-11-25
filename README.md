# redux-vs-mobx
State Management with Redux &amp; MobX - курс

Разбор хранилищ состояний с нуля
* Redux
* MobX

###Redux
```
applyMiddleware: function()
bindActionCreators: function()  // helper function
combineReducers: function()     // helper function
compose: function()             // helper function
createStore(): function()
```

Разбор каждой функции

* [compose](https://jsbin.com/dibemu/edit?js,console)

```
compose(...functions)
```
Очень простая функция-композиция, которая по цепочке возвращает знаечение;
Объединяет функции справа налево.

Пример:
```
//создаем 3 функции
const makeLouder = (string) => string.toUpperCase();
const repeatThreeTimes = (string) => string.repeat(3);
const embolden = (string) => string.bold();

//создаем супер функцию справа налево
const makeLoaderAndBoldAndRepeatThreeTimes = 
      compose(embolden, repeatThreeTimes, makeLouder);

console.log(makeLoaderAndBoldAndRepeatThreeTimes('Dima'))

//результат
// "<b>DIMADIMADIMA</b>"
```

* [createStore](https://jsbin.com/dibemu/edit?js,console)
```
createStore(reducer, [preloadedState], [enhancer])
```
createStore принимает функцию reducer, initialSate, усилители.
```
const store = createStore(reducer);
```
reducer - это функция, которая принимает 2 параметра:
1. state
2. action
```
const reducer = (state, action) => {
  return state;
}
```
createStore возвращает объект с 4 свойствами:
1. dispatch
2. subscribe
3. getState
4. replaceReducer
