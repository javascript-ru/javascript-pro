# javascript-pro
Материалы программы по продвинутому JS



# Программа


- Babel, современные средства сборки
  - Мы будем использовать пока-не-стандартные, но устоявшиеся фичи языка, которые легко понимает babel (система сборки везде на frontend) и (обычно) node.js
  - repl

- modern classes, properties
  - Для создания объектов в современном JS используются классы
    - Простой пример
  - Символы, {}.toString.call(obj)  window[Symbol.toStringTag]
  - Методы и свойства
    - Properties есть поддержка в ноде за флагом  --harmony-public-fields и в babel давно, а #props, скорее всего,  есть поддержка в babel7
    - https://github.com/tc39/proposal-class-fields https://github.com/babel/proposals/issues/12
    - #props если в babel пока не работают, то только упоминаем
      - node --harmony-private-fields
    - Для приватных свойств пример с кофемашиной
      - … многим они уже знакомы

- Подвиды методов/свойств
  - Static
    - Методы класса, не объекта (в современном js работает их наследование, увидим позже)
  - property getters and setters
    - Пример, существуют давно

- Наследование
  - super в конструкторе потомка обязательно первым
    - По техническим причинам (классы-наследники не создают объект this, это делают только базовые классы)
  - Наследование статических свойств см диаграмку
    - http://javascript.info/class-inheritance#static-methods-and-inheritance

  - Обращение к статическому методу из обычного - задача, как сделать, с учетом наследования?
    - Было так http://next.plnkr.co/edit/IJnomy9Qf0fVSnUI
    - Но после наследования переопределенный метод не подхватывается
      - http://next.plnkr.co/edit/zDwREnoSEJuIjABs (this.constructor.method)
  - Имя класса для отладки или чтения каких-то файлов (json?)
    - this.constructor.name

- modules, import

  - Зачем нужны модули? (вопрос в зал)
    - Maintainability
    - Namespacing
    - Reusability

  - Old SChool: Module pattern, CommonJS, AMD and UMD
  - import / export, export default
    - Export class
    - Default export
    - Aliases (as syntax)
    - Export *


- async/await  (book)

  - Promise
    - Promise.finally
      - нужны ли базовые promise - сделаем опрос перед МК
  - async/await
  - Fetch   (+abortcontroller)

- iteration (https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of)

  - String, Array, Map, Set
  - arguments
  - DOM Collection
  - Symbol.iterator (https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols)
  - difference between for...of and for...in

- Async Iterators  (http://2ality.com/2016/10/asynchronous-iteration.html)

  - generators
  - Async iterators (https://jakearchibald.com/2017/async-iterators-and-generators/)

- Memory managements: WeakMap, WeakSet

- DOM methods
  - append/prepend/…

- service workers + Notification api