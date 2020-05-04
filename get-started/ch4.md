# You Don't Know JS Yet: Get Started - 2nd Edition
# 챕터 4: 큰 그림
# Chapter 4: The Bigger Picture

이 책은 여러분이 JS를 *시작하기*에 알아야만 하는 지식들에 관해 설명하고 있습니다. 이 책은 JS를 처음으로 접하는 독자들이 실수할 수도 있는 것들을 방지하것을 목표로 삼고 있습니다. 또한 JS에 대해 더 자세히 알고 싶어하는 호기심을 불러일으킬 수 있을만큼 충분한 세세한 내용들을 전달하길 바랍니다.

This book surveys what you need to be aware of as you *get started* with JS. The goal is to fill in gaps that readers newer to JS might have tripped over in their early encounters with the language. I also hope that we've hinted at enough deeper detail throughout to pique your curiosity to want to dig more into the language.

이 시리즈의 나머지 책들에서는 이전 챕터들에서 가볍게 다룬 것보다 더 세부적인 JS에 관한 것들을 전부 알아볼 예정입니다.

The rest of the books in this series are where we will unpack all of the rest of the language, in far greater detail than we could have done in a few brief chapters here.

시간을 충분히 들여 곱씹어 보는 것을 명심하세요. 다음 책으로 급하게 넘어가며 모든 책을 편의상 훑어보는 것보다 다시 이전으로 돌아가 충분한 시간을 들여가며 보는 것이 훨씬 낫습니다. 여러분의 현재 프로젝트 코드를 살펴보고 이 책에서 다루었던 내용들과 한 번 비교해보시기 바랍니다.

Remember to take your time, though. Rather than rushing onto the next book in an attempt to churn through all the books expediently, spend some time going back over the material in this book. Spend some more time looking through code in your current projects, and comparing what you see to what's been discussed so far.

준비가 되었다면 이 마지막 챕터를 통해 JS 언어 조직을 세 개의 큰 기둥으로 나눌 수 있을 것입니다. 그리고 이를 통해 이 책의 나머지 시리즈에서 무엇을 다룰지 어떻게 나아가야 할 지 간단한 로드맵을 살펴보실 수 있을 것입니다. 부록 역시, 특히나 부록 B를, 그냥 넘어가지 말아주세요. "연습하고, 연습하고, 또 연습하십시오!".

When you're ready, this final chapter divides the organization of the JS language into three main pillars, then offers a brief roadmap of what to expect from the rest of the book series, and how I suggest you proceed. Also, don't skip the appendices, especially Appendix B, "Practice, Practice, Practice!".

## 기둥 1: 스코프와 클로져

## Pillar 1: Scope and Closure

스코프(함수와 블록으로 된)에서 변수의 구조는 어느 언어에서나 있는 가장 근본적인 특징 중 하나입니다. 심지어는 그 어떠한 특성도 프로그램에 있어 더 큰 영향을 미치지 않을 것입니다.

The organization of variables into units of scope (functions, blocks) is one of the most foundational characteristics of any language; perhaps no other characteristic has a greater impact on how programs behave.

스코프는 하나의 양동이와 같고 변수는 그 안에 있는 구슬과 같습니다. 언어에 있어 스코프 모델은 일종의 규칙과도 같습니다. 이 규칙은 여러분이 구슬의 색깔과 매칭되는 색을 가진 양동이로 들어갈지 결정해줍니다.

Scopes are like buckets, and variables are like marbles you put into those buckets. The scope model of a language is like the rules that help you determine which color marbles go in which matching-color buckets.

스코프는 서로 내부에 중첩될 수 있으며, 어떠한 절이나 구문에 접근 가능한 반면, 해당 스코프 혹은 그 보다 상위/외부에 있는 스코프에 있는 변수에만 접근이 가능합니다. 하위/내부 스코프에 있는 변수들은 숨겨져 있으며 접근이 불가능합니다.

Scopes nest inside each other, and for any given expression or statement, only variables at that level of scope nesting, or in higher/outer scopes, are accessible; variables from lower/inner scopes are hidden and inaccessible.

대부분의 언어에서 스코프는 이렇게 작동하며 이를 곧 렉시컬 스코프<sup>lexical scope</sup>이라고 부릅니다. 프로그램이 파싱(컴파일)되는 중간에 스코프 단위의 경계선과 그 속에서 변수가 어떻게 조직될지 결정됩니다. 다른 말로, 저자가 결정한다고 얘기할 수 있는데 이 말인 즉슨, 함수와 스코프의 위치가 프로그램에서 스코프 어떻게 구조화될지 결정된다는 얘기입니다.

This is how scopes behave in most languages, which is called lexical scope. The scope unit boundaries, and how variables are organized in them, is determined at the time the program is parsed (compiled). In other words, it's an author-time decision: where you locate a function/scope in the program determines what the scope structure of that part of the program will be.

JS는 렉시컬 스코프이지만 많은 이들은 그렇지 않다고 주장하는데, 그 이유는 다른 렉시컬 스코프 모델의 언어에는 있지 않는 두 가지 특징 때문입니다.

JS is lexically scoped, though many claim it isn't, because of two particular characteristics of its model that are not present in other lexically scoped languages.

첫 번째 특징은 흔히 *호이스팅<sup>hoisting</sup>* 이라고 불립니다. 스코프 내부에서 선언된 모든 변수가 그 선언된 위치에 상관없이 스코프 시작점에서 선언된 것처럼 취급을 하는 것입니다. 또 다른 특징은 `var`로 선언된 변수는 블락 내부에 선언되어 있을지라도 함수 스코프<sup>function scoped</sup>라는 것입니다.

The first is commonly called *hoisting*: when all variables declared anywhere in a scope are treated as if they're declared at the beginning of the scope. The other is that `var`-declared variables are function scoped, even if they appear inside a block.

JS가 렉시컬 스코프가 아니라고 주장을 뒷받침하기에는 호이스팅이나 `var`의 함수 스코프 모두 충분하지 않습니다. `let`과 `const` 선언은 "시간 제약이 있는 중립 지역<sup>Temporal Dead Zone</sup>" (TDZ)라고 불리는 특이한 오류가 있는데 이로 인해 변수들이 관찰할 순 있지만 사용은 불가능할 수 있습니다. TDZ는 이상하긴 하지만, 이 *역시* JS가 렉시컬 스코프가 아니라고 얘기하는에는 충분하진 않습니다. 이 모두가 모든 JS 개발자라면 습득하고 이해해야만하는 단순히 언어의 독특한 특징일 뿐입니다.

Neither hoisting nor function-scoped `var` are sufficient to back the claim that JS is not lexically scoped. `let`/`const` declarations have a peculiar error behavior called the "Temporal Dead Zone" (TDZ) which results in observable but unusable variables. Though TDZ can be strange to encounter, it's *also* not an invalidation of lexical scoping. All of these are just unique parts of the language that should be learned and understood by all JS developers.

클로져는 JS처럼 함수를 값으로 여기는 언어들에서 렉시컬 스코프로인해 자연스레 발생하는 결과와 같습니다. 외부 스코프에 있는 함수의 참조값을 변수에 집어넣을 때 그리고 다른 스코프에서 함수가 값으로 전달되거나 실행되어질 때, 이 함수에서는 함수 내 원본 스코프 변수들에 접근 권한을 계속해서 유지하게 되는데 이를 곧 클로져라 부릅니다.

Closure is a natural result of lexical scope when the language has functions as first-class values, as JS does. When a function makes reference to variables from an outer scope, and that function is passed around as a value and executed in other scopes, it maintains access to its original scope variables; this is closure.

프로그래밍 전반에 걸쳐 특히나 JS에서는 클로져를 통해 모듈과 같이 가장 중요한 프로그래밍 패턴들 중 다수를 사용할 수 있도록 만들어줍니다. JS에서 코드를 조직화하는데 있어 모듈은 우리가 얻을 수 *결실*과도 같은 것입니다.

Across all of programming, but especially in JS, closure drives many of the most important programming patterns, including modules. As I see it, modules are as *with the grain* as you can get, when it comes to code organization in JS.

스코프, 클로져 그리고 모듈이 어떻게 작동하는지 더 깊이있게 파고들기위해서는 두 번째 책 *스코프와 클로져<sup>Scope & Closures</sup>*를 읽어보시기 바랍니다.

To dig further into scope, closures, and how modules work, read Book 2, *Scope & Closures*.

## 기둥 2: 프로토타입

## Pillar 2: Prototypes

이 언어에서 두 번째 기둥은 프로토타입 시스템입니다. 이미 챕터 3("프로토타입")에서 상세히 살펴봤지만 프로토타입의 중요성에대해 단지 몇 마디만 더 하려고합니다.

The second pillar of the language is the prototypes system. We covered this topic in-depth in Chapter 3 ("Prototypes"), but I just want to make a few more comments about its importance.

JS는 객체의 구조를 먼저 클래스로 정의하지 않고도 직접적이고 명시적으로 만들 수 있는 몇 안되는 언어중 하나입니다.

JS is one of very few languages where you have the option to create objects directly and explicitly, without first defining their structure in a class.

수년간 사람들은 프로토타입 위에 클래스 디자인 패턴을 구현했는데 이를 "프로토타입형 상속<sup>prototypal inheritance</sup>"라고 부릅니다 (부록 A "프로토타입형 '클래스'"). 그 후, ES6에서 `class` 키워드의 출현으로 JS는 객체/클래스 형태의 프로그래밍으로 더더욱 지향하게 됩니다.

For many years, people implemented the class design pattern on top of prototypes—so-called "prototypal inheritance" (see Appendix A, "Prototypal 'Classes'")—and then with the advent of ES6's `class` keyword, the language doubled-down on its inclination toward OO/class-style programming.

하지만 저는 이러한 경향이 프로토타입 시스템이 가지고 있는 힘과 아름다움이 가리고 있다고 생각합니다. `this` 컨텍스트를 공유함으로 두 개의 객체가 상호간에 연결되어 있고 유동적으로 협동하는 (함수/메서드의 실행과정에서) 그 힘과 아름다움이 말입니다.

But I think that focus has obscured the beauty and power of the prototype system: the ability for two objects to simply connect with each other and cooperate dynamically (during function/method execution) through sharing a `this` context.

클래스는 단순히 이러한 능력을 기반으로 무언가를 만들 수 있는 하나의 패턴일뿐입니다. 전혀 다른 방향에서 또다른 접근법은 클래스에 관해서는 잊어버린채 객체를 단순히 객체로써 감싸버리고 이 객체들이 프로토타입 체인<sup>prototype chain</sup>을 통해 협동하도록 만드는 것입니다. 이러한 방법을 *행동 위임<sup>behavior delegation</sup>*이라고 부릅니다. 전 이러한 행동 위임이 프로그램 속에서 데이터와 그 작동 방식을 조직함으로써 클래스 상속보다 더 강력한 방법이라고 생각합니다.

Classes are just one pattern you can build on top of such power. But another approach, in a very different direction, is to simply embrace objects as objects, forget classes altogether, and let objects cooperate through the prototype chain. This is called *behavior delegation*. I think delegation is more powerful than class inheritance, as a means for organizing behavior and data in our programs.

하지만 클래스 상속이 대부분의 이러한 모든 관심을 받고있습니다. 그 중 나머지는 함수형 프로그래밍<sup>functional programming</sup> (FP)이 "반-클래스<sup>anti-class</sup>"를 지향하는 방법 중 일부로써 그 집중을 받고있죠. 행동 위임이 실행가능한 대안으로써 선택될 여지를 없애버리기 때문에 이러한 경향은 절 슬프게 만듭니다.

But class inheritance gets almost all the attention. And the rest goes to functional programming (FP), as the sort of "anti-class" way of designing programs. This saddens me, because it snuffs out any chance for exploration of delegation as a viable alternative.

세번째 시리즈 *객체와 클래스<sup>Objects & Classes</sup>*에서 충분한 시간을 들여 객체 위임이 저희가 알고 있는 것보다 훨씬 더 강한 힘을 가지고 있는지 알아볼 수 있길 바랍니다. 반-`클래스`<sup>anti-class<sup>를 지향하라는 얘기가 아니라 "클래스만이 객체를 사용할 유일한 방법이 아니다"라는 걸 더 많은 JS 개발자분들이 알아주셨으면 좋겠다는 얘기입니다.

I encourage you to spend plenty of time deep in Book 3, *Objects & Classes*, to see how object delegation holds far more potential than we've perhaps realized. This isn't an anti-`class` message, but it is intentionally a "classes aren't the only way to use objects" message that I want more JS developers to consider.

객체 위임이 클래스보다 더 JS에 더 많은 *결실*을 가져다 줄 거라고 생각합니다.

Object delegation is, I would argue, far more *with the grain* of JS, than classes (more on *grains* in a bit).

## 기둥 3: 타입과 강제 변환

## Pillar 3: Types and Coercion

JS의 세번째 기둥은 JS에서 가장 간과되는 본질중 하나입니다.

The third pillar of JS is by far the most overlooked part of JS's nature.

개발자의 대다수는 *타입<sup>types</sup>*이 프로그래밍 언어 특히나 JS에서 어떻게 작동하는지 큰 오해를 하고 있습니다. 광범위한 JS 커뮤니티의 관심사 물결은 *정적 타입<sup>static typing<sup>* 접근법에서 타입 인식 도구<sup>type-aware tooling</sup>인 타입스크립트<sup>TypeScript</sup>나 플로우<sup>Flow</sup>를 사용하는 것으로 옮겨가고 있습니다.

The vast majority of developers have strong misconceptions about how *types* work in programming languages, and especially how they work in JS. A tidal wave of interest in the broader JS community has begun to shift to "static typing" approaches, using type-aware tooling like TypeScript or Flow.

JS 개발자는 타입에 관해 더 많이 배워야 하고 JS가 타입 변환을 어떻게 하는지 배워야만 한다고 생각합니다. 물론 타입 인식 도구가 개발자들에게 도움을 주지만 처음부터 이에 관한 지식을 얻고 사용한다면 더 큰 도움이 될 거라고 생각됩니다.

I agree that JS developers should learn more about types, and should learn more about how JS manages type conversions. I also agree that type-aware tooling can help developers, assuming they have gained and used this knowledge in the first place!

저는 JS의 타입 매커니즘이 나쁘다고 결론 짓고 그로인해 언어 외부의 솔루션으로 JS의 타입을 다루는 게 불가피한 결론이라는 의견에 전적으로 반대합니다. 프로그램에서 현명하고 믿음직한 방법인 "정적 타입"을 굳이 따를 필요는 없습니다. 단지 여러 선택지 중 하나이며 만약 대중들과 다른 길을 가고자 한다면 JS를 통해서

But I don't agree at all that the inevitable conclusion of this is to decide JS's type mechanism is bad and that we need to cover up JS's types with solutions outside the language. We don't have to follow the "static typing" way to be smart and solid with types in our programs. There are other options, if you're just willing to go *against the grain* of the crowd, and *with the grain* of JS (again, more on that to come).

만약 값의 타입 그리고 타입 변환(강제 변환)을 제대로 사용하지 않고 있다면 JS 프로그램이 어떠한 유익한 일도 하지 못 한다는 점에서 다른 두 기둥보다 훨씬 더 중요 사항합니다.

Arguably, this pillar is more important than the other two, in the sense that no JS program will do anything useful if it doesn't properly leverage JS's value types, as well as the conversion (coercion) of values between types.

만약 타입스크립트/플로우를 좋아할지라도 여러분이 그 언어에서 값의 타입을 어떻게 다루는지 깊숙이 알고있지 않다면 그러한 도구와 코딩의 접근법의 대다수를 제대로 이해할 수 없을 것입니다.

Even if you love TypeScript/Flow, you are not going to get the most out of those tools or coding approaches if you aren't deeply familiar with how the language itself manages value types.

JS의 타입과 강제 변환에 관해 더 배우기 위해 네번째 시리즈 *타입과 문법<sup>Types & Grammar</sup>*를 확인해주시기 바랍니다. 하지만 단순히 `===`를 사용해야만 하고 나머지는 잊어도 된다는 말을 항상 듣곤했다는 변명으로 이 주제를 건너 뛰지 말아주세요.

To learn more about JS types and coercion, check out Book 4, *Types & Grammar*. But please don't skip over this topic just because you've always heard that we should use `===` and forget about the rest.

이 기둥을 배우지 않고는 여러분의 JS에 대한 근본적인 지식은 쉽게 흔들리고 불완전할 것입니다.

Without learning this pillar, your foundation in JS is shaky and incomplete at best.

## 결실

## With the Grain

독자 여러분이 JS를 배워나가며 그리고 이 시리즈의 나머지를 읽어가는 여정에 첨언을 드리자면 *결실*에 관해 반드시 알아주길 바랍니다. (이 챕터 이전에 여러번 발언했던 *결실*에 관해 회상해주시기 바랍니다)

I have some advice to share on continuing your learning journey with JS, and your path through the rest of this book series: be aware of the *grain* (recall various references to *grain* earlier in this chapter).

우선, 대부분의 사람들이 어떻게 JS에 접근하고 사용하는지 생각하게 되는게 그 첫 *결실*입니다. 이미 이 시리즈가 다양한 방면에서 그러한 *결실*에 반하고 있다는것을 아마도 알아차리셨을 것입니다. YDKJSY에서는 저는 JS의 인기있는 일부만이 아닌 전반적인 모든 내용을 충분히 설명해줄만큼 독자 여러분을 존중합니다. 전 여러분이 이러한 지식을 습득하기에 유능하며 충분히 가치가 있다고 생각합니다.

First, consider the *grain* (as in, wood) of how most people approach and use JS. You've probably already noticed that these books cut against that *grain* in many respects. In YDKJSY, I respect you the reader enough to explain all the parts of JS, not only some select popular parts. I believe you're both capable and deserving of that knowledge.

하지만 이것이 다른 많은 자료들로부터 얻을 수 있는 게 아닙니다. 여러분이 이 책의 지침을 잘 따르고 준수할수록 어떤 코드가 최선인지 더 숙고하고 분석하게 됨으로써 더욱더 뛰어난 개발자가 될 것입니다. 이것이 좋을 수도 혹은 나쁠 수도 있습니다. 대중으로부터 벗어나길 원한다면, 그들이 일하는 방식으로부터 벗어나야만 합니다!

But that is not what you'll find from a lot of other material out there. It also means that the more you follow and adhere to the guidance from these books—that you think carefully and analyze for yourself what's best in your code—the more you will stand out. That can be a good and bad thing. If you ever want to break out from the crowd, you're going to have to break from how the crowd does it!

하지만 저는 많은 분들이 면접에서 이 책의 몇가지 주제와 설명을 인용하였었고 면접관이 그들의 주장이 틀렸다고 얘기했던 것을 들었습니다. 게다가 소문에 따르면 그 결과 일자리 제의를 잃은 걸 들은 바 있습니다.

But I've also had many people tell me that they quoted some topic/explanation from these books during a job interview, and the interviewer told the candidate they were wrong; indeed, people have reportedly lost out on job offers as a result.

가능한 한 전 이 책이 JS에 관한 완전히 정확한 정보를 제공하도록 노력하겠습니다. 하지만 여러분이 프로그램에서 최고의 효율을 위해 어떻게 JS를 해석하고 사용할지에 관한 제 의견 또한 많이 제시하려고 합니다. 제 의견을 사실처럼 혹은 그 반대로 사실을 제 의견처럼 늘어놓진 않겠습니다. 그렇기에 항상 이 책에 어떤 부분이 사실인지 의견인지 인지해주시길 바랍니다.

As much as possible, I endeavor in these books to provide completely accurate information about JS, informed generally from the specification itself. But I also dose out quite a bit of my opinions on how you can interpret and use JS to the best benefit in your programs. I don't present opinion as fact, or vice versa. You'll always know which is which in these books.

JS에 관한 진실은 실제로 논재의 여지가 없습니다. 사양에 설명되어 있다던가 그렇지 않거나 둘 중 하나인거죠. 사양이 나와있는 내용이나 제가 전달하는 게 마음에 들지 않으시다면 TC39로 가져가십시오! 면접 중 면접관들이 여러분에게 틀렸다고 한다면
만약 면접을 한다던가 실제로 여러분이 틀렸다고 얘기를 한다면, 사양에서 찾아볼 수 있는지 질문하십시오. 면접관이 다시 고려하지 않는다면 어찌됐든 여러분은 그곳에서 일하고 싶지 않으실겁니다.

Facts about JS are not really up for debate. Either the specification says something, or it doesn't. If you don't like what the specification says, or my relaying of it, take that up with TC39! If you're in an interview and they claim you're wrong on the facts, ask them right then and there if you can look it up in the specification. If the interviewer won't re-consider, then you shouldn't want to work there anyway.

하지만 만약 저의 의견과 일치하길 바라신다면 *왜* 그렇게 생각하는지 근거를 가지고 여러분의 선택을 지지할 준비를 하셔야합니다. 제가 얘기하는 걸 그저 앵무새처럼 따라하려고 하지 마십시오. 여러분 자신의 의견으로 만드시고 그것들을 지키십시오. 그리고 만약 함께 일하고 싶어하는 이가 여러분의 의견에 반대한다면, 고개를 들고 의견을 피력하십시오. JS는 거대하며 다양한 다른 방법들이 있습니다.

But if you choose to align with my opinions, you have to be prepared to back up those choices with *why* you feel that way. Don't just parrot what I say. Own your opinions. Defend them. And if someone you were hoping to work with disagrees, walk away with your head still held high. It's a big JS, and there's plenty of room for lots of different ways.

다시 말해, 이 시리즈와 가르쳐왔던 것처럼 *결실*에 거스르길 두려워하지 마십시오. 그 어떤 누구도 여러분에게 어떤 방식이 JS를 제일 잘 사용하는 방법이라고 얘기할 수 없으며 결정해 줄수도 없습니다. 저는 단지 여러분 자신의 결론에 이르도록 힘을 실어주기위해 노력할 뿐입니다.

In other words, don't be afraid to go against the *grain*, as I have done with these books and all my teachings. Nobody can tell you how you will best make use of JS; that's for you to decide. I'm merely trying to empower you in coming to your own conclusions, no matter what they are.

다른 말로, 여러분이 진심으로 집중하고 따라야만하는 것은 JS가 언어 단계에서 어떻게 동작하는지 알아야만하는 *결실*입니다. 주어진 올바른 연습 문제와 접근법을 통해 JS에 자연스레 작동하는 것들을 그리고 절대로 해서는 안 되는 것들을 발견하게 될 것입니다.

On the other hand, there's a *grain* you really should pay attention to and follow: the *grain* of how JS works, at the language level. There are things that work well and naturally in JS, given the right practice and approach, and there are things you really shouldn't try to do in the language.

JS 프로그램을 자바<sup>Java</sup>, C# 혹은 펄<sup>Perl</sup> 프로그램처럼 만들 수 있을까요? 파이썬<sup>Python</sup>, 루비<sup>Ruby</sup> 혹은 PHP는 어떨까요? 다양할 정도를 할 수 있습니다. 하지만 그렇게 해야만 할까요?

Can you make your JS program look like a Java, C#, or Perl program? What about Python or Ruby, or even PHP? To varying degrees, sure you can. But should you?

그렇지 않다고 생각합니다. 대신 전 JS의 방식을 배우고 포용하여 JS 프로그램을 실용적이며 JS다운 방식으로 만들어야 됩니다. 몇몇은 이런 방식이 엉성하며 비형식적인 프로그래밍이라고 생각할 수도 있지만 그런 의미가 아닙니다. 단지 JS는 "JS"라고 쉽게 알아볼 수 있을만한 수많은 패턴과 어법이 있으며, *결실*과 함께하는 것이 최상의 성공까지 가는 가장 보편적인 경로라는 말입니다.

No, I don't think you should. I think you should learn and embrace the JS way, and make your JS programs as JS'y as is practical. Some will think that means sloppy and informal programming, but I don't mean that at all. I just mean that JS has a lot of patterns and idioms that are recognizably "JS," and going with that *grain* is the general path to best success.

마지막으로 가장 중요한 *결실*은 여러분이 작업하고 있는 이미 존재하고 있는 프로그램을 그리고 여러분과 함께 작업할 개발자들을 어떻게 받아들일지에 관한 것입니다. 이 책을 단순히 일고 모든 프로젝트에 *모든 결실*을 적용하기위해 밤을 세우는 일을 하지 마십시오. 이러한 접근법은 늘 실패할 뿐입니다.

Finally, maybe the most important *grain* to recognize is how the existing program(s) you're working on, and developers you're working with, do stuff. Don't read these books and then try to change *all that grain* in your existing projects over night. That approach will always fail.

단지 이러한 변화를 조금씩 조금씩 계속해서 변화시켜야만 합니다. 접근방식에 관해 다시 논의하고 고려하는 것이 중요한 이유에대해 여러분의 동료 개발자들과 합의문을 작성하십시오. 하지만 단순히 하나의 자그마한 주제에 관해 하나씩만 작성을 하고 코드의 전과 후를 비교하여 이에 관해 이야기를 나누십시오. 팀원 전체를 데려와 함께 토론을 하고, "우리의 상위 개발자가 언제나 이런식으로 해왔으니까"와 같은 관성이 아닌 분석과 근거를 토대로 결정을 내리십시오.

You'll have to shift these things little by little, over time. Work on building consensus with your fellow developers on why it's important to re-visit and re-consider an approach. But do so with just one small topic at a time, and let before-and-after code comparisons do most of the talking. Bring everyone on the team together to discuss, and push for decisions that are based on analysis and evidence from the code rather than the inertia of "our senior devs have always done it this way."

이것이 여러분이 JS를 배우는데 도움이 될 가장 중요한 조언입니다. 항상 JS가 우리에게 더 좋은 가독성을 가진 코드를 쓸 수 있는 더 나은 방법을 찾으십시오. 여러분을 포함해서 여러분의 코드에 작업하는 모든 이들이 여러분에게 고마워 할 것입니다!

That's the most important advice I can impart to help you learn JS. Always keep looking for better ways to use what JS gives us to author more readable code. Everyone who works on your code, including your future self, will thank you!

## 순서

## In Order

지금 JS에 관해 탐험해 나가기위해 더 넓은 관점과 남은 시리즈의 여정으로 향하기 위한 올바른 자세를 가지게 됐습니다.

So now you've got a broader perspective on what's left to explore in JS, and the right attitude to approach the rest of your journey.

하지만 여기서 제가 얘기할 가장 흔한 실용적인 질문은 "어떠한 순서로 이 책을 읽어야되나요?"입니다. 여기에는 직관적인 답이 있지만 상황에 따라 조금 다를수도 있습니다.

But one of the most common practical questions I get at this point is, "What order should I read the books?" There is a straightforward answer... but it also depends.

저는 아래와 같은 순서로 이 책을 읽어나가길 제안합니다.

My suggestion for most readers is to proceed through this series in this order:

1. *시작하기 <sup>Get Started</sup>* (첫번째 책)를 통해 단단한 기반을 다지십시오. 좋은 소식이 있다면 저흰 이미 이 책을 거의 끝마쳤습니다!

1. Get started with a solid foundation of JS from *Get Started* (Book 1) -- good news, you've already almost finished this book!

2. *스코프와 클로져 <sup>Scopes & Closures</sup>* (두번째 책)을 통해 JS의 첫번째 기둥에 관해 파헤쳐보십시오. 여기서는 렉시컬 스코프<sup>Lexical scope</sup>, 클로져<sup>Closure</sup>를 지원하는 방법, 그리고 모듈<sup>Module</sup> 방식으로 코드를 조직하는 방법에 관한 것이 있습니다.

2. In *Scope & Closures* (Book 2), dig into the first pillar of JS: lexical scope, how that supports closure, and how the module pattern organizes code.

3. *객체과 클래스 <sup>Objects & Classes</sup>* (세번째 책)을 통해 JS의 두번째 기둥에 관해 집중적으로 다룰 것입니다. JS에서 `this`가 어떻게 작동하는지, 객체 프로토타입<sup>Object prototypes</sup>이 위임<sup>Delegation</sup>을 어떻게 지원하는지, 그리고 프로토타입이 객체 지향 형식의 코드 구성을 위해 `class` 방식을 지원하는지에 관한 것이 있습니다.

3. In *Objects & Classes* (Book 3), focus on the second pillar of JS: how JS's `this` works, how object prototypes support delegation, and how prototypes enable the `class` mechanism for OO-style code organization.

4. *타입과 문법 <sup>Types & Grammar</sup>* (네번째 책)을 통해 JS의 세번째이자 마지막 기둥에 관해 뒤져볼 것입니다. 타입과 강제 타입 변화<sup>Coercion</sup> 그리고 JS의 문법이 우리가 작성한 코드를 정의하는 방법에 관한 것이 있습니다.

4. In *Types & Grammar* (Book 4), tackle the third and final pillar of JS: types and type coercion, as well as how JS's syntax and grammar define how we write our code.

5. **세 기둥**이 굳건히 자리잡은 상태에서 *동기와 비동기 <sup>Sync & Async</sup>* (다섯번째 책)에서는 동기적으로 (즉각 수행하는) 그리고 비동기적으로 (시간에 걸쳐) 방법으로 프로그램에서 상태 변화를 어떻게 모형화 시키는지에 관해 탐험해 볼 것입니다.

5. With the **three pillars** solidly in place, *Sync & Async* (Book 5) then explores how we use flow control to model state change in our programs, both synchronously (right away) and asynchronously (over time).

6. 이 시리즈는 *ES.Next 그리고 그 너머 <sup>ES.Next & Beyond</sup>* (여섯번째 책)을 통해 끝마쳐집니다. 이 책을 통해 가까운 시일 혹은 어느정도 시간에 걸쳐 추후 JS에 포함될 다양한 기능들에 관해 다룰 것입니다.

6. The series concludes with *ES.Next & Beyond* (Book 6), a forward look at the near- and mid-term future of JS, including a variety of features likely coming to your JS programs before too long.

이 것이 이 시리즈를 읽는 순서입니다.

That's the intended order to read this book series.

하지만 책 2, 3, 4는 일반적으로 여러분이 가장 궁금해하는 주제가 무엇이고 뭘 가장 먼저 알아보고 싶은지에 따라 어떠한 순서로 읽어도 상관이 없습니다. 하지만 이 세권의 책과 *타입과 문법<sup>Types & Grammar</sup>*는 이미 이 주제에 관해 알고 있을지라도 건너뛰지 말길 바랍니다.

However, Books 2, 3, and 4 can generally be read in any order, depending on which topic you feel most curious about and comfortable exploring first. But I don't recommend you skip any of these three books—not even *Types & Grammar*, as some of you will be tempted to do!—even if you think you already have that topic down.

책 5 (*동기와 비동기<sup>Sync & Async</sup>*)는 JS를 깊이있게 이해하기 위해 중요하지만 만약 여기서부터 시작한다거나 해당 책이 너무 어렵다면 JS와 더 친숙해질때까지 미뤄놓아도 괜찮습니다. JS를 더 많이 사용할 수록 (그리고 노력할 수록!), 이 책에 더 많이 감사하게 될 것입니다. 그러니 나중에 다시 돌아오게 될지라도 두려워하지 마십시오.

Book 5 (*Sync & Async*) is crucial for deeply understanding JS, but if you start digging in and find it's too intimidating, this book can be deferred until you're more experienced with the language. The more JS you've written (and struggled with!), the more you'll come to appreciate this book. So don't be afraid to come back to it at a later time.

이 시리즈의 마지막 책인 *ES.Nest 그리고 그 너머<sup>ES.Next & Beyond* 다소 그 자체로 독립적인 면이 있습니다. 제가 제안드렸던 것처럼 가장 마지막에 읽을 수도 있지만 JS의 전반에 걸쳐 좀 더 시야를 넓히기위한 지름길로 가길 원한다면 *시작하기<sup>Getting Started</sup>*를 마친 이후 읽을수도 있습니다. 이 책은 향후 갱신될 가능성이 높으므로 이따금 다시 방문하는 것이 좋습니다.

The final book in the series, *ES.Next & Beyond*, in some respects stands alone. It can be read at the end, as I suggest, or right after *Getting Started* if you're looking for a shortcut to broaden your radar of what JS is all about. This book will also be more likely to receive updates in the future, so you'll probably want to re-visit it occasionally.

하지만 YDKJSY를 진행함에 있어 이 책의 부록을 특히 부록 B "연습, 연습, 그리고 또 연습!"에 있는 예제들을 먼저 확인해주십시오. 연습에 관해 언급드린 일이 있었죠!? 코드를 배우는데 실제 작성하는 것보다 더 좋은 방법은 없습니다.

However you choose to proceed with YDKJSY, check out the appendices of this book first, especially practicing the snippets in Appendix B, "Practice, Practice, Practice!" Did I mention you should go practice!? There's no better way to learn code than to write it.
