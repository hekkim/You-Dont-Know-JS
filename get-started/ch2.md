# You Don't Know JS Yet: Get Started - 2nd Edition
# 챕터 2: JS 조사하기
# Chapter 2: Surveying JS

JS를 배우는 가장 좋은 방법은 JS를 사용하기 시작하는 것 부터 시작합니다.

The best way to learn JS is to start writing JS.

JS를 사용하기 위해서는 이 언어가 어떻게 동작하는지 먼저 알아야하고 이에 대해 집중해서 파헤쳐보도록 하겠습니다. 다른 언어로 프로그래밍을 이미해봤을지라도, JS에 익숙해지기까지 충분한 시간을 들이고 각각의 예제들을 충분히 짚고 학습십시오.

To do that, you need to know how the language works, and that's what we'll focus on here. Even if you've programmed in other languages before, take your time getting comfortable with JS, and make sure to practice each piece.

이 챕터에서는 JS의 모든 문법에 관한 완전한 참고문가 되진 않을 것이지만 그렇다고 완전하게 "JS로의 입문"와 같은 완벽한 기본 입문서를 지향하고 있지는 않습니다.

This chapter is not an exhaustive reference on every bit of syntax of the JS language. It's also not intended to be a complete "intro to JS" primer.

대신 우리는 언어의 가장 중요한 몇가지 주제들에 관해 알아가고자 합니다. 우리의 목표는 더 많은 *깨달음*을 얻고 그로인해 더 큰 자신감을 가지고 우리의 프로그램을 개발해나가는데 있습니다. 이 책과 시리즈를 나아감에 따라 이런 주제들에 관해 성공적으로 더 많은 세부사항에 관해 다시 논의하게 될 것입니다.

Instead, we're just going to survey some of the major topic areas of the language. Our goal is to get a better *feel* for it, so that we can move forward writing our own programs with more confidence. We'll revisit many of these topics in successively more detail as you go through the rest of this book, and the rest of the series.

이 챕터를 쉽게 읽고 넘어갈 것이라고 생각하지 말아주세요. 이 챕터는 길고 짚고 넘어갈 충분히 많은 상세한 내용들이 있습니다. 그러니 천천히 짚고 넘어가길 바랍니다.

Please don't expect this chapter to be a quick read. It's long and there's plenty of detail to chew on. Take your time.

| 팁: |
| :--- |
| 만약 이미 충분히 JS와 친근하더라도 저는 여러분이 이곳에 충분히 많은 시간을 들이길 제안드립니다. 각 섹션을 충분히 숙지하시고 각 주제에 관해 충분한 시간을 들여 곰곰히 생각하고 분석해 보십시오. 존재하는 JS 프로그램을 살펴보고 코드와 여기에 있는 설명(그리고 의논들에 관해서도!)들에 관해 비교해 보십시오. 이 책과 시리즈를 통해 여러분은 JS의 *본질*에 관해 더 많은 것을 알아갈 수 있을 것입니다. |

| TIP: |
| :--- |
| If you're still getting familiar with JS, I suggest you reserve plenty of extra time to work through this chapter. Take each section and ponder and explore the topic for awhile. Look through existing JS programs and compare what you see in them to the code and explanations (and opinions!) presented here. You will get a lot more out of the rest of the book and series with a solid foundation of JS's *nature*. |

## 각 파일은 프로그램이다

## Each File is a Program

우리가 사용하는 대부분의 웹 사이트 (웹 어플리케이션)는 여러개의 각기 다른 JS 파일(대표적으로 .js 확장자명을 갖고 있는)들로 구성되어 있습니다. 보통 파일들 전체를 하나로 생각하는 경향이 있습니다. 하지만 JS는 그렇게 바라보지 않습니다.

Almost every website (web application) you use is comprised of many different JS files (typically with the .js file extension). It's tempting to think of the whole thing (the application) as one program. But JS sees it differently.

JS에서 각각의 개별 파일들은 분리된 개별의 프로그램입니다.

In JS, each standalone file is its own separate program.

이 문제가 중요한 이유는 주로 에러 처리와 관련되어 있습니다. JS는 각각의 파일들을 개별 프로그램으로 여기기때문에 만약 한 파일에서 (파싱/컴파일 혹은 실행 도중) 에러가 발생하더라도 그것이 그 다음 파일이 처리를 막는 것을 의미하지 않습니다. 조금 더 정확하게는 여러분의 어플리케이션이 다섯개의 .js 파일에 구성되어 있고 그 중 하나에서 실패를 한다면 잘해야 전체 어플리케이션 중 일부는 작동할 수도 있다는 얘기입니다. 그 말인즉슨 각각의 파일들이 정확하게 동작 하고 다른 파일에서 발생할 수 있는 오류를 오류를 가능한 한 적절하게 처리하는 것이 중요합니다.

The reason this matters is primarily around error handling. Since JS treats files as programs, one file may fail (during parse/compile or execution) and that will not necessarily prevent the next file from being processed. Obviously, if your application depends on five .js files, and one of them fails, the overall application will probably only partially operate, at best. It's important to ensure that each file works properly, and that to whatever extent possible, they handle failure in other files as gracefully as possible.

분리된 .js 파일들을 별개의 JS 프로그램으로 여기는 것이 아마 조금 이상할 수도 있습니다. 어플리케이션을 사용하는 관점에 따르면 그저 단지 하나의 큰 프로그램으로 여겨지기 때문입니다. 그렇기에 어플리케이션을 실행하는 것은 이러한 여러 개별 *프로그램들*을 하나의 프로그램처럼 협력하고 행동하도록 만드는 것입니다.

It may surprise you to consider separate .js files as separate JS programs. From the perspective of your usage of an application, it sure seems like one big program. That's because the execution of the application allows these individual *programs* to cooperate and act as one program.

| 노트: |
| :--- |
| 많은 프로젝트들은 한 프로젝트를 개별 파일들을 결합하여 웹 페이지에 배포해주는 빌드 프로세스 툴(build process tool)을 사용합니다. 이러한 과정에서 JS는 하나의 통합된 파일로 합쳐지고 하나의 전체 프로그램으로 인식합니다. |

| NOTE: |
| :--- |
| Many projects use build process tools that end up combining separate files from the project into a single file to be delivered to a web page. When this happens, JS treats this single combined file as the entire program. |

여러개의 독자적인 .js 파일들을 하나의 프로그램처럼 동작하게 만드는 유일한 방법은 "글로벌 스코프(global scope)"를 통해 그들의 상태(그리고 그들의 공공 기능들에 접근해서)를 공유하는 것입니다. JS 프로그램은 글로벌 스코프 네임스페이스(global scope namespace)에 섞여지고 런타임(runtime) 동안 마치 하나인 것처럼 작동하게 됩니다.

The only way multiple standalone .js files act as a single program is by sharing their state (and access to their public functionality) via the "global scope." They mix together in this global scope namespace, so at runtime they act as as whole.

ES6부터는 일반적인 독립 JS 프로그램 포맷뿐만이 아니라 JS는 모듈(module) 포맷 또한 지원해오고 있습니다. 모듈 역시 파일 기반으로 돼있습니다. 파일이 `import` 문이나 `<script type="module">` 태그와 같은 모듈 로딩 방식으로 파일이 불러오면 이 모든 코드들이 단일 모듈로 취급됩니다.

Since ES6, JS has also supported a module format in addition to the typical standalone JS program format. Modules are also file-based. If a file is loaded via module-loading mechanism such as an `import` statement or a `<script type=module>` tag, all its code is treated as a single module.

상태들과 그 상태들을 조작하는 공개적으로 노출된 함수들의 집합체인 모듈을 일반적으로 독자적인 프로그램으로 생각하지 않을 수도 있지만 JS 실제로는 각각의 모듈을 독자적인 프로그램으로 간주합니다. "글로벌 스코프"가 런타임 기간동안 독자적인 파일간 서로간 혼합되어 사용 가능하게 만들어주는 방식은 모듈간에 서로 불로오는 것은 런타임 기간동안 서로 상호작용하도록 만들어주는 것과 흡사합니다.

Though you wouldn't typically think about a module—a collection of state and publicly exposed methods to operate on that state—as a standalone program, JS does in fact still treat each module separately. Similar to how "global scope" allows standalone files to mix together at runtime, importing a module into another allows runtime interoperation between them.

파일(독자적인 혹은 모듈)을 불러오는데 어떤 코드의 구조 패턴이 사용되는지에 상관없이 여러분은 여전히 각 파일들을 전체 어플리케이션의 그능들을 수행하는 다른 작은 프로그램들과 상호작용할 조그마한 프로그램으로 생각해야만 합니다.

Regardless of which code organization pattern (and loading mechanism) is used for a file (standalone or module), you should still think of each file as its own (mini) program, which may then cooperate with other (mini) programs to perform the functions of your overall application.

## 값

## Values

프로그램에서 가장 근본적인 정보의 단위는 값(value)입니다. 값들은 곧 데이터입니다. 값들은 프로그램이 상태를 유지하는 방법입니다. 값들은 JS에서는 두 가지 형식으로 존재합니다: **원시(primitive)** 혹은 **객체(object)**

The most fundamental unit of information in a program is a value. Values are data. They're how the program maintains state. Values come in two forms in JS: **primitive** and **object**.

값들은 프로그램 내부에서 *리터럴(literals)*로 사용됩니다:

Values are embedded in programs using *literals*:

```js
greeting("My name is Kyle.");
```

이 프로그램에서 `"My name is Kyle."`이란 값은 원시 문자역 리터럴입니다. 문자열은 순서대로 나열된 문자들의 집합이며 보통 단어 혹은 문장을 표현하기위해 사용됩니다.

In this program, the value `"My name is Kyle."` is a primitive string literal; strings are ordered collections of characters, usually used to represent words and sentences.

큰따옴표 `"`는 문자열 값의 *범위를 정하는데(delimit)* (감싸고, 분리하고, 정의하는데) 사용됩니다. 하지만 작은따옴표 `'` 역시 문자열을 위해 사용될 수 있습니다. 어떠한 따옴표를 사용할 지에 관해서는 전적으로 그 스타일에따라 달려있습니다. 중요한 것은 프로그램의 전반에 있어 코드의 가독성 유지보수성을 위해 그 중 한가지를 선택해 꾸준히 사용해야 된다는 것입니다.

I used the double-quote `"` character to *delimit* (surround, separate, define) the string value. But I could have used the single-quote `'` character as well. The choice of which quote character is entirely stylistic. The important thing, for code readability and maintainability sake, is to pick one and to use it consistently throughout the program.

문자열의 리터럴의 범위를 정하는 또 다른 선택지는 백틱(back-tick) `` ` ``을 사용하는 것입니다. 다만, 이 선택지는 단순히 스타일적인 문제가 아닙니다. 왜냐하면 동작하는데 차이가 있기 때문이죠.

Another option to delimit a string literal is to use the back-tick `` ` `` character. However, this choice is not merely stylistic; there's a behavioral difference as well. Consider:

```js
console.log("My name is ${ firstName }.");
// My name is ${ firstName }.

console.log('My name is ${ firstName }.');
// My name is ${ firstName }.

console.log(`My name is ${ firstName }.`);
// My name is Kyle.
```

이 프로그램에서 `firstName`이란 이름의 변수가 `"Kyle"`이란 값을 가지고 있다고 가정할 때, `` ` ``으로 한정된 문자열은 변수 표현식(`${ .. }`으로 나타나는)을 현재 값을 치환합니다. 이러한 것을 **인터폴레이션(interpolation)**이라 부릅니다.

Assuming this program has already defined a variable `firstName` with the string value `"Kyle"`, the `` ` ``-delimited string then resolves the variable expression (indicated with `${ .. }`) to its current value. This is called **interpolation**.

문자열을 한정짓는 백틱은 인터폴레이션 표현식 없이도 사용될 수 있지만 문자열 리터럴 문법을 전부 다 대체하기에는 결점이 있습니다.

The back-tick `` ` ``-delimited string can be used without including interpolated expressions, but that defeats the whole purpose of that alternate string literal syntax:

```js
console.log(
    `Am I confusing you by omitting interpolation?`
);
// Am I confusing you by omitting interpolation?
```

`"` 그리고 `'` (다시 한번 더 얘기하지만 하나만 선택해서 사용하십시오!)을 사용하는 더 좋은 방법은 인터폴레이션이 필요없는 문자열만을 위해 사용하고 `` ` ``는 오직 인터폴레이션이 필요한 곳에서만 사용하는 방법이 있습니다.

The better approach is to use `"` or `'` (again, pick one and stick to it!) for strings *unless you need* interpolation; reserve `` ` `` only for strings that will include interpolated expressions.

문자열과 다르게 JS 프로그램은 종종 다른 불리언(boolean)과 숫자처럼 원시 리터럴 값에 포함된 값도 포함합니다.

Other than strings, JS programs often contain other primitive literal values such as booleans and numbers:

```js
while (false) {
    console.log(3.141592);
}
```

`while` 은 반복문을 표현하고 *while* 문의 조건이 참일 때 계속해서 내부 연산 작업을 반복하도록 작동합니다.

`while` represents a loop type, a way to repeat operations *while* its condition is true.

이러한 경우 `false(거짓)` 불리언 값을 조건문의 조건에 사용하였기에 반복문 내부는 실행되지 않습니다(아무것도 출력되지 않습니다). 반복문 조건이 `true(참)`일 경우 영원토록 반복되기에 주의를 기울여야 됩니다!

In this case, the loop will never run (and nothing will be printed), because we used the `false` boolean value as the loop conditional. `true` would have resulted in a loop that keeps going forever, so be careful!

숫자 `3.141592`는 아시다시피 파이(PI)의 소수점 첫 6자리까지 나타난 유사값입니다. 값을 직접 집어넣는 대신 일반적으로 이미 정의되어있는 `Math.PI` 값을 이용할 것입니다. 숫자들의 또다른 변형의 `bigint` (big-integer)란 원시값으로 임의의 큰 숫자를 저장하기위해 사용됩니다.

The number `3.141592` is, as you may know, an approximation of mathematical PI to the first six digits. Rather than embed such a value, however, you would typically use the predefined `Math.PI` value for that purpose. Another variation on numbers is the `bigint` (big-integer) primitive type, which is used for storing arbitrarily large numbers.

숫자들은 종종 프로그램에서 반복문과 같이 단계를 센다던가 숫자 위치의 정보(배열의 인덱스라고도 부르는)에 접근하는데 사용됩니다. 배열과 객체에 관해 예제와 함께 조금 다뤄보도록 하겠습니다. `names`라고 불리우는 배열이 있을 때 두번째 자리에 있는 요소(element)에 접근하기 위해서는 아래와 같이 할 수 있습니다.

Numbers are most often used in programs for counting steps, such as loop iterations, and accessing information in numeric positions (i.e., an array index). We'll cover arrays/objects in a little bit, but as an example, if there was an array called `names`, we could access the element in its second position like this:

```js
console.log(`My name is ${ names[1] }.`);
// My name is Kyle.
```

두 번째 위치에 있는 요소에 접근하위해 `2` 대신 `1`을 사용하였는데 이는 JS 배열은 0에서부터 시작하기 때문입니다 (`0`이 첫 번째 자리입니다).

We used `1` for the element in the second position, instead of `2`, because like in most programming languages, JS array indices are 0-based (`0` is the first position).

문자열, 숫자, 그리고 불리언 외에 JS 프로그램에 있는 두 *원시*값은 `널(null)` 그리고 `정의되지 않은(undefined)`입니다. 이 두 가지 원시값은 (역사적으로도 현대로 봐도) 다르지만 *빈 값* (혹은 값의 부재)를 나타내는 용도로 대부분 사용됩니다.

In addition to strings, numbers, and booleans, two other *primitive* values in JS programs are `null` and `undefined`. While there are differences between them (some historic and some contemporary), for the most part both values serve the purpose of indicating *emptiness* (or absence) of a value.

많은 개발자들은 이러한 형식으로 일관되게 마치 두 값은 구분이 불가능한 값처럼 이 두 값을 대하길 선호합니다. 주의를 기울이면 가능한 편이지만, `널(null)`이 조금 더 짧기에 사용하는데 더 용의해 보이지만 `정의되지 않은(undefined)`만이 오직 비어있는 값으로서 사용하는 것이 가장 안전하고 최선의 방법입니다!

Many developers prefer to treat them both consistently in this fashion, which is to say that the values are assumed to be indistinguishable. If care is taken, this is often possible. However, it's safest and best to use only `undefined` as the single empty value, even though `null` seems attractive in that it's shorter to type!

```js
while (value != undefined) {
    console.log("Still got something!");
}
```

마지막 원시값은 숨겨지고 추측이 불가능한 값으로써 특수한 목적을 가진 심볼(symbol)입니다. 심볼은 대게 객체에 특수 키를 위해 사용됩니다.

The final primitive value to be aware of is a symbol, which is a special-purpose value that behaves as a hidden unguessable value. Symbols are almost exclusively used as special keys on objects:

```js
hitchhikersGuide[ Symbol("meaning of life") ];
// 42
```

일반적인 JS 프로그램에서 심볼을 직접 사용할 일은 없을 것입니다. 심볼은 라이브러리나 프레임워크와 같은 하위 단계(low-level)의 코드에서 보통 사용됩니다.

You won't encounter direct usage of symbols very often in typical JS programs. They're mostly used in low-level code such as in libraries and frameworks.

### 배열과 객체

### Arrays And Objects

원시값 이외에 JS에 있는 또다른 타입은 객체 값입니다.

Besides primitives, the other value type in JS is an object value.

이미 언급드렸듯이 배열은 순서가 있고 숫자로 된 인덱스가 있는 데이터들로 구성된 객체의 특수한 타입입니다.

As mentioned earlier, arrays are a special type of object that's comprised of an ordered and numerically indexed list of data:

```js
var names = [ "Frank", "Kyle", "Peter", "Susan" ];

names.length;
// 4

names[0];
// Frank

names[1];
// Kyle
```

JS 배열은 원시값 혹은 객체(다른 배열 역시 포함해서)인 모든 타입의 값을 가지고 있을 수 있습니다. 챕터 3의 마지막에 향하며 볼 것이지만, 함수 역시도 배열이나 함수에 등록될 수 있는 값입니다.

JS arrays can hold any value type, either primitive or object (including other arrays). As we'll see toward the end of Chapter 3, even functions are values that can be held in arrays or objects.

| 노트: |
| :--- |
| 배열과 같은 함수는 객체의 특수한 (부분 집합으로도 알려진) 종류입니다. 함수에 관해서 조금 더 자세히 추후에 다로도록 하겠습니다. |

| NOTE: |
| :--- |
| Functions, like arrays, are a special kind (aka, sub-type) of object. We'll cover functions in more detail in a bit. |

객체는 조금 더 일반적입니다. 순서가 없으며 key를 통해 접근 가능한 아무 종류의 값들의 모음입니다. 다른말로, 숫자 (배열에서와 마찬가지로) 대신 문자열로 된 위치명을 가진 ("키(key)" 혹은 "프로퍼티(property)"라고도 알려진) 값을 이용해 요소에 접근합니다. 예를 들어,

Objects are more general: an unordered, keyed collection of any various values. In other words, you access the element by a string location name (aka "key" or "property") rather than by its numeric position (as with arrays). For example:

```js
var me = {
    first: "Kyle",
    last: "Simpson",
    age: 39,
    specialties: [ "JS", "Table Tennis" ]
};

console.log(`My name is ${ me.first }.`);
```

여기서 `me`는 객체를 가르키고 있고 `first`는 객체(값의 모음)에서 정보의 위치를 가르키는 이름입니다. 객체에서 객체의 프로퍼티/키를 이용해 정보에 접근할 수 있는 방법은 대괄호 `[]`를 다음과 같이 `me["first"]` 이용하는 방법입니다.

Here, `me` represents an object, and `first` represents the name of a location of information in that object (value collection). Another syntax option that accesses information in an object by its property/key uses the square-brackets `[ ]`, such as  `me["first"]`.

### Value Type Determination

For distinguishing values, the `typeof` operator tells you its built-in type, if primitive, or `"object"` otherwise:

```js
typeof 42;                  // "number"
typeof "abc";               // "string"
typeof true;                // "boolean"
typeof undefined;           // "undefined"
typeof null;                // "object" -- oops, bug!
typeof { "a": 1 };          // "object"
typeof [1,2,3];             // "object"
typeof function hello(){};  // "function"
```

| WARNING: |
| :--- |
| `typeof null` unfortunately returns `"object"` instead of the expected `"null"`. Also, `typeof` returns the specific `"function"` for functions, but not the expected `"array"` for arrays. |

Converting from one value type to another, such as from string to number, is referred to in JS as "coercion." We'll cover this in more detail later in this chapter.

Primitive values and object values behave differently when they're assigned or passed around. We'll cover these details in Appendix A, "Values vs References."

## Declaring and Using Variables

To be explicit about something that may not have been obvious in the previous section: in JS programs, values can either appear as literal values (as many of the preceding examples illustrate), or they can be held in variables; think of variables as just containers for values.

Variables have to be declared (created) to be used. There are various syntax forms that declare variables (aka, "identifiers"), and each form has different implied behaviors.

For example, consider the `var` statement:

```js
var myName = "Kyle";
var age;
```

The `var` keyword declares a variable to be used in that part of the program, and optionally allows an initial assignment of a value.

Another similar keyword is `let`:

```js
let myName = "Kyle";
let age;
```

The `let` keyword has some differences to `var`, with the most obvious being that `let` allows a more limited access to the variable than `var`. This is called "block scoping" as opposed to regular or function scoping.

Consider:

```js
var adult = true;

if (adult) {
    var myName = "Kyle";
    let age = 39;
    console.log("Shhh, this is a secret!");
}

console.log(myName);
// Kyle

console.log(age);
// Error!
```

The attempt to access `age` outside of the `if` statement results in an error, because `age` was block-scoped to the `if`, whereas `myName` was not.

Block-scoping is very useful for limiting how widespread variable declarations are in our programs, which helps prevent accidental overlap of their names.

But `var` is still useful in that it communicates "this variable will be seen by a wider scope (of the whole function)". Both declaration forms can be appropriate in any given part of a program, depending on the circumstances.

| NOTE: |
| :--- |
| It's very common to suggest that `var` should be avoided in favor of `let` (or `const`!), generally because of perceived confusion over how the scoping behavior of `var` has worked since the beginning of JS. I believe this to be overly restrictive advice and ultimately unhelpful. It's assuming you are unable to learn and use a feature properly in combination with other features. I believe you *can* and *should* learn any features available, and use them where appropriate! |

A third declaration form is `const`. It's like `let` but has an additional limitation that it must be given a value at the moment it's declared, and cannot be re-assigned a different value later.

Consider:

```js
const myBirthday = true;
let age = 39;

if (myBirthday) {
    age = age + 1;    // OK!
    myBirthday = false;  // Error!
}
```

The `myBirthday` constant is not allowed to be re-assigned.

`const` declared variables are not "unchangeable", they just cannot be re-assigned. It's ill-advised to use `const` with object values, because those values can still be changed even though the variable can't be re-assigned. This leads to potential confusion down the line, so I think it's wise to avoid situations like:

```js
const actors = [
    "Morgan Freeman", "Jennifer Aniston"
];

actors[2] = "Tom Cruise";   // OK :(
actors = [];                // Error!
```

The best semantic use of a `const` is when you have a simple primitive value that you want to give a useful name to, such as using `myBirthday` instead of `true`. This makes programs easier to read.

| TIP: |
| :--- |
| If you stick to using `const` only with primitive values, you avoid any confusion of re-assignment (not allowed) vs. mutation (allowed)! That's the safest and best way to use `const`. |

Besides `var` / `let` / `const`, there are other syntactic forms that declare identifiers (variables) in various scopes. For example:

```js
function hello(myName) {
    console.log(`Hello, ${ myName }.`);
}

hello("Kyle");
// Hello, Kyle.
```

The identifier `hello` is created in the outer scope, and it's also automatically associated so that it references the function. But the named parameter `myName` is created only inside the function, and thus is only accessible inside that function's scope. `hello` and `myName` generally behave as `var`-declared.

Another syntax that declares a variable is a `catch` clause:

```js
try {
    someError();
}
catch (err) {
    console.log(err);
}
```

The `err` is a block-scoped variable that exists only inside the `catch` clause, as if it had been declared with `let`.

## Functions

The word "function" has a variety of meanings in programming. For example, in the world of Functional Programming, "function" has a precise mathematical definition and implies a strict set of rules to abide by.

In JS, we should consider "function" to take the broader meaning of another related term: "procedure." A procedure is a collection of statements that can be invoked one or more times, may be provided some inputs, and may give back one or more outputs.

From the early days of JS, function definition looked like:

```js
function awesomeFunction(coolThings) {
    // ..
    return amazingStuff;
}
```

This is called a function declaration because it appears as a statement by itself, not as an expression in another statement. The association between the identifier `awesomeFunction` and the function value happens during the compile phase of the code, before that code is executed.

In contrast to a function declaration statement, a function expression can be defined and assigned like this:

```js
// let awesomeFunction = ..
// const awesomeFunction = ..
var awesomeFunction = function(coolThings) {
    // ..
    return amazingStuff;
};
```

This function is an expression that is assigned to the variable `awesomeFunction`. Different from the function declaration form, a function expression is not associated with its identifier until that statement during runtime.

It's extremely important to note that in JS, functions are values that can be assigned (as shown in this snippet) and passed around. In fact, JS functions are a special type of the object value type. Not all languages treat functions as values, but it's essential for a language to support the functional programming pattern, as JS does.

JS functions can receive parameter input:

```js
function greeting(myName) {
    console.log(`Hello, ${ myName }!`);
}

greeting("Kyle");   // Hello, Kyle!
```

In this snippet, `myName` is called a parameter, which acts as a local variable inside the function. Functions can be defined to receive any number of parameters, from none upward, as you see fit. Each parameter is assigned the argument value that you pass in that position (`"Kyle"`, here) of the call.

Functions also can return values using the `return` keyword:

```js
function greeting(myName) {
    return `Hello, ${ myName }!`;
}

var msg = greeting("Kyle");

console.log(msg);   // Hello, Kyle!
```

You can only `return` a single value, but if you have more values to return, you can wrap them up into a single object/array.

Since functions are values, they can be assigned as properties on objects:

```js
var whatToSay = {
    greeting() {
        console.log("Hello!");
    },
    question() {
        console.log("What's your name?");
    },
    answer() {
        console.log("My name is Kyle.");
    }
};

whatToSay.greeting();
// Hello!
```

In this snippet, references to three functions (`greeting()`, `question()`, and `answer()`) are included in the object held by `whatToSay`. Each function can be called by accessing the property to retrieve the function reference value. Compare this straightforward style of defining functions on an object to the more sophisticated `class` syntax discussed later in this chapter.

There are many varied forms that `function`s take in JS. We dig into these variations in Appendix A, "So Many Function Forms."

## Comparisons

Making decisions in programs requires comparing values to determine their identity and relationship to each other. JS has several mechanisms to enable value comparison, so let's take a closer look at them.

### Equal...ish

The most common comparison in JS programs asks the question, "Is this X value *the same as* that Y value?" What exactly does "the same as" really mean to JS, though?

For ergonomic and historical reasons, the meaning is more complicated than the obvious *exact identity* sort of matching. Sometimes an equality comparison intends *exact* matching, but other times the desired comparison is a bit broader, allowing *closely similar* or *interchangeable* matching. In other words, we must be aware of the nuanced differences between an **equality** comparison and an **equivalence** comparison.

If you've spent any time working with and reading about JS, you've certainly seen the so-called "triple-equals" `===` operator, also described as the "strict equality" operator. That seems rather straightforward, right? Surely, "strict" means strict, as in narrow and *exact*.

Not *exact*ly.

Yes, most values participating in an `===` equality comparison will fit with that *exact same* intuition. Consider some examples:

```js
3 === 3.0;              // true
"yes" === "yes";        // true
null === null;          // true
false === false;        // true

42 === "42";            // false
"hello" === "Hello";    // false
true === 1;             // false
0 === null;             // false
"" === null;            // false
null === undefined;     // false
```

| NOTE: |
| :--- |
| Another way `===`'s equality comparison is often described is, "checking both the value and the type". In several of the examples we've looked at so far, like `42 === "42"`, the *type* of both values (number, string, etc.) does seem to be the distinguishing factor. There's more to it than that, though. **All** value comparisons in JS consider the type of the values being compared, not *just* the `===` operator. Specifically, `===` disallows any sort of type conversion (aka, "coercion") in its comparison, where other JS comparisons *do* allow coercion. |

But the `===` operator does have some nuance to it, a fact many JS developers gloss over, to their detriment. The `===` operator is designed to *lie* in two cases of special values: `NaN` and `-0`. Consider:

```js
NaN === NaN;            // false
0 === -0;               // true
```

In the case of `NaN`, the `===` operator *lies* and says that an occurrence of `NaN` is not equal to another `NaN`. In the case of `-0` (yes, this is a real, distinct value you can use intentionally in your programs!), the `===` operator *lies* and says it's equal to the regular `0` value.

Since the *lying* about such comparisons can be bothersome, it's best to avoid using `===` for them. For `NaN` comparisons, use the `Number.isNaN(..)` utility, which does not *lie*. For `-0` comparison, use the `Object.is(..)` utility, which also does not *lie*. `Object.is(..)` can also be used for non-*lying* `NaN` checks, if you prefer. Humorously, you could think of `Object.is(..)` as the "quadruple-equals" `====`, the really-really-strict comparison!

There are deeper historical and technical reasons for these *lies*, but that doesn't change the fact that `===` is not actually *strictly exactly equal* comparison, in the *strictest* sense.

The story gets even more complicated when we consider comparisons of object values (non-primitives). Consider:

```js
[ 1, 2, 3 ] === [ 1, 2, 3 ];    // false
{ a: 42 } === { a: 42 }         // false
(x => x * 2) === (x => x * 2)   // false
```

What's going on here?

It may seem reasonable to assume that an equality check considers the *nature* or *contents* of the value; after all, `42 === 42` considers the actual `42` value and compares it. But when it comes to objects, a content-aware comparison is generally referred to as "structural equality."

JS does not define `===` as *structural equality* for object values. Instead, `===` uses *identity equality* for object values.

In JS, all object values are held by reference (see "Values vs References" in Appendix A), are assigned and passed by reference-copy, **and** to our current discussion, are compared by reference (identity) equality. Consider:

```js
var x = [ 1, 2, 3 ];

// assignment is by reference-copy, so
// y references the *same* array as x,
// not another copy of it.
var y = x;

y === x;              // true
y === [ 1, 2, 3 ];    // false
x === [ 1, 2, 3 ];    // false
```

In this snippet, `y === x` is true because both variables hold a reference to the same initial array. But the `=== [1,2,3]` comparisons both fail because `y` and `x`, respectively, are being compared to new *different* arrays `[1,2,3]`. The array structure and contents don't matter in this comparison, only the **reference identity**.

JS does not provide a mechanism for structural equality comparison of object values, only reference identity comparison. To do structural equality comparison, you'll need to implement the checks yourself.

But beware, it's more complicated than you'll assume. For example, how might you determine if two function references are "structurally equivalent"? Even stringifying to compare their source code text wouldn't take into account things like closure. JS doesn't provide structural equality comparison because it's almost intractable to handle all the corner cases!

### Coercive Comparisons

Coercion means a value of one type being converted to its respective representation in another type (to whatever extent possible). As we'll discuss in Chapter 4, coercion is a core pillar of the JS language, not some optional feature that can reasonably be avoided.

But where coercion meets comparison operators (like equality), confusion and frustration unfortunately crop up more often than not.

Few JS features draw more ire in the broader JS community than the `==` operator, generally referred to as the "loose equality" operator. The majority of all writing and public discourse on JS condemns this operator as poorly designed and dangerous/bug-ridden when used in JS programs. Even the creator of the language himself, Brendan Eich, has lamented how it was designed as a big mistake.

From what I can tell, most of this frustration comes from a pretty short list of confusing corner cases, but a deeper problem is the extremely widespread misconception that it performs its comparisons without considering the types of its compared values.

The `==` operator performs an equality comparison similarly to how the `===` performs it. In fact, both operators consider the type of the values being compared. And if the comparison is between the same value type, both `==` and `===` **do exactly the same thing, no difference whatsoever.**

If the value types being compared are different, the `==` differs from `===` in that it allows coercion before the comparison. In other words, they both want to compare values of like types, but `==` allows type conversions *first*, and once the types have been converted to be the same on both sides, then `==` does the same thing as `===`. Instead of "loose equality," the `==` operator should be described as "coercive equality."

Consider:

```js
42 == "42";             // true
1 == true;              // true
```

In both comparisons, the value types are different, so the `==` causes the non-number values (`"42"` and `true`) to be converted to numbers (`42` and `1`, respectively) before the comparisons are made.

Just being aware of this nature of `==`—that it prefers primitive numeric comparisons—helps you avoid most of the troublesome corner cases, such as staying away from a gotchas like `"" == 0` or `0 == false`.

You may be thinking, "Oh, well, I will just always avoid any coercive equality comparison (using `===` instead) to avoid those corner cases"! Eh, sorry, that's not quite as likely as you would hope.

There's a pretty good chance that you'll use relational comparison operators like `<`, `>` (and even `<=` and `>=`).

Just like `==`, these operators will perform as if they're "strict" if the types being relationally compared already match, but they'll allow coercion first (generally, to numbers) if the types differ.

Consider:

```js
var arr = [ "1", "10", "100", "1000" ];
for (let i = 0; i < arr.length && arr[i] < 500; i++) {
    // will run 3 times
}
```

The `i < arr.length` comparison is "safe" from coercion because `i` and `arr.length` are always numbers. The `arr[i] < 500` invokes coercion, though, because the `arr[i]` values are all strings. Those comparisons thus become `1 < 500`, `10 < 500`, `100 < 500`, and `1000 < 500`. Since that fourth one is false, the loop stops after its third iteration.

These relational operators typically use numeric comparisons, except in the case where **both** values being compared are already strings; in this case, they use alphabetical (dictionary-like) comparison of the strings:

```js
var x = "10";
var y = "9";

x < y;      // true, watch out!
```

There's no way to get these relational operators to avoid coercion, other than to just never use mismatched types in the comparisons. That's perhaps admirable as a goal, but it's still pretty likely you're going to run into a case where the types *may* differ.

The wiser approach is not to avoid coercive comparisons, but to embrace and learn their ins and outs.

Coercive comparisons crop up in other places in JS, such as conditionals (`if`, etc.), which we'll revisit in Appendix A, "Coercive Conditional Comparison."

## How We Organize in JS

Two major patterns for organizing code (data and behavior) are used broadly across the JS ecosystem: classes and modules. These patterns are not mutually exclusive; many programs can and do use both. Other programs will stick with just one pattern, or even neither!

In some respects, these patterns are very different. But interestingly, in other ways, they're just different sides of the same coin. Being proficient in JS requires understanding both patterns and where they are appropriate (and not!).

### Classes

The terms "object-oriented," "class-oriented," and "classes" are all very loaded full of detail and nuance; they're not universal in definition.

We will use a common and somewhat traditional definition here, the one most likely familiar to those with backgrounds in "object-oriented" languages like C++ and Java.

A class in a program is a definition of a "type" of custom data structure that includes both data and behaviors that operate on that data. Classes define how such a data structure works, but classes are not themselves concrete values. To get a concrete value that you can use in the program, a class must be *instantiated* (with the `new` keyword) one or more times.

Consider:

```js
class Page {
    constructor(text) {
        this.text = text;
    }

    print() {
        console.log(this.text);
    }
}

class Notebook {
    constructor() {
        this.pages = [];
    }

    addPage(text) {
        var page = new Page(text);
        this.pages.push(page);
    }

    print() {
        for (let page of this.pages) {
            page.print();
        }
    }
}

var mathNotes = new Notebook();
mathNotes.addPage("Arithmetic: + - * / ...");
mathNotes.addPage("Trigonometry: sin cos tan ...");

mathNotes.print();
// ..
```

In the `Page` class, the data is a string of text stored in a `this.text` member property. The behavior is `print()`, a method that dumps the text to the console.

For the `Notebook` class, the data is an array of `Page` instances. The behavior is `addPage(..)`, a method that instantiates new `Page` pages and adds them to the list, as well as `print()` (which prints out all the pages in the notebook).

The statement `mathNotes = new Notebook()` creates an instance of the `Notebook` class, and `page = new Page(text)` is where instances of the `Page` class are created.

Behavior (methods) can only be called on instances (not the classes themselves), such as `mathNotes.addPage(..)` and `page.print()`.

The `class` mechanism allows packaging data (`text` and `pages`) to be organized together with their behaviors (e.g., `addPage(..)` and `print()`). The same program could have been built without any `class` definitions, but it would likely have been much less organized, harder to read and reason about, and more susceptible to bugs and subpar maintenance.

#### Class Inheritance

Another aspect inherent to traditional "class-oriented" design, though a bit less commonly used in JS, is "inheritance" (and "polymorphism"). Consider:

```js
class Publication {
    constructor(title,author,pubDate) {
        this.title = title;
        this.author = author;
        this.pubDate = pubDate;
    }

    print() {
        console.log(`
            Title: ${ this.title }
            By: ${ this.author }
            ${ this.pubDate }
        `);
    }
}
```

This `Publication` class defines a set of common behavior that any publication might need.

Now let's consider more specific types of publication, like `Book` and `BlogPost`:

```js
class Book extends Publication {
    constructor(bookDetails) {
        super(
            bookDetails.title,
            bookDetails.author,
            bookDetails.publishedOn
        );
        this.publisher = bookDetails.publisher;
        this.ISBN = bookDetails.ISBN;
    }

    print() {
        super.print();
        console.log(`
            Publisher: ${ this.publisher }
            ISBN: ${ this.ISBN }
        `);
    }
}

class BlogPost extends Publication {
    constructor(title,author,pubDate,URL) {
        super(title,author,pubDate);
        this.URL = URL;
    }

    print() {
        super.print();
        console.log(this.URL);
    }
}
```

Both `Book` and `BlogPost` use the `extends` clause to *extend* the general definition of `Publication` to include additional behavior. The `super(..)` call in each constructor delegates to the parent `Publication` class's constructor for its initialization work, and then they do more specific things according to their respective publication type (aka, "sub-class" or "child class").

Now consider using these child classes:

```js
var YDKJS = new Book({
    title: "You Don't Know JS",
    author: "Kyle Simpson",
    publishedOn: "June 2014",
    publisher: "O'Reilly",
    ISBN: "123456-789"
});

YDKJS.print();
// Title: You Don't Know JS
// By: Kyle Simpson
// June 2014
// Publisher: O'Reilly
// ISBN: 123456-789

var forAgainstLet = new BlogPost(
    "For and against let",
    "Kyle Simpson",
    "October 27, 2014",
    "https://davidwalsh.name/for-and-against-let"
);

forAgainstLet.print();
// Title: For and against let
// By: Kyle Simpson
// October 27, 2014
// https://davidwalsh.name/for-and-against-let
```

Notice that both child class instances have a `print()` method, which was an override of the *inherited* `print()` method from the parent `Publication` class. Each of those overridden child class `print()` methods call `super.print()` to invoke the inherited version of the `print()` method.

The fact that both the inherited and overridden methods can have the same name and co-exist is called *polymorphism*.

Inheritance is a powerful tool for organizing data/behavior in separate logical units (classes), but allowing the child class to cooperate with the parent by accessing/using its behavior and data.

### Modules

The module pattern has essentially the same goal as the class pattern, which is to group data and behavior together into logical units. Also like classes, modules can "include" or "access" the data and behaviors of other modules, for cooperation sake.

But modules have some important differences from classes. Most notably, the syntax is entirely different.

#### Classic Modules

ES6 added a module syntax form to native JS syntax, which we'll look at in a moment. But from the early days of JS, modules was an important and common pattern that was leveraged in countless JS programs, even without a dedicated syntax.

The key hallmarks of a *classic module* are an outer function (that runs at least once), which returns an "instance" of the module with one or more functions exposed that can operate on the module instance's internal (hidden) data.

Because a module of this form is *just a function*, and calling it produces an "instance" of the module, another description for these functions is "module factories".

Consider the classic module form of the earlier `Publication`, `Book`, and `BlogPost` classes:

```js
function Publication(title,author,pubDate) {
    var publicAPI = {
        print() {
            console.log(`
                Title: ${ title }
                By: ${ author }
                ${ pubDate }
            `);
        }
    };

    return publicAPI;
}

function Book(bookDetails) {
    var pub = Publication(
        bookDetails.title,
        bookDetails.author,
        bookDetails.publishedOn
    );

    var publicAPI = {
        print() {
            pub.print();
            console.log(`
                Publisher: ${ bookDetails.publisher }
                ISBN: ${ bookDetails.ISBN }
            `);
        }
    };

    return publicAPI;
}

function BlogPost(title,author,pubDate,URL) {
    var pub = Publication(title,author,pubDate);

    var publicAPI = {
        print() {
            pub.print();
            console.log(URL);
        }
    };

    return publicAPI;
}
```

Comparing these forms to the `class` forms, there are more similarities than differences.

The `class` form stores methods and data on an object instance, which must be accessed with the `this.` prefix. With modules, the methods and data are accessed as identifier variables in scope, without any `this.` prefix.

With `class`, the "API" of an instance is implicit in the class definition—also, all data and methods are public. With the module factory function, you explicitly create and return an object with any publicly exposed methods, and any data or other unreferenced methods remain private inside the factory function.

There are other variations to this factory function form that are quite common across JS, even in 2020; you may run across these forms in different JS programs: AMD (Asynchronous Module Definition), UMD (Universal Module Definition), and CommonJS (classic Node.js-style modules). The variations are minor (not quite compatible). However, all of these forms rely on the same basic principles.

Consider also the usage (aka, "instantiation") of these module factory functions:

```js
var YDKJS = Book({
    title: "You Don't Know JS",
    author: "Kyle Simpson",
    publishedOn: "June 2014",
    publisher: "O'Reilly",
    ISBN: "123456-789"
});

YDKJS.print();
// Title: You Don't Know JS
// By: Kyle Simpson
// June 2014
// Publisher: O'Reilly
// ISBN: 123456-789

var forAgainstLet = BlogPost(
    "For and against let",
    "Kyle Simpson",
    "October 27, 2014",
    "https://davidwalsh.name/for-and-against-let"
);

forAgainstLet.print();
// Title: For and against let
// By: Kyle Simpson
// October 27, 2014
// https://davidwalsh.name/for-and-against-let
```

The only observable difference here is the lack of using `new`, calling the module factories as normal functions.

#### ES Modules

ES modules (ESM), introduced to the JS language in ES6, are meant to serve much the same spirit and purpose as the existing *classic modules* just described, especially taking into account important variations and use cases from AMD, UMD, and CommonJS.

The implementation approach does, however, differ significantly.

First, there's no wrapping function to *define* a module. The wrapping context is a file. ESMs are always file-based; one file, one module.

Second, you don't interact with a module's "API" explicitly, but rather use the `export` keyword to add a variable or method to its public API definition. If something is defined in a module but not `export`ed, then it stays hidden (just as with *classic modules*).

Third, and maybe most noticeably different from previously discussed patterns, you don't "instantiate" an ES module, you just `import` it to use its single instance. ESMs are, in effect, "singletons," in that there's only one instance ever created, at first `import` in your program, and all other `import`s just receive a reference to that same single instance. If your module needs to support multiple instantiations, you have to provide a *classic module-style* factory function on your ESM definition for that purpose.

In our running example, we do assume multiple-instantiation, so these following snippets will mix both ESM and *classic modules*.

Consider the file `publication.js`:

```js
function printDetails(title,author,pubDate) {
    console.log(`
        Title: ${ title }
        By: ${ author }
        ${ pubDate }
    `);
}

export function create(title,author,pubDate) {
    var publicAPI = {
        print() {
            printDetails(title,author,pubDate);
        }
    };

    return publicAPI;
}
```

To import and use this module, from another ES module like `blogpost.js`:

```js
import { create as createPub } from "publication.js";

function printDetails(pub,URL) {
    pub.print();
    console.log(URL);
}

export function create(title,author,pubDate,URL) {
    var pub = createPub(title,author,pubDate);

    var publicAPI = {
        print() {
            printDetails(pub,URL);
        }
    };

    return publicAPI;
}
```

And finally, to use this module, we import into another ES module like `main.js`:

```js
import { create as newBlogPost } from "blogpost.js";

var forAgainstLet = newBlogPost(
    "For and against let",
    "Kyle Simpson",
    "October 27, 2014",
    "https://davidwalsh.name/for-and-against-let"
);

forAgainstLet.print();
// Title: For and against let
// By: Kyle Simpson
// October 27, 2014
// https://davidwalsh.name/for-and-against-let
```

| NOTE: |
| :--- |
| The `as newBlogPost` clause in the `import` statement is optional; if omitted, a top-level function just named `create(..)` would be imported. In this case, I'm renaming it for readability sake; its more generic factory name of `create(..)` becomes more semantically descriptive of its purpose as `newBlogPost(..)`. |

As shown, ES modules can use *classic modules* internally if they need to support multiple-instantiation. Alternatively, we could have exposed a `class` from our module instead of a `create(..)` factory function, with generally the same outcome. However, since you're already using ESM at that point, I'd recommend sticking with *classic modules* instead of `class`.

If your module only needs a single instance, you can skip the extra layers of complexity: `export` its public methods directly.

## The Rabbit Hole Deepens

As promised at the top of this chapter, we just glanced over a wide surface area of the main parts of the JS language. Your head may still be spinning, but that's entirely natural after such a firehose of information!

Even with just this "brief" survey of JS, we covered or hinted at a ton of details you should carefully consider and ensure you are comfortable with. I'm serious when I suggest: re-read this chapter, maybe several times.

In the next chapter, we're going to dig much deeper into some important aspects of how JS works at its core. But before you follow that rabbit hole deeper, make sure you've taken adequate time to fully digest what we've just covered here.
