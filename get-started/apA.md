# You Don't Know JS Yet: Get Started - 2nd Edition
# 부록 A: 더 알아보기
# Appendix A: Exploring Further

이 부록에서는 주요 챕터로부터 몇몇 주제에 관해 조금 더 나아가 알아 보겠습니다. 남은 책들을 통해 배울 세부 사항의 일부를 선택적으로 미리본다고 생각해주시기 바랍니다.

In this appendix, we're going to explore some topics from the main chapter text in a bit more detail. Think of this content as an optional preview of some of the more nuanced details covered throughout the rest of the book series.

## 값<sup>Value</sup> 대 참조<sup>Reference</sup>

## Values vs. References

챕터 2에서 값의 원시값과 객체란 두 종류를 소개했었습니다. 하지만 이 둘의 중요한 차이점에 관해 얘기하진 않았습니다. 그 차이점은 이 값들이 할당되고 전달되는 방법에 있습니다.

In Chapter 2, we introduced the two main types of values: primitives and objects. But we didn't discuss yet one key difference between the two: how these values are assigned and passed around.

많은 언어에서 개발자는 값을 할당하고 전달하는데 있어 값 그 자체를 쓸 지 아니면 참조값을 쓸지 선택할 수 있습니다. 하지만 JS에서는 값의 종류에 따라 전적으로 결정이 됩니다. 이러한 점이 다른 언어로부터 온 많은 개발자들을 놀라게 만듭니다.

In many languages, the developer can choose between assigning/passing a value as the value itself, or as a reference to the value. In JS, however, this decision is entirely determined by the kind of value. That surprises a lot of developers from other languages when they start using JS.

값 그 자체를 할당하거나 전달하면 이 값은 복사가 되어집니다.

If you assign/pass a value itself, the value is copied. For example:

```js
var myName = "Kyle";

var yourName = myName;
```

여기에서 `yourName` 변수는 `myName`에 저장된 값 `"Kyle"`의 복사본을 별도로 가지게 됩니다. 이렇게 된 이유는 이 값이 원시값이고, 원시값은 항상 **값 복사**를 통해 할당되거나 복사되기 때문입니다.

Here, the `yourName` variable has a separate copy of the `"Kyle"` string from the value that's stored in `myName`. That's because the value is a primitive, and primitive values are always assigned/passed as **value copies**.

두 값이 별도임을 증명하는 방법은 아래와 같습니다.

Here's how you can prove there's two separate values involved:

```js
var myName = "Kyle";

var yourName = myName;

myName = "Frank";

console.log(myName);
// Frank

console.log(yourName);
// Kyle
```

`yourName`이 `myName`을 `"Frank"`로 재할당하는 것에 아무런 영향을 받지 않을 수 있었을까요? 이는 각 변수가 값의 복사본을 가지고 있기 때문입니다.

See how `yourName` wasn't affected by the re-assignment of `myName` to `"Frank"`? That's because each variable holds its own copy of the value.

반대로 참조값은 두 개 이상의 변수가 똑같은 값을 가르기고 있는 것 입니다. 예를 들어 공유하고 있는 값을 변경시키면 이는 곧 참조값을 통해 각 변수들에 반영이 됩니다. JS에서 배열, 객체, 함수 등등 객체값으로 여겨지는 모든 것들은 참조값으로 여겨집니다.

By contrast, references are the idea that two or more variables are pointing at the same value, such that modifying this shared value would be reflected by an access via any of those references. In JS, only object values (arrays, objects, functions, etc.) are treated as references.

Consider:

```js
var myAddress = {
    street: "123 JS Blvd",
    city: "Austin",
    state: "TX"
};

var yourAddress = myAddress;

// I've got to move to a new house!
myAddress.street = "456 TS Ave";

console.log(yourAddress.street);
// 456 TS Ave
```

`myAddress`에 할당된 값은 객체이기에 이 객체는 참조값을 가지고 할당되어 있습니다. 그리고 결국 `yourAddress` 변수에 할당문은 객체값 그 자체가 아닌 참조값의 복사본을 가지도록 만들어줍니다. 그렇기에 새로운 값을 `myAddress.street`에 할당하는 것이 `yourAddress.street`에 반영되는 원인입니다. `myAddress`와 `yourAddress`는 공통된 하나의 객체를 바라보고 있는 참조값의 복사본을 가지고 있습니다. 그렇기에 한 쪽에서 수정하게되면 다른 한 쪽에서도 똑같이 반영되는 것입니다.

Because the value assigned to `myAddress` is an object, it's held/assigned by reference, and thus the assignment to the `yourAddress` variable is a copy of the reference, not the object value itself. That's why the updated value assigned to the `myAddress.street` is reflected when we access `yourAddress.street`. `myAddress` and `yourAddress` have copies of the reference to the single shared object, so an update to one is an update to both.

다시 한 번 말하자면 JS는 값의 타입에 의존해 값 복사<sup>Value-copy</sup>할지 참조값 복사<sup>Reference-copy</sup>할지 결정되게 됩니다. 값은 원시값을 가지고 참조값은 객체를 가지고 있습니다. JS에서 이 정책을 무시할 수 있는 방법은 없습니다.

Again, JS chooses the value-copy vs. reference-copy behavior based on the value type. Primitives are held by value, objects are held by reference. There's no way to override this in JS, in either direction.

## 많은 함수 형태

## So Many Function Forms

챕터 2 "함수" 섹션에서 보았던 예제를 되뇌어 보시기 바랍니다.

Recall this snippet from the "Functions" section in Chapter 2:

```js
var awesomeFunction = function(coolThings) {
    // ..
    return amazingStuff;
};
```

여기에 있는 함수 표현식은 *익명 함수 표현식<sup>Anonymous function expression</sup>* 이라 불립니다. 이는 `function`이란 키워드와 `(..)` 매개 변수 사이에 식별자가 없기 때문입니다.
ES6부터 JS는 익명 함수에 "이름 추론<sup>Name inference</sup>"을 수행하기 때문에 이러한 점은 많은 JS 개발자들을 혼란스럽게 만듭니다.

The function expression here is referred to as an *anonymous function expression*, since it has no name identifier between the `function` keyword and the `(..)` parameter list. This point confuses many JS developers because as of ES6, JS performs a "name inference" on an anonymous function:

```js
awesomeFunction.name;
// "awesomeFunction"
```

함수의 `name` 프로퍼티는 함수 선언에서 직접 주어진 이름이나 익명 함수 표현식에서 추론된 이름 중 하나를 나타냅니다. 이 값은 일반적으로 함수 값을 조사하거나 오류 스택 기록을 알려줄 때 개발자 도구에서 사용됩니다.

The `name` property of a function will reveal either its directly given name (in the case of a declaration) or its inferred name in the case of an anonymous function expression. That value is generally used by developer tools when inspecting a function value or when reporting an error stack trace.

그러므로 익명 함수 표현식조차 이름을 가질 수도 있습니다. 하지만 이름 추론은 함수 표현식이 `=`를 통해 할당될 경우와 같이 한정된 상황에서만 발생합니다. 예를들어 함수 표현식을 함수 호출에서 인수로 전달하면 이름 추론은 발생하지 않을 것입니다. 즉 `name` 프로퍼티는 비어있는 문자열일 것이고 개발자 콘솔에선 "익명 함수"라고 보고할 것입니다.

So even an anonymous function expression *might* get a name. However, name inference only happens in limited cases such as when the function expression is assigned (with `=`). If you pass a function expression as an argument to a function call, for example, no name inference occurs; the `name` property will be an empty string, and the developer console will usually report "(anonymous function)".

하지만 이름이 추론 됐을지라도 **여전히 익명 함수일 것입니다.** 이유인 즉슨 추론된 이름은 메타데이터 문자열 값이지 함수를 가르키는 식별자가 아니기 때문입니다. 익명 함수는 재귀 함수 호출을 위해 이 함수 자체를 나타낼 식별자를 가지고 있지 않습니다.

Even if a name is inferred, **it's still an anonymous function.** Why? Because the inferred name is a metadata string value, not an available identifier to refer to the function. An anonymous function doesn't have an identifier to use to refer to itself from inside itself—for recursion, event unbinding, etc.

아래 예시를 익명 함수 표현식고 비교해 보겠습니다.

Compare the anonymous function expression form to:

```js
// let awesomeFunction = ..
// const awesomeFunction = ..
var awesomeFunction = function someName(coolThings) {
    // ..
    return amazingStuff;
};

awesomeFunction.name;
// "someName"
```

위 함수 표현식은 *명명된 함수 표현식*입니다. `someName`은 함수 표현식에 식별자로써 컴파일 와중에 직접 연계되게 됩니다. 이 연계는 식별자 `awesomeFunction`과 해당 명령문이 실행되기 전 런타임이 될 때까지 그 어떠한 일도 발생하지 않습니다. 두 식별자가 서로 일치할 필요가 없습니다. 때때로 이 둘은 다르는 게 더 어울릴 때도 있지만 그렇지 않은 경우 같은 식별자를 갖는게 낫습니다.

This function expression is a *named function expression*, since the identifier `someName` is directly associated with the function expression at compile time; the association with the identifier `awesomeFunction` still doesn't happen until runtime at the time of that statement. Those two identifiers don't have to match; sometimes it makes sense to have them be different, other times it's better to have them be the same.

또한 `name` 프로퍼티에 *이름*을 할당할 때 명시적인 함수 이름 `someName`이 우선적으로 취해지는 것을 눈여겨 봐주시기 바랍니다.

Notice also that the explicit function name, the identifier `someName`, takes precedence when assigning a *name* for the `name` property.

함수 표현식은 명시적일까요 익명일까요? 이에대한 의견은 상당히 다릅니다. 대부분의 개발자들은 익명 함수를 무심하게 사용하는 경향이 있습니다. 이들이 조금 더 짧고 의심할 나위 없이 넓은 JS 환경에서 더 흔하게 볼 수 있습니다.

Should function expressions be named or anonymous? Opinions vary widely on this. Most developers tend to be unconcerned with using anonymous functions. They're shorter, and unquestionably more common in the broad sphere of JS code out there.

제 생각에는 함수가 목적이 없다면 익명 함수로 그렇지 않고 목적이 있다면 그 목적을 묘사하는 자연스러운 이름을 갖게 될 것입니다.

In my opinion, if a function exists in your program, it has a purpose; otherwise, take it out! And if it has a purpose, it has a natural name that describes that purpose.

함수가 이름을 가지고 있다면 코드 작성자는 그 이름을 코드에 포함시켜야만 합니다. 그래서 코드를 읽는 이는 함수의 소스 코드를 읽고 실행시키며 추론할 필요가 없습니다. 심지어 `x * 2`와 같이 사소한 내용물을 가진 함수조차도 "double" 혹은 "multBy2"와 같은 이름을 추론해야만 합니다. 여러분이 일단 함수에 짧은 시간을 들여 "double" "multBy2" 같은 이름을 부여한다면 이런 짧은 추가적인 마음속으로 해야할 작업은 불필요합니다. 이는 추후에 코드를 읽는 이에게 추론을 위해 매번 하는 반복적인 작업하는 시간을 아껴주게 됩니다.

If a function has a name, you the code author should include that name in the code, so that the reader does not have to infer that name from reading and mentally executing that function's source code. Even a trivial function body like `x * 2` has to be read to infer a name like "double" or "multBy2"; that brief extra mental work is unnecessary when you could just take a second to name the function "double" or "multBy2" *once*, saving the reader that repeated mental work every time it's read in the future.

여러모로 유감스럽지만 2020년 초기의 JS에는 함수를 정의할 수 있는 많은 형식이 있습니다. 아마도 미래에는 더 있을 수도 있습니다!

There are, regrettably in some respects, many other function definition forms in JS as of early 2020 (maybe more in the future!).

아래 조금 더 많은 선언 형식이 있습니다.

Here are some more declaration forms:

```js
// generator function declaration
// 제너레이터(Generator) 함수 선언
function *two() { .. }

// async function declaration
// 비동기 함수 선언
async function three() { .. }

// async generator function declaration
// 비동기 제너레이터 함수 선언
async function *four() { .. }

// named function export declaration (ES6 modules)
// 내보낼 명명된 함수 선언 (ES6 모듈)
export function five() { .. }
```

여기에 더 많은 함수 표현식 형식이 있습니다.

And here are some more of the (many!) function expression forms:

```js
// IIFE
(function(){ .. })();
(function namedIIFE(){ .. })();

// asynchronous IIFE
// 비동기 IIFE
(async function(){ .. })();
(async function namedAIIFE(){ .. })();

// arrow function expressions
// 화살표 함수(Arrow function) 표현식
var f;
f = () => 42;
f = x => x * 2;
f = (x) => x * 2;
f = (x,y) => x * y;
f = x => ({ x: x * 2 });
f = x => { return x * 2; };
f = async x => {
    var y = await doSomethingAsync(x);
    return y * 2;
};
someOperation( x => x * 2 );
// ..
```

화살표 함수 표현식은 **문법적으로 익명**이라는 것을 명심해주시기 바랍니다. 이는 곧 직접적으로 식별자 이름을 제공할 수 있는 문법상 없다는 얘기입니다. 할당식 형태라면 함수 표현식은 아마도 추론된 이름을 가지게 될 수도 있지만 예체의 마지막 줄에서 보이는 것과 같이 함수 호출 인수로 전해질 때는 그렇지 않습니다.

Keep in mind that arrow function expressions are **syntactically anonymous**, meaning the syntax doesn't provide a way to provide a direct name identifier for the function. The function expression may get an inferred name, but only if it's one of the assignment forms, not in the (more common!) form of being passed as a function call argument (as in the last line of the snippet).

익명 함수를 프로그램에서 빈번하게 사용하는 것이 전 좋지 않다고 생각합니다. 그렇기에 전 `=>` 화살표 함수 형식을 사용하는 것을 선호하지 않습니다. 화살표 함수는 `this` 키워드를 다루기위해 특별한 목적을 가지고 있지만 우리가 모든 함수를 이렇게 작성할 필요가 없단 얘기입니다. 가장 적절한 도구를 각각의 작업에 맞게 적절히 사용해주기 바랍니다.

Since I don't think anonymous functions are a good idea to use frequently in your programs, I'm not a fan of using the `=>` arrow function form. This kind of function actually has a specific purpose (i.e., handling the `this` keyword lexically), but that doesn't mean we should use it for every function we write. Use the most appropriate tool for each job.

함수는 역시 클래스 정의 그리고 객체 리터럴 정의 내부에도 명시될 수 있습니다. 일반적으로 이러한 형식을 "메서드<sup>Method</sup>"라고 부르지만 JS에서 이러한 용어는 "함수"와 크게 눈에 띄는 차이점은 없습니다.

Functions can also be specified in class definitions and object literal definitions. They're typically referred to as "methods" when in these forms, though in JS this term doesn't have much observable difference over "function":

```js
class SomethingKindaGreat {
    // class methods
    // 클래스 메서드
    coolMethod() { .. }   // no commas!
    boringMethod() { .. }
}

var EntirelyDifferent = {
    // object methods
    // 객체 메서드
    coolMethod() { .. },   // commas!
    boringMethod() { .. },

    // (anonymous) function expression property
    // 프로퍼티 익명 함수 표현식
    oldSchool: function() { .. }
};
```

함수를 정의하는 정말 다양한 방법이 있습니다.

Phew! That's a lot of different ways to define functions.

이를 익히 다 알 수 있는 간단히 갈 수 있는 지름길은 없습니다. 단지 모든 함수 형식으로 함수를 만들 수 있게 익숙해져야만 합니다. 이로인해 여러분은 존재하는 코드를 파악하게되고 적절하게 사용할 수 있게됩니다. 이것들을 면밀히 학습하시고 연습하십시오!

There's no simple shortcut path here; you just have to build familiarity with all the function forms so you can recognize them in existing code and use them appropriately in the code you write. Study them closely and practice!

## 강제적인 조건 비교

## Coercive Conditional Comparison

섹션 이름이 다소 복잡합니다. 무엇을 얘기하고 싶은걸까요? 여기에서 결정을 내리기위해 우린 강제 변환을 지향하는 비교 조건 표현식을 얘기하고자 합니다.

Yes, that section name is quite a mouthful. But what are we talking about? We're talking about conditional expressions needing to perform coercion-oriented comparisons to make their decisions.

`if`와 `? :` 삼항 연산자, 그리고 `while`과 `for` 반복문에 있는 검사절에서는 모두 암시적 값 비교를 수행하게 됩니다. 그렇다면 어떠한 종류의 비교를 수행하게 될까요? "엄격한" 형식일까요 아니면 "강제 변환"적일까요? 실제로는 둘 다 입니다.

`if` and `? :`-ternary statements, as well as the test clauses in `while` and `for` loops, all perform an implicit value comparison. But what sort? Is it "strict" or "coercive"? Both, actually.

아래 예시를 살펴보겠습니다.

Consider:

```js
var x = 1;

if (x) {
    // 수행될 겁니다.
    // will run!
}

while (x) {
    // 한 번 수행될 겁니다.
    // will run, once!
    x = false;
}
```

아마도 `(x)` 조건 표현식을 아래와 같다고 생각하실 수 있습니다.

You might think of these `(x)` conditional expressions like this:

```js
var x = 1;

if (x == true) {
    // 수행될 겁니다.
    // will run!
}

while (x == true) {
    // 한 번 수행될 겁니다.
    // will run, once!
    x = false;
}
```

`x`의 값이 `1`인 특별한 경우 첫 예시를 마음속으로 위와 같이 수정한 형태는 정상적으로 작동을 할 것입니다. 하지만 좀 더 넓게 보자면 정확하지 않습니다. 아래 예시를 한 번 더 살펴보겠습니다.

In this specific case -- the value of `x` being `1` -- that mental model works, but it's not accurate more broadly. Consider:

```js
var x = "hello";

if (x) {
    // 수행될 겁니다.
    // will run!
}

if (x == true) {
    // 수행되지 않을 것입니다. ㅠㅠ
    // won't run :(
}
```

그렇다면 `if`문은 실제로 무엇을 하는 것일까요? 조금 더 정확한 상상속 모델은 아래와 같습니다.

Oops. So what is the `if` statement actually doing? This is the more accurate mental model:

```js
var x = "hello";

if (Boolean(x) == true) {
    // 수행될 겁니다.
    // will run
}

// 이는 곧 아래와 동일합니다.
// which is the same as:

if (Boolean(x) === true) {
    // 수행될 겁니다.
    // will run
}
```

`Boolean(..)` 함수는 항상 불리언 타입의 값을 반환하므로 예시 속 `==` 대 `===` 문제는 전혀 상관이 없습니다. 예시 속 두 비교문은 실제로는 둘 다 같습니다. 하지만 주시해야 할 중요한 부분은 강제 변환을 통해 `x`의 현재 타입으로부터 불리언으로 값이 바뀐다는 점입니다.

Since the `Boolean(..)` function always returns a value of type boolean, the `==` vs `===` in this snippet is irrelevant; they'll both do the same thing. But the important part is to see that before the comparison, a coercion occurs, from whatever type `x` currently is, to boolean.

단지 JS 비교에서 강제 변환으로부터 달아날 수 없습니다. 강제 변환에 관해 본격적으로 배워야만 합니다.

You just can't get away from coercions in JS comparisons. Buckle down and learn them.

## 프로토타입형 "클래스"

## Prototypal "Classes"

챕터 3에서 프로토타입을 소개하였고 객체간에 프로토타입 체인을 통해 어떻게 연결되는지 보여줬습니다.

In Chapter 3, we introduced prototypes and showed how we can link objects through a prototype chain.

ES6 `class` 시스템의 간결함에 전임자 역할을 하던 프로토타입 간 연결을 지원하는 또다른 방법이 있습니다. 이러한 방법은 프로토타입형 클래스라고 부릅니다.

Another way of wiring up such prototype linkages served as the (honestly, ugly) predecessor to the elegance of the ES6 `class` system (see Chapter 2, "Classes"), and is referred to as prototypal classes.

| 팁: |
| :--- |
| 오늘날의 JS에서 이러한 코드 방식은 다소 흔하지 않습니다만, 여전히 당황스럽게도 면접에서 질문을 다소 자주 하기도 합니다! |

| TIP: |
| :--- |
| While this style of code is quite uncommon in JS these days, it's still perplexingly rather common to be asked about it in job interviews! |

`Object.create(..)` 사용했던 코드를 우선 다시 상기해 보겠습니다.

Let's first recall the `Object.create(..)` style of coding:

```js
var Classroom = {
    welcome() {
        console.log("Welcome, students!");
    }
};

var mathClass = Object.create(Classroom);

mathClass.welcome();
// Welcome, students!
```

여기서 `mathClass` 객체는 프로토타입을 통해 `Classroom` 객체에 연결됩니다. 이러한 연결을 통해 `mathClass.welcome()` 함수 호출하는 것은 이 함수가 정의되어 있는 `Classroom`에 위임되게 됩니다.

Here, a `mathClass` object is linked via its prototype to a `Classroom` object. Through this linkage, the function call `mathClass.welcome()` is delegated to the method defined on `Classroom`.

프로토타입형 클래스 형식은 동작 위임 "상속"이라 부릅니다. 그리고 동일한 동작을 하여 대체할 수 있게 아래와 같이 작성할 수도 있습니다.

The prototypal class pattern would have labeled this delegation behavior "inheritance," and alternatively have defined it (with the same behavior) as:

```js
function Classroom() {
    // ..
}

Classroom.prototype.welcome = function hello() {
    console.log("Welcome, students!");
};

var mathClass = new Classroom();

mathClass.welcome();
// Welcome, students!
```

모든 함수는 기본적으로 `prototype`이란 프로퍼티가 비어있는 객체를를 가르키도록 되어있습니다. 혼동되는 이름이지만 이 함수의 프로토타입이 연결되는 *프로토타입*이 **아닙니다**. 하지만 대신`new`를 통해 함수가 호출되면 객체가 만들어지고 이 객체는 프로토타입 객체와 통해 연결이 됩니다.

All functions by default reference an empty object at a property named `prototype`. Despite the confusing naming, this is **not** the function's *prototype* (where the function is prototype linked to), but rather the prototype object to *link to* when other objects are created by calling the function with `new`.

여기서 저희는 비어있는 객체 `Classroom.prototype`에 `welcome` 프로퍼티를 추가하면 이 프로퍼티는 `hello()` 함수를 가르키게 됩니다.

We add a `welcome` property on that empty object (called `Classroom.prototype`), pointing at the `hello()` function.

그 후 `new Classroom()`은 새로운 객체를 만들고 `mathClass`에 할당이 됩니다. 이를 통해 프로토타입이 존재하는 `Classroom.prototype` 객체에 연결이 되게 됩니다.

Then `new Classroom()` creates a new object (assigned to `mathClass`), and prototype links it to the existing `Classroom.prototype` object.

`mathClass`가 `welcome()` 프로퍼티 즉 함수를 가지고 있지 않지만, `mathClass`는 함수 `Classroom.prototype.welcome()`에 성공적으로 할당하게 됩니다.

Though `mathClass` does not have a `welcome()` property/function, it successfully delegates to the function `Classroom.prototype.welcome()`.

이 "프로토타입형 클래스" 방식은 현재 강력하게 사용하지 말라고 권유되고 있고 ES6의 `class` 방식을 사용하라고 합니다.

This "prototypal class" pattern is now strongly discouraged, in favor of using ES6's `class` mechanism:

```js
class Classroom {
    constructor() {
        // ..
    }

    welcome() {
        console.log("Welcome, students!");
    }
}

var mathClass = new Classroom();

mathClass.welcome();
// Welcome, students!
```

이러한 방법으로 동일한 프로토타입 연결 완성할 수 있지만, `class` 문법이 "프로토타입형 클래스"보다도 더 클래스 지향 방식에 훨씬 더 잘 어울립니다.

Under the covers, the same prototype linkage is wired up, but this `class` syntax fits the class-oriented design pattern much more cleanly than "prototypal classes".
