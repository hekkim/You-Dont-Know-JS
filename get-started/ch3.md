# You Don't Know JS Yet: Get Started - 2nd Edition
# 챕터 3: JS의 뿌리 파헤치기
# Chapter 3: Digging to the Roots of JS

이미 챕터 1, 2를 읽고 충분한 시간을 들여 소화하고 흡수했다면 이제 JS를 조금 더 잘 *알수있는* 준비가 됐을 것입니다. 그렇지 않고 이전의 챕터들을 특히나 챕터 2를 건너 뛰셨다면, 저는 다시 돌아가 해당 챕터들을 공부하는데 시간을 투자하길 추천드립니다.

If you've read Chapters 1 and 2, and taken the time to digest and percolate, you're hopefully starting to *get* JS a little more. If you skipped/skimmed them (especially Chapter 2), I recommend going back to spend some more time with that material.

챕터 2에서 우린 고등 수준의 문법과 패턴 그리고 작동 방식들에 관해 알아봤다면, 이 챕터에서는 JS의 근간을 이루는 하위 단계의 특징들에 관해 주의깊게 살펴보고자 합니다.

In Chapter 2, we surveyed syntax, patterns, and behaviors at a high level. In this chapter, our attention shifts to some of the lower-level root characteristics of JS that underpin virtually every line of code we write.

이 챕터에서는 프로그래밍 언어에 관해 일반적으로 생각하는 것보다 조금 더 깊이 파고들어간단 사실을 명심해주시기 바랍니다. 제 목표는 JS가 어떻게 작동하는 그 핵심을 이해하는데 도움을 드리는 것입니다. 이 챕터는 JS를 탐험하는데 있어 불쑥 발생하곤 하는 "왜?"라는 질문들에 답하는 걸로 시작해야만 할 것입니다. 하지만 이 언어에 대한 완벽하고 철저한 설명이 되진 못할 것입니다. 대신 이 시리즈의 나머지 책들이 이에 관해 다룰 예정입니다! 우리의 목표는 여전히 단순하게 *시작하기*이며 조금 더 JS 어떻게 작동하는지 알아가며 조금 더 친숙해지는 것입니다.

Be aware: this chapter digs much deeper than you're likely used to thinking about a programming language. My goal is to help you appreciate the core of how JS works, what makes it tick. This chapter should begin to answer some of the "Why?" questions that may be cropping up as you explore JS. However, this material is still not an exhaustive exposition of the language; that's what the rest of the book series is for! Our goal here is still just to *get started*, and become more comfortable with, the *feel* of JS, how it ebbs and flows.

이 챕터를 너무 서둘러서 읽어 숲속에서 길을 잃지 마십시오. 이미 수차례 얘기했지만 **충분히 많은 시간을 들여주세요**. 그렇게 많은 시간을 들여 이 챕터를 끝내더라도 여전히 여러분에게 몇몇 의문점들이 남아 있을 것입니다. 괜찮습니다. 여전히 더 탐험해나갈 시리즈가 남아있습니다!

Don't run so quickly through this material that you get lost in the weeds. As I've said a dozen times already, **take your time**. Even still, you'll probably finish this chapter with remaining questions. That's OK, because there's a whole book series ahead of you to keep exploring!

## 반복문

## Iteration

프로그램은 본질적으로 데이터를 처리하기 위해 만들어지기 때문에, 데이터를 단계별로 처리하는 방법은 프로그램의 가독성에 큰 영향을 미칩니다.

Since programs are essentially built to process data (and make decisions on that data), the patterns used to step through the data have a big impact on the program's readability.

반복자<sup>Iterator</sup>를 사용하는 방법은 수십년이 된 패턴이고, 한 덩어리의 데이터를 하나씩 처리하는데 사용되는 "표준화된" 접근법입니다. 이러한 접근법은 한 무리의 데이터의 전체를 한 번에 처리하는 것보다 첫 일부에서부터 시작해 그 끝에 이르기까지 데이터 전체를 순환하며 처리하는데 아주 흔히 사용하며 유용한 방법입니다.

The iterator pattern has been around for decades, and suggests a "standardized" approach to consuming data from a source one *chunk* at a time. The idea is that it's more common and helpful to iterate the data source—to progressively handle the collection of data by processing the first part, then the next, and so on, rather than handling the entire set all at once.

여러개의 행으로 구성된 자료 구조를 관계형 데이터베이스에서 `SELECT` 쿼리를 통해 얻었다고 한 번 가정해 보겠습니다.

일반적으로 결과물을 행으로 구성해서 주는 관계형 데이터베이스의 `SELECT` 쿼리로 대표되는 자료구조가 있다고 가정해 보겠습니다. 이 쿼리를 통해 소수의 행을 가져온다면 여러분은 이 결과값 전체를 한꺼번에 처리하기도하고, 각각의 열을 지역 변수로 할당하기도 하고, 데이터에 적절한 연산을 수행하도록 만들 수도 있습니다.

Imagine a data structure that represents a relational database `SELECT` query, which typically organizes the results as rows. If this query had only one or a couple of rows, you could handle the entire result set at once, and assign each row to a local variable, and perform whatever operations on that data that were appropriate.

하지만 쿼리가 100개 혹은 1000개 혹은 그 이상의 행을 가지고 있다면 이 데이터를 처리하기 위해서는 반복적인 연산 과정을 필요로 할 것입니다.

But if the query has 100 or 1,000 (or more!) rows, you'll need iterative processing to deal with this data (typically, a loop).

반복자 방식에서는 "반복자"라고 불리는 자료 구조를 정의하며, 이 반복자는 쿼리의 결과 행과 같은 원본 데이터에 대한 참조값을 가집니다. 또한 이 반복자에는 `next()`와 같은 메서드를 가지고 있습니다. 메서드 `next()`를 호출하면 데이터의 그 다음 조각(데이터베이스 쿼리에서 얻은 "기록<sup>Record</sup>"와 "행")을 반환받게 됩니다.

The iterator pattern defines a data structure called an "iterator" that has a reference to an underlying data source (like the query result rows), which exposes a method like `next()`. Calling `next()` returns the next piece of data (i.e., a "record" or "row" from a database query).

반복문에 사용될 데이터에 얼마나 많은 조각들이 있는지 항상 알지는 못하므로 이러한 방법은 일반적으로 특정 값이나 전체 집합을 반복하고 그 *끝을 지나면* 예외 처리를 통해 완료됩니다.

You don't always know how many pieces of data that you will need to iterate through, so the pattern typically indicates completion by some special value or exception once you iterate through the entire set and *go past the end*.

반복자 방법에서 중요한 점은 데이터를 반복 처리하는 *표준* 방식을 고수하는 것입니다. 이렇게 하면 모든 데이터 구조가 각기 다른 방식으로 처리될 때와는 다르게 코드를 더 깨끗하고 이해하기 쉽게 만들어 줄 것입니다.

The importance of the iterator pattern is in adhering to a *standard* way of processing data iteratively, which creates cleaner and easier to understand code, as opposed to having every data structure/source define its own custom way of handling its data.

여러 JS 커뮤니티에서 수년에 걸친 노력 끝에 반복문에 관한 상호간 합의를 만들어 내었고, ES6 에서는 반복자 패턴을 위한 특별한 프로토콜<sup>Protocol</sup>을 표준화<sup>Standardize</sup> 하였습니다. 프로토콜의 `next()`란 메서드를 정의하는데 이 메서드는 *반복자 결과*라고 불리는 `value`와 `done` 프로퍼티를 가지고 있는 객체를 반환해줍니다. 여기서 `done`은 불리언 값으로 데이터 원본을 순환하는 것을 완료하기 전까지는 `false`인 상태로 남아있습니다.

After many years of various JS community efforts around mutually agreed-upon iteration techniques, ES6 standardized a specific protocol for the iterator pattern directly in the language. The protocol defines a `next()` method whose return is an object called an *iterator result*; the object has `value` and `done` properties, where `done` is a boolean that is `false` until the iteration over the underlying data source is complete.

### 반복자 소비하기

### Consuming Iterators

ES6 반복문 프로토콜을 통해 데이터를 한 번에 하나씩 사용할 수 있게 만들어주며 매번 `next()`를 호출한 이후 `done`이 `true`로 바뀌게 반복문을 멈추게 합니다. 하지만 이러한 방법은 다소 수동적이기에, ES6는 반복문 처리를 위해 표준화된 몇몇 문법과 API를 가지고 있습니다.

With the ES6 iteration protocol in place, it's workable to consume a data source one value at a time, checking after each `next()` call for `done` to be `true` to stop the iteration. But this approach is rather manual, so ES6 also included several mechanisms (syntax and APIs) for standardized consumption of these iterators.

한 가지 예로 `for..of` 반복문이 있습니다.

One such mechanism is the `for..of` loop:

```js
// 반복자에게 줄 원본 데이터
// given an iterator of some data source:
var it = /* .. */;

// 한 번에 하나씩 순환하게 됩니다
// loop over its results one at a time
for (let val of it) {
    console.log(`Iterator value: ${ val }`);
}
// Iterator value: ..
// Iterator value: ..
// ..
```

| 노트: |
| :--- |
| 여기서는 수동 반복문을 생략하겠지만 `for..of` 반복문에 비해 가동성이 좋지 않습니다! |

| NOTE: |
| :--- |
| We'll omit the manual loop equivalent here, but it's definitely less readable than the `for..of` loop! |

반복자를 소비하는 또 다른 방법은 `...` 연산자입니다. 이 연산자는 *확산<sup>Spread</sup>* 그리고 *나머지<sup>Rest</sup>* (또는 제가 선호하는 명칭인 *수집<sup>Gather</sup>*)과 같이 대칭인 두 형태를 가지고 있습니다. *확산*은 반복자-소비자와 같은 형태입니다.

Another mechanism that's often used for consuming iterators is the `...` operator. This operator actually has two symmetrical forms: *spread* and *rest* (or *gather*, as I prefer). The *spread* form is an iterator-consumer.

반복자를 *확산*시키는 것은 퍼뜨려야 할 *무언가* 가지고 있어야만 합니다. 여기에서 JS에는 두 가지 선택지가 있는데, 하나는 배열이고 또 다른 하나는 함수 호출에 있어 인수값이 배열인 경우입니다.

To *spread* an iterator, you have to have *something* to spread it into. There are two possibilities in JS: an array or an argument list for a function call.

배열을 확산시키는 예시입니다.

An array spread:

```js
// 반복자를 배열에 확산시키고
// 각각의 순환되는 값은 배열에서
// 요소로써 자리를 잡습니다
// spread an iterator into an array,
// with each iterated value occupying
// an array element position.
var vals = [ ...it ];
```

함수 호출에서 확산시키는 예시입니다.

A function call spread:

```js
// 반복자를 함수에서 확산시키고 호출합니다
// 각각의 순환되는 값은 하나의
// 인수로써 자리를 잡습니다
// spread an iterator into a function,
// call with each iterated value
// occupying an argument position.
doSomethingUseful( ...it );
```

두 경우 모두 반복자-소비 프로토콜을 따르는 반복자-확산 형식입니다. 여기서 반복자-소비 프로토콜은 `for..of`와 동일하게 모든 사용 가능한 값을 반복자로부터 가져오고 그것을 배열 혹은 인수 리스트인 수신자에 넣게됩니다.

두 경우 모두 반복문은 `...` 형식이고 반복자-소비 프로토콜(`for..of`와 마찬가지로)을 따라 모든 사용 가능한 값을 반복자로부터 가져오게 되고 이 값들을 수신자(배열 혹은 인자 리스트)에게 배정합니다(확산으로 알려진).

In both cases, the iterator-spread form of `...` follows the iterator-consumption protocol (the same as the `for..of` loop) to retrieve all available values from an iterator and place (aka, spread) them into the receiving context (array, argument list).

### 이터러블<sup>Iterable</sup>

### Iterables

반복자-소비 프로토콜은 *이터러블<sup>Iterable</sup>* 값들을 소비하도록 기술적 정의되어 있습니다. 이터러블은 반복될 수 있는 값을 얘기합니다.

The iterator-consumption protocol is technically defined for consuming *iterables*; an iterable is a value that can be iterated over.

반복자-소비 프로토콜은 이터러블로부터 반복자 인스턴스를 생성하고, *단지 반복자 인스턴스*를 소모함으로써 끝이 납니다. 이는 곧 하나의 이터러블이 한 번 이상 소비될 수 있고, 한 번 소모될 때마다 새로운 반복자 인스턴스를 생성하고 사용해야 된다는 얘기입니다.

The protocol automatically creates an iterator instance from an iterable, and consumes *just that iterator instance* to its completion. This means a single iterable could be consumed more than once; each time, a new iterator instance would be created and used.

그렇다면 이렇게 이터러블은 어디에 있을까요?

So where do we find iterables?

ES6는 JS에 기본 데이터 구조와 집합<sup>Collection</sup> 타입을 이터러블이라고 정의하고 있습니다. 여기에는 문자열, 배열, 맵<sup>Map</sup>, 세트<sup>Set</sup> 등이 있습니다.

ES6 defined the basic data structure/collection types in JS as iterables. This includes strings, arrays, maps, sets, and others.

Consider:

```js
// 배열은 이터러블입니다
// an array is an iterable
var arr = [ 10, 20, 30 ];

for (let val of arr) {
    console.log(`Array value: ${ val }`);
}
// Array value: 10
// Array value: 20
// Array value: 30
```

배열은 이터러블이므로 확산 연산자인 `...`를 통해 배열을 얕은 복사<sup>Shallow-copy</sup>를 할 수 있습니다.

Since arrays are iterables, we can shallow-copy an array using iterator consumption via the `...` spread operator:

```js
var arrCopy = [ ...arr ];
```

또한 문자열 역시도 한번에 문자들을 반복하여 사용할 수 있습니다.

We can also iterate the characters in a string one at a time:

```js
var greeting = "Hello world!";
var chars = [ ...greeting ];

chars;
// [ "H", "e", "l", "l", "o", " ",
//   "w", "o", "r", "l", "d", "!" ]
```

`맵` 자료 구조는 키 기반의 객체를 사용합니다. 이 키는 하나의 값을 객체를 연결하는데 사용됩니다. 맵은 반복문이 단순히 맵에 있는 값이 아닌 맵의 *엔트리<sup>Entry</sup>*를 반복한다는 점에서 이전에 보았던 보이는 것과는 다소 다른 반복문을 가지게 됩니다. *엔트리*는 키와 값을 포함하고 있는 2-원소 배열인 튜플<sup>Tuple</sup>입니다.

A `Map` data structure uses objects as keys, associating a value (of any type) with that object. Maps have a different default iteration than seen here, in that the iteration is not just over the map's values but instead its *entries*. An *entry* is a tuple (2-element array) including both a key and a value.

Consider:

```js
// 두 개의 DOM 요소인 `btn1`과 `btn2`가 있습니다
// given two DOM elements, `btn1` and `btn2`

var buttonNames = new Map();
buttonNames.set(btn1,"Button 1");
buttonNames.set(btn2,"Button 2");

for (let [btn,btnName] of buttonNames) {
    btn.addEventListener("click",function onClick(){
        console.log(`Clicked ${ btnName }`);
    });
}
```

기본 맵 순회하며 `for..of` 사용할 때, "배열 분해<sup>Array destructing</sup>"이라고 불리는 문법을 사용하는데 튜플을 각각 키와 값의 짝인 `btn1`/`"Button 1"` 그리고 `btn2`/`"Button2"`으로 분해하고 이들을 `[bth,btnName]`와 같이 사용하게 됩니다.

In the `for..of` loop over the default map iteration, we use the `[btn,btnName]` syntax (called "array destructuring") to break down each consumed tuple into the respective key/value pairs (`btn1` / `"Button 1"` and `btn2` / `"Button 2"`).

JS에 내장된 이터러블 각각은 매우 직관적인 기본 반복문을 가지고 있습니다. 필요에 따라 특별한 반복문을 선택할 수도 있습니다. 예를들어, 위의 `buttonNames` 맵에서 오직 값만을 사용하길 원한다면 `values()`를 호출하여 값만 가지고 있는 반복자를 가져올 수도 있습니다.

Each of the built-in iterables in JS expose a default iteration, one which likely matches your intuition. But you can also choose a more specific iteration if necessary. For example, if we want to consume only the values of the above `buttonNames` map, we can call `values()` to get a values-only iterator:

```js
for (let btnName of buttonNames.values()) {
    console.log(btnName);
}
// Button 1
// Button 2
```

또다른 예시로 배열 반복문에서 만약 값과 인덱스를 사용하길 원한다면, `entries()` 메서드를 통해 엔트리 반복자를 만들어 사용할 수도 있습니다.

Or if we want the index *and* value in an array iteration, we can make an entries iterator with the `entries()` method:

```js
var arr = [ 10, 20, 30 ];

for (let [idx,val] of arr.entries()) {
    console.log(`[${ idx }]: ${ val }`);
}
// [0]: 10
// [1]: 20
// [2]: 30
```

대다수의 경우 JS에 내장된 이터러블은 세가지 형태의 반복자를 사용할 수 있습니다. 키만 사용할 경우 (`keys()`), 값만 사용할 경우 (`values()`), 그리고 엔트리를 사용할 경우 (`entries()`).

For the most part, all built-in iterables in JS have three iterator forms available: keys-only (`keys()`), values-only (`values()`), and entries (`entries()`).

단순히 내장된 이터러블을 넘어서서 반복문 프로토콜을 독자적인 자료 구조가 반복문 프로 만들수도 있습니다. 이는 곧 새로운 자료구조가 `for..of` 혹은 `...` 연산자를 통해 데이터를 소비할 수 있는 기능을 사용할 수도 있다는 뜻입니다. 이러한 프로토콜에서 "표준화<sup>Standardizing</sup>"란 전반적으로 코드를 더 빠르게 인식할 수 있고 가독성을 높이는 것을 의미합니다.

Beyond just using built-in iterables, you can also ensure your own data structures adhere to the iteration protocol; doing so means you opt into the ability to consume your data with `for..of` loops and the `...` operator. "Standardizing" on this protocol means code that is overall more readily recognizable and readable.

| 노트: |
| :--- |
| 아마 이 토론에서 미묘한 변화를 발견하셨을 수도 있습니다. **반복자**를 소비하는 것에 관해 얘길하는 것으로 시작했지만 이내 곧 **이터러블**을 통해 반복하는 것으로 그 주제가 바뀌었습니다. 반복-소비 프로토콜이 *이터러블*을 필요할거라고 생각되지만, *반복자*를 제공해야되는 이유는 단순히 반복자가 곧 이터러블 그 자체이기 때문입니다! 반복자 인스턴스를 이미 존재하는 반복자로부터 만들면, 그 반복자 자체가 반환됩니다. |

| NOTE: |
| :--- |
| You may have noticed a nuanced shift that occurred in this discussion. We started by talking about consuming **iterators**, but then switched to talking about iterating over **iterables**. The iteration-consumption protocol expects an *iterable*, but the reason we can provide a direct *iterator* is that an iterator is just an iterable of itself! When creating an iterator instance from an existing iterator, the iterator itself is returned. |

## 클로져<sup>Closure</sup>

## Closure

아마도 깨닫지 못 했겠지만, 대부분의 모든 JS 개발자들은 클로져를 사용하고 있습니다. 실은, 클로져는 대부분의 언어에서 가장 널리 사용되고 있는 기능 중 하나입니다. 심지어는 클로져가 얼마나 핵심적인지 아는 것이 값이나 반복문에 관해 이해하는 것만큼 중요할 수도 있습니다.

Perhaps without realizing it, almost every JS developer has made use of closure. In fact, closure is one of the most pervasive programming functionalities across a majority of languages. It might even be as important to understand as variables or loops; that's how fundamental it is.

하지만 클로져는 마법인 것 마냥 숨겨져 있는 것처럼 느껴지실 것입니다. 그리고 클로져는 매우 추상적이거나 매우 비공식적인 용어로 종종 얘기되곤 하는데, 이런 말은 클로져가 무엇인지 정확하게 파악하는데에 전혀 도움이 되지 않습니다.

Yet it feels kind of hidden, almost magical. And it's often talked about in either very abstract or very informal terms, which does little to help us nail down exactly what it is.

때때로는 클로져의 유무로 인해 때때로는 버그 혹은 성능 문제가 발생하므로, 우선 프로그램에서 클로져가 어떻게 사용되는지 파악할 필요가 있습니다.

We need to be able to recognize where closure is used in programs, as the presence or lack of closure is sometimes the cause of bugs (or even the cause of performance issues).

그럼 실용적이며 구제적인 방법으로 클로져를 정의해보도록 하겠습니다.

So let's define closure in a pragmatic and concrete way:

> 클로져는 어떠한 함수가 전혀 다른 스코프에서 불리더라도 그 함수의 바깥 스코프에 있는 변수를 기억하고 지속적으로 접근하는 것을 말합니다.

> Closure is when a function remembers and continues to access variables from outside its scope, even when the function is executed in a different scope.

여기서 두 가지 명확한 특징을 찾아낼 수 있습니다. 우선, 클로져는 함수의 본질 중 일부라는 것입니다. 객체는 클로져를 가지고 있지 않지만, 함수는 가지고 있습니다. 두 번째로는 클로져를 관찰하기 위해서는 함수가 정의된 위치가 아닌 다른 스코프에서 함수를 실행해봐야 한다는 점입니다.

We see two definitional characteristics here. First, closure is part of the nature of a function. Objects don't get closures, functions do. Second, to observe a closure, you must execute a function in a different scope than where that function was originally defined.

Consider:

```js
function greeting(msg) {
    return function who(name) {
        console.log(`${ msg }, ${ name }!`);
    };
}

var hello = greeting("Hello");
var howdy = greeting("Howdy");

hello("Kyle");
// Hello, Kyle!

hello("Sarah");
// Hello, Sarah!

howdy("Grant");
// Howdy, Grant!
```

우선 `greeting(..)` 외부 함수는 실행되면 내부 함수 `who(..)`의 인스턴스를 생성하게 됩니다. `who(..)` 함수는 `msg`란 변수를 포함하고 있는데 이는 바깥 스코프 `greeting(..)`에 있는 매개 변수입니다. 내부 함수 `who(..)`가 반환되면 이 함수의 참조값은 외부 스코프에 있는 `hello` 변수에 할당되게 됩니다. 그 후 `greeting(..)`을 다시 한 번 부르면, 새로운 `msg` 변수를 포함한 클로져를 갖고있는 새로운 내부 함수 인스턴스가 만들어집니다. 그리고 새로운 내부 함수 인스턴스는 반환되어 변수 `howdy`에 할당되게 됩니다.

First, the `greeting(..)` outer function is executed, creating an instance of the inner function `who(..)`; that function closes over the variable `msg`, which is the parameter from the outer scope of `greeting(..)`. When that inner function is returned, its reference is assigned to the `hello` variable in the outer scope. Then we call `greeting(..)` a second time, creating a new inner function instance, with a new closure over a new `msg`, and return that reference to be assigned to `howdy`.

`greeting(..)` 함수의 작업이 모두 완료되면 일반적으로 우리는 여기에 사용되었던 모든 변수가 가비지 콜렉터<sup>Garbage collector</sup>에 의해 메모리에서 제거될 것이라고 생각합니다. 그러므로 `greeting(..)` 함수가 실행된 이후 `msg`가 사라질 거라고 예상되지만 실제로는 그렇지 않습니다. 이는 클로져 덕분입니다. 내부 함수 인스턴스는 여전히 `hello`와 `howdy`에 각각 할당된 채 살아있는 상태이기 때문에, 이들의 클로져는 여전히 `msg` 변수를 보존하고 있습니다.

When the `greeting(..)` function finishes running, normally we would expect all of its variables to be garbage collected (removed from memory). We'd expect each `msg` to go away, but they don't. The reason is closure. Since the inner function instances are still alive (assigned to `hello` and `howdy`, respectively), their closures are still preserving the `msg` variables.

이러한 클로져들은 `msg` 변수 값의 스냅샷<sup>Snapshot</sup>이 아니라 변수 자체를 직접적으로 연결하고 보존하고 있습니다. 이 말인즉슨 클로져는 실제로는 이 변수들의 변화를 관찰하고 값을 변경시킬수도 있다는 의미입니다.

These closures are not a snapshot of the `msg` variable's value; they are a direct link and preservation of the variable itself. That means closure can actually observe (or make!) updates to these variables over time.

```js
function counter(step = 1) {
    var count = 0;
    return function increaseCount(){
        count = count + step;
        return count;
    };
}

var incBy1 = counter(1);
var incBy3 = counter(3);

incBy1();       // 1
incBy1();       // 2

incBy3();       // 3
incBy3();       // 6
incBy3();       // 9
```

내부 함수 `increateCount()` 인스턴스는 외부 함수인 `counter(..)` 스코프로부터 `count`와 `step` 변수를 포함하고 있습니다. `step`은 기존과 똑같지만, `count`는 내부 함수가 호출될 때마다 변동되는 값입니다. 클로져는 단순한 값의 스냅샷이 아닌 변수이기 때문에, 이러한 변경사항은 변수에 반영됩니다.

Each instance of the inner `increaseCount()` function is closed over both the `count` and `step` variables from its outer `counter(..)` function's scope. `step` remains the same over time, but `count` is updated on each invocation of that inner function. Since closure is over the variables and not just snapshots of the values, these updates are preserved.

클로져의 콜백<sup>Callback</sup>과 같은 비동기<sup>Asynchronous</sup> 코드를 작업할 때 가장 흔히 볼 수 있습니다.

Closure is most common when working with asynchronous code, such as with callbacks. Consider:

```js
function getSomeData(url) {
    ajax(url,function onResponse(resp){
        console.log(
            `Response (from ${ url }): ${ resp }`
        );
    });
}

getSomeData("https://some.url/wherever");
// Response (from https://some.url/wherever): ...
```

내부 함수 `onResponse(..)`는 `url`을 포함하고 있고, 이는 곧 Ajax 호출이 콜백 함수 `onResponse(..)`를 반환하고 실행할 때까지 변수 `url`를 보존하고 기억하게 됩니다. `getSomeData(..)`가 바로 끝날지라도 `url` 매개 변수는 클로져 내부에서 필요할 때까지 계속해서 살아있게 됩니다.

The inner function `onResponse(..)` is closed over `url`, and thus preserves and remembers it until the Ajax call returns and executes `onResponse(..)`. Even though `getSomeData(..)` finishes right away, the `url` parameter variable is kept alive in the closure for as long as needed.

외부 스코프가 일반적으로 함수이긴 하지만 꼭 그럴 필요는 없습니다. 하지만 적어도 외부 스코프에 있는 하나의 변수에 접근하는 내부 함수가 있어야 합니다.

It's not necessary that the outer scope be a function—it usually is, but not always—just that there be at least one variable in an outer scope accessed from an inner function:

```js
for (let [idx,btn] of buttons.entries()) {
    btn.addEventListener("click",function onClick(){
       console.log(`Clicked on button (${ idx })!`);
    });
}
```

이 반복문에서 `let` 선언문을 사용하기 때문에, 각 반복문은 `idx`, `btn`, `onClick(..)`라는 각각의 새로운 블록 스코프<sup>Block-scoped</sup> 혹은 지역 스코프<sup>Local-scoped</sup>라고 하는 변수와 함수를 가지게 됩니다. 내부 함수는 `idx`를 포함하게 되는데 이 변수는 `btn`에 클릭 이벤트 핸들러<sup>Handler</sup>로 설정되어 있는 한 계속해서 보존되게 됩니다. 각각의 핸들러는 `idx` 변수를 기억하고 있으므로 버튼을 클릭할 때마다 자신과 연관된 인덱스 값을 출력하게 됩니다.

Because this loop is using `let` declarations, each iteration gets new block-scoped (aka, local) `idx` and `btn` variables;  the loop also creates a new inner `onClick(..)` function each time. That inner function closes over `idx`, preserving it for as long as the click handler is set on the `btn`. So when each button is clicked, its handler can print its associated index value, because the handler remembers its respective `idx` variable.

클로져는 값(`1`, `3`과 같은)이 아닌 `idx` 변수 그 자체임을 명심해두세요.

Remember: this closure is not over the value (like `1` or `3`), but over the variable `idx` itself.

클로져는 어떤 언어이든간에 가장 널리 퍼져있으며 중요한 패턴중 하나입니다. 물론 JS 역시 그러한 언어 중 하나인 것은 분명한 사실입니다. 어느식으로든 클로져를 활용하지 않고 유용한 무언가를 해내는 것은 상상하기 어려운 일입니다.

Closure is one of the most prevalent and important programming patterns in any language. But that's especially true of JS; it's hard to imagine doing anything useful without leveraging closure in one way or another.

여전히 클로져에 관해 불분명하고 불확실하다고 느껴진다면 두 번째 책 *스코프와 클로져<sup>Scope & Closure</sup>*의 주제에 집중해 주시기 바랍니다.

If you're still feeling unclear or shaky about closure, the majority of Book 2, *Scope & Closures* is focused on the topic.

## `this` 키워드

## `this` Keyword

`this` 키워드는 JS에서 강력한 메커니즘 중 하나인 동시에 가장 오해받는 기능 중 하나이기도 합니다. 흔한 오해 중 하나는 함수에서 쓰이는 `this`가 함수 자신을 가르킨다는 것입니다. 다른 언어에서 `this`가 작동하는 방법으로 인해 생기는 또 다른 오해는 `this`가 메서드가 소속되어 있는 인스턴스를 가르키고 있다는 것입니다. 둘 다 틀린 이야기입니다.

One of JS's most powerful mechanisms is also one of its most misunderstood: the `this` keyword. One common misconception is that a function's `this` refers to the function itself. Because of how `this` works in other languages, another misconception is that `this` points the instance that a method belongs to. Both are incorrect.

이전에 이야기했듯이 함수가 정의될 때 함수는 클로져를 통해 이 함수를 둘러싼 스코프에 첨부되게 됩니다. 스코프는 규칙의 집합이며 이 규칙들을 통해 어떻게 변수를 참조할지 결정하게 됩니다.

As discussed previously, when a function is defined, it is *attached* to its enclosing scope via closure. Scope is the set of rules that controls how references to variables are resolved.

하지만 함수 역시 그들의 스코프 외에도 그들이 접근할 수 있는 것들에 영향을 미치는 또다른 특성이 있습니다. 이 특성은 *실행 컨텍스트<sup>Execution context</sup>*라고 가장 잘 설명될 수 있고, 이는 `this`라는 키워드를 통해 함수에 노출되게 됩니다.

But functions also have another characteristic besides their scope that influences what they can access. This characteristic is best described as an *execution context*, and it's exposed to the function via its `this` keyword.

스코프는 정적입니다. 스코프는 함수를 정의하는 시점과 위치에 따라 고정된 개수의 변수만을 포함하고 있으며 이 변수만을 이용할 수 밖에 없습니다. 하지만 함수의 실행 *컨텍스트*는 동적입니다. 실행 *컨텍스트*는 함수가 정의된 위치나 함수를 호출하는 위치가 아닌 **함수를 호출하는 방법**에 따라 전혀 달라집니다.

Scope is static and contains a fixed set of variables available at the moment and location you define a function, but a function's execution *context* is dynamic, entirely dependent on **how it is called** (regardless of where it is defined or even called from).

`this`는 함수의 정의에 따라 고정된 특성이 아닌 함수가 매번 불릴때마다 결정되는 유동적인 특징입니다.

`this` is not a fixed characteristic of a function based on the function's definition, but rather a dynamic characteristic that's determined each time the function is called.

*실행 컨텍스트*는 함수가 실행되는동안 존재하며 내부 프로퍼티를 사용할 수 있는 객체라고 생각할 수 있습니다.

*실행 컨텍스트*를 스코프와 비교하면 *스코프 객체*는 JS 엔진 내부에 숨겨져 있단 점만 제외하고는 똑같다고 여길 수도 있습니다. 스코프와 비교하면 실행 컨텍스트를 하나의 *객체*라고 생각할 수도 있습니다. 다만 이 *스코프 객체<sup>Scope object</sup>*는 JS 엔진 내부에 숨겨져 있으며, 하나의 함수에 관해 늘 동일하며, 이 객체의 *프로퍼티*는 함수에서 사용할 수 있는 변수 식별자 모양을 하고 있다는 점만 제외한다면 말입니다.

One way to think about the *execution context* is that it's a tangible object whose properties are made available to a function while it executes. Compare that to scope, which can also be thought of as an *object*; except, the *scope object* is hidden inside the JS engine, it's always the same for that function, and its *properties* take the form of identifier variables available inside the function.

```js
function classroom(teacher) {
    return function study() {
        console.log(
            `${ teacher } says to study ${ this.topic }`
        );
    };
}
var assignment = classroom("Kyle");
```

외부 함수 `classroom(..)`은 `this` 키워드에 그 어떠한 참조값도 가지고 있지 않기에 이전에 봐왔던 다른 함수들과 비슷합니다. 하지만 내부 함수 `study()`는 `this`를 참조하고 있고, 이는 곧 `study()`가 `this`를 인식하는<sup>`this`-aware</sup> 함수란 얘기입니다. 즉, 이 함수는 *실행 컨텍스트*에 의존적이라고 얘기할 수 있습니다.

The outer `classroom(..)` function makes no reference to a `this` keyword, so it's just like any other function we've seen so far. But the inner `study()` function does reference `this`, which makes it a `this`-aware function. In other words, it's a function that is dependent on its *execution context*.

| 노트: |
| :--- |
| 물론 `study()` 함수는 외부 스코프로부터 가져온 `teacher` 변수를 포함하고 있습니다. |

| NOTE: |
| :--- |
| `study()` is also closed over the `teacher` variable from its outer scope. |

`classroom("Kyle")`를 호출하면 내부 함수 `study()`가 반환되어 `assignment`라는 변수에 할당되게 됩니다. 그렇다면 `assignment()` (`study()`라고도 알려진) 함수는 어떻게 호출될 수 있을까요?

The inner `study()` function returned by `classroom("Kyle")` is assigned to a variable called `assignment`. So how can `assignment()` (aka `study()`) be called?

```js
assignment();
// Kyle says to study undefined  -- Oops :(
```

위 예제에서는 *실행 컨텍스트*를 제공하지 않고 `assignment()`를 평범하게 일반 함수처럼 호출해 보았습니다.

In this snippet, we call `assignment()` as a plain, normal function, without providing it any *execution context*.

이 프로그램은 엄격 모드(챕터 1 "정확하게 말하자면"을 참고)가 아니기에 컨텍스트를 인식하는<sup>Context-aware</sup> 함수를 **명시된 컨텍스트 없이** 호출할 경우 글로벌 객체(브라우저의 경우 `window`)를 컨텍스트의 기본값으로 갖게 됩니다. `topic` 이라는 이름을 가진 글로벌 변수가 없고 또한 글로벌 객체에 그런 프로퍼티는 없기 때문에 `this.topic`은 `undefined`로 귀결되게 되어 있습니다.

Since this program is not in strict mode (see Chapter 1, "Strictly Speaking"), context-aware functions that are called **without any context specified** default the context to the global object (`window` in the browser). As there is no global variable named `topic` (and thus no such property on the global object), `this.topic` resolves to `undefined`.

아래 예제를 살펴보도록 하겠습니다.

Now consider:

```js
var homework = {
    topic: "JS",
    assignment: assignment
};

homework.assignment();
// Kyle says to study JS
```

위 예제에서는 `assignment` 함수 참조값을 복사하여 `homework` 객체의 프로퍼티에 넣어둔 뒤 `homework.assignment()`를 호출합니다. 그로인해 `homework.assignment()` 호출에서 `this`는 `homework` 객체가 됩니다. 따라서, `this.topic`은 `"JS"`가 됩니다.

A copy of the `assignment` function reference is set as a property on the `homework` object, and then it's called as `homework.assignment()`. That means the `this` for that function call will be the `homework` object. Hence, `this.topic` resolves to `"JS"`.

마지막으로 `this`에 관한 하나의 예제를 더 보겠습니다.

Lastly:

```js
var otherHomework = {
    topic: "Math"
};

assignment.call(otherHomework);
// Kyle says to study Math
```

함수를 호출하는 세 번째 방법은 `call(..)` 메서드를 통해서 하는 방법입니다. 이 메서드는 하나의 객체를 가져가 `this`가 이 객체를 참조한 채로 호출되게 만들어줍니다(위 예제에서는 `otherHomework`입니다). 그래서 위 예제의 `this.topic`는 `"Math"`가 됩니다.

A third way to invoke a function is with the `call(..)` method, which takes an object (`otherHomework` here) to use for setting the `this` reference for the function call. The property reference `this.topic` resolves to `"Math"`.

동일한 컨텍스트를 인식하는 함수는 세 가지 다른 방식으로 호출해 보았는데, `this` 객체가 무엇을 참조하냐에 따라 각기 다른 결과를 만들었습니다.

The same context-aware function invoked three different ways, gives different answers each time for what object `this` will reference.

`this`를 인식하는 함수, 즉 유동적인 컨텍스트는 하나의 함수가 각기 다른 객체 데이터를 통해 더 유연한 재사용성을 가지게 만들었습니다. 스코프를 포함하는 함수는 다른 스코프나 변수를 절대 참조할 수 없습니다. 하지만 함수가 유동적인 `this` 컨텍스트를 인식하게되면 되면 특정 업무에 관해서 정말 유용해지게 됩니다.

The benefit of `this`-aware functions—and their dynamic context—is the ability to more flexibly re-use a single function with data from different objects. A function that closes over a scope can never reference a different scope or set of variables. But a function that has dynamic `this` context awareness can be quite helpful for certain tasks.

## 프로토타입<sup>Prototypes</sup>

## Prototypes

`this`가 함수를 실행하는데에 관한 특성이라면 프로토타입은 객체에 관한 특징입니다. 조금 더 정확하게는 객체의 프로퍼티에 접근하는 특별한 방법입니다.

Where `this` is a characteristic of function execution, a prototype is a characteristic of an object, and specifically resolution of a property access.

프로토타입을 두 객체를 사이의 결합<sup>Linkage</sup> 같은 것입니다. 이러한 결합은 보이지 않게 숨겨져있지만 이 결합을 노출하고 관찰할 수도 있습니다. 객체를 생성할 때 이미 존재하는 또다른 객체와 연결하여 프로토타입 결합이 발생하게 됩니다.

Think about a prototype as a linkage between two objects; the linkage is hidden behind the scenes, though there are ways to expose and observe it. This prototype linkage occurs when an object is created; it's linked to another object that already exists.

여럿 객체들을 프로토타입을 통해 한꺼번에 결합시키는 것을 "프로토타입 체인<sup>Prototype chain</sup>"이라고 부릅니다.

A series of objects linked together via prototypes is called the "prototype chain."

예를 들어 객체 B를 객체 A에 결합하는 목적은 B에는 없는 프로퍼티나 메서드에 대해 접근을 A가 처리하도록 *위임<sup>Delegate</sup>*하기 위함입니다. 다수의 객체에게 각각의 프로퍼티/메서드에 접근하도록 위임하여 상호간에 협력하고 일을 수행할 수 있게 만들어줍니다.

The purpose of this prototype linkage (i.e., from an object B to another object A) is so that accesses against B for properties/methods that B does not have, are *delegated* to A to handle. Delegation of property/method access allows two (or more!) objects to cooperate with each other to perform a task.

객체를 평범한 리터럴로 정의하는 예시를 한 번 보겠습니다.

Consider defining an object as a normal literal:

```js
var homework = {
    topic: "JS"
};
```

`homework` 객체는 오직 하나의 프로퍼티 `topic`만을 가지고 있습니다. 하지만 프로토타입 결합은 `Object.prototype`라는 객체에 기본적으로 연결이 됩니다. 그리고 `Object.prototype`은 보통 `toString()`, `valueOf()`과 같은 내재된 메서드를 가지고 있습니다.

The `homework` object only has a single property on it: `topic`. However, its default prototype linkage connects to the `Object.prototype` object, which has common built-in methods on it like `toString()` and `valueOf()`, among others.

`homework`에서 `Object.prototype`에 프로토타입 결합을 *위임*하는 것을 볼 수 있습니다.

We can observe this prototype linkage *delegation* from `homework` to `Object.prototype`:

```js
homework.toString();    // [object Object]
```

`homework.toString()`는 `homework`에는 `toString()`가 정의되어 있지는 않아도 사용될 수 있는데 그 이유는 위임자가 `Object.prototype.toString()`를 대신 호출하기 때문입니다.

`homework.toString()` works even though `homework` doesn't have a `toString()` method defined; the delegation invokes `Object.prototype.toString()` instead.

### 객체 결합

### Object Linkage

객체 프로토타입 결합을 정의하기 위해서는 `Object.create(..)` 유틸리티를 사용해서 객체를 만들 수 있습니다.

To define an object prototype linkage, you can create the object using the `Object.create(..)` utility:

```js
var homework = {
    topic: "JS"
};

var otherHomework = Object.create(homework);

otherHomework.topic;   // "JS"
```

`Object.create(..)`에서 첫 번째 인수 값은 새롭게 생성될 객체와 결합할 객체를 명시화하고 그 결과 새롭게 생성된 (그리고 연동된!) 객체가 반환됩니다.

The first argument to `Object.create(..)` specifies an object to link the newly created object to, and then returns the newly created (and linked!) object.

그림 4에서 보는 것과 같이 세 객체(`otherHomework`, `homework` 그리고 `Object.prototype`)는 프로토타입 체인을 통해 연결되어 있습니다.

Figure 4 shows how the three objects (`otherHomework`, `homework`, and `Object.prototype`) are linked in a prototype chain:

<figure>
    <img src="images/fig4.svg" width="200" alt="Prototype chain with 3 objects" align="center">
    <figcaption><em>Fig. 4: Objects in a prototype chain</em></figcaption>
    <br><br>
</figure>

프로토타입 체인을 통한 위임은 오직 프로퍼티 안에 있는 값을 살펴볼 수 있는 접근 권한을 가지고 있습니다. 만약 객체의 프로퍼티에 다른 값을 할당하려하면, 객체가 어떠한 프로토타입과 연결되어 있던지간에 객체에 직접적으로 적용이 됩니다.

Delegation through the prototype chain only applies for accesses to lookup the value in a property. If you assign to a property of an object, that will apply directly to the object regardless of where that object is prototype linked to.

| 팁: |
| :--- |
| `Object.create(null)`은 그 어떠한 프로토타입도 연결되지 않은 객체를 생성합니다. 그러므로 이 객체는 순수하게 독립된 객체이며 몇몇 환경에서는 더 나은 방법일 수도 있습니다. |

| TIP: |
| :--- |
| `Object.create(null)` creates an object that is not prototype linked anywhere, so it's purely just a standalone object; in some circumstances, that may be preferable. |

Consider:

```js
homework.topic;
// "JS"

otherHomework.topic;
// "JS"

otherHomework.topic = "Math";
otherHomework.topic;
// "Math"

homework.topic;
// "JS" -- not "Math"
```

`topic`에 할당하는 것은 `otherHomework`에 직접적으로 프로퍼티를 생성하게 됩니다. 그 결과 `homework`에 있는 프로퍼티 `topic`에는 그 어떠한 영향도 없습니다. 그 다음 명령문에서는 `otherHomework.topic`에 접근하는데 새 프로퍼티 `"Math"`가 위임되지 않은 결과로 나오는 것을 확인할 수 있습니다.

The assignment to `topic` creates a property of that name directly on `otherHomework`; there's no effect on the `topic` property on `homework`. The next statement then accesses `otherHomework.topic`, and we see the non-delegated answer from that new property: `"Math"`.

그림 5는 값 할당으로 인해 `otherHomework.topic` 프로퍼티가 생성된 위 예제의 객체/프로퍼티 상황을 보여줍니다.

Figure 5 shows the objects/properties after the assignment that creates the `otherHomework.topic` property:

<figure>
    <img src="images/fig5.svg" width="200" alt="3 objects linked, with shadowed property" align="center">
    <figcaption><em>Fig. 5: Shadowed property 'topic'</em></figcaption>
    <br><br>
</figure>

`otherHomework`에 있는 `topic`은 체인속 `homework` 객체에 있는 프로퍼티와 동일한 이름을 가진 "그림자(shadowing)" 프로퍼티입니다.

The `topic` on `otherHomework` is "shadowing" the property of the same name on the `homework` object in the chain.

| 노트: |
| :--- |
| 솔직히 조금 더 복잡하지만 프로토타입 결합을 가진 객체를 만드는 또 다른 방법은 여전히 "원형 클래스(prototypal class)" 패턴을 이용하는 방법입니다. 이 방법은 ES6에 `class` (챕터2 "클래스") 이전부터 사용되었고 아마도 여전히 조금 더 일반적인 방법일 것입니다. 이에 관해 조금 더 자세한 것은 부록 A "원형 클래스"에서 다루도록 하겠습니다. |

| NOTE: |
| :--- |
| Another frankly more convoluted but perhaps still more common way of creating an object with a prototype linkage is using the "prototypal class" pattern, from before `class` (see Chapter 2, "Classes") was added in ES6. We'll cover this topic in more detail in Appendix A, "Prototypal 'Classes'". |

### `this`로 돌아가서

### `this` Revisited

`this` 키워드에 관해 이미 살펴봤지만 프로토타입-위임된 함수의 호출을 강화할 때 그 진정한 중요성이 빛을 발하게 됩니다. 게다가 `this`가 함수가 호출되는 방법에따라 유동적인 컨텍스트를 제공하는 가장 중요한 이유 중 하나는, 프로토타입 체인을 통해 위임되는 객체의 메서드를 호출하여도 `this`를 계속해서 유지하기 위해서입니다.

We covered the `this` keyword earlier, but its true importance shines when considering how it powers prototype-delegated function calls. Indeed, one of the main reasons `this` supports dynamic context based on how the function is called is so that method calls on objects which delegate through the prototype chain still maintain the expected `this`.

Consider:

```js
var homework = {
    study() {
        console.log(`Please study ${ this.topic }`);
    }
};

var jsHomework = Object.create(homework);
jsHomework.topic = "JS";
jsHomework.study();
// Please study JS

var mathHomework = Object.create(homework);
mathHomework.topic = "Math";
mathHomework.study();
// Please study Math
```

두 객체 `jsHomework`와 `mathHomework`은 각각 하나의 `study()` 함수를 갖고 있는 `homework` 객체에 연결됩니다. `jsHomework`와 `mathHomework`는 각자 그들만의 `topic` 프로퍼티가 주어지게 됩니다 (그림 6).
The two objects `jsHomework` and `mathHomework` each prototype link to the single `homework` object, which has the `study()` function. `jsHomework` and `mathHomework` are each given their own `topic` property (see Figure 6).

<figure>
    <img src="images/fig6.svg" width="495" alt="4 objects prototype linked" align="center">
    <figcaption><em>Fig. 6: Two objects linked to a common parent</em></figcaption>
    <br><br>
</figure>

`jsHomework.study()`는 `homework.study()`에 위임되는 반면, 함수가 호출된 방법에 따라 `this`(`this.topic`)는 `jsHomework`가 됩니다. 유사하게 `mathHomework.study()` 역시 `homework.study()`에 위임하지만, 여전히 `this`는 `mathHomework`로 귀결되고 결론적으로 `this.topic`은 `"Math"`가 됩니다.

`jsHomework.study()` delegates to `homework.study()`, but its `this` (`this.topic`) for that execution resolves to `jsHomework` because of how the function is called, so `this.topic` is `"JS"`. Similarly for `mathHomework.study()` delegating to `homework.study()` but still resolving `this` to `mathHomework`, and thus `this.topic` as `"Math"`.

이전의 코드 예제에서 만약 `this`가 `homework`가 되었다면 훨씬 덜 유용하였을 것입니다. 하지만 많은 다른 언어에서는 `study()` 메서드가 `homework`에서 정의되었기 때문에 `this`는 `homework`가 되게 됩니다.

The preceding code snippet would be far less useful if `this` was resolved to `homework`. Yet, in many other languages, it would seem `this` would be `homework` because the `study()` method is indeed defined on `homework`.

그런 언어들과는 다르게 JS의 유동적인 `this`는 프로토타입 위임과 더불어 `클래스(class)`가 예상한대로 작동하는데에 중요한 요소입니다.

Unlike many other languages, JS's `this` being dynamic is a critical component of allowing prototype delegation, and indeed `class`, to work as expected!

## "왜?"라고 질문하기

## Asking "Why?"

이 챕터에서는 표면에서 쉽게 알아차릴 수 있는 것보다 JS의 저면 아래에 있는 더 많은 것들과 연관이 있어 의도적으로 제거된 부분이 있습니다.

The intended take-away from this chapter is that there's a lot more to JS under the hood than is obvious from glancing at the surface.

*시작하기*를 통해 JS에 조금 더 면밀하게 배우고 알게됨에 따라 여러분이 연습하고 개선해야 할 가장 중요한 기술은 호기심 그리고 언어에 관련된 무언가를 마주할 때 "왜?"라고 질문하는 방법입니다.

As you are *getting started* learning and knowing JS more closely, one of the most important skills you can practice and bolster is curiosity, and the art of asking "Why?" when you encounter something in the language.

이 챕터에서 몇몇 주제에 관해 다소 깊이 다루기도 했지만, 더 많은 세부 사항들을 여전히 전반적으로 훑어보았을 뿐입니다. 더 많이 배워야 할 것들이 있고 여러분의 코드속에서 *옳은* 질문을 하기 시작해야할 방향 역시 있습니다. 옳은 질문을 함으로써 중요한 기술을 가진 더 나은 개발자가 되십시오.

Even though this chapter has gone quite deep on some of the topics, many details have still been entirely skimmed over. There's much more to learn here, and the path to that starts with you asking the *right* questions of your code. Asking the right questions is a critical skill of becoming a better developer.

이 책의 마지막 챕터에서는 *You Don't Know JS Yet*의 나머지 책 시리즈를 전반적으로 훑어보며, JS는 어떻게 쪼개져있는지 가볍게 살펴볼 것입니다. 또한 이 책에서 다뤘던 주요 주제들을 복습할 수 있는 연습 코드가 있는 부록 B를 그냥 지나치고 넘어가지 말아주시기 바랍니다.

In the final chapter of this book, we're going to briefly look at how JS is divided, as covered across the rest of the *You Don't Know JS Yet* book series. Also, don't skip Appendix B of this book, which has some practice code to review some of the main topics covered in this book.
