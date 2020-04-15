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

여기서 `me`는 객체를 가르키고 있고 `first`는 객체(값의 모음)에서 정보의 위치를 가르키는 이름입니다. 객체에서 객체의 프로퍼티/키를 이용해 정보에 접근할 수 있는 방법은 대괄호 `[]`를 통해 다음과 같이 `me["first"]` 이용하는 방법입니다.

Here, `me` represents an object, and `first` represents the name of a location of information in that object (value collection). Another syntax option that accesses information in an object by its property/key uses the square-brackets `[ ]`, such as  `me["first"]`.

### 값 타입 측정

### Value Type Determination

값을 구분하기 위한 `typeof` 연산자는 값이 타입을 알려주는데 객체가 아닌 원시값일 경우 내장형(built-in) 타입을 알려줍니다.

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

| 경고: |
| :--- |
| `typeof null`은 불행하게도 `"null"` 대신 `"object"`를 반환해줍니다. 또한, `typeof`는 함수에 관해서는 `"function"`라고 반환하지만 배열에게는 예상과는 다르게 `"array"`가 아닌 `"object"`를 반환합니다.

| WARNING: |
| :--- |
| `typeof null` unfortunately returns `"object"` instead of the expected `"null"`. Also, `typeof` returns the specific `"function"` for functions, but not the expected `"array"` for arrays. |

문자열을 숫자로 바꾸는 것처럼 하나의 값의 타입을 다른 걸로 바꾸는 것은 JS에서는 "강제 변환(coercion)"이라고 부릅니다. 추후에 이 챕터에서 조금 더 자세히 다루도록 하겠습니다.

Converting from one value type to another, such as from string to number, is referred to in JS as "coercion." We'll cover this in more detail later in this chapter.

원시 값과 객체는 값이 부여되거나 전달될 때 서로 다르게 작동합니다. 이에 관해 자세한 사항은 부록 A, "값 vs 참조"에서 다루겠습니다.

Primitive values and object values behave differently when they're assigned or passed around. We'll cover these details in Appendix A, "Values vs References."

## 변수 선언과 사용

## Declaring and Using Variables

이전 섹션에서 자세히 설명하지 않았던 것을 명쾌하게 설명드리겠습니다. JS 프로그램에서 값(value)은 리터럴 값(많은 이전 예제들에서 사용된 것처럼)으로 존재하기도 하고 변수가 직접 들고 있을 수도 있습니다. 여기서 변수를 단순히 값을 담을 그릇으로 생각해주시기 바랍니다.

To be explicit about something that may not have been obvious in the previous section: in JS programs, values can either appear as literal values (as many of the preceding examples illustrate), or they can be held in variables; think of variables as just containers for values.

변수가 사용되기 위해서는 반드시 선언이 되어야만 합니다. 변수를 선언("식별자(identifiers)"라고도 알려진)하는 여러 종류의 방식이 있는데 각 방식은 그 행동양식이 다르게 적용됩니다.

Variables have to be declared (created) to be used. There are various syntax forms that declare variables (aka, "identifiers"), and each form has different implied behaviors.

예를 들어 `var` 문을 보면,

For example, consider the `var` statement:

```js
var myName = "Kyle";
var age;
```

`var` 키워드는 프로그램의 일부분으로 변수를 선언하기 위해 사용되고 선택적으로 변수에 초기값을 할당할 수도 있습니다.

The `var` keyword declares a variable to be used in that part of the program, and optionally allows an initial assignment of a value.

또다른 비슷한 키워드는 `let` 입니다.

Another similar keyword is `let`:

```js
let myName = "Kyle";
let age;
```

`let` 키워드는 `var`와는 조금 다른데 가장 큰 차이점은 `let`은 변수에대한 접근 권한을 `var`에 비해 제한하는데 있습니다. 일반 혹은 정규 스코핑 혹은 함수 스코핑과는 달리 "블락 스코핑(block scoping)"이라고 부릅니다.

The `let` keyword has some differences to `var`, with the most obvious being that `let` allows a more limited access to the variable than `var`. This is called "block scoping" as opposed to regular or function scoping.

예를 보면,

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

`age`는 `myName`과는 다르게 `if`문 내부 블락에 스코핑되어 있으므로(block-scoped) `if` 문 밖에서 `age`에 접근하려는 시도가 오류를 발생시켰습니다.

The attempt to access `age` outside of the `if` statement results in an error, because `age` was block-scoped to the `if`, whereas `myName` was not.

블락 스코핑은 여러분의 프로그램에서 퍼져있는 변수 선언으로 인해 변수 이름이 의도치 않게 중복되어 사용되는 걸 방지하는데 큰 도움이 됩니다.

Block-scoping is very useful for limiting how widespread variable declarations are in our programs, which helps prevent accidental overlap of their names.

하지만 `var` 역시 "조금 더 넓은 범위(함수 전체와 같이)에서 이 함수는 사용될 것입니다"라고 알려준다는 점에서 여전히 유용합니다. 두 변수 선언 방식 모두 프로그램에서 적절한 장소에서 그 환경에 맞게 사용할 수 있습니다.

But `var` is still useful in that it communicates "this variable will be seen by a wider scope (of the whole function)". Both declaration forms can be appropriate in any given part of a program, depending on the circumstances.

| 노트: |
| `let`(혹은 `const`)을 장점을 살리기 위해 `var`를 사용하는 것을 피하자는 의견은 아주 흔합니다. JS의 초창기부터 이어온 `var`의 스코핑 행동 양식이 일반적으로 혼동된다는 의식 때문입니다. 하지만 저는 이러한 의견이 지나치게 제한된 조언이며 궁극적으로는 전혀 도움이 되지 않는다고 생각합니다. 이는 여러분이 어떠한 기능을 잘 학습하지도 못하고 다른 기능들과 함께 잘 사용할 수 없다고 가정하기에 생겨난다고 생각합니다. 대신에 저는 여러분이 어떠한 사용가능한 기술이든 배울수 있으며 그 기능들을 적절한 곳에서 사용할 *가능성이 있고* *그래야만 한다고* 생각합니다!

| NOTE: |
| :--- |
| It's very common to suggest that `var` should be avoided in favor of `let` (or `const`!), generally because of perceived confusion over how the scoping behavior of `var` has worked since the beginning of JS. I believe this to be overly restrictive advice and ultimately unhelpful. It's assuming you are unable to learn and use a feature properly in combination with other features. I believe you *can* and *should* learn any features available, and use them where appropriate! |

세 번째 변수 선언 방식은 `const`입니다. 이것은 `let`과 비슷하지만 선언된 당시에 부여된 값만을 가지고 있으며 절대 다시 다른 값으로 재할당 할 수 없는 제약이 있습니다.

A third declaration form is `const`. It's like `let` but has an additional limitation that it must be given a value at the moment it's declared, and cannot be re-assigned a different value later.

예제를 살펴보겠습니다.

Consider:

```js
const myBirthday = true;
let age = 39;

if (myBirthday) {
    age = age + 1;    // OK!
    myBirthday = false;  // Error!
}
```

`myBirthday` 상수는 값을 재할당하는 게 불가능합니다.

The `myBirthday` constant is not allowed to be re-assigned.

`const`로 선언된 변수는 "불변하며" 절대 다른 값을 재할당 할 수 없습니다. `const`를 객체 값과사용하는 것은 문제의 소지가 있습니다. 변수에 다른 값을 재할당 할 수는 없지만 객체 내부에 있는 값들은 여전히 변경할 수 있기 때문입니다. 이로인해 아래의 예제와 같은 혼란을 초래할 수 있으므로 이러한 상황은 피하는 게 현명하다고 생각됩니다.

`const` declared variables are not "unchangeable", they just cannot be re-assigned. It's ill-advised to use `const` with object values, because those values can still be changed even though the variable can't be re-assigned. This leads to potential confusion down the line, so I think it's wise to avoid situations like:

```js
const actors = [
    "Morgan Freeman", "Jennifer Aniston"
];

actors[2] = "Tom Cruise";   // OK :(
actors = [];                // Error!
```

최선의 안정적인 `const` 사용방법은 `true` 대신 `myBirthday`를 사용하는 것처럼 단순 원시값에 유의미한 이름을 부여하는 경우입니다. 이로인해 프로그램은 한층 더 읽기 쉬어지게 됩니다.

The best semantic use of a `const` is when you have a simple primitive value that you want to give a useful name to, such as using `myBirthday` instead of `true`. This makes programs easier to read.

| 팁: |
| :--- |
| `const`를 원시값을 사용할 때만 쓴다면 재할당(re-assign(불가능합니다))과 뮤테이션(mutation(가능합니다))로 인해 오는 혼동을 피할 수 있습니다! 그리고 이는 곧 가장 안전하며 최고의 `const` 사용 방법입니다.

| TIP: |
| :--- |
| If you stick to using `const` only with primitive values, you avoid any confusion of re-assignment (not allowed) vs. mutation (allowed)! That's the safest and best way to use `const`. |

`var` / `let` / `const` 외에도 다양한 스코프에서 식별자를 선언하는 또 다른 방식들이 있습니다. 예를들어,

Besides `var` / `let` / `const`, there are other syntactic forms that declare identifiers (variables) in various scopes. For example:

```js
function hello(myName) {
    console.log(`Hello, ${ myName }.`);
}

hello("Kyle");
// Hello, Kyle.
```

식별자 `hello`는 바깥 스코프에서 생성됐고 함수를 참조하도록 자동으로 연결이 됩니다. 하지만 `myName`으로 이름이 붙여진 매개 변수(parameter)는 함수 내부에서만 생성됐고 그래서 함수 스코프 내부에서만 접근이 가능합니다. `hello` 그리고 `myName`은 일반적으로 `var`로 선언된 변수처럼 행동합니다.

The identifier `hello` is created in the outer scope, and it's also automatically associated so that it references the function. But the named parameter `myName` is created only inside the function, and thus is only accessible inside that function's scope. `hello` and `myName` generally behave as `var`-declared.

또다른 변수를 선언하는 방식은 `catch` 절에 있습니다.

Another syntax that declares a variable is a `catch` clause:

```js
try {
    someError();
}
catch (err) {
    console.log(err);
}
```

여기서 `err`은 블록 스코프 변수로 `catch` 절에서 마치 `let`을 통해 선언된 것처럼 존재합니다.

The `err` is a block-scoped variable that exists only inside the `catch` clause, as if it had been declared with `let`.

## 함수

## Functions

"함수"란 단어는 프로그램에서 다양한 의미를 가지고 있습니다. 예를 들어, 함수형 프로그램에서 "함수"는 정확한 수학적 정의를 가지고 있으며 엄격한 규칙의 집합을 가지고 있습니다.

The word "function" has a variety of meanings in programming. For example, in the world of Functional Programming, "function" has a precise mathematical definition and implies a strict set of rules to abide by.

JS에서 "함수"를 바라볼 때 "절차(procedure)"라는 또 다른 연관된 용어의 넓은 의미를 고려해야합니다. 절차는 여러번 불릴 수 있고 입력을 받을 수도 있기도 하고 하나 혹은 여러개의 결과를 다시 돌려줄 수도 있는 명령문의 집합입니다.

In JS, we should consider "function" to take the broader meaning of another related term: "procedure." A procedure is a collection of statements that can be invoked one or more times, may be provided some inputs, and may give back one or more outputs.

초기의 JS로 부터 함수의 정의는 아래와 같습니다.

From the early days of JS, function definition looked like:

```js
function awesomeFunction(coolThings) {
    // ..
    return amazingStuff;
}
```

이는 함수의 선언이라고도 불리는데 다른 명령문의 수식으로써가 아니라 명령문 그 자체로 나타나기 때문입니다. 이러한 연합체 식별자 `awesomeFunction`와 함수 값이 연계되는 건 코드가 실행되기 전 코드의 컴파일 단계에서 일어납니다.

This is called a function declaration because it appears as a statement by itself, not as an expression in another statement. The association between the identifier `awesomeFunction` and the function value happens during the compile phase of the code, before that code is executed.

반대로 함수의 선언문과 다르게 함수 표현식은 아래와 같이 정의되고 할당될 수 있습니다.

In contrast to a function declaration statement, a function expression can be defined and assigned like this:

```js
// let awesomeFunction = ..
// const awesomeFunction = ..
var awesomeFunction = function(coolThings) {
    // ..
    return amazingStuff;
};
```

이 함수는 변수 `awesomeFunction`에 할당되는 표현식입니다. 함수 선언문과 다르게 함수 표현식은 식발자와 해당 명령문이 실제 실행 단계(runtime)에 이르기 전까지는 서로 연결되지 않습니다.

This function is an expression that is assigned to the variable `awesomeFunction`. Different from the function declaration form, a function expression is not associated with its identifier until that statement during runtime.

이는 JS에서 굉장히 중요한 부분인데 함수는 값으로 다른 곳으로 전달될 수도 있고 (위 예제와 같이) 값으로 할당이 될 수도 있습니다. 실제로 JS 함수는 객체의 특별한 타입입니다. 모든 언어에서 함수를 값으로 다루진 않지만 JS 코드처럼 함수형 프로그래밍 패턴을 지원하는 언어에서는 필수적인 요소입니다.

It's extremely important to note that in JS, functions are values that can be assigned (as shown in this snippet) and passed around. In fact, JS functions are a special type of the object value type. Not all languages treat functions as values, but it's essential for a language to support the functional programming pattern, as JS does.

JS 함수는 매개 변수(parameter)를 입력값으로 받을 수도 있습니다.

JS functions can receive parameter input:

```js
function greeting(myName) {
    console.log(`Hello, ${ myName }!`);
}

greeting("Kyle");   // Hello, Kyle!
```

이 예제에서 `myName`는 매개 변수라고 불리우며 함수 내부에서 지역 변수로 활약하게 됩니다. 함수는 특별한 제약없이 함수의 역할에 맞도록 무한개의 매개 변수를 받을 수 있게 정의될 수 있습니다. 각 매개 변수는 호출될 때 전달받는 인수 값(argument)을 할당 받습니다 (위 에졔에서는 `"Kyle"`이 이에 해당합니다).

In this snippet, `myName` is called a parameter, which acts as a local variable inside the function. Functions can be defined to receive any number of parameters, from none upward, as you see fit. Each parameter is assigned the argument value that you pass in that position (`"Kyle"`, here) of the call.

또한 함수는 `return`이란 키워드를 통해 값을 반환할 수도 있습니다.

Functions also can return values using the `return` keyword:

```js
function greeting(myName) {
    return `Hello, ${ myName }!`;
}

var msg = greeting("Kyle");

console.log(msg);   // Hello, Kyle!
```

`return`으로 오직 한 개의 값만 반환할 수 있지만 여러개의 값을 반환하고 싶을 때는 그 값들을 하나의 객체나 배열로 감싸 반환할 수도 있습니다.

You can only `return` a single value, but if you have more values to return, you can wrap them up into a single object/array.

함수는 값이기도 하기에 객체의 프로퍼티에 할당할 수도 있습니다.

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

위 예제에서는 세 개의 함수(`greeting()`, `question()`, `answer()`)가 `whatToSay` 변수에 의해 객체안에 포함되어 있습니다. 각 함수는 객체의 프로퍼티에 접근해 함수 참조값을 가져옴으로써 호출될 수 있습니다. 함수를 객체 안에 선언하는 직관적인 방법과 조금 더 복잡한 `class` 문법에 정의하는 방법은 추후 이 챕터에서 다루도록 하겠습니다.

In this snippet, references to three functions (`greeting()`, `question()`, and `answer()`) are included in the object held by `whatToSay`. Each function can be called by accessing the property to retrieve the function reference value. Compare this straightforward style of defining functions on an object to the more sophisticated `class` syntax discussed later in this chapter.

JS에서는 함수를 가져오는 여러가지 변형된 방법이 있습니다 이에 관해서는 부록 A "함수의 여러가지 형태"에서 좀 더 깊이 다루도록 하겠습니다.

There are many varied forms that `function`s take in JS. We dig into these variations in Appendix A, "So Many Function Forms."

## 비교

## Comparisons

프로그램에서 값을 어떠한 결정을 내릴 때 비교할 때에는 이들의 정체와 관계에 관해 밝혀내어 값을 비교하곤 합니다. JS에는 몇몇 값을 비교하는 방법이 있고 이에 관해 조금 더 살펴보도록 하겠습니다.

Making decisions in programs requires comparing values to determine their identity and relationship to each other. JS has several mechanisms to enable value comparison, so let's take a closer look at them.

### 같은...듯

### Equal...ish

JS 프로그램에서 대부분의 일반적인 비교는 질문을 하는 것과 같습니다. "이 X값은 Y값과 *같나요*?" 여기서 *같다*가 실제로 JS에서 어떤 의미를 가지고 있을까요?

The most common comparison in JS programs asks the question, "Is this X value *the same as* that Y value?" What exactly does "the same as" really mean to JS, though?

인체 공학적이고 역사적인 이유에 의해 그 의미는 명백하게 *정확한 동일성*과 같은 의미보다는 조금 더 복잡합니다. 때때로 동등 비교는 *정확한* 동일을 지향하기도 하지만 그에 반해 *거의 유사하다*거나 *서로 교환할 수 있다* 같은 조금 더 큰 의미의 비교를 원할 때도 있습니다. 다른 말로 **동등(equality)** 비교와 **등가(equivalance)** 비교의 미묘한 차이를 알아야만 한다는 뜻입니다.

For ergonomic and historical reasons, the meaning is more complicated than the obvious *exact identity* sort of matching. Sometimes an equality comparison intends *exact* matching, but other times the desired comparison is a bit broader, allowing *closely similar* or *interchangeable* matching. In other words, we must be aware of the nuanced differences between an **equality** comparison and an **equivalence** comparison.

JS에 관해 일하고 읽어볼 때 "삼중 등호(triple-equals)" `===` 연산자를 본 것은 물론이고 이 연산자가 "엄격한 동등" 연산자라고 설명되는 것을 본 적이 있을 것입니다. 이 설명이 조금 더 직관적이라고 생각될 것입니다. "엄격하다"는 말은 곧 한정되며 *정확하단* 의미를 내포하고 있습니다.

If you've spent any time working with and reading about JS, you've certainly seen the so-called "triple-equals" `===` operator, also described as the "strict equality" operator. That seems rather straightforward, right? Surely, "strict" means strict, as in narrow and *exact*.

딱 *정확하*진 않지만요.

Not *exact*ly.

`===` 동등 비교에 들어가는 대부분의 값들의 경우 *정확하게 같음*과 직관적으로 적합합니다. 아래의 예제를 살펴보도록 하겠습니다.

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

| 노트: |
| :--- |
| `===`의 동등 비교는 "두 값과 타입을 확인한다"라로 설명되기도 합니다. `42 === "42"`와 같은 위 예시의 몇몇 경우 두 값의 *타입*(숫자와 문자열 기타 등등)은 구분할 수 있을만한 요소로 보입니다. 하지만 여기에는 조금 더 자세히 살펴볼 사항이 있습니다. `===` 뿐만이 아니라 JS에 있는 **모든** 값 비교는 값의 타입 역시 고려하고 비교합니다. 특별히 `===` 연산자가 단지 특이하게도 값을 비교하는데 있어 타입 변환("강제 변환(coercion)"이라고 알려진)을 허용하지 않고 다른 JS 비교 연산자들은 이를 혀용하는 차이가 있을 뿐입니다. |

| NOTE: |
| :--- |
| Another way `===`'s equality comparison is often described is, "checking both the value and the type". In several of the examples we've looked at so far, like `42 === "42"`, the *type* of both values (number, string, etc.) does seem to be the distinguishing factor. There's more to it than that, though. **All** value comparisons in JS consider the type of the values being compared, not *just* the `===` operator. Specifically, `===` disallows any sort of type conversion (aka, "coercion") in its comparison, where other JS comparisons *do* allow coercion. |

하지만 `===` 연산자는 많은 JS 개발자들을 속이고 손해 보게하는 미묘한 차이를 가지고 있습니다. `===` 연산자는 특수 값인 `NaN`와 `-0`의 경우에 *거짓말*하도록 설계되어 있습니다.

But the `===` operator does have some nuance to it, a fact many JS developers gloss over, to their detriment. The `===` operator is designed to *lie* in two cases of special values: `NaN` and `-0`. Consider:

```js
NaN === NaN;            // false
0 === -0;               // true
```

`NaN`의 경우 `===` 연산자는 `NaN`는 또다른 `NaN`와는 다르다고 *거짓말합니다*. `-0`의 경우에는 (실제로 의도적으로 구분되는 값으로 사용할 수도 있습니다!) `===` 연산자는 일반적인 `0`값과 같다고 *거짓말합니다*.

In the case of `NaN`, the `===` operator *lies* and says that an occurrence of `NaN` is not equal to another `NaN`. In the case of `-0` (yes, this is a real, distinct value you can use intentionally in your programs!), the `===` operator *lies* and says it's equal to the regular `0` value.

이러한 비교는 성가시게 작용하기도 하기에 `===`은 이 값들을 위해서는 사용하지 않는 것이 최선책입니다. `NaN` 비교를 위해서는 *거짓말*을 하지 않는 `Number.isNaN(..)` 유틸리티를 사용하고 `-0`의 비교를 위해서는 역시나 *거짓말* 하지 않는 `Object.is(..)` 유틸리티를 사용하십시오. 물론 선호에 따라 `Object.is(..)`는 `NaN`를 위해서도 사용될 수 있습니다. 우습기도 하지만 `Object.is(..)`를 정말 정말 엄격한 비교를 하는 "사중 등호(quadruple-equals)" `====` 라고 생각할 수도 있습니다.

Since the *lying* about such comparisons can be bothersome, it's best to avoid using `===` for them. For `NaN` comparisons, use the `Number.isNaN(..)` utility, which does not *lie*. For `-0` comparison, use the `Object.is(..)` utility, which also does not *lie*. `Object.is(..)` can also be used for non-*lying* `NaN` checks, if you prefer. Humorously, you could think of `Object.is(..)` as the "quadruple-equals" `====`, the really-really-strict comparison!

이러한 *거짓말들*에는 조금 더 깊이있는 역사적이고 기술적인 이유가 있습니다만 `===`가 실제로는 *가장 엄격하게*라는 의미하는 *엄격하고 정확한 동등* 비교를 하지 않는다는 점은 여전히 변화가 없습니다.

There are deeper historical and technical reasons for these *lies*, but that doesn't change the fact that `===` is not actually *strictly exactly equal* comparison, in the *strictest* sense.

객체 값(원시값이 아닌)의 비교는 조금 더 복잡합니다.

The story gets even more complicated when we consider comparisons of object values (non-primitives). Consider:

```js
[ 1, 2, 3 ] === [ 1, 2, 3 ];    // false
{ a: 42 } === { a: 42 }         // false
(x => x * 2) === (x => x * 2)   // false
```

무슨 일이 일어난 것일까요?

What's going on here?

동등성 비교는 값의 *본질*과 *내용물*을 비교한다고 생각하는 게 조금 더 합리적이라고 생각될 수도 있습니다. `42 === 42`는 실제 `42` 값을 비교하는 것처럼 말입니다. 하지만 객체를 비교할 경우 내용 비교는 "구조적 동등성(structural equality)"를 일반적으로 말합니다.

It may seem reasonable to assume that an equality check considers the *nature* or *contents* of the value; after all, `42 === 42` considers the actual `42` value and compares it. But when it comes to objects, a content-aware comparison is generally referred to as "structural equality."

JS는 `===`를 객체 값들에 관해 *구조적 동등성*을 비교하도록 정의되어 있지 않습니다. 대신 객체 값들에 관해서는 `===`는 *정체성 일치(identity equality)*를 위해 사용됩니다.

JS does not define `===` as *structural equality* for object values. Instead, `===` uses *identity equality* for object values.

JS에서 모든 객체 값은 이것의 참조값(부록 A "값과 참조"를 참고해주세요)을 가지고 있습니다. 이 참조값은 복사되어 값에 할당하고 전달되기도 합니다. **그리고** 객체 값들은 참조 (정체성) 동일함을 비교하도록 되어 있습니다.

In JS, all object values are held by reference (see "Values vs References" in Appendix A), are assigned and passed by reference-copy, **and** to our current discussion, are compared by reference (identity) equality. Consider:

```js
var x = [ 1, 2, 3 ];

// 참조 복사를 통해 값이 할당되어,
// y는 x의 또다른 복사본이 아닌,
// x와 *동일한* 배열을 참조하게 됩니다.

// assignment is by reference-copy, so
// y references the *same* array as x,
// not another copy of it.
var y = x;

y === x;              // true
y === [ 1, 2, 3 ];    // false
x === [ 1, 2, 3 ];    // false
```

이 예제에서 처음에는 `x`와 `y` 두 변수 모두 하나의 동일한 배열을 참조하므로 `y === x`는 참이 되게 됩니다. 하지만 `=== [1,2,3]` 비교에서는 `x`와 `y` 각각 새로운 *다른* 배열 `[1,2,3]`과 비교를 하기에 모두 실패하게 됩니다. 객체 비교에 있어서 **참조 정체성**만이 중요하고 그 구조와 내용물은 중요하지 않습니다.

In this snippet, `y === x` is true because both variables hold a reference to the same initial array. But the `=== [1,2,3]` comparisons both fail because `y` and `x`, respectively, are being compared to new *different* arrays `[1,2,3]`. The array structure and contents don't matter in this comparison, only the **reference identity**.

JS는 객체 비교에 있어 참조 동일성 비교는 그 방법을 제공해주지만 구조적 동일성을 비교하는 방법은 제공해주지 않습니다. 구조 동일 비교를 하기 위해서는 직접 비교를 하는 방법밖에 없습니다.

JS does not provide a mechanism for structural equality comparison of object values, only reference identity comparison. To do structural equality comparison, you'll need to implement the checks yourself.

하지만 이는 생각보다 더 복잡하다는 점을 명심해주시기 바랍니다. 예를 들어, 두 함수의 참조가 "구조적으로 동일한지" 어떻게 비교할 수 있을까요? 두 원본 코드를 문자열 화를 비교한다 하더라도 이는 "클로져(closure)"와 같은 것들을 고려할 수는 없을 것입니다. 아주 다루기 힘든 모든 경우의 수를 모두 다루는 것은 일반적으로 아주 어렵기에 JS는 구조적 동일 비교는 제공하지 않습니다!

But beware, it's more complicated than you'll assume. For example, how might you determine if two function references are "structurally equivalent"? Even stringifying to compare their source code text wouldn't take into account things like closure. JS doesn't provide structural equality comparison because it's almost intractable to handle all the corner cases!

### 강제적인 비교

### Coercive Comparisons

강제 변환(coercion)은 하나의 값의 타입을 이에 대응되는 또다른 타입으로 변환 시키는 것을 말합니다. 챕터 4에서 다뤘듯이, 강제 변환은 합리적인 이유로 피할 수 있는 선택적인 특성이 아닌 JS의 핵심적인 요소입니다.

Coercion means a value of one type being converted to its respective representation in another type (to whatever extent possible). As we'll discuss in Chapter 4, coercion is a core pillar of the JS language, not some optional feature that can reasonably be avoided.

하지만 강제 변환이 비교 연산자를 만났을 때는 불행하게도 혼란과 절망이 보다 더 자주 발생합니다.

But where coercion meets comparison operators (like equality), confusion and frustration unfortunately crop up more often than not.

흔히 "느슨한 동등(loose equality)" 연산자라고 알려진 `==` 연산자는 JS 커뮤니티에서 많은 노여움을 사고 있고 이로인해 이 보다 더 많은 노여움을 사는 JS의 특징은 아주 적습니다. JS상에서 공개적인 의견 다수는 `==` 연산자가 JS 프로그램에서 사용될 때 형편없이 설계됐으며 위험하고 버그가 들끓는 공공 담론 비난합니다. 심지어 언어의 설계자인 Brendan Eich 마저도 이 연산자의 설계 방법에 큰 실수가 있었다고 한탄하기까지 했습니다.

Few JS features draw more ire in the broader JS community than the `==` operator, generally referred to as the "loose equality" operator. The majority of all writing and public discourse on JS condemns this operator as poorly designed and dangerous/bug-ridden when used in JS programs. Even the creator of the language himself, Brendan Eich, has lamented how it was designed as a big mistake.

제가 해줄 수 있는 이야기는 혼란스러운 아주 소수의 특이한 경우들로부터 이러한 절망이 야기했으며 더 심각한 문제는 이 비교 연산자가 값을 비교할 때 타입을 고려하지 않고 한다는 아주 넓게퍼진 오해에 있습니다.

From what I can tell, most of this frustration comes from a pretty short list of confusing corner cases, but a deeper problem is the extremely widespread misconception that it performs its comparisons without considering the types of its compared values.

`==` 연산자는 동등성 비교를 `===`가 수행하는 것과 유사하게 수행합니다. 실은 두 연산자 모두 값을 비교할 때 값의 타입을 고려하며 비교를 합니다. 그리고 비교하는데 있어서 값의 타입이 서로 같다면 `==`와 `===`는 **어떠한 차이도 없이 정확히 똑같이 합니다.**

The `==` operator performs an equality comparison similarly to how the `===` performs it. In fact, both operators consider the type of the values being compared. And if the comparison is between the same value type, both `==` and `===` **do exactly the same thing, no difference whatsoever.**

비교를 할 때 값의 타입이 다르다면 `==`는 비교 직전에 타입의 강제 변환을 할 수 있다는 점에서 `===`와 다릅니다. 다른말로 하자면 두 연산자 모두 값을 비교하지만 `==`는 타입 전환을 *우선* 수행하고 일단 타입이 동일하게 변환되면 `==`는 `===`와 동일하게 작동한다는 것입니다. 그러므로 `==` 연산자는 "느슨한 동등(loose equality)"이 아니라 "강제적인 동등(coercive equality)"라고 설명되야만 합니다.

If the value types being compared are different, the `==` differs from `===` in that it allows coercion before the comparison. In other words, they both want to compare values of like types, but `==` allows type conversions *first*, and once the types have been converted to be the same on both sides, then `==` does the same thing as `===`. Instead of "loose equality," the `==` operator should be described as "coercive equality."

Consider:

```js
42 == "42";             // true
1 == true;              // true
```

위 예시의 두 비교문에서 값의 타입은 다르지만 `==`는 숫자가 아닌 값들(`"42"`와 `true`)를 숫자(각각 `42` 그리고 `1`)로 비교를 하기 전에 변경시킵니다.

In both comparisons, the value types are different, so the `==` causes the non-number values (`"42"` and `true`) to be converted to numbers (`42` and `1`, respectively) before the comparisons are made.

단지 원시 숫자 비교를 선호하는 `==`의 특성을 알고 있다면 이러한 특이한 경우들을 피하는 데에 도움이 될 것입니다. 예를 들어 `"" == 0` 라던가 `0 == false`와 같은 상황을 피할 수 있죠.

Just being aware of this nature of `==`—that it prefers primitive numeric comparisons—helps you avoid most of the troublesome corner cases, such as staying away from a gotchas like `"" == 0` or `0 == false`.

아마도 여러분은 "이러한 특별한 경우를 피하기 위해 모든 강제 전환 비교(`===`을 사용하는 대신)를 사용하지 말아야겠네"라고 생각하실 수도 있습니다. 하지만 여러분의 희망처럼 일이 흘리가진 않을 것입니다.

You may be thinking, "Oh, well, I will just always avoid any coercive equality comparison (using `===` instead) to avoid those corner cases"! Eh, sorry, that's not quite as likely as you would hope.

`<`, `>` (그리고 `<=`, `>=`)와 같은 상대 비교 연산자를 사용하는 경우가 있을 것입니다.

There's a pretty good chance that you'll use relational comparison operators like `<`, `>` (and even `<=` and `>=`).

상대 비교 연산자들은 타입이 이미 동일할 경우 마치 "엄격한"한 비교 연산자인 것처럼 행동하겠지만 타입이 다를 경우네는 `==` 연산자처럼 강제 변환(일반적으로는 숫자로)을 먼저 수행하게 될 것입니다.

Just like `==`, these operators will perform as if they're "strict" if the types being relationally compared already match, but they'll allow coercion first (generally, to numbers) if the types differ.

Consider:

```js
var arr = [ "1", "10", "100", "1000" ];
for (let i = 0; i < arr.length && arr[i] < 500; i++) {
    // will run 3 times
}
```

`i < arr.length` 비교는 `i`와 `arr.length` 모두 숫자이기에 강제 변환으로부터 "안전"합니다. 하지만 모든 `arr[i]` 값이 문자열이기에 `arr[i] < 500`은 강제 변환이 발생하게 됩니다. 이러한 비교는 곧 `1 < 500`, `10 < 500`, `100 < 500`, `1000 < 500`으로 바귀게 되죠. 네번째 연산은 거짓이기에 세 번의 반복이후 더 이상의 순환을 멈추게 됩니다.

The `i < arr.length` comparison is "safe" from coercion because `i` and `arr.length` are always numbers. The `arr[i] < 500` invokes coercion, though, because the `arr[i]` values are all strings. Those comparisons thus become `1 < 500`, `10 < 500`, `100 < 500`, and `1000 < 500`. Since that fourth one is false, the loop stops after its third iteration.

이러한 비교 연산자는 **두 값** 모두 문자열인 경우를 제외하고는 일반적으로 숫자들을 비교할 때 사용됩니다. 두 값이 모두 문자열일 경우에는 문자열을 영어의 알파벳순으로 비교하게 됩니다.

These relational operators typically use numeric comparisons, except in the case where **both** values being compared are already strings; in this case, they use alphabetical (dictionary-like) comparison of the strings:

```js
var x = "10";
var y = "9";

x < y;      // true, watch out!
```

비교 연산자에서 타입이 같지 않을 때는 절대 사용하지 않는 방법외에는 강제 변환을 피할 수 있는 방법은 없습니다. 아마도 대단한 목표이지만, 타입이 *아마도* 다른 경우를 마주할 상황이 많이 있을 것입니다.

There's no way to get these relational operators to avoid coercion, other than to just never use mismatched types in the comparisons. That's perhaps admirable as a goal, but it's still pretty likely you're going to run into a case where the types *may* differ.

조금 더 현명한 접근법은 강제 비교를 피하는 게 아닌 이 연산자들의 전후사정을 포용하고 배우는 것일 겁니다.

The wiser approach is not to avoid coercive comparisons, but to embrace and learn their ins and outs.

JS에서 강제 비교는 조건문(`if` 등등)과 같은 곳에서도 발생하곤 하는데, 부록 A "강제 조건부 비교"에서 다시 다루도록 하겠습니다.

Coercive comparisons crop up in other places in JS, such as conditionals (`if`, etc.), which we'll revisit in Appendix A, "Coercive Conditional Comparison."

## JS에서 코드를 조직하는 방법

## How We Organize in JS

JS 환경에 넓리 사용되는 코드(데이터와 연산)를 조직하는 주요 두 가지 패턴은 클래스(classes)와 모듈(modules)입니다. 이 패턴은 배타적인 관계는 아니고 많은 프로그램은 둘 다 사용 가능하며 사용하고 있습니다. 다른 프로그램은 오직 한 가지 패턴에 집착하거나 그 어떠한 패턴도 사용하지 않기도 합니다!

Two major patterns for organizing code (data and behavior) are used broadly across the JS ecosystem: classes and modules. These patterns are not mutually exclusive; many programs can and do use both. Other programs will stick with just one pattern, or even neither!

몇몇 부분에서 이러한 패턴들은 아주 다릅니다. 하지만 흥미롭게도 이 패턴들은 동전의 양면과도 같습니다. JS에 능숙해지기 위해서는 두 패턴 모두에 관해 깊이있게 이해하고 어느 상황에 적절하고 그렇지 않은지 알아야만 합니다.

In some respects, these patterns are very different. But interestingly, in other ways, they're just different sides of the same coin. Being proficient in JS requires understanding both patterns and where they are appropriate (and not!).

### 클래스

### Classes

"객체 지향(object-oriented)", "클래스 지향(class-oriented)" "클래스(classes)"는 그 세부 사항과 미묘한 차이까지 매우 잘 포괄한 용어입니다. 그 정의에 따르면 이것들은 보편적이지는 않습니다.

The terms "object-oriented," "class-oriented," and "classes" are all very loaded full of detail and nuance; they're not universal in definition.

C++, Java와 같은 "객체 지향" 언어에 대한 배경 지식이 있는 분들에게 가장 친숙한 일반적이며 다소 전통적인 정의를 사용해보겠습니다.

We will use a common and somewhat traditional definition here, the one most likely familiar to those with backgrounds in "object-oriented" languages like C++ and Java.

프로그램에서 클래스란 데이터와 데이터 간의 연산들에 관해 정의한 행동 양식 모두를 포함한 자료 구조 "타입"입니다. 클래스 이러한 데이터 구조가 어떻게 작동을 할지 정의하지만 클래스 그 자체로 실체가 있는 값은 아닙니다. 프로그램에서 실체가 있는 값을 얻기 위해서는 클래스는 *인스턴스화(instantiated)* (`new`란 키워드를 통해) 되어야만 합니다.

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

`Page` 클래스에는 `this.text`라는 멤버 프로퍼티(member property) 내부에 문자열 형태의 데이터를 가지고 있습니다. 그리고 `print()`라는 이 문자열을 콘솔에 출력하는 메서드(method)를 가지고 있습니다.

In the `Page` class, the data is a string of text stored in a `this.text` member property. The behavior is `print()`, a method that dumps the text to the console.

`Notebook` 클래스에서는 `Page`이 인스턴스 배열을 데이터 가지고 있습니다. 또한 `addPage(..)`는 `Page`를 초기화하고 배열안에 추가하는 메서드입니다. 마찬가지로 `print()`는 노트북에 있는 모든 페이지를 출력하는 메서드입니다.

For the `Notebook` class, the data is an array of `Page` instances. The behavior is `addPage(..)`, a method that instantiates new `Page` pages and adds them to the list, as well as `print()` (which prints out all the pages in the notebook).

명령문 `mathNotes = new Notebook()`은 `Notebook` 클래스의 인스턴스를 생성하고 `page = new Page(text)`는 `Page` 클래스의 인스턴스가 생성됩니다.

The statement `mathNotes = new Notebook()` creates an instance of the `Notebook` class, and `page = new Page(text)` is where instances of the `Page` class are created.

메서드(methods)는 (클래스 스스로가 아닌) 인스턴스를 통해서만 불리울 수 있습니다. 예를들어 `mathNotes.addPage(..)`나 `page.print()`와 같이 말입니다.

Behavior (methods) can only be called on instances (not the classes themselves), such as `mathNotes.addPage(..)` and `page.print()`.

`class`를 이용하여 데이터(`text`와 `page`)를 묶을 수 있고 그들의 행동 양식(`addPage(..)`와 `print()`)을 함께 구성해 낼 수 있습니다. `class` 정의를 하나도 하지 않고 동일한 프로그램을 구성할 수도 있지만, 이렇게 될 경우 코드가 잘 구조화되어 있지 않게 되고 코드를 읽고 이유를 추론하는 것이 어려워지며 더 많은 버그와를 수준이하의 유지보수성을 가지게 될 수 있습니다.

The `class` mechanism allows packaging data (`text` and `pages`) to be organized together with their behaviors (e.g., `addPage(..)` and `print()`). The same program could have been built without any `class` definitions, but it would likely have been much less organized, harder to read and reason about, and more susceptible to bugs and subpar maintenance.

#### 클래스 상속

#### Class Inheritance

JS에 조금은 덜 사용되긴 하지만 전통적인 "클래스 지향" 설계에 내재된 또다른 특징은 "상속(inheritance)" (그리고 "다형성(polymorphism)")이 있습니다.

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

`Publication` 클래스는 출판에 필요한 일반적인 행동 양식을 정의하고 있습니다.

This `Publication` class defines a set of common behavior that any publication might need.

`Book`이나 `BlogPost`처럼 조금 더 특별한 타입의 출판에 관해 생각해 보도록 하겠습니다.

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

`Book`과 `BlogPost` 모두 `extends`라는 절을 사용해 `Publication`의 공통된 정의 그리고 추가적인 행동 양식을 포함해서 조금 더 확장하였습니다. 각 생성자(constructor)에서는 `super(..)`를 호출하여 부모 클래스 `Publication`의 생성자에 초기화 작업을 위임하였고, 그 이후 각각의 출판 타입("서브 클래스(sub-class)" 혹은 "자식 클래스(child class)"라도 알려진)에 맞는 조금 더 상세한 작업을 수행하였습니다.

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

두 자식 클래스의 인스턴스 부모 `Publication` 클래스로부터 상속되고 `print()` 자식 클래스에서 오버라이드된(overridden)된 `print()` 메서드를 가지고 있는 걸 신경 써서 봐주시기 바랍니다. 각 오버라이드된 클래스의 `print()` 메서드는 `super.print()`를 통해 부모로부터 상속받은 `print()` 메서드를 호출할 수 잇습니다.

Notice that both child class instances have a `print()` method, which was an override of the *inherited* `print()` method from the parent `Publication` class. Each of those overridden child class `print()` methods call `super.print()` to invoke the inherited version of the `print()` method.

상속받거나 오버라이드된 메서드 모두 동일한 이름을 가지고 동시에 존재할 수 있는 현상을 *다형성(polymorphism)*이라고 부릅니다.

The fact that both the inherited and overridden methods can have the same name and co-exist is called *polymorphism*.

상속은 데이터와 그 행동 양식을 분리된 논리 단위(클래스라고 하는)로 나누며 자식 클래스가 그 부모의 데이터와 행동 양식을 사용하고 접근하여 협력할 수 있게 하는 훌륭한 방법입니다.

Inheritance is a powerful tool for organizing data/behavior in separate logical units (classes), but allowing the child class to cooperate with the parent by accessing/using its behavior and data.

### 모듈

### Modules

모듈 패턴은 근본적으로 클래스 패턴과 같이 데이터와 그 행동 양식을 각각의 논리적인 단위로 모아 놓는다는 동일한 목표를 가지고 있습니다. 모듈은 협력을 목표로하고 다른 모듈을 "포함"할 때도 있고 "접근"할 때도 있습니다.

The module pattern has essentially the same goal as the class pattern, which is to group data and behavior together into logical units. Also like classes, modules can "include" or "access" the data and behaviors of other modules, for cooperation sake.

하지만 모듈은 클래스와 몇몇 중요한 차이점들이 있습니다. 가장 눈에 띄는 차이점은 뭄법이 전반적으로 다르다는 것입니다.

But modules have some important differences from classes. Most notably, the syntax is entirely different.

#### 전통적 모듈

#### Classic Modules

ES6가 JS 문법에 모듈 문법을 추가했었습니다. 그러나 초기의 JS에서부터 모듈은 특별한 문법이 없음에도 불구하고 수많은 JS 프로그램에서 이용되는 중요하고 일반적인 패턴이였습니다.

ES6 added a module syntax form to native JS syntax, which we'll look at in a moment. But from the early days of JS, modules was an important and common pattern that was leveraged in countless JS programs, even without a dedicated syntax.

*전통 모듈*의 중요한 특징은 내부 데이터와 이를 조작할 몇몇 접근 가능한 함수를 가진 모듈 "인스턴스"를 반환하는 외부 함수(최소 한 번은 실행되는)라는 것입니다.

The key hallmarks of a *classic module* are an outer function (that runs at least once), which returns an "instance" of the module with one or more functions exposed that can operate on the module instance's internal (hidden) data.

이러한 형식의 모듈은 *단지 함수*였고 이 함수를 호출하여 모듈의 *인스턴스*를 생성하였기에 이 함수를 "모듈 팩토리(module factories)"라고 설명하기도 했습니다.

Because a module of this form is *just a function*, and calling it produces an "instance" of the module, another description for these functions is "module factories".

한 번 `Publication`, `Book`, `BlogPost`를 전통 모듈에선 어떤 형식이였을지 살펴봅시다.

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

`class` 형식일 때와 비교해서 차이점보다 더 많은 유사함을 가지고 있습니다.

Comparing these forms to the `class` forms, there are more similarities than differences.

`class` 형식은 객체 인스턴스에 메서드와 데이터를 저장하며 `this.`라는 접두사를 통해 접근하기 메서드와 데이터에 접근했습니다. 모듈에서는 `this.` 접두사가 아닌 스코프에 있는 변수 식별자를 이용하여 메서드와 데이터에 접근하였습니다.

The `class` form stores methods and data on an object instance, which must be accessed with the `this.` prefix. With modules, the methods and data are accessed as identifier variables in scope, without any `this.` prefix.

`class`에서는 인스턴스의 모든 데이터와 메스드는 바깥에서 접근 가능한 것은 물론이고 인스턴스의 "API"가 클래스 정의에 내재되어 있습니다. 모듈 팩토리 함수의 경우는 노출된 함수 그리고 함수 내부에서만 유지될 데이터와 메서드를 가지고 있는 객체를 명백하게 만들고 반환해야 하게 만들어야 됩니다.

With `class`, the "API" of an instance is implicit in the class definition—also, all data and methods are public. With the module factory function, you explicitly create and return an object with any publicly exposed methods, and any data or other unreferenced methods remain private inside the factory function.

2020년에 이르기까지 JS 전반에 걸쳐 공통적인 형식의 팩토리 함수에는 여러가지 변형이 있습니다. AMD (Asynchronous Module Definition), UMD (Universal Module Definition), 그리고 CommonJS (classic Node.js-style modules)와 같은 각기 다른 변형을 구동시켰던 경험이 있을 수도 있습니다. 이러한 변경은 (상호 호환이 잘 안 되는) 사소한 일이긴 합니다. 하지만, 이러한 모든 형식들은 공통된 원리 원칙에 의존하고 있습니다.

There are other variations to this factory function form that are quite common across JS, even in 2020; you may run across these forms in different JS programs: AMD (Asynchronous Module Definition), UMD (Universal Module Definition), and CommonJS (classic Node.js-style modules). The variations are minor (not quite compatible). However, all of these forms rely on the same basic principles.

이러한 모듈 팩토리 함수의 사용 방법("인스턴스화(instantiation)" 라고도 알려진)에 관해 알아보겠습니다.

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

딱 한가지 눈에 띄는 차이점은 `new`를 사용하지 않고 모듈 팩토리를 일반 함수처럼 부르는 것입니다.

The only observable difference here is the lack of using `new`, calling the module factories as normal functions.

#### ES 모듈

#### ES Modules

ES 모듈(ES modules(ESM))은 ES6에서 JS에 처음으로 소개되었고 이미 존재하는 *전통 모듈*과 동일한 목표를 제공해줍니다. 특히, 중요한 변형이나 ADM, UMD, CommonJS와 같은 사용 관례를 고려하여 만들어졌습니다.

ES modules (ESM), introduced to the JS language in ES6, are meant to serve much the same spirit and purpose as the existing *classic modules* just described, especially taking into account important variations and use cases from AMD, UMD, and CommonJS.

하지만, 그 접근 방법은 상당히 달랐습니다.

The implementation approach does, however, differ significantly.

우선 모듈을 *정의*하기 위한 하나의 감싸진 함수가 없습니다. 대신, 하나의 파일에 이에 관해 감싸져 있습니다. ESM은 항상 파일을 기반으로 하고 있습니다. 하나의 파일은 하나의 모듈이죠.

First, there's no wrapping function to *define* a module. The wrapping context is a file. ESMs are always file-based; one file, one module.

두번째로 모듈의 "API"와 명시적으로 상호작용하지 않는 대신 `export`라는 키워드를 사용하여 변수나 함수를 공공 API에 노출시켜줍니다. 모듈 내에 `export` 없이 정의된 것들은 (*전통 모듈*에서도 그러했듯이) 감춰진 상태로 머무르게 됩니다.

Second, you don't interact with a module's "API" explicitly, but rather use the `export` keyword to add a variable or method to its public API definition. If something is defined in a module but not `export`ed, then it stays hidden (just as with *classic modules*).

세번째로 아마도 이전에 얘기했던 패턴과 가장 눈에 띄는 차이점은 ES 모듈을 "인스턴스화(instantiate)" 하지 않는 다는 것입니다. 대신 `import`를 사용하여 하나의 인스턴스를 사용할 수 있습니다. 실은, ESM는 프로그램에서 `import`를 처음으로 부를 때 하나의 인스턴스만 생성되고 그 이외에의 모든 `import`에서는 이미 만들어진 인스턴스의 참조값만 가져오도록 되어있는 "싱글턴(singletons)" 패턴입니다. 만약 모듈이 여러개의 인스턴스를 필요로 한다면 *전통 모듈 형태(classic module-style)*의 팩토리 함수를 ESM에 그 용도에 맞게 정의하고 제공해줘야 될 것입니다.

Third, and maybe most noticeably different from previously discussed patterns, you don't "instantiate" an ES module, you just `import` it to use its single instance. ESMs are, in effect, "singletons," in that there's only one instance ever created, at first `import` in your program, and all other `import`s just receive a reference to that same single instance. If your module needs to support multiple instantiations, you have to provide a *classic module-style* factory function on your ESM definition for that purpose.

ESM과 *전통 모듈*을 석어 사용하는 아래 예제를 통해 여러개의 인스턴스에 관해 알 수 있을 것입니다.

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

이 모듈을 다른 ES 모듈(`blogpost.js`)에서 가져와 사용하는 방법은 아래와 같습니다.

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

마지막으로 또다른 ES 모듈 `main.js`에서 위 모듈을 가져와 사용하는 방법입니다.

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

| 노트: |
| :--- |
| `import` 문에 있는 `as newBlogPost` 절은 선택적으로 사용할 수 있습니다. 만약 해당 절이 없을 경우에는 단지 `create(..)`라는 이름으로 불릴 것입니다. 이 경우 가독성을 향상시키기 위한 목적으로 이름을 다시 지은 것입니다. `create(..)`의 일반적인 팩토리 이름이 그 용도에 맞게 조금 더 상세한 이름인 `newBlogPost(..)` 갖게 됐습니다. |

| NOTE: |
| :--- |
| The `as newBlogPost` clause in the `import` statement is optional; if omitted, a top-level function just named `create(..)` would be imported. In this case, I'm renaming it for readability sake; its more generic factory name of `create(..)` becomes more semantically descriptive of its purpose as `newBlogPost(..)`. |

보시는 바와 같이 ES 모듈은 여러개의 인스턴스를 지원해야 할 필요가 있을 경우 *전통 모듈*을 내부적으로 사용할 수도 있습니다. 동일한 결과를 만드는 또 다른 방법으로는 `create(..)`라는 팩토리 함수가 아닌 `클래스(class)`를 노출시킬 수도 있습니다. 하지만 이 시점에 ESM을 이미 사용하고 있으므로 *전통 모듈*을 `클래스(class)` 대신 사용하는 것을 추천드립니다.

As shown, ES modules can use *classic modules* internally if they need to support multiple-instantiation. Alternatively, we could have exposed a `class` from our module instead of a `create(..)` factory function, with generally the same outcome. However, since you're already using ESM at that point, I'd recommend sticking with *classic modules* instead of `class`.

오직 한개의 인스턴스만을 필요로 한다면 `export`를 이용해 공용 함수들을 직접 내보냄으로써 복잡한 추가 과정을 건너 뛸 수 있습니다.

If your module only needs a single instance, you can skip the extra layers of complexity: `export` its public methods directly.

## 토끼굴 깊이 파고들기

## The Rabbit Hole Deepens

이 챕터의 상단에서 약속했듯이 JS 언어의 전반적인 주요 사항들에 관해 광범위한 표면들을 훑어보았습니다. 여전히 여러분의 머리속에 맴돌고 있겠지만 이는 전적으로 자연스러운 일입니다!

As promised at the top of this chapter, we just glanced over a wide surface area of the main parts of the JS language. Your head may still be spinning, but that's entirely natural after such a firehose of information!

단지 JS에 관한 "짧게" 살펴보았을 뿐이지만 이미 조심 스럽게 살펴보고 친숙한지 확실히 해야만 할 수많은 세부 내용들의 전반에 관해 다루었고 자그마한 암시들 역시 알게되었습니다. 진지하게 저는 이 챕터를 몇 번이고 다시 읽어보길 제안해드립니다.

Even with just this "brief" survey of JS, we covered or hinted at a ton of details you should carefully consider and ensure you are comfortable with. I'm serious when I suggest: re-read this chapter, maybe several times.

다음 챕터에서는 JS가 그 중심부에서 어떻게 작동하는지 몇몇 중요한 면모에 관해 조금 더 깊이 파고들 예정입니다. 더 깊은 도끼 굴에 따라들어오기 전에 우리가 다루었던 것들을 충분히 소화할 시간을 가지시길 바랍니다.

In the next chapter, we're going to dig much deeper into some important aspects of how JS works at its core. But before you follow that rabbit hole deeper, make sure you've taken adequate time to fully digest what we've just covered here.
