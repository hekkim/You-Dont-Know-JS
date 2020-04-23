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

프로그래밍 전반에 걸쳐 특히나 JS에서는 클로져를 통해 모듈과 같이 가장 중요한 프로그래밍 패턴들 중 다수를 사용할 수 있도록 만들어줍니다.

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

The vast majority of developers have strong misconceptions about how *types* work in programming languages, and especially how they work in JS. A tidal wave of interest in the broader JS community has begun to shift to "static typing" approaches, using type-aware tooling like TypeScript or Flow.

I agree that JS developers should learn more about types, and should learn more about how JS manages type conversions. I also agree that type-aware tooling can help developers, assuming they have gained and used this knowledge in the first place!

But I don't agree at all that the inevitable conclusion of this is to decide JS's type mechanism is bad and that we need to cover up JS's types with solutions outside the language. We don't have to follow the "static typing" way to be smart and solid with types in our programs. There are other options, if you're just willing to go *against the grain* of the crowd, and *with the grain* of JS (again, more on that to come).

Arguably, this pillar is more important than the other two, in the sense that no JS program will do anything useful if it doesn't properly leverage JS's value types, as well as the conversion (coercion) of values between types.

Even if you love TypeScript/Flow, you are not going to get the most out of those tools or coding approaches if you aren't deeply familiar with how the language itself manages value types.

To learn more about JS types and coercion, check out Book 4, *Types & Grammar*. But please don't skip over this topic just because you've always heard that we should use `===` and forget about the rest.

Without learning this pillar, your foundation in JS is shaky and incomplete at best.

## With the Grain

I have some advice to share on continuing your learning journey with JS, and your path through the rest of this book series: be aware of the *grain* (recall various references to *grain* earlier in this chapter).

First, consider the *grain* (as in, wood) of how most people approach and use JS. You've probably already noticed that these books cut against that *grain* in many respects. In YDKJSY, I respect you the reader enough to explain all the parts of JS, not only some select popular parts. I believe you're both capable and deserving of that knowledge.

But that is not what you'll find from a lot of other material out there. It also means that the more you follow and adhere to the guidance from these books—that you think carefully and analyze for yourself what's best in your code—the more you will stand out. That can be a good and bad thing. If you ever want to break out from the crowd, you're going to have to break from how the crowd does it!

But I've also had many people tell me that they quoted some topic/explanation from these books during a job interview, and the interviewer told the candidate they were wrong; indeed, people have reportedly lost out on job offers as a result.

As much as possible, I endeavor in these books to provide completely accurate information about JS, informed generally from the specification itself. But I also dose out quite a bit of my opinions on how you can interpret and use JS to the best benefit in your programs. I don't present opinion as fact, or vice versa. You'll always know which is which in these books.

Facts about JS are not really up for debate. Either the specification says something, or it doesn't. If you don't like what the specification says, or my relaying of it, take that up with TC39! If you're in an interview and they claim you're wrong on the facts, ask them right then and there if you can look it up in the specification. If the interviewer won't re-consider, then you shouldn't want to work there anyway.

But if you choose to align with my opinions, you have to be prepared to back up those choices with *why* you feel that way. Don't just parrot what I say. Own your opinions. Defend them. And if someone you were hoping to work with disagrees, walk away with your head still held high. It's a big JS, and there's plenty of room for lots of different ways.

In other words, don't be afraid to go against the *grain*, as I have done with these books and all my teachings. Nobody can tell you how you will best make use of JS; that's for you to decide. I'm merely trying to empower you in coming to your own conclusions, no matter what they are.

On the other hand, there's a *grain* you really should pay attention to and follow: the *grain* of how JS works, at the language level. There are things that work well and naturally in JS, given the right practice and approach, and there are things you really shouldn't try to do in the language.

Can you make your JS program look like a Java, C#, or Perl program? What about Python or Ruby, or even PHP? To varying degrees, sure you can. But should you?

No, I don't think you should. I think you should learn and embrace the JS way, and make your JS programs as JS'y as is practical. Some will think that means sloppy and informal programming, but I don't mean that at all. I just mean that JS has a lot of patterns and idioms that are recognizably "JS," and going with that *grain* is the general path to best success.

Finally, maybe the most important *grain* to recognize is how the existing program(s) you're working on, and developers you're working with, do stuff. Don't read these books and then try to change *all that grain* in your existing projects over night. That approach will always fail.

You'll have to shift these things little by little, over time. Work on building consensus with your fellow developers on why it's important to re-visit and re-consider an approach. But do so with just one small topic at a time, and let before-and-after code comparisons do most of the talking. Bring everyone on the team together to discuss, and push for decisions that are based on analysis and evidence from the code rather than the inertia of "our senior devs have always done it this way."

That's the most important advice I can impart to help you learn JS. Always keep looking for better ways to use what JS gives us to author more readable code. Everyone who works on your code, including your future self, will thank you!

## In Order

So now you've got a broader perspective on what's left to explore in JS, and the right attitude to approach the rest of your journey.

But one of the most common practical questions I get at this point is, "What order should I read the books?" There is a straightforward answer... but it also depends.

My suggestion for most readers is to proceed through this series in this order:

1. Get started with a solid foundation of JS from *Get Started* (Book 1) -- good news, you've already almost finished this book!

2. In *Scope & Closures* (Book 2), dig into the first pillar of JS: lexical scope, how that supports closure, and how the module pattern organizes code.

3. In *Objects & Classes* (Book 3), focus on the second pillar of JS: how JS's `this` works, how object prototypes support delegation, and how prototypes enable the `class` mechanism for OO-style code organization.

4. In *Types & Grammar* (Book 4), tackle the third and final pillar of JS: types and type coercion, as well as how JS's syntax and grammar define how we write our code.

5. With the **three pillars** solidly in place, *Sync & Async* (Book 5) then explores how we use flow control to model state change in our programs, both synchronously (right away) and asynchronously (over time).

6. The series concludes with *ES.Next & Beyond* (Book 6), a forward look at the near- and mid-term future of JS, including a variety of features likely coming to your JS programs before too long.

That's the intended order to read this book series.

However, Books 2, 3, and 4 can generally be read in any order, depending on which topic you feel most curious about and comfortable exploring first. But I don't recommend you skip any of these three books—not even *Types & Grammar*, as some of you will be tempted to do!—even if you think you already have that topic down.

Book 5 (*Sync & Async*) is crucial for deeply understanding JS, but if you start digging in and find it's too intimidating, this book can be deferred until you're more experienced with the language. The more JS you've written (and struggled with!), the more you'll come to appreciate this book. So don't be afraid to come back to it at a later time.

The final book in the series, *ES.Next & Beyond*, in some respects stands alone. It can be read at the end, as I suggest, or right after *Getting Started* if you're looking for a shortcut to broaden your radar of what JS is all about. This book will also be more likely to receive updates in the future, so you'll probably want to re-visit it occasionally.

However you choose to proceed with YDKJSY, check out the appendices of this book first, especially practicing the snippets in Appendix B, "Practice, Practice, Practice!" Did I mention you should go practice!? There's no better way to learn code than to write it.
