# You Don't Know JS Yet: Get Started - 2nd Edition
# 챕터 1: 자바스크립트란 무엇인가?
# Chapter 1: What *Is* JavaScript?

당신은 아직 JS를 모릅니다. 제가 완벽하게 그러하지 못 하고. 우리 중 그 누구도 그렇지 못 하죠. 하지만 우리 모두는 JS를 더 잘 알아갈 수는 있습니다.
You don't know JS, yet. Neither do I, not fully anyway. None of us do. But we can all start getting to know JS better.

*You Don't Know JS Yet* (YDKJSY) 시리즈의 첫 책의 첫 챕터에서는 앞으로 나아가기위한 기초 지식을 쌓을 것입니다. JS 라는 언어가 실제로 무엇인지에 관한 중요한 배경 지식의 디테일, 몇몇 미신들 그리고 오해에 관해 알아갈 것입니다.

In this first chapter of the first book of the *You Don't Know JS Yet* (YDKJSY) series, we will take some time to build a foundation to move forward on. We need to start by covering a variety of important background housekeeping details, clearing up some myths and misconceptions about what the language really is (and isn't!).

JS의 정체성에 관한 귀중한 깨달음과 어떻게 JS 구성되어 있고 유지되어 왔는지 알게 해주는 과정이 될 것입니다. 모든 JS 개발자들은 알아야하는 것이지요. JS에 관해 알고 싶어하는 분들을 위한 그 첫 발판이 되어줄 것입니다.

This is valuable insight into the identity and process of how JS is organized and maintained; all JS developers should understand it. If you want to get to know JS, this is how to *get started* taking the first steps in that journey.

## 이 책에 관해서

*JS를 알아가기*는 목적지가 아닌 방향성이기 때문에 여정이란 말을 강조하고 싶습니다. 여태까지 여러분이 얼마나 많은 시간을 이 언어와 함께하던지간에, 여러분은 이 언어에 관해 항상 다른 무언가 배우고 더 잘 이해할 수 있습니다. 그러므로 단기간에 무언가를 성취하기 위해 이 책을 허겁지겁 읽는 어리석은 짓을 하지마세요. 그 대신, 인내와 집요함만이 첫 몇 발걸음을 디디는 위한 최선의 선택이 될 것 입니다.

I emphasize the word journey because *knowing JS* is not a destination, it's a direction. No matter how much time you spend with the language, you will always be able to find something else to learn and understand a little better. So don't look at this book as something to rush through for a quick achievement. Instead, patience and persistence are best as you take these first few steps.

이 다음에 나올 배경 지식에 관한 챕터에서는, YDKJSY 책에서 다뤄질 이 책의 나머지부분에서 전반적으로 큰 그림들에 관해 다룰 것입니다.

Following this background chapter, the rest of the book lays out a high-level map of what you will find as you dig into and study JS with the YDKJSY books.

특히, 챕터 4는 JS를 구성하는 세 가지 주요 기초 지식인 스코프와 클로져, 프로토타입과 객체, 그리고 타입과 강제 변환에 관해 알아보게 될 것입니다. JS는 다양한 특징과 이용성이 있는 암시적이고 복잡한 언어이지만, JS는 이러한 세 가지 주요 기초지식에 기반하고 있습니다.

In particular, Chapter 4 identifies three main pillars around which the JS language is organized: scope/closures, prototypes/objects, and types/coercion. JS is a broad and sophisticated language, with many features and capabilities. But all of JS is founded on these three foundational pillars.

이 책의 주제가 "시작하기 (Get Started)"지만 단순한 초보자나 도입이 아님을 늘 새겨두세요. 이 책의 주요한 역할은 나머지 시리즈들에서 JS를 심도있게 공부하기 위함입니다. 그렇기에 나머지 시리즈는 독자분들이 이미 JS와 친숙하다고 가정한 채로 서술할 것입니다. 그러므로 *시작하기 (Get Started)*의 전반적인 지식을 얻기위해 충분히 많은 시간을 JS 코드를 작성하는데 할애하십시오.

Keep in mind that even though this book is titled "Get Started," it's **not intended as a beginner/intro book**. This book's main job is to get you ready for studying JS deeply throughout the rest of the series; it's written assuming you already have familiarity with JS over at least several months experience before moving on in YDKJSY. So to get the most out of *Get Started*, make sure you spend plenty of time writing JS code to build up your experience.

만약 이미 충분히 많은 JS 코드를 작성해봤었더라도, 이 책을 그저 훑어보거나 건너뛰지 마시고, 이 책의 내용을 이해하는데 충분히 많은 시간을 들여주세요. **좋은 시작은 언제나 견고한 첫 발걸음으로부터 늘 시작한답니다**

Even if you've already written a lot of JS before, this book should not be skimmed over or skipped; take your time to fully process the material here. **A good start always depends on a solid first step.**

## JavaScript, 그 이름의 유래

JavaScript란 이름은 아마도 가장 크게 잘못 알려지고 오해받는 프로그래밍 언어 이름일 것입니다.

The name JavaScript is probably the most mistaken and misunderstood programming language name.

Java랑 연관이 있는 언어일까? Java 전용 스크립트형 언어일까? 단순 스크립트를 작성하는 실제 프로그램 작성을 위한 언어는 아닌 것일까?

Is this language related to Java? Is it only the script form for Java? Is it only for writing scripts and not real programs?

진실은 JavaScript란 언어의 이름은 마케팅용 전략의 산물이란 것입니다. Brendan Eich가 처음으로 이 언어를 구상했을 때만해도 Mocha란 코드명을 가지고 있었죠. Netscape 내부에서는 LiveScript라고 이용되었었습니다. 그런데, 이 언어를 대중에게 공개할 무렵 "JavaScript"란 이름이 투표에서 이겨버렸었죠.

The truth is, the name JavaScript is an artifact of marketing shenanigans. When Brendan Eich first conceived of the language, he code-named it Mocha. Internally at Netscape, the brand LiveScript was used. But when it came time to publicly name the language, "JavaScript" won the vote.

왜죠? 왜냐하면 이 언어는 근본적으로 대부분의 Java 개발자들의 관심을 끌기위해 설계되었었고, 그 무렵만해도 가벼운 프로그램을 지칭하는데 "script"란 용어를 쓰는게 대중적이였습니다. 이러한 가벼운 "script"는 웹(Web)이라고 불리우는 페이지 내부에 처음으로 도입됐죠.

Why? Because this language was originally designed to appeal to an audience of mostly Java programmers, and because the word "script" was popular at the time to refer to lightweight programs. These lightweight "scripts" would be the first ones to embed inside of pages on this new thing called the web!

다시 말해, JavaScript는 당시 무겁고 훨씬 더 잘 알려진 Java를 빛 좋은 대용 언어로 자리잡기 위한 마케팅 전략이였죠. "WebJava"라고 쉽게 부를 수도 있습니다.

In other words, JavaScript was a marketing ploy to try to position this language as a palatable alternative to writing the heavier and more well-known Java of the day. It could just as easily have been called "WebJava," for that matter.

JavaScript는 Java의 코드와 다소 표면적으로 비슷해 보이는 점은 있습니다만, 그 유사함은 공통적으로 개발하기 위함이 아니라, 두 언어 모두가 C 혹은 C++ 개발자들에게 익숙한 문법을 목표로했기 때문입니다.

There are some superficial resemblances between JavaScript's code and Java code. Those similarities don't particularly come from shared development, but from both languages targeting developers with assumed syntax expectations from C (and to an extent, C++).

예로 들어, `{`로 시작하고 `}`로 묶여있는 코드 블락은 C/C++ 그리고 Java에서 모두 공통적으로 사용됩니다. 또한 `;`을 통해 문장의 끝맺음 짖죠.

For example, we use the `{` to begin a block of code and the `}` to end that block of code, just like C/C++ and Java. We also use the `;` to punctuate the end of a statement.

어떤면에서는 법적관계는 이런 문법적인 관계보다 보다 더 깊숙이 연관되어 있습니다. 오라클 (Oracal, 전신 썬 마이크로시스템즈 - Sun)은 Java를 소유하고 운영하고 있을뿐만이 아닌 "JavaScript"의 공식 상표 역시도 소유하고 있습니다. 이 상표는 거의 시행되지 않았으며 현재로서는 사용이 불가능했을 것입니다.

In some ways, legal relationships run even deeper than the syntax. Oracle (via Sun), the company that still owns and runs Java, also owns the official trademark for the name "JavaScript" (via Netscape). This trademark is almost never enforced, and likely couldn't be at this point.

이러한 이유로 인해 몇몇 사람들은 JavaScript란 말 대신 JS라고 사용하자고 제안하곤 합니다. 공식적으로 대체할 단어가 없는 상황에서는 JS는 매우 흔히 쓰이는 약어입니다. 게다가, 이 시리즈 전반적으로 JS는 JavaScript를 칭할 때 주로 쓰이게 될 것입니다.

For these reasons, some have suggested we use JS instead of JavaScript. That is a very common shorthand, if not a good candidate for an official language branding itself. Indeed, these books use JS almost exclusively to refer to the language.

오라클이 소유 상표로 부터 약간의 거리를 내자면, TC39에 의해 지정되고 ECMA 표준기군에 의해 명명된 공식 명칭은 **ECMAScript** 입니다. 게다가 2016년 이후로 개정년도를 어미로 붙여 공식적으로 사용되고 있습니다. 현재 이 책이 쓰인 년도에 따라 ECMAScript 2019 혹은 줄여서 ES2019라고 쓰이고 있죠.

Further distancing the language from the Oracle-owned trademark, the official name of the language specified by TC39 and formalized by the ECMA standards body is **ECMAScript**. And indeed, since 2016, the official language name has also been suffixed by the revision year; as of this writing, that's ECMAScript 2019, or otherwise abbreviated ES2019.

다시 말해, 당신의 브라우저 혹은 Node.js에서 실행되는 JavaScript 혹은 JS는 ES2019 표준의 구현체란 것이지요.

In other words, the JavaScript/JS that runs in your browser or in Node.js, is *an* implementation of the ES2019 standard.

| 노트: |
| :--- |
| 이 언어를 언급할 때 "JS6" 또는 "ES8"과 같은 말로 명명해주지 말아주세요. 몇몇은 그렇게 사용하기도 하지만 이러한 용어들은 혼란을 지속시킬 뿐입니다. "ES20xx" 혹은 단순히 "JS" 란 용어를 지속해서 사용해주세요. |

| NOTE: |
| :--- |
| Don't use terms like "JS6" or "ES8" to refer to the language. Some do, but those terms only serve to perpetuate confusion. "ES20xx" or just "JS" are what you should stick to. |

이 언어를 JavaScript, JS, ECMAScript 혹은 ES2019 중 뭐라고 부르던간에, 이 언어는 정말 진심으로 Java의 변형이 아닙니다.

Whether you call it JavaScript, JS, ECMAScript, or ES2019, it's most definitely not a variant of the Java language!

> "Java는 JavaScript에게 있어 햄과 햄스터의 관계와 같다." --Jeremy Keith, 2009

> "Java is to JavaScript as ham is to hamster." --Jeremy Keith, 2009

## 언어 지침서

이전에 언급하였던 TC39란 JS를 관리하는 기술 운영 위원회를 말합니다. 그들의 주요 업무는 언어의 공식 스펙을 관리하는 것이지요. 그들은 주기적으로 만나 변경점을 투표하고 ECMA란 표준 기구에 그 결과를 제출합니다.

I mentioned TC39, the technical steering committee that manages JS. Their primary task is managing the official specification for the language. They meet regularly to vote on any agreed changes, which they then submit to ECMA, the standards organization.

ES 지침서에는 이러한 JS의 문법과 행동 양식이 정의되어 있습니다.

JS's syntax and behavior are defined in the ES specification.

ES2019는 1995년 JS 창설 이래로있는 10번째 메이저 지침서이자 수정본이고, ECMA가 호스팅하고 있는 공식 URL을 통해 "10.0" 버전을 찾아볼 수 있습니다.

https://www.ecma-international.org/ecma-262/10.0/

ES2019 happens to be the 10th major numbered specification/revision since JS's inception in 1995, so in the specification's official URL as hosted by ECMA, you'll find "10.0":

https://www.ecma-international.org/ecma-262/10.0/

TC39 위원회는 모질라, 구글, 애플과 같은 웹 투자 회사 혹은 삼성과 같은 장비 개발사의 다방면에서 일하고 있는 50 ~ 100명으로 구성되어 있습니다. 아마도 회사로부터 많은 보상을 받고 있겠지만은 구성원 모두 자발적 참여자입니다.

The TC39 committee is comprised of between 50 and about 100 different people from a broad section of web-invested companies, such as browser makers (Mozilla, Google, Apple) and device makers (Samsung, etc). All members of the committee are volunteers, though many of them are employees of these companies and so may receive compensation in part for their duties on the committee.

TC39는 일반적으로 매달 모여 지난 회의 이후로의 작업물을 3일에 걸쳐 검토하고 문제에 관해 토론하고 제안들에 관해 투표를 합니다. 회의 장소는 회의를 주최하려는 회사들 사이에서 교대로 주최하게 됩니다.

TC39 meets generally about every other month, usually for about three days, to review work done by members since the last meeting, discuss issues, and vote on proposals. Meeting locations rotate among member companies willing to host.

모든 TC39 제안 과정은 스테이지 0부터 스테이지 4까지의 5개의 단계 통해 진행됩니다. 진행 과정에 관해서는 다음의 공식 사이트에서 더 자세히 알 수 있습니다 https://tc39.es/process-document/

All TC39 proposals progress through a five-stage process—of course, since we're programmers, it's 0-based!—Stage 0 through Stage 4. You can read more about the Stage process here: https://tc39.es/process-document/

스테이지 0는 간단히 얘기하자면 TC39 중 누군가가 괜찮은 아이디어에 관해 생각하고는 이를 주장하고 작업을 착수할 계획을 세웁니다. 즉, TC39의 위원회가 아닌 사람들도 소셜 네트워크나 블로그와 같은 비공식적인 채널을 통해 제안한 여러가지 아이디어는 실질적으로 "사전 스테이지 0"임을 뜻합니다. 이는 곧 TC39 위원회원이 "스테이지 0"에 공식적으로 제안을 주장할 수 있다는 뜻입니다.

Stage 0 means roughly, someone on TC39 thinks it's a worthy idea and plans to champion and work on it. That means lots of ideas that non-TC39 members "propose," through informal means such as social media or blog posts, are really "pre-stage 0." You have to get a TC39 member to champion a proposal for it to be considered "Stage 0" officially.

일단 어떠한 제안이 "스테이지 4"에 이르게 되면, 이는 그 다음해의 개정판에 포함되기 충분한 준비가 된 상태임을 뜻 합니다. 이러한 제안들은 그 과정이 몇 개월에서 몇 년까지도 걸리기도 합니다.

Once a proposal reaches "Stage 4" status, it is eligible to be included in the next yearly revision of the language. It can take anywhere from several months to a few years for a proposal to work its way through these stages.

TC39의 Github 저장소에 모든 제안들은 공식적으로 관리되고 있습니다: https://github.com/tc39/proposals

All proposals are managed in the open, on TC39's Github repository: https://github.com/tc39/proposals

TC39 위원회든 아니든간에 이런 공공 토론장과 과정에 참여하는 것은 환영받는 일입니다. 하지만 오직 TC39 위원회만이 회의에 참여하고 제안과 그 변경에 관해 투표할 수 있습니다. 따라서 사실상 TC39 위원회의 목소리가 JS가 미래 방향에 관해 많은 비중을 차지하고 있는 셈이지요.

Anyone, whether on TC39 or not, is welcome to participate in these public discussions and the processes for working on the proposals. However, only TC39 members can attend meetings and vote on the proposals and changes. So in effect, the voice of a TC39 member carries a lot of weight in where JS will go.

일부는 확신하고 절망적일만큼 지속되고 있는 미신과는 달리, 여러가지 버전의 JavaScript는 *존재하지 않습니다*. 오직 *한 가지 버전의 JS*만이 TC39와 ECMA에 의해 관리되고 있습니다.

Contrary to some established and frustratingly perpetuated myth, there are *not* multiple versions of JavaScript in the wild. There's just **one JS**, the official standard as maintained by TC39 and ECMA.

2000년대 초반으로 돌아가 마이크로소프트가 관리하던 분리되어지고 역공학된(reverse-engineered) 버전의 "JScript" (심지어는 완전히 호환되지도 않던)라고 명명됐던 JS는 여러 버전의 JS가 있었습니다. 하지만 이로부터 시간이 흘렀고 오늘날의 JS에 관해 얘기할 때 여러 버전의 JS가 있다는 것은 이제 완전히 구식이고 맞지않는 주장이 되었습니다.

Back in the early 2000s, when Microsoft maintained a forked and reverse-engineered (and not entirely compatible) version of JS called "JScript," there were legitimately "multiple versions" of JS. But those days are long gone. It's outdated and inaccurate to make such claims about JS today.

이제는 중앙 통제하에 모든 주요 브라우저들과 장비 제작자들은 그들의 JS 구현체를 준수하고 있습니다. 물론, 각 엔진의 특징들은 때때로 다르기도 합니다. 하지만 이는 v8 엔진 (크롬의 JS 엔진)의 특정 기능이 SpiderMonkey 엔진 (모질라의 JS 엔진)과 다르다거나 혹은 비호환적으로 작동한다는 뜻이 아닙니다.

All major browsers and device makers have committed to keeping their JS implementations compliant with this one central specification. Of course, engines implement features at different times. But it should never be the case that the v8 engine (Chrome's JS engine) implements a specified feature differently or incompatibly as compared to the SpiderMonkey engine (Mozilla's JS engine).

이는 곧 여러분이 **하나의 JS**를 공부할 수 있음을 뜻하고 어느곳에서든 똑같은 JS에 의존할 수 있음을 의미합니다.

That means you can learn **one JS**, and rely on that same JS everywhere.

### JS의 지배자 웹 The Web Rules Everything About (JS)

JS 환경이 브라우저에서 서버 그너머 로봇 등등 지속적으로 넓혀진데에 반해 JS를 지배한 단 하나의 환경은 웹입니다. 이 말인 즉슨 어떻게 JS가 웹을 위해 구현되는지가 실질적으로 중요한 현실이란 것입니다.

While the array of environments that run JS is constantly expanding (from browsers, to servers (Node.js), to robots, to lightbulbs, to...), the one environment that rules JS is the web. In other words, how JS is implemented for web browsers is, in all practicality, the only reality that matters.

대부분의 경우 특별한 환경에서든 브라우저 기반 JS 엔진에서 구동되든 JS는 정확히 똑같이 정의되어 있습니다. 하지만 약간의 차이에 관해 분명히 짚고 넘어가야됩니다.

For the most part, the JS defined in the specification and the JS that runs in browser-based JS engines is the same. But there are some differences that must be considered.

때때로 JS 스펙은 다소 새로운 방식 혹은 재정의된 행동을 수행하고 심지어 그러한 일들이 브라우저 기반 JS 엔진에서의 행동 양식과 정확히 일치하지 않기도 한다는 것입니다. 이러한 실수는 20여년이 넘도록 비정상적이지만 예측 가능한 범위에서 기능하고 있는 웹 컨텐츠들에 기반하고 있기 때문입니다. 그로인해, 그러한 웹 컨텐츠의 손상을 방지하고자 때때로 JS 엔진은 사양에 따른 변경을 따르지 않기도 할 것 입니다.

Sometimes the JS specification will dictate some new or refined behavior, and yet that won't exactly match with how it works in browser-based JS engines. Such a mismatch is historical: JS engines have had 20+ years of observable behaviors around corner cases of features that have come to be relied on by web content. As such, sometimes the JS engines will refuse to conform to a specification-dictated change because it would break that web content.

이러한 경우 종종 TC39는 역추적을 하기도하고 그러한 웹 환경의 특이점을 가볍게 수긍하기도 합니다. 예로 들어, TC39는 `contains(..)`라는 함수를 배열 (Array)에 추가할 계획을 갖고 있었지만 몇몇 사이트들에서 이 함수명이 오래된 JS 프레임워크에서 여전히 사용되고 있는 것을 발견했고, 그로인해 그들은 충돌이 발생하지 않는 `includes(..)`란 이름으로 함수를 변경하기도 했습니다. 이렇게 희극 혹은 비극같은 일은 "Smooshgate" 라고 별칭하는 되는 때에도 똑같이 발생했는데, 이 때는 `flatten(..)`으로 계획되었던 함수는 결국 `flat(..)`이라고 이름을 바꿔야만 됐습니다.

In these cases, often TC39 will backtrack and simply choose to conform the specification to the reality of the web. For example, TC39 planned to add a `contains(..)` method for Arrays, but it was found that this name conflicted with old JS frameworks still in use on some sites, so they changed the name to a non-conflicting `includes(..)`. The same happened with a comedic/tragic JS *community crisis* dubbed "smooshgate," where the planned `flatten(..)` method was eventually renamed `flat(..)`.

하지만 때때로, TC39는 스펙이 그러한 특이점에서도 정확하고 분명하게 작동하도록 결정할 것입니다. 그러한 브라우저 기반 JS 엔진에 잘 작동하지 못 할지라도 말이죠.

But occasionally, TC39 will decide the specification should stick firm on some point even though it is unlikely that browser-based JS engines will ever conform.

결론은? 부록 B "웹 브라우저를 위한 추가적인 ECMAScript 특징"[^specApB]에서 공식 JS 스펙과 웹에서 구동되고 있는 JS의 현실의 차이에 관한 자세한 스펙을 포함하고 있습니다. 다시 말해, 이러한 예외점들은 *오직* 웹 JS 환경에서만 있다는 것입니다. 다른 JS 환경은 설명서에 토씨하나에도 틀리지 않고 정확하게 작동되어야만 하죠.

The solution? Appendix B, "Additional ECMAScript Features for Web Browsers".[^specApB] The JS specification includes this appendix to detail out any known mismatches between the official JS specification and the reality of JS on the web. In other words, these are exceptions that are allowed *only* for web JS; other JS environments must stick to the letter of the law.

섹션 B.1과 B.2는 역사적인 근거에는 반하지만 TC39가 코어 JS에서는 형식적으로 구체적으로 설명치 않은 *추가적인* 웹 JS 문법 혹은 API에 관해 다루고 있습니다. `0` 접두사를 가진 8진법 숫자라던가 `escape(..)` / `unescape(..)` 유틸리티 함수라던가 String에 있는 `anchor(..)`, `blink()` 함수 RegExp에 있는 `compile(..)` 함수와 같은 것들에 관한 것이지요.

Section B.1 and B.2 cover *additions* to JS (syntax and APIs) that web JS includes, again for historical reasons, but which TC39 does not plan to formally specify in the core of JS. Examples include `0`-prefixed octal literals, the global `escape(..)` / `unescape(..)` utilities, String "helpers" like `anchor(..)` and `blink()`, and the RegExp `compile(..)` method.

섹션 B.3에서는 웹과 웹이 아닌 JS 엔진에서 똑같이 사용가능하지만 다른 행동 양식이 보인다던가 다른 결과물을 내는 충돌들에 관해 다룰 것입니다. 대부분의 이런 차이점들은 strict mode에서 구현되고 있던 초창기 에러들이라고 딱지표가 붙은 상황들로 구성되어 있습니다.

Section B.3 includes some conflicts where code may run in both web and non-web JS engines, but where the behavior *could* be observably different, resulting in different outcomes. Most of the listed changes involve situations that are labeled as early errors when code is running in strict mode.

부록 B *올ㅋ (gotchas)*에선 흔히 마주치긴 어렵지만 미래의 안전을 위해 피해야만하는 구조들에 관한 좋은 아이디어들에 관해 다룰 것입니다. 가능한 한 특정 JS 환경에서만 적용되는 동작에 의존하지 마시고 어디서든 사용 가능한 JS 사양을 준수하시기 바랍니다.

Appendix B *gotchas* aren't encountered very often, but it's still a good idea to avoid these constructs to be future safe. Wherever possible, adhere to the JS specification and don't rely on behavior that's only applicable in certain JS engine environments.

### Not All (Web) JS...

이것은 JS 프로그램 코드 일까요?

Is this code a JS program?

```js
alert("Hello, JS!");
```

위 코드를 어떻게 바로보냐에 따라 달려있습니다. 위의 `alert(..)` 함수는 JS 스펙에는 포함돼있지는 않지만 모든 웹 JS 관경에 *존재*하고 있습니다. 하지만, 부록 B에서 이에 관해 찾진 못 할 것입니다.

Depends on how you look at things. The `alert(..)` function shown here is not included in the JS specification, but it *is* in all web JS environments. Yet, you won't find it in Appendix B, so what gives?

브라우저 JS 엔진 Node.js 등등의 다양한 JS 환경에서는 브라우저에서 뜨는 경고창과 같은 특정 환경에 친화적인 여러 API가 여러분의 JS 프로그램에 추가되어 있습니다.

Various JS environments (like browser JS engines, Node.js, etc.) add APIs into the global scope of your JS programs that give you environment-specific capabilities, like being able to pop an alert-style box in the user's browser.

실은 `fetch(..)`, `getCurrentLocation(..)` 혹은 `getUserMedia(..)`와 같이 다양한 JS의 API로 보이는 것들은 JS API로 가장한 웹 API들입니다. 반면, Node.js 환경에서는 `fs.write(..)`과 같은 다양한 모듈들을 내장하고 있죠.

In fact, a wide range of JS-looking APIs, like `fetch(..)`, `getCurrentLocation(..)`, and `getUserMedia(..)`, are all web APIs that look like JS. In Node.js, we can access hundreds of API methods from various built-in modules, like `fs.write(..)`.

`console.log(..)`처럼 모든 `console.*` 함수들은 역시 위와 같은 예입니다. 그것들은 JS에 특정되어 스펙화되어 있지는 않지만, 어느정도의 합의에 따라 보편적인 이용성때문에 대부분의 JS 환경에서 정의되어 있습니다.

Another common example is `console.log(..)` (and all the other `console.*` methods!). These are not specified in JS, but because of their universal utility are defined by pretty much every JS environment, according to a roughly agreed consensus.

그래서 결론적으로 `alert(..)` 혹은 `console.log(..)`와 같은 것들은 JS에 의해 정의되어 있지는 않습니다. 다만 JS 처럼 *여겨질뿐*입니다. JS 문법을 잘 지키는 그저 함수나 객체의 함수들입니다. 그들의 작동 방식은 JS 엔진의 환경에의해 관리되지만 표면적으로 그들은 JS의 환경에서 제 역할을 하기위해 JS를 따르고 있을 뿐입니다.

So `alert(..)` and `console.log(..)` are not defined by JS. But they *look* like JS. They are functions and object methods and they obey JS syntax rules. The behaviors behind them are controlled by the environment running the JS engine, but on the surface they definitely have to abide by JS to be able to play in the JS playground.

대부분의 브라우저간 차이에 관해 "JS는 너무 일관성이 없어"라고 불평하곤하는 주장들은 실제로는 JS의 작동 양식이 아닌 그들의 환경의 차이로 인해 발생하는 것입니다.

Most of the cross-browser differences people complain about with "JS is so inconsistent!" claims are actually due to differences in how those environment behaviors work, not in how the JS itself works.

그래서 `alert(..)`를 호출하는 것은 JS지만 `alert` 자체는 공식 JS의 스펙의 일부가 아닌 그저 단순한 손님과도 같은 것입니다.

So an `alert(..)` call *is* JS, but `alert` itself is really just a guest, not part of the official JS specification.

### It's Not Always JS

브라우저의 개발자툴에서나 Node 환경에서 console 혹은 REPL(Read-Evaluate-Print-Loop)을 사용하는 것은 언뜻보기에는 매우 마치 JS 환경인 것 같은 느낌을 줍니다. 하지만 실제로 그렇지 않죠.

Using the console/REPL (Read-Evaluate-Print-Loop) in your browser's Developer Tools (or Node) feels like a pretty straightforward JS environment at first glance. But it's not, really.

개발자 툴은 그저 개발자들을 위한 도구일 뿐입니다. 개발자 도구는 개발자들의 삶을 편하게 만들어 주는 게 주요 목적입니다. 개발자 경험 (DX - Developer Experience)을 최우선시하고 있죠. JS의 엄격한 스펙의 미효한 차이를 정확하고 순수하게 반영하기 위한 도구가 *아닙니다*. 그렇기에 콘솔을 *순수한* JS 환경이라고 여긴다면 많은 우연과도 같은 일들이 "깨달음"을 줬다고 착각해버릴 여지가 있습니다.

Developer Tools are... tools for developers. Their primary purpose is to make life easier for developers. They prioritize DX (Developer Experience). It is *not* a goal of such tools to accurately and purely reflect all nuances of strict-spec JS behavior. As such, there's many quirks that may act as "gotchas" if you're treating the console as a *pure* JS environment.

어쨋든 이러한 편의성은 큰 장점입니다. 전 개발자 도구가 여타 다른 개발자들의 삶을 쉽게 만들어 준다는 사실에 정말 기쁩니다. 변수와 같은 것들을 자동 완성해주는 매력적인 UX를 가지고 있다는 사실에 매우 만족스럽습니다. 하지만 이러한 개발자 도구들이 JS 프로그램의 엄격한 작동 양식과 늘 동일하게 작동할 거라고 기대하지 않았으면 좋겠다는 점을 짚고 넘어가고 싶습니다. 왜냐하면 그런 용도의 도구들이 아니기 때문이지요.

This convenience is a good thing, by the way! I'm glad Developer Tools make developers' lives easier! I'm glad we have nice UX charms like auto-complete of variables/properties, etc. I'm just pointing out that we can't and shouldn't expect such tools to *always* adhere strictly to the way JS programs are handled, because that's not the purpose of these tools.

그러한 도구들의 행동 양식은 브라우저별로 다를뿐더러 순식간에 바뀔 때도 있기에 저는 이 곳에서 그 도구들의 디테일한 부분까지 굳이 "하드코드" 하는 것 처럼 다루지 않을 것입니다. 그렇게 될 경우 이 책의 내용들은 너무나도 순식간에 구식의 내용에 관해서 다루게 될 것이니까요.

Since such tools vary in behavior from browser to browser, and since they change (sometimes rather frequently), I'm not going to "hardcode" any of the specific details into this text, thereby ensuring this book text is outdated quickly.

다만, 저는 네이티비 JS에서 동작하지 않을 거라는 가정을 부각시키기위해 각기 다른 JS 콘솔 환경에서 사실처럼 여겨지던 몇몇의 우연의 예시들에 관한 힌드들만 드리도록 하겠습니다.

But I'll just hint at some examples of quirks that have been true at various points in different JS console environments, to reinforce my point about not assuming native JS behavior while using them:

* 콘솔의 top-level에서 행해지는 `var(변수)` 혹은 `function(함수)` 선언은 글로벌 변수(`window`에 반영될 프로퍼티)를 생성할까요?

* Whether a `var` or `function` declaration in the top-level "global scope" of the console actually creates a real global variable (and mirrored `window` property, and vice versa!).

* "글로벌 스코프"이자 top-level에서는 여러번의 `let` 혹은 `const` 선언할 경우 무슨 일이 생길까요?

* What happens with multiple `let` and `const` declarations in the top-level "global scope."

* .js 파일에서 `"use strict";`를 실행하면 해당 세션을 strict 모드로 바꿔주는 것처럼 첫 실행문에서 `"use strict";`를 수행하도록 `<enter>`를 눌러 명령문을 실행할 경우 경우 모든 콘솔 세션을 strict 모드로 전환하게 할까요?

* Whether `"use strict";` on one line-entry (pressing `<enter>` after) enables strict mode for the rest of that console session, the way it would on the first line of a .js file, as well as whether you can use `"use strict";` beyond the "first line" and still get strict mode turned on for that session.

* non-strict 모드에서 함수 호출의 경우 `this`는 어떻게 바인딩될까요? 그리고 "global 객체"는 글로벌 변수들을 모두 포함하고 있을까요?

* How non-strict mode `this` default-binding works for function calls, and whether the "global object" used will contain expected global variables.

* 여러줄의 엔트리에서 호이스팅은 어떻게 작동할까요?

* How hoisting (see Book 2, *Scope & Closures*) works across multiple line entries.

* 기타 등등...

* ...several others

개발자 콘솔은 마치 JS 컴파일러가 JS 엔진을 통해 .js에 있는 코드를 실행하는 것처럼 행동하려고 노력하지 않습니다. 단지, 여러분에게서 간단한 몇 줄의 코드들을 빠르게 입력받고 그 결과를 재빠르게 확인할 수 있도록 쉽게 도와줄 뿐입니다. 이러한 부분들은 전반적으로 실사용 사례와 다를 뿐더러 각각의 환경에서 불합리한 다른 결과 도출하기도 합니다.

The developer console is not trying to pretend to be a JS compiler that handles your entered code exactly the same way the JS engine handles a .js file. It's trying to make it easy for you to quickly enter a few lines of code and see the results immediately. These are entirely different use cases, and as such, it's unreasonable to expect one tool to handle both equally.

JS 문법으로 표현되는 개발자 도구에서 보여주는 결과와 행동 양식을 믿지 마세요. 대신해서 스펙을 참고하고 콘솔을 "JS 친화적" 환경이라고 생각하세요. 개발자 도구는 그렇기 위해 존재하는 유용한 친구들입니다.

Don't trust what behavior you see in a developer console as representing *exact* to-the-letter JS semantics; for that, read the specification. Instead, think of the console as a "JS-friendly" environment. That's useful in its own right.

## 다양한 면모

프로그래밍 언어의 맥락에서 "패러다임"이란 용어는 넓은 사고 방식과 코드의 구조화하는 접근법을 말한다. 패러다임에는 각각의 프로그램들을 구별짓는 스타일과 형태의 무수히 많은 차이가 있다. 예를들어 코드에 담긴 그들만의 특별한 많은 라이브러리나 프레임워크들이 각기 가지고 있는 특징과 같은 것들이다.

The term "paradigm" in programming language context refers to a broad (almost universal) mindset and approach to structuring code. Within a paradigm, there are myriad variations of style and form that distinguish programs, including countless different libraries and frameworks that leave their unique signature on any given code.

하지만 프로그램 고유 스타일이 어떠하든 패러다임에 관한 전반적인 모습은 거의 늘 항상 모든 프로그램을 한 눈에 알 수 있도록 구분되어 있습니다.

But no matter what a program's individual style may be, the big picture divisions around paradigms are almost always evident at first glance of any program.

대표적인 패러다임 레벨의 코드 범주로는 절차지향적(prodedural), 객체지향(object-oriented - OO/classes), 그리고 함수형 프로그래밍(functional - FP)들이 있습니다.

Typical paradigm-level code categories include procedural, object-oriented (OO/classes), and functional (FP):

* 절차지향적 스타일은 절차(procedure)라고 불리우는 단위들이 함께 묶여서 구성하고, 이러한 절차들을 미리 결정되어있는 작업들의 순서에 맞춰 절차지향적(linear progression)인 과정을 통해 탑-다운(top-down) 형태로 구성된 스타일입니다.

* Procedural style organizes code in a top-down, linear progression through a pre-determined set of operations, usually collected together in related units called procedures.

* 객체지향 스타일은 데이터와 연산 로직들로 구성된 코드들을 하나의 클래스라는 단위로 묶어 구성하는 형태를 얘기합니다.

* OO style organizes code by collecting logic and data together into units called classes.

* 함수형 프로그래밍은 코드들을 각각의 절차(procedure)와는 다르게 순수 함수형태로 코드들을 구성하고 이렇게 구성된 함수들을 값으로써 이용하는 모습을 합니다.

* FP style organizes code into functions (pure computations as opposed to procedures), and the adaptations of those functions as values.

패러다임은 옳고 그름의 문제가 아닙니다. 단지 패러다임이란 프로그래머가 문제와 해결책의 접근 방법에 관해 안내해주고, 코드의 구성과 유지 방법에 관한 방향성에 관한 이야기입니다.

Paradigms are neither right nor wrong. They're orientations that guide and mold how programmers approach problems and solutions, how they structure and maintain their code.

몇몇 언어들은 하나의 패러다임에 지나치게 편향되어 있기도 합니다. C는 절차지향적인 반면 Java와 C++는 전반적으로 클래스 지향적이고 Haskell는 함수형 프로그래밍의 연속이죠.

Some languages are heavily slanted toward one paradigm—C is procedural, Java/C++ are almost entirely class oriented, and Haskell is FP through and through.

하지만 많은 언어들은 다양한 여럿 패러다임으로부터 유래한 코드 패턴들을 지원하고 심지어는 이들을 같이 사용할 수도 있게 설계되어 있습니다. 그래서 이러한 언어들을 다중 패러다임 언어(multi-paradigm language)라고 부르며 무한한 사용성을 가지고 있습니다. 한 프로그램에서 여러 패러다임들이 혼용되어 사용되는 경우도 있습니다.

But many languages also support code patterns that can come from, and even mix and match from, different paradigms. So called "multi-paradigm languages" offer ultimate flexibility. In some cases, a single program can even have two or more expressions of these paradigms sitting side by side.

JavaScript 또한 다중 패러다임 언어입니다. JavaScript에서는 절차지향적으로 클래스 중심으로 혹은 함수형 형태로도 코드를 짤수 있습니다. 코드 전반에 걸쳐 혹은 특정 패러다임만을 이용할 수 있도록 강요하지 않고 한 줄 한 줄 각각 다른 선택을 할 수 있도록 되어있습니다.

JavaScript is most definitely a multi-paradigm language. You can write procedural, class-oriented, or FP-style code, and you can make those decisions on a line-by-line basis instead of being forced into an all-or-nothing choice.

## Backwards & Forwards

JavaScript가 지향하는 근본적 원리 중 하나는 *하위 호환성(backwards compatibility)*의 보호하자는 것입니다. 많은 이들이 이 용어의 함축된 의미를 혼동을 하곤하기도 하고 연관되어 있지만 다른 용어인 *상위 호환성(forwards compatibility)*과 종종 헷갈려하기도 합니다.

One of the most foundational principles that guides JavaScript is preservation of *backwards compatibility*. Many are confused by the implications of this term, and often confuse it with a related but different term: *forwards compatibility*.

지금부터 이 용어에 관해 정확하게 정의를 세워보도록 하겠습니다.

Let's set the record straight.

하위 호완성은 만약 JS에 적합하다고 일단 인정되어진 어떠한 특징들은 JS에서 부적합하다고 변경될 일이 없다는 것을 뜻합니다. 원시적이고 제한된 환경이기도 했던 1995에 작성된 코드일지라도 오늘날에도 여전히 작동되야 된다는 것이죠. TC39의 한 명으로써 말하자면 "저흰 웹을 파괴하지 않을 것입니다!"

Backwards compatibility means that once something is accepted as valid JS, there will not be a future change to the language that causes that code to become invalid JS. Code written in 1995—however primitive or limited it may have been!—should still work today. As TC39 members often proclaim, "we don't break the web!"

이러한 발상은 브라우저 업데이트로 인해 예상치 못 하게 작동하지 않는 일이 없도록 해주고 이러한 신뢰를 바탕으로 JS 개발자들이 코드를 작성할 수 있는데 기여합니다. 이로인해 향후 수 년 동안 프로그램을 위해 JS를 선택하는게 안전하며 현명한 투자가 되도록 해줍니다.

The idea is that JS developers can write code with confidence that their code won't stop working unpredictably because a browser update is released. This makes the decision to choose JS for a program a more wise and safe investment, for years into the future.

이러한 "보장(gurantee)"는 결코 작은 일이 아닙니다. 거의 25년에 가까운 언어의 역사에 긴 역사를 가진 언어의 하위 호환성을 유지하는 것은 몹시 부담스러운 일이고 각기 다른 고유의 도전 과제들의 항연이기도 합니다. 위원회가 하위호환성을 보존하기위해 다양한 예제들을 찾아보는 것에 큰 압박을 받을 수도 있습니다.

That "guarantee" is no small thing. Maintaining backwards compatibility, stretched out across almost 25 years of the language's history, creates an enormous burden and a whole slew of unique challenges. You'd be hard pressed to find many other examples in computing of such a commitment to backwards compatibility.

이러한 원칙을 지키는데 들어가는 비용은 결코 쉽게 넘어갈 수 없습니다. 언어를 변경시키고 확장하는 일은 정말로 높은 기준치를 불가피하게 만드는 것까지 포함하고 있습니다. 실수이든 아니든 그 어떠한 결정도 결론적으로 영구적이기 때문입니다. 일단 JS에 들어오게되면 정말 진심으로 이러한 특징을 제거하고 싶더라도 결코 빼는 것은 불가능합니다. 왜냐하면 이건 아마도 프로그램을 망가뜨릴 수도 있기 때문입니다.

The costs of sticking to this principle should not be casually dismissed. It necessarily creates a very high bar to including changing or extending the language; any decision becomes effectively permanent, mistakes and all. Once it's in JS, it can't be taken out because it might break programs, even if we'd really, really like to remove it!

이러한 규칙에 아주 작은 예외들도 있습니다. JS에는 몇몇 하위 비호환(backwards-imcompatible)되는 변경점들을 가지고 있는데 TC39는 절대 이러한 특징을 사용하지 않길 경고합니다. TC39는 이러한 예외들이 만들어내는 결과를 측정하기위해 웹상에 존재하는 코드들(수집된 브라우저 데이터를 통해)을 연구하곤 하는데, 이를 통해 브라우저들은 결과적으로 사용자들에게 미세한 예외들을 고칠 때 어떠한 이득에 반하는지 미세한 영향을 가늠하고 감수할지말지 결론을 짓고 투표를 합니다.

There are some small exceptions to this rule. JS has had some backwards-incompatible changes, but TC39 is extremely cautious in doing so. They study existing code on the web (via browser data gathering) to estimate the impact of such breakage, and browsers ultimately decide and vote on whether they're willing to take the heat from users for a very small-scale breakage weighed against the benefits of fixing or improving some aspect of the language for many more sites (and users).

이러한 종류의 변경은 몹시 드물고 대부분의 사이트에서 눈에 띄지 않게 깨지지 않는 특이한 경우들이 그 대부분을 차지합니다.

These kinds of changes are rare, and are almost always in corner cases of usage that are unlikely to be observably breaking in many sites.

*하위 호환성*과 대응 관계에 있는 *상위 호환성*과 비교해봅시다. 상위 호환이 된다는 것은 프로그램의 언어에 새로운 추가 기능을 포함해도 이전 버전의 JS 엔진에서 실행된 경우 해당 프로그램이 중단되지 않는다는 얘기입니다. 많은 이들이 원하거나 심지어는 오해하는 경우도 있지만 **JS는 상위 호환적이지 않습니다**.

Compare *backwards compatibility* to its counterpart, *forwards compatibility*. Being forwards-compatible means that including a new addition to the language in a program would not cause that program to break if it were run in an older JS engine. **JS is not forwards-compatible**, despite many wishing such, and even incorrectly believing the myth that it is.

반대로 HTML 그리고 CSS는 하위 호환적이지 않고 상위 호환적입니다. 1995년에 작성된 HTML이나 CSS 지금 살펴보면 불완전하게 작동한다던가 아니면 그 당시와는 다르게 작동하는 경우가 있습니다. 하지만 만약 2019년에 추가된 기능을 2010년에 만들어진 브라우저에서 사용할 경우 페이지가 망가진 않습니다 -- 인식되지 않는 CSS/HTML는 무시하고 그렇지 않는 CSS/HTML은 정상적으로 그에 맞게 작동합니다.

HTML and CSS, by contrast, are forwards-compatible but not backwards-compatible. If you dug up some HTML or CSS written back in 1995, it's entirely possible it would not work (or work the same) today. But, if you use a new feature from 2019 in a browser from 2010, the page isn't "broken" -- the unrecognized CSS/HTML is skipped over, while the rest of the CSS/HTML would be processed accordingly.

프로그래밍 언어 설계에 있어서 상위 호환성을 추구하는게 이상적인 것처럼 보이지만 이는 대게 비현실적입니다. HTML과 같은 마크업(Markup) 혹은 CSS와 같은 스타일링(styling)은 서술적이고 그래서 훨씬 더 인식되지 않는 선언문에 관해 최소한의 인식되는 선언문들에 최소한의 영향을 미치며 "무시"하는 것이 쉽습니다.

It may seem desirable for forwards-compatibility to be included in programming language design, but it's generally impractical to do so. Markup (HTML) or styling (CSS) are declarative in nature, so it's much easier to "skip over" unrecognized declarations with minimal impact to other recognized declarations.

반면 프로그래밍 언어 엔진이 선택적으로 인식되지 않는 특정 문장 혹은 표현문이라도 선택적으로 거르게 될 경우 혼돈과 비결정성이 따라오게 될 것입니다. 마치, 프로그래밍 언어 엔진이 예측하지 못하게 무시되어진 부분이 프로그램의 일부가 제대로 처리될지 안될지 확신을 주지 못 합니다.

But chaos and non-determinism would ensue if a programming language engine selectively skipped statements (or even expressions!) that it didn't understand, as it's impossible to ensure that a subsequent part of the program wasn't expecting the skipped-over part to have been processed.

JS는 상위 호환적이지 않고 그럴 수 없음에도 불구하고 JS에 있는 하위 호환성을 통해 얻어지는 웹 환경에 지속적인 이득과 제약 그리고 어려움을 걸 알고 있는 것은 중요합니다.

Though JS isn't, and can't be, forwards-compatible, it's critical to recognize JS's backwards compatibility, including the enduring benefits to the web and the constraints and difficulties it places on JS as a result.

### Jumping the Gaps

Since JS is not forwards-compatible, it means that there is always the potential for a gap between code that you can write that's valid JS, and the oldest engine that your site or application needs to support. If you run a program that uses an ES2019 feature in an engine from 2016, you're very likely to see the program break and crash.

If the feature is a new syntax, the program will in general completely fail to compile and run, usually throwing a syntax error. If the feature is an API (such as ES6's `Object.is(..)`), the program may run up to a point but then throw a runtime exception and stop once it encounters the reference to the unknown API.

Does this mean JS developers should always lag behind the pace of progress, using only code that is on the trailing edge of the oldest JS engine environments they need to support? No!

But it does mean that JS developers need to take special care to address this gap.

For new and incompatible syntax, the solution is transpiling. Transpiling is a contrived and community-invented term to describe using a tool to convert the source code of a program from one form to another (but still as textual source code). Typically, forwards-compatibility problems related to syntax are solved by using a transpiler (the most common one being Babel (https://babeljs.io)) to convert from that newer JS syntax version to an equivalent older syntax.

For example, a developer may write a snippet of code like:

```js
if (something) {
    let x = 3;
    console.log(x);
}
else {
    let x = 4;
    console.log(x);
}
```

This is how the code would look in the source code tree for that application. But when producing the file(s) to deploy to the public website, the Babel transpiler might convert that code to look like this:

```js
var x$0, x$1;
if (something) {
    x$0 = 3;
    console.log(x$0);
}
else {
    x$1 = 4;
    console.log(x$1);
}
```

The original snippet relied on `let` to create block-scoped `x` variables in both the `if` and `else` clauses which did not interfere with each other. An equivalent program (with minimal re-working) that Babel can produce just chooses to name two different variables with unique names, producing the same non-interference outcome.

| NOTE: |
| :--- |
| The `let` keyword was added in ES6 (in 2015). The preceding example of transpiling would only need to apply if an application needed to run in a pre-ES6 supporting JS environment. The example here is just for simplicity of illustration. When ES6 was new, the need for such a transpilation was quite prevalent, but in 2020 it's much less common to need to support pre-ES6 environments. The "target" used for transpiliation is thus a sliding window that shifts upward only as decisions are made for a site/application to stop supporting some old browser/engine. |

You may wonder: why go to the trouble of using a tool to convert from a newer syntax version to an older one? Couldn't we just write the two variables and skip using the `let` keyword? The reason is, it's strongly recommended that developers use the latest version of JS so that their code is clean and communicates its ideas most effectively.

Developers should focus on writing the clean, new syntax forms, and let the tools take care of producing a forwards-compatible version of that code that is suitable to deploy and run on the oldest-supported JS engine environments.

### Filling the Gaps

If the forwards-compatibility issue is not related to new syntax, but rather to a missing API method that was only recently added, the most common solution is to provide a definition for that missing API method that stands in and acts as if the older environment had already had it natively defined. This pattern is called a polyfill (aka "shim").

Consider this code:

```js
// getSomeRecords() returns us a promise for some
// data it will fetch
var pr = getSomeRecords();

// show the UI spinner while we get the data
startSpinner();

pr
.then(renderRecords)   // render if successful
.catch(showError)      // show an error if not
.finally(hideSpinner)  // always hide the spinner
```

This code uses an ES2019 feature, the `finally(..)` method on the promise prototype. If this code were used in a pre-ES2019 environment, the `finally(..)` method would not exist, and an error would occur.

A polyfill for `finally(..)` in pre-ES2019 environments could look like this:

```js
if (!Promise.prototype.finally) {
    Promise.prototype.finally = function f(fn){
        return this.then(
            function t(v){
                return Promise.resolve( fn() )
                    .then(function t(){
                        return v;
                    });
            },
            function c(e){
                return Promise.resolve( fn() )
                    .then(function t(){
                        throw e;
                    });
            }
        );
    };
}
```

| WARNING: |
| :--- |
| This is only a simple illustration of a basic (not entirely spec-compliant) polyfill for `finally(..)`. Don't use this polyfill in your code; always use a robust, official polyfill wherever possible, such as the collection of polyfills/shims in ES-Shim. |

The `if` statement protects the polyfill definition by preventing it from running in any environment where the JS engine has already defined that method. In older environments, the polyfill is defined, but in newer environments the `if` statement is quietly skipped.

Transpilers like Babel typically detect which polyfills your code needs and provide them automatically for you. But occasionally you may need to include/define them explicitly, which works similar to the snippet we just looked at.

Always write code using the most appropriate features to communicate its ideas and intent effectively. In general, this means using the most recent stable JS version. Avoid negatively impacting the code's readability by trying to manually adjust for the syntax/API gaps. That's what tools are for!

Transpilation and polyfilling are two highly effective techniques for addressing that gap between code that uses the latest stable features in the language and the old environments a site or application needs to still support. Since JS isn't going to stop improving, the gap will never go away. Both techniques should be embraced as a standard part of every JS project's production chain going forward.

## What's in an Interpretation?

A long-debated question for code written in JS: is it an interpreted script or a compiled program? The majority opinion seems to be that JS is an interpreted (scripting) language. But the truth is more complicated than that.

For much of the history of programming languages, "interpreted" languages and "scripting" languages have been looked down on as inferior compared to their compiled counterparts. The reasons for this acrimony are numerous, including the perception that there is a lack of performance optimization, as well as dislike of certain language characteristics, such as scripting languages generally using dynamic typing instead of the "more mature" statically typed languages.

Languages regarded as "compiled" usually produce a portable (binary) representation of the program that is distributed for execution later. Since we don't really observe that kind of model with JS (we distribute the source code, not the binary form), many claim that disqualifies JS from the category. In reality, the distribution model for a program's "executable" form has become drastically more varied and also less relevant over the last few decades; to the question at hand, it doesn't really matter so much anymore what form of a program gets passed around.

These misinformed claims and criticisms should be set aside. The real reason it matters to have a clear picture on whether JS is interpreted or compiled relates to the nature of how errors are handled.

Historically, scripted or interpreted languages were executed in generally a top-down and line-by-line fashion; there's typically not an initial pass through the program to process it before execution begins (see Figure 1).

<figure>
    <img src="images/fig1.svg" width="650" alt="Interpreting a script to execute it" align="center">
    <figcaption><em>Fig. 1: Interpreted/Scripted Execution</em></figcaption>
    <br><br>
</figure>

In scripted or interpreted languages, an error on line 5 of a program won't be discovered until lines 1 through 4 have already executed. Notably, the error on line 5 might be due to a runtime condition, such as some variable or value having an unsuitable value for an operation, or it may be due to a malformed statement/command on that line. Depending on context, deferring error handling to the line the error occurs on may be a desirable or undesirable effect.

Compare that to languages which do go through a processing step (typically, called parsing) before any execution occurs, as illustrated in Figure 2:

<figure>
    <img src="images/fig2.svg" width="650" alt="Parsing, compiling, and executing a program" align="center">
    <figcaption><em>Fig. 2: Parsing + Compilation + Execution</em></figcaption>
    <br><br>
</figure>

In this processing model, an invalid command (such as broken syntax) on line 5 would be caught during the parsing phase, before any execution has begun, and none of the program would run. For catching syntax (or otherwise "static") errors, generally it's preferred to know about them ahead of any doomed partial execution.

So what do "parsed" languages have in common with "compiled" languages? First, all compiled languages are parsed. So a parsed language is quite a ways down the road toward being compiled already. In classic compilation theory, the last remaining step after parsing is code generation: producing an executable form.

Once any source program has been fully parsed, it's very common that its subsequent execution will, in some form or fashion, include a translation from the parsed form of the program—usually called an Abstract Syntax Tree (AST)—to that executable form.

In other words, parsed languages usually also perform code generation before execution, so it's not that much of a stretch to say that, in spirit, they're compiled languages.

JS source code is parsed before it is executed. The specification requires as much, because it calls for "early errors"—statically determined errors in code, such as a duplicate parameter name—to be reported before the code starts executing. Those errors cannot be recognized without the code having been parsed.

So **JS is a parsed language**, but is it *compiled*?

The answer is closer to yes than no. The parsed JS is converted to an optimized (binary) form, and that "code" is subsequently executed (Figure 2); the engine does not commonly switch back into line-by-line execution (like Figure 1) mode after it has finished all the hard work of parsing—most languages/engines wouldn't, because that would be highly inefficient.

To be specific, this "compilation" produces a binary byte code (of sorts), which is then handed to the "JS virtual machine" to execute. Some like to say this VM is "interpreting" the byte code. But then that means Java, and a dozen other JVM-driven languages, for that matter, are interpreted rather than compiled. Of course, that contradicts the typical assertion that Java/etc are compiled languages.

Interestingly, while Java and JavaScript are very different languages, the question of interpreted/compiled is pretty closely related between them!

Another wrinkle is that JS engines can employ multiple passes of JIT (Just-In-Time) processing/optimization on the generated code (post parsing), which again could reasonably be labeled either "compilation" or "interpretation" depending on perspective. It's actually a fantastically complex situation under the hood of a JS engine.

So what do these nitty-gritty details boil down to? Step back and consider the entire flow of a JS source program:

1. After a program leaves a developer's editor, it gets transpiled by Babel, then packed by Webpack (and perhaps half a dozen other build processes), then it gets delivered in that very different form to a JS engine.

2. The JS engine parses the code to an AST.

3. Then the engine converts that AST to a kind-of byte code, a binary intermediate representation (IR), which is then refined/converted even further by the optimizing JIT compiler.

4. Finally, the JS VM executes the program.

To visualize those steps, again:

<figure>
    <img src="images/fig3.svg" width="650" alt="Steps of JS compilation and execution" align="center">
    <figcaption><em>Fig. 3: Parsing, Compiling, and Executing JS</em></figcaption>
    <br><br>
</figure>

Is JS handled more like an interpreted, line-by-line script, as in Figure 1, or is it handled more like a compiled language that's processed in one-to-several passes first, before execution (as in Figures 2 and 3)?

I think it's clear that in spirit, if not in practice, **JS is a compiled language**.

And again, the reason that matters is, since JS is compiled, we are informed of static errors (such as malformed syntax) before our code is executed. That is a substantively different interaction model than we get with traditional "scripting" programs, and arguably more helpful!

### Web Assembly (WASM)

One dominating concern that has driven a significant amount of JS's evolution is performance, both how quickly JS can be parsed/compiled and how quickly that compiled code can be executed.

In 2013, engineers from Mozilla Firefox demonstrated a port of the Unreal 3 game engine from C to JS. The ability for this code to run in a browser JS engine at full 60fps performance was predicated on a set of optimizations that the JS engine could perform specifically because the JS version of the Unreal engine's code used a style of code that favored a subset of the JS language, named "ASM.js".

This subset is valid JS written in ways that are somewhat uncommon in normal coding, but which signal certain important typing information to the engine that allow it to make key optimizations. ASM.js was introduced as one way of addressing the pressures on the runtime performance of JS.

But it's important to note that ASM.js was never intended to be code that was authored by developers, but rather a representation of a program having been transpiled from another language (such as C), where these typing "annotations" were inserted automatically by the tooling.

Several years after ASM.js demonstrated the validity of tooling-created versions of programs that can be processed more efficiently by the JS engine, another group of engineers (also, initially, from Mozilla) released Web Assembly (WASM).

WASM is similar to ASM.js in that its original intent was to provide a path for non-JS programs (C, etc.) to be converted to a form that could run in the JS engine. Unlike ASM.js, WASM chose to additionally get around some of the inherent delays in JS parsing/compilation before a program can execute, by representing the program in a form that is entirely unlike JS.

WASM is a representation format more akin to Assembly (hence, its name) that can be processed by a JS engine by skipping the parsing/compilation that the JS engine normally does. The parsing/compilation of a WASM-targeted program happen ahead of time (AOT); what's distributed is a binary-packed program ready for the JS engine to execute with very minimal processing.

An initial motivation for WASM was clearly the potential performance improvements. While that continues to be a focus, WASM is additionally motivated by the desire to bring more parity for non-JS languages to the web platform. For example, if a language like Go supports threaded programming, but JS (the language) does not, WASM offers the potential for such a Go program to be converted to a form the JS engine can understand, without needing a threads feature in the JS language itself.

In other words, WASM relieves the pressure to add features to JS that are mostly/exclusively intended to be used by transpiled programs from other languages. That means JS feature development can be judged (by TC39) without being skewed by interests/demands in other language ecosystems, while still letting those languages have a viable path onto the web.

Another perspective on WASM that's emerging is, interestingly, not even directly related to the web (W). WASM is evolving to become a cross-platform virtual machine (VM) of sorts, where programs can be compiled once and run in a variety of different system environments.

So, WASM isn't only for the web, and WASM also isn't JS. Ironically, even though WASM runs in the JS engine, the JS language is one of the least suitable languages to source WASM programs with, because WASM relies heavily on static typing information. Even TypeScript (TS)—ostensibly, JS + static types—is not quite suitable (as it stands) to transpile to WASM, though language variants like AssemblyScript are attempting to bridge the gap between JS/TS and WASM.

This book isn't about WASM, so I won't spend much more time discussing it, except to make one final point. *Some* folks have suggested WASM points to a future where JS is excised from, or minimized in, the web. These folks often harbor ill feelings about JS, and want some other language—any other language!—to replace it. Since WASM lets other languages run in the JS engine, on its face this isn't an entirely fanciful fairytale.

But let me just state simply: WASM will not replace JS. WASM significantly augments what the web (including JS) can accomplish. That's a great thing, entirely orthogonal to whether some people will use it as an escape hatch from having to write JS.

## *Strict*ly Speaking

Back in 2009 with the release of ES5, JS added *strict mode* as an opt-in mechanism for encouraging better JS programs.

The benefits of strict mode far outweigh the costs, but old habits die hard and the inertia of existing (aka "legacy") code bases is really hard to shift. So sadly, more than 10 years later, strict mode's *optionality* means that it's still not necessarily the default for JS programmers.

Why strict mode? Strict mode shouldn't be thought of as a restriction on what you can't do, but rather as a guide to the best way to do things so that the JS engine has the best chance of optimizing and efficiently running the code. Most JS code is worked on by teams of developers, so the *strict*-ness of strict mode (along with tooling like linters!) often helps collaboration on code by avoiding some of the more problematic mistakes that slip by in non-strict mode.

Most strict mode controls are in the form of *early errors*, meaning errors that aren't strictly syntax errors but are still thrown at compile time (before the code is run). For example, strict mode disallows naming two function parameters the same, and results in an early error. Some other strict mode controls are only observable at runtime, such as how `this` defaults to `undefined` instead of the global object.

Rather than fighting and arguing with strict mode, like a kid who just wants to defy whatever their parents tell them not to do, the best mindset is that strict mode is like a linter reminding you how JS *should* be written to have the highest quality and best chance at performance. If you find yourself feeling handcuffed, trying to work around strict mode, that should be a blaring red warning flag that you need to back up and rethink the whole approach.

Strict mode is switched on per file with a special pragma (nothing allowed before it except comments/whitespace):

```js
// only whitespace and comments are allowed
// before the use-strict pragma
"use strict";
// the rest of the file runs in strict mode
```

| WARNING: |
| :--- |
| Something to be aware of is that even a stray `;` all by itself appearing before the strict mode pragma will render the pragma useless; no errors are thrown because it's valid JS to have a string literal expression in a statement position, but it also will silently *not* turn on strict mode! |

Strict mode can alternatively be turned on per-function scope, with exactly the same rules about its surroundings:

```js
function someOperations() {
    // whitespace and comments are fine here
    "use strict";

    // all this code will run in strict mode
}
```

Interestingly, if a file has strict mode turned on, the function-level strict mode pragmas are disallowed. So you have to pick one or the other.

The **only** valid reason to use a per-function approach to strict mode is when you are converting an existing non-strict mode program file and need to make the changes little by little over time. Otherwise, it's vastly better to simply turn strict mode on for the entire file/program.

Many have wondered if there would ever be a time when JS made strict mode the default? The answer is, almost certainly not. As we discussed earlier around backwards compatibility, if a JS engine update started assuming code was strict mode even if it's not marked as such, it's possible that this code would break as a result of strict mode's controls.

However, there are a few factors that reduce the future impact of this non-default "obscurity" of strict mode.

For one, virtually all transpiled code ends up in strict mode even if the original source code isn't written as such. Most JS code in production has been transpiled, so that means most JS is already adhering to strict mode. It's possible to undo that assumption, but you really have to go out of your way to do so, so it's highly unlikely.

Moreover, a wide shift is happening toward more/most new JS code being written using the ES6 module format. ES6 modules assume strict mode, so all code in such files is automatically defaulted to strict mode.

Taken together, strict mode is largely the de facto default even though technically it's not actually the default.

## Defined

JS is an implementation of the ECMAScript standard (version ES2019 as of this writing), which is guided by the TC39 committee and hosted by ECMA. It runs in browsers and other JS environments such as Node.js.

JS is a multi-paradigm language, meaning the syntax and capabilities allow a developer to mix and match (and bend and reshape!) concepts from various major paradigms, such as procedural, object-oriented (OO/classes), and functional (FP).

JS is a compiled language, meaning the tools (including the JS engine) process and verify a program (reporting any errors!) before it executes.

With our language now *defined*, let's start getting to know its ins and outs.

[^specApB]: ECMAScript 2019 Language Specification, Appendix B: Additional ECMAScript Features for Web Browsers, https://www.ecma-international.org/ecma-262/10.0/#sec-additional-ecmascript-features-for-web-browsers (latest as of time of this writing in January 2020)
