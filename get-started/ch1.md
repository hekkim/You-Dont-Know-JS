# You Don't Know JS Yet: Get Started - 2nd Edition
# 챕터 1: 자바스크립트란 *무엇*인가?

당신은 아직 JS를 모릅니다. 제가 완벽하게 그러하지 못 하고, 우리 중 그 누구도 그렇지 못 합니다. 다만 우리 모두는 JS를 더 잘 알아갈 수는 있습니다.

You don't know JS, yet. Neither do I, not fully anyway. None of us do. But we can all start getting to know JS better.

*You Don't Know JS Yet* (YDKJSY) 시리즈의 첫 책의 첫 챕터에서는 앞으로 나아가기위한 기초 지식을 쌓을 것입니다. JS가 실제로 어떠한지에 관해 다룸으로써 몇몇 미신과 오해에 관해 명확하게 하여, JS의 세부 사항과 연관된 중요한 배경 지식들의 다방면에 대해 다룰 것입니다.

In this first chapter of the first book of the *You Don't Know JS Yet* (YDKJSY) series, we will take some time to build a foundation to move forward on. We need to start by covering a variety of important background housekeeping details, clearing up some myths and misconceptions about what the language really is (and isn't!).

JS 개발자라면 의래 알아야 할 JS가 어떻게 구성되어 있고 유지되어 가고 있는지 그 정체성과 진행 과정에 관해 알게될 것입니다. JS를 *시작하는* 여정으로 향하는 첫 발판이 되어줄 것입니다.

This is valuable insight into the identity and process of how JS is organized and maintained; all JS developers should understand it. If you want to get to know JS, this is how to *get started* taking the first steps in that journey.

## 이 책에 관해서

*JS를 알아가는* 것은 목적지가 아닌 방향성이기 때문에 여정이란 말을 강조하고 싶습니다. 여태까지 여러분이 얼마나 많은 시간을 이 언어와 함께하던지간에, 여러분은 이 책을 통해 JS에 관한 다른 무언가 배우고 더 잘 이해할 무언가를 계속해서 찾으실 수 있을겁니다. 그러므로 단기간에 무언가를 성취하기 위해 이 책을 허겁지겁 읽는 어리석은 짓을 하지마세요. 대신, 인내와 집요함만이 첫 몇 발걸음을 디디기 위한 최선의 선택이 될 것 입니다.

I emphasize the word journey because *knowing JS* is not a destination, it's a direction. No matter how much time you spend with the language, you will always be able to find something else to learn and understand a little better. So don't look at this book as something to rush through for a quick achievement. Instead, patience and persistence are best as you take these first few steps.

배경 지식을 다루는 현재 챕터 이후에는 YDKJSY 시리즈에서 다뤄질 주제들의 전반적인 내용들을 다룰 것입니다.

Following this background chapter, the rest of the book lays out a high-level map of what you will find as you dig into and study JS with the YDKJSY books.

특히, 챕터 4는 JS를 구성하는 세 가지 주요 기반인 스코프<sup>Scope</sup>와 클로져<sup>Closure</sup>, 프로토타입<sup>Prototype</sup>과 객체<sup>Object</sup>, 그리고 타입<sup>Types</sup>과 강제 변환<sup>Coercion</sup>에 관해 알아보게 될 것입니다. JS는 다양한 특징과 능력이 있는 암시적이고 복잡한 언어이지만, JS의 모든 특징은 위 세 가지 주요 기반에 기초하고 있습니다.

In particular, Chapter 4 identifies three main pillars around which the JS language is organized: scope/closures, prototypes/objects, and types/coercion. JS is a broad and sophisticated language, with many features and capabilities. But all of JS is founded on these three foundational pillars.

이 책이 "시작하기"란 제목을 가지고 있지만 단순한 초보자나 첫 시작을 위한 책이 아님을 새겨두시기 바랍니다. 이 책의 주역할은 나머지 시리즈들에서 JS를 심도있게 공부하기 위한 준비를 하는 것입니다. 그렇기에 나머지 시리즈는 독자분들이 이미 JS와 친숙하다고 가정한 채로 서술할 것입니다. 그러므로 *시작하기*에서 경험을 쌓기위해 충분히 많은 시간을 들여 JS 코드를 작성하십시오.

Keep in mind that even though this book is titled "Get Started," it's **not intended as a beginner/intro book**. This book's main job is to get you ready for studying JS deeply throughout the rest of the series; it's written assuming you already have familiarity with JS over at least several months experience before moving on in YDKJSY. So to get the most out of *Get Started*, make sure you spend plenty of time writing JS code to build up your experience.

만약 이미 충분히 많은 JS 코드를 작성해봤었더라도, 이 책을 그저 훑어보거나 건너뛰지 마시고, 이 책의 내용들을 이해하는데 충분히 많은 시간을 들여주세요. **좋은 시작은 언제나 견고한 첫 발걸음으로부터 늘 시작합니다.**

Even if you've already written a lot of JS before, this book should not be skimmed over or skipped; take your time to fully process the material here. **A good start always depends on a solid first step.**

## 자바스크립트, 그 이름의 유래

자바스크립트란 이름은 아마도 가장 크게 잘못 알려지고 오해받는 프로그래밍 언어 이름일 것입니다.

The name JavaScript is probably the most mistaken and misunderstood programming language name.

자바<sup>Java</sup>랑 연관이 있는 언어일까? 자바 전용 스크립트형 언어일까? 단순 스크립트를 작성하는 실제 프로그램 작성을 위한 언어는 아닌 것일까?

Is this language related to Java? Is it only the script form for Java? Is it only for writing scripts and not real programs?

진실은 자바스크립트란 언어의 이름은 마케팅용 전략의 산물이란 것입니다. Brendan Eich가 처음으로 이 언어를 구상했을 때만해도 Mocha란 코드명을 가지고 있었죠. 넷스케이프<sup>Netscape</sup> 내부에서는 라이브스크립트<sup>LiveScript</sup>라고 이용됐습니다. 하지만 이 언어를 대중에게 공개할 무렵 "자바스크립트"란 이름이 투표에서 이겨버렸었죠.

The truth is, the name JavaScript is an artifact of marketing shenanigans. When Brendan Eich first conceived of the language, he code-named it Mocha. Internally at Netscape, the brand LiveScript was used. But when it came time to publicly name the language, "JavaScript" won the vote.

왜죠? 왜냐하면 이 언어는 기본적으로 대부분의 자바 개발자들의 관심을 끌기위해 설계되었었고, 그 무렵만해도 가벼운 프로그램을 지칭하는데 "스크립트"란 용어를 쓰는게 일반적이였습니다. 이러한 가벼운 "스크립트"는 새로운 웹<sup>Web</sup>이라는 공간 속 페이지에서 처음으로 도입됐죠.

Why? Because this language was originally designed to appeal to an audience of mostly Java programmers, and because the word "script" was popular at the time to refer to lightweight programs. These lightweight "scripts" would be the first ones to embed inside of pages on this new thing called the web!

다시 말해, 자바스크립트는 무겁고 그 당시에 훨씬 더 잘 알려진 자바를 빛 좋은 대용 언어로서 자리잡기 위한 마케팅 전략이였죠. 이러한 점에서 "웹자바"<sup>WebJava</sup>라고 쉽게 부를 수도 있습니다.

In other words, JavaScript was a marketing ploy to try to position this language as a palatable alternative to writing the heavier and more well-known Java of the day. It could just as easily have been called "WebJava," for that matter.

자바스크립트는 자바의 코드와 다소 표면적으로 비슷해 보이는 점은 있습니다만, 그 유사함은 공통적으로 개발하기 위함이 아니라, 두 언어 모두가 C (혹은 더 넓혀서 C++) 개발자들에게 익숙한 문법을 목표로했기 때문입니다.

There are some superficial resemblances between JavaScript's code and Java code. Those similarities don't particularly come from shared development, but from both languages targeting developers with assumed syntax expectations from C (and to an extent, C++).

예로 들어, `{`로 시작하고 `}`로 끝나는 코드 블락은 C/C++ 그리고 Java에서 모두 공통적으로 사용됩니다. 또한 `;`을 통해 문장의 끝맺음 짖죠.

For example, we use the `{` to begin a block of code and the `}` to end that block of code, just like C/C++ and Java. We also use the `;` to punctuate the end of a statement.

어떤면에서는 이러한 문법적인 관계보다 법적관계가 더 깊숙이 연관되어 있기도 합니다. 전신 썬 마이크로시스템즈<sup>Sun</sup>인 오라클<sup>Oracal</sup>은 자바를 소유하고 운영하고 있을뿐만이 아니라 넷스케프를 통해서 "자바스크립트"의 공식 상표 역시도 소유하고 있습니다. 이 상표는 거의 시행되지 않고있으며 그 당시에는 사용이 불가능했을 것입니다.

In some ways, legal relationships run even deeper than the syntax. Oracle (via Sun), the company that still owns and runs Java, also owns the official trademark for the name "JavaScript" (via Netscape). This trademark is almost never enforced, and likely couldn't be at this point.

이러한 이유로 인해 몇몇 사람들은 자바스크립트란 말 대신 JS라고 부르자고 제안하곤 합니다. 공식적으로 대체할 단어가 없는 상황에서는 JS는 매우 흔히 쓰이는 약어입니다. 실은 이 시리즈 전체적으로 JS를 자바스크립트를 칭할 때 주로 쓰이게 될 것입니다.

For these reasons, some have suggested we use JS instead of JavaScript. That is a very common shorthand, if not a good candidate for an official language branding itself. Indeed, these books use JS almost exclusively to refer to the language.

오라클이 소유한 상표와 약간의 거리를 둬보자면, TC39에 의해 명세서가 작성된 언어이자 ECMA 표준기구에 의해 공인된 명칭은 **ECMAScript** 입니다. 실제로는 2016년 이후로 공식 언어 명칭은 개정년도를 어미로 붙여 사용되고 있습니다. 현재 이 책이 쓰인 년도에 따르면 ECMAScript 2019 혹은 줄여서 ES2019라고 쓰입니다.

Further distancing the language from the Oracle-owned trademark, the official name of the language specified by TC39 and formalized by the ECMA standards body is **ECMAScript**. And indeed, since 2016, the official language name has also been suffixed by the revision year; as of this writing, that's ECMAScript 2019, or otherwise abbreviated ES2019.

다시 말해, 여러분의 브라우저 혹은 Node.js에서 실행되는 자바스크립트 혹은 JS는 ES2019 표준의 *하나의* 구현체입니다.

In other words, the JavaScript/JS that runs in your browser or in Node.js, is *an* implementation of the ES2019 standard.

| 노트: |
| :--- |
| 이 언어를 언급할 때 "JS6" 또는 "ES8"과 같이 명명해주지 말아주십시오. 몇몇은 그렇게 사용할지라도 이러한 용어들은 혼란을 지속시킬 뿐입니다. "ES20xx" 혹은 단순히 "JS" 란 용어를 지속해서 사용해주시기 바랍니다. |

| NOTE: |
| :--- |
| Don't use terms like "JS6" or "ES8" to refer to the language. Some do, but those terms only serve to perpetuate confusion. "ES20xx" or just "JS" are what you should stick to. |

이 언어를 자바스크립트, JS, ECMAScript 혹은 ES2019 뭐라고 부르던간에, 이 언어는 절대로 자바의 변형이 아닙니다!

Whether you call it JavaScript, JS, ECMAScript, or ES2019, it's most definitely not a variant of the Java language!

> "자바는 자바스크립트에게 있어 햄과 햄스터의 관계와 같다." --Jeremy Keith, 2009

> "Java is to JavaScript as ham is to hamster." --Jeremy Keith, 2009

## 언어 명세서<sup>Specification</sup>

이전에 언급하였던 TC39란 JS를 관리하는 기술 운영 위원회를 말합니다. 그들의 주요 업무는 언어의 공식 명세<sup>Specification</sup>를 관리하는 것입니다. 그들은 주기적으로 만나 합의된 변경안에 관해 투표하고 표준 기구인 ECMA에 그 결과를 제출합니다.

I mentioned TC39, the technical steering committee that manages JS. Their primary task is managing the official specification for the language. They meet regularly to vote on any agreed changes, which they then submit to ECMA, the standards organization.

ES 명세서에는 JS의 문법과 행동 양식이 정의되어 있습니다.

JS's syntax and behavior are defined in the ES specification.

ES2019는 1995년 JS 창설 이래로 있는 10번째 메이저 명세서이자 수정본<sup>Revision</sup>이고, ECMA가 관리하고 있는 공식 URL을 통해 "10.0" 버전을 찾아볼 수 있습니다.

https://www.ecma-international.org/ecma-262/10.0/

ES2019 happens to be the 10th major numbered specification/revision since JS's inception in 1995, so in the specification's official URL as hosted by ECMA, you'll find "10.0":

https://www.ecma-international.org/ecma-262/10.0/

TC39 위원회는 브라우저 제작자(모질라<sup>Mozilla</sup>, 구글<sup>Google</sup>, 애플<sup>Apple</sup>) 혹은 장비 개발사(삼성<sup>Samsung</sup> 등등)와 같은 웹 투자사의 다양한 집단에서 일하고 있는 50 ~ 100명 사람들로 구성되어 있습니다. 그 중 대다수가 이러한 기업의 직원이고 아마도 회사로부터 위원회로써의 의무를 다함으로써 보상을 받겠지만은 구성원 모두가 자발적 참여자입니다.

The TC39 committee is comprised of between 50 and about 100 different people from a broad section of web-invested companies, such as browser makers (Mozilla, Google, Apple) and device makers (Samsung, etc). All members of the committee are volunteers, though many of them are employees of these companies and so may receive compensation in part for their duties on the committee.

TC39는 일반적으로 매달 모여 약 3일에 걸쳐 지난 회의 이후로의 작업물을 검토하고, 문제에 관해 토론하고, 의견들에 관해 투표를 합니다. 회의 장소는 회의를 주최하려는 구성원들의 회사들 사이에서 순환됩니다.

TC39 meets generally about every other month, usually for about three days, to review work done by members since the last meeting, discuss issues, and vote on proposals. Meeting locations rotate among member companies willing to host.

모든 TC39 제안 과정은 0 단계부터 4 단계까지 총 5개의 단계<sup>Stage</sup> 통해 진행됩니다. 진행 과정에 관해서는 다음의 공식 사이트에서 더 자세히 알 수 있습니다 https://tc39.es/process-document/

All TC39 proposals progress through a five-stage process—of course, since we're programmers, it's 0-based!—Stage 0 through Stage 4. You can read more about the Stage process here: https://tc39.es/process-document/

단계 0는 간단히 얘기하자면 TC39 중 누군가가 괜찮은 방안을 고안해내고 이를 주장<sup>Champion</sup>하고 작업을 착수할 계획을 세웁니다. 이는 곧 TC39의 위원회가 아닌 사람들이 소셜 네트워크나 블로그와 같은 비공식적인 방법을 통해 "제안한" 여러가지 방안은 실질적으로 "0 단계 이전"이라는 얘기입니다. 공식적인 "단계 0"가 되기위해서는 한 TC39 회원이 이 제안을 주장해야만 합니다.

Stage 0 means roughly, someone on TC39 thinks it's a worthy idea and plans to champion and work on it. That means lots of ideas that non-TC39 members "propose," through informal means such as social media or blog posts, are really "pre-stage 0." You have to get a TC39 member to champion a proposal for it to be considered "Stage 0" officially.

일단 어떠한 제안이 "단계 4"에 이르게 되면, 이는 그 다음해의 개정판에 포함되기 충분한 준비가 된 상태가 되었단 얘기입니다. 하나의 제안이 이러한 단계를 거치는데 몇 개월에서 몇 년까지도 걸리수도 있습니다.

Once a proposal reaches "Stage 4" status, it is eligible to be included in the next yearly revision of the language. It can take anywhere from several months to a few years for a proposal to work its way through these stages.

TC39의 Github 저장소에 모든 제안들은 공개되어 관리되고 있습니다: https://github.com/tc39/proposals

All proposals are managed in the open, on TC39's Github repository: https://github.com/tc39/proposals

TC39 위원회든 아니든간에 이런 공공 토론장과 제안서 작업 과정에 참여하는 것은 환영받는 일입니다. 하지만 오직 TC39 위원회만이 회의에 참여할 수 있고 제안과 그 변경에 관해 투표할 수 있습니다. 따라서 사실상 TC39 위원회의 목소리가 JS가 미래 방향에 관해 많은 비중을 차지하고 있는 셈입니다.

Anyone, whether on TC39 or not, is welcome to participate in these public discussions and the processes for working on the proposals. However, only TC39 members can attend meetings and vote on the proposals and changes. So in effect, the voice of a TC39 member carries a lot of weight in where JS will go.

일부는 확신하고 절망적일만큼 계속되고 있는 미신과는 달리, 여러가지 버전의 자바스크립트는 *존재하고 있지 않습니다*. 오직 **한 가지 버전의 JS**만이 TC39와 ECMA에 의해 관리되고 있습니다.

Contrary to some established and frustratingly perpetuated myth, there are *not* multiple versions of JavaScript in the wild. There's just **one JS**, the official standard as maintained by TC39 and ECMA.

2000년대 초반으로 돌아가 마이크로소프트가 분리 관리하고<sup>Forked</sup> 역공학하여<sup>Reverse-engineered</sup> 관리하던 "JScript"가 있던 시절엔, JS는 분명히 "여러 버전"의 JS가 있었습니다. 하지만 이로부터 많은 시간이 흘렀습니다. 현재의 JS에 관해 얘기할 때 이러한 주장은 이제는 완전히 구식이고 더 이상 맞지 않습니다.

Back in the early 2000s, when Microsoft maintained a forked and reverse-engineered (and not entirely compatible) version of JS called "JScript," there were legitimately "multiple versions" of JS. But those days are long gone. It's outdated and inaccurate to make such claims about JS today.

모든 주요 브라우저 및 장비 제작자들은 그들의 JS 구현체가 하나의 중앙화된 명세서에 따라 유지하자고 약속했습니다. 물론, 엔진들은 기능을 각기 다른 시간에 구현합니다. 하지만 이는 크롬의 JS 엔진인 v8 엔진 이 구현한 특정 기능이 모질라의 JS 엔인 스파이더몽키<sup>SpiderMonkey</sup> 엔진 과 다르거나 혹은 호환이 안 된다는 뜻이 아닙니다.

All major browsers and device makers have committed to keeping their JS implementations compliant with this one central specification. Of course, engines implement features at different times. But it should never be the case that the v8 engine (Chrome's JS engine) implements a specified feature differently or incompatibly as compared to the SpiderMonkey engine (Mozilla's JS engine).

이는 곧 여러분이 **하나의 JS**를 공부할 수 있음을 뜻하고 어느곳에서든 똑같은 JS에 의존할 수 있다는 얘기입니다.

That means you can learn **one JS**, and rely on that same JS everywhere.

### JS 관한 웹 규칙의 모든 것

JS 환경이 브라우저에서 서버 그너머 로봇 등등 지속적으로 넓혀진데에 반해 JS를 지배한 단 하나의 환경은 웹입니다. 이는 곧 어떻게 JS가 웹을 위해 구현되는지가 실질적으로 중요한 현실이란 것입니다.

While the array of environments that run JS is constantly expanding (from browsers, to servers (Node.js), to robots, to lightbulbs, to...), the one environment that rules JS is the web. In other words, how JS is implemented for web browsers is, in all practicality, the only reality that matters.

대부분의 경우 특별한 환경에서든 브라우저 기반 JS 엔진에서 구동되든 JS는 정확히 똑같이 정의되어 있습니다. 하지만 분명히 짚고 넘어갈 몇몇 차이점이 있습니다.

For the most part, the JS defined in the specification and the JS that runs in browser-based JS engines is the same. But there are some differences that must be considered.

때때로 JS 명세서는 새롭거나 재정의된 동작을 지시하기도 하지만 브라우저 기반 JS 엔진에서 작동하는 방식과 정확하게 일치하지 않는 경우도 있습니다. 이러한 불일치는 역사적인 문제에 기반하고 있는데, JS 엔진은 웹 컨텐츠가 사용하고있는 기능들의 특이한 경우<sup>Corner case</sup>까지 20년이 넘도록 지원해주고 있습니다. 그로인해 이런 웹 컨텐츠의 손상을 방지하고자 JS 엔진은 때때로 명세서의 변경 사항들을 따르지 않을 수도 있습니다.

Sometimes the JS specification will dictate some new or refined behavior, and yet that won't exactly match with how it works in browser-based JS engines. Such a mismatch is historical: JS engines have had 20+ years of observable behaviors around corner cases of features that have come to be relied on by web content. As such, sometimes the JS engines will refuse to conform to a specification-dictated change because it would break that web content.

이러한 경우 종종 TC39는 역추적을 하기도하고 그러한 웹 환경과 연관된 명세서를 가볍게 순응하기도 합니다. 예로 들어, TC39는 `contains(..)`라는 메서드<sup>Method</sup>를 배열<sup>Array</sup>에 추가할 계획을 갖고 있었지만 몇몇 오래된 JS 프레임워크<sup>Framework</sup>에서 이 메서드가 사용되고 있어 그로 인해 충돌<sup>Conflict</sup>이 발생할 가능성이 있는 걸 발견했습니다. 결국 그들은 충돌이 발생하지 않는 `includes(..)`로 메서드의 이름을 변경하기도 했습니다. 이렇게 희극 혹은 비극같은 JS *커뮤니티내 위기*는 "smooshgate" 라고 불리는 일에도 똑같이 발생했는데, 이 때는 `flatten(..)`으로 계획되었던 메서드는 결국 `flat(..)`이라고 이름을 바꿔야만 됐습니다.

In these cases, often TC39 will backtrack and simply choose to conform the specification to the reality of the web. For example, TC39 planned to add a `contains(..)` method for Arrays, but it was found that this name conflicted with old JS frameworks still in use on some sites, so they changed the name to a non-conflicting `includes(..)`. The same happened with a comedic/tragic JS *community crisis* dubbed "smooshgate," where the planned `flatten(..)` method was eventually renamed `flat(..)`.

하지만 때때로, TC39는 명세서가 그러한 특이한 경우에서도 정확하고 분명하게 작동하도록 결정해야 할 것입니다. 그러한 브라우저 기반 JS 엔진에는 적합하지 않더라도 말이죠.

But occasionally, TC39 will decide the specification should stick firm on some point even though it is unlikely that browser-based JS engines will ever conform.

그럼 이러한 환경에서 해결법은 있을까요? 부록 B "웹 브라우저를 위한 ECMAScript 추가 기능"[^specApB]입니다. JS 명세서는 위 부록에서 자세히 다룰 내용인 공식 JS 명세서와 웹에서 구동되고 있는 JS의 차이에 관한 내용을 포함하고 있습니다. 즉, 이러한 예외점들은 *오직* 웹 JS 환경에서만 있다는 것입니다. 반면, 다른 JS 환경은 설명서에 토씨하나에도 틀리지 않고 정확하게 작동되어야만 합니다.

The solution? Appendix B, "Additional ECMAScript Features for Web Browsers".[^specApB] The JS specification includes this appendix to detail out any known mismatches between the official JS specification and the reality of JS on the web. In other words, these are exceptions that are allowed *only* for web JS; other JS environments must stick to the letter of the law.

섹션 B.1과 B.2에서는 TC39가 JS에서는 공식적으로는 명시되지 않은 그리고 다시 말하지만 역사적인 이유에 근간한 *추가적인* 웹 JS 문법 혹은 API에 관해 다루고 있습니다. `0` 접두사를 가진 8진법 숫자, `escape(..)` / `unescape(..)` 유틸리티 함수, 혹은 String에 있는 `anchor(..)`, `blink()` 함수 RegExp에 있는 `compile(..)` 메서드와 같은 예시들이 있습니다.

Section B.1 and B.2 cover *additions* to JS (syntax and APIs) that web JS includes, again for historical reasons, but which TC39 does not plan to formally specify in the core of JS. Examples include `0`-prefixed octal literals, the global `escape(..)` / `unescape(..)` utilities, String "helpers" like `anchor(..)` and `blink()`, and the RegExp `compile(..)` method.

섹션 B.3에서는 웹과 웹이 아닌 JS 엔진에서 똑같이 사용가능하지만 작동 방식이 다르다던가 그 결과물이 다른 경우에 관해 다룰 것입니다. 위에 나열한 변경점들 대다수는 엄격 모드<sup>Strict mode</sup>에서 작동할 경우 조기 오류들<sup>Early errors</sup>로 분류되는 상황들입니다.

Section B.3 includes some conflicts where code may run in both web and non-web JS engines, but where the behavior *could* be observably different, resulting in different outcomes. Most of the listed changes involve situations that are labeled as early errors when code is running in strict mode.

부록 B *깨달음*에선 흔히 마주치긴 어렵지만 미래의 안전을 위해 피해야만하는 구조들에 관한 좋은 방안에 관해 다룰 것입니다. 가능한 한 특정 JS 환경에서만 적용되는 동작에 의존하지 마시고 어디서든 사용 가능한 JS 명세서를 준수하시기 바랍니다.

Appendix B *gotchas* aren't encountered very often, but it's still a good idea to avoid these constructs to be future safe. Wherever possible, adhere to the JS specification and don't rely on behavior that's only applicable in certain JS engine environments.

### JS가 아니고 웹인 것들...

이것은 JS 프로그램 코드 일까요?

Is this code a JS program?

```js
alert("Hello, JS!");
```

이는 위 코드를 어떻게 바로보냐에 따라 달려있습니다. `alert(..)` 함수<sup>Function</sup>는 JS 명세서에는 없지만, 모든 웹 JS 환경에 *존재*합니다. 하지만, 부록 B에서 이에 관해 찾을 수 없을겁니다.

Depends on how you look at things. The `alert(..)` function shown here is not included in the JS specification, but it *is* in all web JS environments. Yet, you won't find it in Appendix B, so what gives?

브라우저 JS 엔진, Node.js 등등의 다양한 JS 환경에서는 사용자의 브라우저에서 뜨는 경고창과 같이 특정 환경에 특화된 여러 API가 여러분의 JS 프로그램에 추가되어 있습니다.

Various JS environments (like browser JS engines, Node.js, etc.) add APIs into the global scope of your JS programs that give you environment-specific capabilities, like being able to pop an alert-style box in the user's browser.

실제로 `fetch(..)`, `getCurrentLocation(..)` 그리고 `getUserMedia(..)`와 같이 다양한 JS의 API로 보이는 것들은 웹 API입니다. 반면, Node.js 환경에서는 `fs.write(..)`과 같은 내장된 다양한 모듈<sup>Module</sup>을 내장하고 있습니다.

In fact, a wide range of JS-looking APIs, like `fetch(..)`, `getCurrentLocation(..)`, and `getUserMedia(..)`, are all web APIs that look like JS. In Node.js, we can access hundreds of API methods from various built-in modules, like `fs.write(..)`.

`console.log(..)`을 비롯해 모든 `console.*` 메서드는 역시 위와 같은 경우입니다. 이러한 것들은 JS에 명시화되어 있지는 않지만, 어느정도의 합의 하에 보편적인 이용성을 위해 거의 모든 JS 환경에서 정의되어 있습니다.

Another common example is `console.log(..)` (and all the other `console.*` methods!). These are not specified in JS, but because of their universal utility are defined by pretty much every JS environment, according to a roughly agreed consensus.

그래서 결론적으로 `alert(..)` 혹은 `console.log(..)`와 같은 것들은 JS에 정의되어 있지 않습니다. 다만 JS 처럼 *여겨질뿐*입니다. JS 문법을 잘 지키는 그저 함수 혹은 객체 메서드입니다. 이러한 것들이 JS의 환경에서 제 역할을 하기위해 표면적으로 JS에 내재되어 있는 것처럼 보이지만, 그들의 작동 방식은 JS 엔진을 구동하는 환경에의해 관리됩니다.

So `alert(..)` and `console.log(..)` are not defined by JS. But they *look* like JS. They are functions and object methods and they obey JS syntax rules. The behaviors behind them are controlled by the environment running the JS engine, but on the surface they definitely have to abide by JS to be able to play in the JS playground.

브라우저간<sup>Cross-browser</sup> 차이로 인해 발생하는 대부분의 "JS는 너무 일관성이 없다!"란 불평은 실제로는 JS 자체의 작동 방식이 아닌 그들의 환경의 작동 방식의 차이로 인한 것입니다.

Most of the cross-browser differences people complain about with "JS is so inconsistent!" claims are actually due to differences in how those environment behaviors work, not in how the JS itself works.

그래서 `alert(..)`를 호출하는 것은 JS지만 `alert` 자체는 공식 JS 명세서의 부분이 아닌 그저 단순한 손님과도 같은 것입니다.

So an `alert(..)` call *is* JS, but `alert` itself is really just a guest, not part of the official JS specification.

### 항상 JS인 건 아니다

브라우저의 개발자 도구<sup>Developer tools</sup> 혹은 Node에서 콘솔<sup>Console</sup> 혹은 REPL (Read-Evaluate-Print-Loop)을 사용하는 것은 언뜻보기에는 마치 JS 환경인 것 같은 느낌을 줍니다. 하지만 실제로 그렇지 않습니다.

Using the console/REPL (Read-Evaluate-Print-Loop) in your browser's Developer Tools (or Node) feels like a pretty straightforward JS environment at first glance. But it's not, really.

개발자 도구는 그저 개발자들을 위한 도구일 뿐입니다. 개발자 도구는 개발자들의 삶을 조금 더 편하게 만들어 주는 게 주요 목적입니다. 개발자 도구들은 개발자 경험<sup>DX (Developer Experience)</sup>을 최우선으로 합니다. JS의 동작의 미묘한 차이를 정확하고 순수하게 반영하기 위한 도구가 *아닙니다*. 그렇기에 콘솔을 *순수한* JS 환경이라고 여긴다면 많은 우연과도 같은 일들이 "깨달음"을 줬다고 착각해버릴 여지가 있습니다.

Developer Tools are... tools for developers. Their primary purpose is to make life easier for developers. They prioritize DX (Developer Experience). It is *not* a goal of such tools to accurately and purely reflect all nuances of strict-spec JS behavior. As such, there's many quirks that may act as "gotchas" if you're treating the console as a *pure* JS environment.

어쨋든 이러한 편의성은 큰 장점입니다. 전 개발자 도구가 여타 다른 개발자들의 삶을 쉽게 만들어 준다는 사실에 정말 기쁩니다. 변수<sup>Variable</sup>나 프로퍼티<sup>Property</sup>를 자동 완성해주는 것과 같은 매력적인 UX를 가지고 있다는 사실에 매우 만족스럽습니다. 하지만 이러한 개발자 도구들이 JS 프로그램의 엄격한 작동 양식과 늘 동일하게 작동할 거라고 기대하지 않았으면 좋겠다는 점을 짚고 넘어가고 싶습니다. 왜냐하면 그런 용도의 도구들이 아니기 때문이지요.

This convenience is a good thing, by the way! I'm glad Developer Tools make developers' lives easier! I'm glad we have nice UX charms like auto-complete of variables/properties, etc. I'm just pointing out that we can't and shouldn't expect such tools to *always* adhere strictly to the way JS programs are handled, because that's not the purpose of these tools.

이런 도구들의 동작 방식은 브라우저별로 다를뿐더러 (때로는 다소 자주) 바뀌기도 하고 저는 이 곳에서 그 도구들의 디테일한 부분까지 굳이 "하드코드" 하는 것 처럼 다루지 않을 것입니다. 그렇게 될 경우 이 책의 내용들은 너무나도 순식간에 구식의 내용에 관해서 다루게 될 것이니까요.

Since such tools vary in behavior from browser to browser, and since they change (sometimes rather frequently), I'm not going to "hardcode" any of the specific details into this text, thereby ensuring this book text is outdated quickly.

다만, 저는 기본 JS의 동작과 다르다는 점 부각시키기위해 몇몇 JS 콘솔 환경에서 사실처럼 여겨지던 몇몇의 우연히 일어날 수 있는 몇몇 예시들에 관한 힌트만 드리도록 하겠습니다.

But I'll just hint at some examples of quirks that have been true at various points in different JS console environments, to reinforce my point about not assuming native JS behavior while using them:

* 콘솔의 최상위층<sup>Top-level</sup> "글로벌 스코프"<sup>Global scope</sup>에서 선언된 `var` 혹은 `function`은 실제로 글로벌 변수와 그에 상응하는 `window`의 프로퍼티를 생성할까요?

* Whether a `var` or `function` declaration in the top-level "global scope" of the console actually creates a real global variable (and mirrored `window` property, and vice versa!).

* 최상위층 "글로벌 스코프"에서 여러번 `let` 혹은 `const`를 선언할 경우 무슨 일이 생길까요?

* What happens with multiple `let` and `const` declarations in the top-level "global scope."

* .js 파일에서 `"use strict";`를 실행하면 해당 세션을 엄격 모드<sup>Strict mode</sup>로 바꿔주는 것처럼 첫 실행문에서 `"use strict";` 입력후 `<enter>`를 눌러 해당 명령문을 수행하면 해당 콘솔 세션의 나머지는 엄격 모드로 전환될까요?

* Whether `"use strict";` on one line-entry (pressing `<enter>` after) enables strict mode for the rest of that console session, the way it would on the first line of a .js file, as well as whether you can use `"use strict";` beyond the "first line" and still get strict mode turned on for that session.

* 비엄격 모드<sup>Non-strict mode</sup>에서 함수 호출을 하면 `this`는 어떻게 바인딩될까요? 그리고 "글로벌 객체"<sup>Global object</sup>는 글로벌 변수들을 모두 포함하고 있을까요?

* How non-strict mode `this` default-binding works for function calls, and whether the "global object" used will contain expected global variables.

* 여러줄에 걸쳐 입력을 하면 호이스팅<sup>Hoisting</sup>(책 2 *스코프<sup>Scope</sup>와 클로져<sup>Closure</sup>* 참고)은 어떻게 작동할까요?

* How hoisting (see Book 2, *Scope & Closures*) works across multiple line entries.

* 기타 등등...

* ...several others

개발자 콘솔은 마치 JS 컴파일러가 JS 엔진을 통해 .js에 있는 코드를 실행하는 것처럼 행동하려고 노력하지 않습니다. 단지, 여러분에게서 간단한 몇 줄의 코드를 빠르게 입력받고 그 결과를 즉각적으로 보여줘 여러분을 도와줄 뿐입니다. 이러한 부분들은 전적으로 실사용 사례와 다를 뿐더러, 하나의 도구가 개발자 도구와 실환경 모두 동일하게 결과를 내놓으라고 기대하는 것은 불합리하기도 합니다.

The developer console is not trying to pretend to be a JS compiler that handles your entered code exactly the same way the JS engine handles a .js file. It's trying to make it easy for you to quickly enter a few lines of code and see the results immediately. These are entirely different use cases, and as such, it's unreasonable to expect one tool to handle both equally.

개발자 도구에서 보여지는 동작을 JS 문법 *그대로* 나타난다고 믿지 마시고, 명세서를 읽으십시오. 대신해서 콘솔을 "JS 친화적인" 환경이라고 생각하십시오. 개발자 도구는 그럴만한 권리가 있는 유용한 도구입니다.

Don't trust what behavior you see in a developer console as representing *exact* to-the-letter JS semantics; for that, read the specification. Instead, think of the console as a "JS-friendly" environment. That's useful in its own right.

## 다양한 면모

프로그래밍 언어의 그 흐름에서 "패러다임"<sup>Paradigm</sup>이란 말은 코드의 구조화하기 위한 전반적인 사고 방식과 접근법을 말합니다. 패러다임에는 프로그램을 구분하게 해주는 무수히 많은 변형된 방식과 형태들이 존재하고 있습니다. 예를들어 코드에 담긴 그들만의 독특한 특징들을 포함한 셀수없이 많은 라이브러리나 프레임워크들이 그렇습니다.

The term "paradigm" in programming language context refers to a broad (almost universal) mindset and approach to structuring code. Within a paradigm, there are myriad variations of style and form that distinguish programs, including countless different libraries and frameworks that leave their unique signature on any given code.

하지만 프로그램 개개의 모양새가 어떠하든 패러다임에 관한 전반적인 모습은 거의 늘 항상 모든 프로그램을 한 눈에 알 수 있도록 구분되어 있습니다.

But no matter what a program's individual style may be, the big picture divisions around paradigms are almost always evident at first glance of any program.

대표적인 패러다임 수준의 코드 범주로는 절차지향적<sup>Prodedural</sup> 객체지향<sup>Object-oriented (OO/classes)</sup>, 그리고 함수형 프로그래밍<sup>Functional (FP)</sup>이 있습니다.

Typical paradigm-level code categories include procedural, object-oriented (OO/classes), and functional (FP):

* 절차지향적 방식은 절차<sup>Procedure</sup>라고 불리는 상호 연관된 단위들이 함께 묶고, 이러한 절차들을 미리 결정되어있는 작업들의 순서에 맞춰 절차지향적<sup>linear progression</sup>인 과정인 형태인 탑-다운<sup>top-down</sup>으로 코드를 구성합니다.

* Procedural style organizes code in a top-down, linear progression through a pre-determined set of operations, usually collected together in related units called procedures.

* 객체지향 방식은 데이터와 연산 로직을 하나의 클래스라는 단위로 묶어 구성하는 형태를 얘기합니다.

* OO style organizes code by collecting logic and data together into units called classes.

* 함수형 프로그래밍은 코드들을 절차지향과는 다르게 순수 함수 형태로 함수에 구성하고, 이렇게 구성된 함수들을 값으로써 이용합니다.

* FP style organizes code into functions (pure computations as opposed to procedures), and the adaptations of those functions as values.

패러다임은 옳고 그름의 문제가 아닙니다. 단지 패러다임이란 프로그래머가 문제와 해결책에 대한 접근 방법을 안내하고 이를 통해 만들 수 있게해주며, 코드를 정리하고 유지 방법에 관한 방향성에 관한 이야기입니다.

Paradigms are neither right nor wrong. They're orientations that guide and mold how programmers approach problems and solutions, how they structure and maintain their code.

몇몇 언어들은 하나의 패러다임에 지나치게 편향되어 있기도 합니다. C는 절차지향적인 반면 자바와 C++는 거의 전적으로 클래스 지향적이고 하스켈<sup>Haskell</sup>는 함수형 프로그래밍의 연속이죠.

Some languages are heavily slanted toward one paradigm—C is procedural, Java/C++ are almost entirely class oriented, and Haskell is FP through and through.

하지만 많은 언어들은 다양한 패러다임으로부터 유래한 코딩 양식들을 지원하고 심지어는 이들을 같이 사용할 수도 있게 설계되어 있습니다. 그래서 이러한 언어들을 "다중 패러다임 언어"<sup>Multi-paradigm language</sup>라고 부르며 무한한 사용성을 가지고 있습니다. 몇몇 경우 한 프로그램에서 여러 패러다임들이 혼용되어 사용되는 경우도 있습니다.

But many languages also support code patterns that can come from, and even mix and match from, different paradigms. So called "multi-paradigm languages" offer ultimate flexibility. In some cases, a single program can even have two or more expressions of these paradigms sitting side by side.

자바스크립트 또한 다중 패러다임 언어입니다. 자바스크립트는 절차지향적으로도, 클래스 중심으로도, 혹은 함수형 프로그래밍 형식으로도 코드를 짤수 있습니다. 코드 전반에 걸쳐 혹은 특정 하나의 패러다임만을 이용할 수 있도록 강요하지 않고 한줄 한줄 각각 다른 선택을 할 수 있도록 되어있습니다.

JavaScript is most definitely a multi-paradigm language. You can write procedural, class-oriented, or FP-style code, and you can make those decisions on a line-by-line basis instead of being forced into an all-or-nothing choice.

## 하위 호환성<sup>Backwards</sup>과 상위 호환성<sup>Forwards</sup>

자바스크립트가 지향하는 근본적 원리 중 하나는 *하위 호환성*을 유지하는 것입니다. 많은 이들이 이 용어의 함축된 의미를 혼동을 하곤하기도 하고 연관은 있지만 다른 의미인 *상위 호환성*과 종종 헷갈려하기도 합니다.

One of the most foundational principles that guides JavaScript is preservation of *backwards compatibility*. Many are confused by the implications of this term, and often confuse it with a related but different term: *forwards compatibility*.

지금부터 이 용어에 관해 정확하게 정의를 세워보도록 하겠습니다.

Let's set the record straight.

하위 호완성은 만약 JS에 적합하다고 일단 인정이 된다면, 추후에 JS에서 부적합하다고 변경될 일이 없다는 것을 뜻합니다. 원시적이고 제한된 환경이기도 했던 1995에 작성된 코드일지라도 오늘날에도 여전히 작동되야 된다는 것입니다. "저흰 웹을 파괴하지 않을 것입니다!"라고 TC39의 구성원들은 종종 주장하곤 합니다.

Backwards compatibility means that once something is accepted as valid JS, there will not be a future change to the language that causes that code to become invalid JS. Code written in 1995—however primitive or limited it may have been!—should still work today. As TC39 members often proclaim, "we don't break the web!"

이러한 발상은 브라우저 업데이트로 인해 JS 개발자가 작성한 코드가 예상치 못 하게 작동하지 않는 일이 없도록 해주고 이러한 신뢰를 바탕으로 개발자들이 코드를 작성할 수 있게해줍니다. 이는 곧 향후 수 년 동안 프로그램을 위해 JS를 선택하는게 안전하며 현명한 투자가 되도록 해줍니다.

The idea is that JS developers can write code with confidence that their code won't stop working unpredictably because a browser update is released. This makes the decision to choose JS for a program a more wise and safe investment, for years into the future.

이러한 "보장"은 결코 작은 일이 아닙니다. 거의 25년에 가까운 긴 역사를 가진 언어의 하위 호환성을 유지하는 것은 굉장히 부담스러운 일이고 각기 다른 도전 과제들의 항연이기도 합니다. 위원회가 하위호환성을 보존하기 위해 계산하고 산정하는 일은 많이 어려울 것입니다.

That "guarantee" is no small thing. Maintaining backwards compatibility, stretched out across almost 25 years of the language's history, creates an enormous burden and a whole slew of unique challenges. You'd be hard pressed to find many other examples in computing of such a commitment to backwards compatibility.

이러한 원칙을 지키는데 들어가는 비용은 결코 쉽게 넘어갈 수 없습니다. 언어를 변경시키고 확장학 위해 정말로 높은 기준치를 만드는 것은 불가피합니다. 실수이든 아니든 그 어떠한 결정도 결론적으로 영구적이기 때문입니다. 일단 JS에 포함되면, 정말 진심으로 어떠한 기능을 제거하고 싶더라도 결코 빼는 것은 불가능합니다. 왜냐하면 이로인해 아마도 프로그램을 망가뜨릴 수도 있기 때문입니다.

The costs of sticking to this principle should not be casually dismissed. It necessarily creates a very high bar to including changing or extending the language; any decision becomes effectively permanent, mistakes and all. Once it's in JS, it can't be taken out because it might break programs, even if we'd really, really like to remove it!

이러한 규칙에 작은 예외들도 있습니다. JS에는 몇몇 하위 비호환<sup>Backwards-imcompatible</sup>되는 변경점들을 가지고 있는데 TC39는 절대 이러한 예외적인 기능을 사용하지 말아달라고 경고합니다. TC39는 이러한 예외적인 기능들이 만들어내는 결과을 측정하기위해 수집된 브라우저 데이터를 통해 웹상에 존재하는 코드들을 연구하곤 하는데, 이를 통해 브라우저들은 결과적으로 사용자들에게 이런 미세한 예외들을 고칠 때 어떠한 이득에 반하는지 미세한 영향을 가늠하고 감수할지말지 결론을 짓고 투표를 합니다.

There are some small exceptions to this rule. JS has had some backwards-incompatible changes, but TC39 is extremely cautious in doing so. They study existing code on the web (via browser data gathering) to estimate the impact of such breakage, and browsers ultimately decide and vote on whether they're willing to take the heat from users for a very small-scale breakage weighed against the benefits of fixing or improving some aspect of the language for many more sites (and users).

이러한 종류의 변경은 몹시 드물고 대부분의 사이트에서 눈에 띄지 않게 발생하는 특이한 경우들이 그 대부분을 차지합니다.

These kinds of changes are rare, and are almost always in corner cases of usage that are unlikely to be observably breaking in many sites.

*하위 호환성*과 대응 관계에 있는 *상위 호환성<sup>Forwards compatibility</sup>* 과 비교해 보겠습니다. 상위 호환이 된다는 것은 프로그램의 언어에 새로운 추가 기능을 포함해도 이전 버전의 JS 엔진에서 실행된 경우 해당 프로그램이 중단되지 않는다는 얘기입니다. 많은 이들이 원하거나 심지어는 오해하는 경우도 있지만 **JS는 상위 호환적이지 않습니다**.

Compare *backwards compatibility* to its counterpart, *forwards compatibility*. Being forwards-compatible means that including a new addition to the language in a program would not cause that program to break if it were run in an older JS engine. **JS is not forwards-compatible**, despite many wishing such, and even incorrectly believing the myth that it is.

반대로 HTML 그리고 CSS는 하위 호환적이지 않고 상위 호환적입니다. 1995년에 작성된 HTML이나 CSS 지금 살펴보면 작동하지 않는다던가 그 당시와는 다르게 작동할 수도 있습니다. 하지만 만약 2019년에 추가된 기능을 2010년에 만들어진 브라우저에서 사용할 경우 페이지가 망가진 않습니다. 2010년 브라우저에서는 인식되지 않는 CSS/HTML의 경우 무시하고 그렇지 않는 CSS/HTML은 정상적으로 그에 맞게 작동합니다.

HTML and CSS, by contrast, are forwards-compatible but not backwards-compatible. If you dug up some HTML or CSS written back in 1995, it's entirely possible it would not work (or work the same) today. But, if you use a new feature from 2019 in a browser from 2010, the page isn't "broken" -- the unrecognized CSS/HTML is skipped over, while the rest of the CSS/HTML would be processed accordingly.

프로그래밍 언어 설계에 있어서 상위 호환성을 추구하는게 이상적인 것처럼 보이지만 이는 일반적으로는 비현실적입니다. 마크업<sup>Markup</sup>(HTML) 혹은 스타일<sup>Styling</sup>(CSS)은 일반적으로 서술적이고, 그렇기에 인식되는 선언문들에 최소한의 영향을 미치며 인식되지 않는 선언문을 "무시"하는 것이 쉽습니다.

It may seem desirable for forwards-compatibility to be included in programming language design, but it's generally impractical to do so. Markup (HTML) or styling (CSS) are declarative in nature, so it's much easier to "skip over" unrecognized declarations with minimal impact to other recognized declarations.

반면 프로그래밍 언어 엔진이 선택적으로 인식되지 않는 특정 문장 혹은 표현문을 선택적으로 거르게 되면 혼돈과 비결정성이 따라오게 될 것입니다. 마치, 프로그래밍 언어 엔진이 예측하지 못하게 무시되어진 부분이 프로그램의 일부가 제대로 처리될지 안될지 확신을 주지 못 합니다.

But chaos and non-determinism would ensue if a programming language engine selectively skipped statements (or even expressions!) that it didn't understand, as it's impossible to ensure that a subsequent part of the program wasn't expecting the skipped-over part to have been processed.

JS는 상위 호환적이지 않고 그럴수도 없지도 않습니다. 다만, JS에 있는 하위 호환성에 대해 인지하고 또한 이를 통해 얻어지는 웹 환경에 제공되는 지속적인 이득과 제약 그리고 어려움에 관해 알고 있는 것은 중요합니다.

Though JS isn't, and can't be, forwards-compatible, it's critical to recognize JS's backwards compatibility, including the enduring benefits to the web and the constraints and difficulties it places on JS as a result.

### 버전간 간극을 뛰어넘기

JS는 상위 호환적이지 않기때문에 유효한 JS 코드로 작성할 수 있는 코드와 지원 가능한 엔진 버전간의 간극이 언제나 발생할 수 있습니다. 만약 프로그램이 ES2019에서 추가된 특징들을 포함하고 있다면 2016 버전의 엔진에서는 프로그램이 동작하지 않거나 고장나는 것을 아마도 발견할 수 있을 것입니다.

Since JS is not forwards-compatible, it means that there is always the potential for a gap between code that you can write that's valid JS, and the oldest engine that your site or application needs to support. If you run a program that uses an ES2019 feature in an engine from 2016, you're very likely to see the program break and crash.

만약 새로 추가된 문법을 사용하면 프로그램은 일반적으로 완벽하게 컴파일되고 실행되지 않고 일반적으로는 문법 오류<sup>Syntax error</sup>를 만들것입니다. 반면 ES6에서 `Object.is(..)`와 같이 새로 추가된 API를 사용하면 프로그램은 아마도 해당 지점 직전까진 정상적으로 작동하겠지만 해당 문구에서 알수 없는 API를 참조하고 말하며 런타임 오류<sup>Runtime exception</sup>가 발생시키며 작동을 멈출 것입니다.

If the feature is a new syntax, the program will in general completely fail to compile and run, usually throwing a syntax error. If the feature is an API (such as ES6's `Object.is(..)`), the program may run up to a point but then throw a runtime exception and stop once it encounters the reference to the unknown API.

그래서 이것이 JS 개발자들이 항상 추가적인 기능들로부터 뒤쳐져야만 하고 오래된 JS 엔진 환경의 흔적들 사이에서 코딩해야 된다는 뜻일까요? 그렇지 않습니다!

Does this mean JS developers should always lag behind the pace of progress, using only code that is on the trailing edge of the oldest JS engine environments they need to support? No!

다만 JS 개발자들은 이러한 간극에 주의할 필요할 필요가 있다는 애기입니다.

But it does mean that JS developers need to take special care to address this gap.

새롭지만 호환성이 없는 문법들의 경우 트랜스파일<sup>Transpiling</sup>을 통해 해결할 수 있습니다. 트랜스파일은 커뮤니티에 의해 고안된 용어로 프로그램의 원본 소스 코드를 또다른 소스 코드로 바꿔주는 도구를 사용하는 것을 말합니다. 대표적으로 문법과 연관된 상위 호환성 문제는 트랜스파일러<sup>Transpiler</sup>(가장 흔히 바벨<sup>Babel</sup> (https://babeljs.io))를 통해 새로운 JS 문법을 그와 동일하지만 구식의 문법을 가진 형태로 변경해줌으로써 이러한 문제를 해결합니다.

For new and incompatible syntax, the solution is transpiling. Transpiling is a contrived and community-invented term to describe using a tool to convert the source code of a program from one form to another (but still as textual source code). Typically, forwards-compatibility problems related to syntax are solved by using a transpiler (the most common one being Babel (https://babeljs.io)) to convert from that newer JS syntax version to an equivalent older syntax.

아래와 같은 코드 문법을 작성했다고 생각해봅시다.

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

어플리케이션의 소스 코드는 보통 위와 같은 방식으로 구성되어 있기 마련입니다. 하지만 공개 웹사이트에 배포할 파일을 생성할 때, 바벨 트랜스파일러<sup>Babel transpiler</sup>는 이러한 코드를 아래와 같은 코드로 바꿀 것입니다.

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

원본 코드는 블록 스코프에 갇힌<sup>block-scoped</sup> `x`를 `let`을 이용하여 `if`와 `else`문에 걸쳐 생성하고 있지만 상호간 간섭받는 관계에 있지 않습니다. 바벨이 최소한의 재작업을 통해 만든 동일한 프로그램은 두 변수에 각기 다른 이름을 부여하여 그들이 서로간의 혼선을 방지한 결과물을 만들었습니다.

The original snippet relied on `let` to create block-scoped `x` variables in both the `if` and `else` clauses which did not interfere with each other. An equivalent program (with minimal re-working) that Babel can produce just chooses to name two different variables with unique names, producing the same non-interference outcome.

| NOTE: |
| :--- |
| `let`은 2015년 ES6에 추가된 키워드입니다. 앞선 트랜스파일리의 예제에서는 어플리케이션이 ES6 이전 JS 환경에서도 돌아갈 수 있도록 적용되어진 단순한 실례를 보여주기 위함입니다. ES6가 처음 나왔을 때만해도 트랜스파일의 거의 필수적이였지만 2020년에 이르러서는 ES6 이전의 환경을 지원할 필요성은 상대적으로 적어졌습니다. 트랜스파일을 하는데 "타겟"<sup>Target</sup>은 사이트/어플리케이션이 오래된 브라우저/엔진에서 지원 중단이 결정된 경우 오직 그 이상 버전에서만 작동하기위해 사용됩니다. |

| NOTE: |
| :--- |
| The `let` keyword was added in ES6 (in 2015). The preceding example of transpiling would only need to apply if an application needed to run in a pre-ES6 supporting JS environment. The example here is just for simplicity of illustration. When ES6 was new, the need for such a transpilation was quite prevalent, but in 2020 it's much less common to need to support pre-ES6 environments. The "target" used for transpiliation is thus a sliding window that shifts upward only as decisions are made for a site/application to stop supporting some old browser/engine. |

왜 새로운 버전의 문법을 오래된 버전의 문법으로 변경시키기 위해 도구를 사용하는 어려움을 겪어나가야만 하는지 궁금하실 겁니다. 두 변수를 따로 사용하고 `let`이란 키워드를 사용하지 않으면 문제 없는게 아닐까요? 그 이유는 개발자들간 최신 버전의 JS를 이용해 코드를 깔끔하고 효율적인 의사소통을 도와주기 위함입니다.

You may wonder: why go to the trouble of using a tool to convert from a newer syntax version to an older one? Couldn't we just write the two variables and skip using the `let` keyword? The reason is, it's strongly recommended that developers use the latest version of JS so that their code is clean and communicates its ideas most effectively.

개발자들은 새로운 문법을 통해 코드를 깨끗하고 유지하기위해 노력해야 됩니다. 또한, 트랜스파일러를 통해 지원하기로 결정된 특정 버전 이상의 JS 엔진에서 코드들이 적절하게 동작하는 상위 호환적인 결과물을 만들 수 있도록 도와줘야 됩니다.

Developers should focus on writing the clean, new syntax forms, and let the tools take care of producing a forwards-compatible version of that code that is suitable to deploy and run on the oldest-supported JS engine environments.

### 버전간 간극을 채우기

만약 상위 호환 문제가 새로운 문법과 연관없다면 새롭게 추가된 API 메서드의 부래로 인해 생긴 문제일 것입니다. 가장 흔한 해결법은 오래된 브라우저에서는 빠져있는 API 메서드를 정의해줘 마치 오래된 환경에서도 이미 존재했던 것처럼 만들어주는 방법이 있습니다. 이러한 방식을 폴리필<sup>Polyfill</sup> 혹은 심<sup>Shim</sup>이라고 부릅니다.

If the forwards-compatibility issue is not related to new syntax, but rather to a missing API method that was only recently added, the most common solution is to provide a definition for that missing API method that stands in and acts as if the older environment had already had it natively defined. This pattern is called a polyfill (aka "shim").

아래와 같은 코드를 한 번 살펴보겠습니다.

Consider this code:

```js
// getSomeRecords()는 데이터를 가져오는 프로미스(Promise)를 반환합니다
// getSomeRecords() returns us a promise for some
// data it will fetch
var pr = getSomeRecords();

// 데이터를 가져오는 동안 스피너(Spinner)를 보여줍니다
// show the UI spinner while we get the data
startSpinner();

pr
.then(renderRecords)   // 성공시 데이터를 보여줍니다
.catch(showError)      // 그렇지 않다면 오류를 보여줍니다
.finally(hideSpinner)  // 성공, 실패에 상관없이 스피너를 숨겨줍니다
```

이 코드는 ES2019에서 프로미스<sup>Promise</sup> 프로토타입<sup>Prototype</sup>에 추가된 `finally(..)`라는 메서드를 사용합니다. 만약 이러한 코드가 ES2019 이전의 환경에서 사용된다면 `finally(..)`라는 메서드는 존재하지 않기에 오류를 발생시킬겁니다.

This code uses an ES2019 feature, the `finally(..)` method on the promise prototype. If this code were used in a pre-ES2019 environment, the `finally(..)` method would not exist, and an error would occur.

ES2019 이전 버전에서의 `finally(..)`를 폴리필하는 방법은 아래와 같습니다.

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

| 경고: |
| :--- |
| 이건 `finally(..)`를 위한 폴리필에 대한 대략적인 설명일 뿐입니다. 폴리필을 여러분의 코드에 직접적으로 사용하지 마시고, 항상 ES-Shim에 있는 폴리필/심의 집합체처럼 쳬계적이고 공인된 폴리필을 사용하십시오. |

| WARNING: |
| :--- |
| This is only a simple illustration of a basic (not entirely spec-compliant) polyfill for `finally(..)`. Don't use this polyfill in your code; always use a robust, official polyfill wherever possible, such as the collection of polyfills/shims in ES-Shim. |

`if`문은 JS 엔진이 이미 해당 메서드를 정의하고 있는 환경에서도 재정의되는 것을 방지해줍니다. 오직 오래된 환경에서만 폴리필은 정의되고 새로운 환경에서는 `if`문은 실행되지 않고 무시될 것입니다.

The `if` statement protects the polyfill definition by preventing it from running in any environment where the JS engine has already defined that method. In older environments, the polyfill is defined, but in newer environments the `if` statement is quietly skipped.

바벨과 같은 트랜스파일러들은 여러분의 코드들에 필요한 것들을 자동으로 감지하고 제공해주는 폴리필해주는 대표적인 도구입니다. 하지만 위의 예시에서 본 것처럼 때때로 그것들을 명시적으로 포함하거나 정의해줘야 될 때가 있을 수도 있습니다.

Transpilers like Babel typically detect which polyfills your code needs and provide them automatically for you. But occasionally you may need to include/define them explicitly, which works similar to the snippet we just looked at.

항상 그들의 의도에 가장 부합하는 적절한 기능들이 무엇인지 고려하여 코드를 작성해주세요. 이는 곧 가장 안정적인 최신 JS 버전을 사용하란 뜻이기도 합니다. 문법과 API간의 간극을 수동적으로 조정해서 코드의 가독성에 부정적인 영향을 미칠 것을 지양하십시오. 그런 것들은 다른 도구들이 해야될 일입니다!

Always write code using the most appropriate features to communicate its ideas and intent effectively. In general, this means using the most recent stable JS version. Avoid negatively impacting the code's readability by trying to manually adjust for the syntax/API gaps. That's what tools are for!

트랜스파일과 폴리필 하는 것은 최신의 안정적인 기능을 사용한 코드와 지속적으로 지원해줘야 할 오래된 환경을 가진 사이트와 어플리케이션간의 간극을 조정하기 위한 아주 효율적인 기술입니다. JS가 계속해서 발전해 나갈것이므로 이러한 간극은 사라지지 않을 것입니다. 두 기술은 모든 JS 프로젝트의 결과물의 호환성을 보장해주기 위해 사용되어야만 합니다.

Transpilation and polyfilling are two highly effective techniques for addressing that gap between code that uses the latest stable features in the language and the old environments a site or application needs to still support. Since JS isn't going to stop improving, the gap will never go away. Both techniques should be embraced as a standard part of every JS project's production chain going forward.

## 인터프리트<sup>Interpretation</sup>에는 무엇들이 있을까?

JS가 인터프리트 스크립트<sup>Interpreted script</sup>인지 아니면 컴파일된 프로그램<sup>Compiled program</sup>인지는 오래동안 이어져온 논쟁입니다. 대다수의 의견은 JS는 인터프리트 언어 혹은 스크립트 언어라고 얘기하곤 하지만 그 실상은 훨씬 더 복잡합니다.

A long-debated question for code written in JS: is it an interpreted script or a compiled program? The majority opinion seems to be that JS is an interpreted (scripting) language. But the truth is more complicated than that.

프로그래밍 언어의 역사 전반에 있어서 "인터프리트" 언어와 "스크립트" 언어는 컴파일 언어에 비해 상대적으로 하위 언어라고 경시되곤 했습니다. 이러한 악감정에는 다양한 이유가 있는데 그 중 하나는 성능 최적화에 약점이 있단 인식이 있었습니다. 이는 마치 스크립트 언어가 일반적으로 "더 성숙한" 정적 타입 언어<sup>Statically typed languages</sup>가 아닌 동적 타입<sup>Dynamically typing</sup>을 사용한다며 특정 언어의 특성을 혐오하는 것과 같습니다.

For much of the history of programming languages, "interpreted" languages and "scripting" languages have been looked down on as inferior compared to their compiled counterparts. The reasons for this acrimony are numerous, including the perception that there is a lack of performance optimization, as well as dislike of certain language characteristics, such as scripting languages generally using dynamic typing instead of the "more mature" statically typed languages.

"컴파일" 언어라고 여겨지는 언어들은 일반적으로 추후에 실행되기 위해 배포되는 프로그램을 이식 가능한 이진법의<sup>Binary</sup> 형태로 만듭니다. 이진형태가 아닌 소스 코드를 배포하기에 이러한 종류의 모델을 JS에서 발견하지 못 하기에, 많은 사람들은 JS는 컴파일 언어의 범주에 넣기에는 자격요건을 충족시키지 못 한다고 주장합니다. 하지만 실제로 "실행 가능한"<sup>Executable</sup> 형태의 프로그램을 위한 배포 모델은 굉장히 다양해져왔고 또한 서로간의 연관성 역시 떨어져가고 있습니다. 다시 질문으로 돌아와 프로그램의 형태가 어떻던간에 큰 문제가 되지 않습니다.

Languages regarded as "compiled" usually produce a portable (binary) representation of the program that is distributed for execution later. Since we don't really observe that kind of model with JS (we distribute the source code, not the binary form), many claim that disqualifies JS from the category. In reality, the distribution model for a program's "executable" form has become drastically more varied and also less relevant over the last few decades; to the question at hand, it doesn't really matter so much anymore what form of a program gets passed around.

이러한 잘못 알려진 주장과 비판은 사라져야만 합니다. 이 문제에 있어서 정작 중요한 것은 JS가 인터프리트되는지 아니면 컴파일되는지 명확히 알아야되는 이유가 오류가 처리되는 방식과 연관되어 있습니다.

These misinformed claims and criticisms should be set aside. The real reason it matters to have a clear picture on whether JS is interpreted or compiled relates to the nature of how errors are handled.

역사적으로 스크립트 그리고 인터프리트 언어는 일반적으로 탑-다운<sup>Top-down</sup> 방식이고 한 줄씩<sup>Line-by-line</sup> 실행됩니다. 이러한 실행 방식은 일반적으로 프로그램의 실행되기 전에 진행되는 단계가 없습니다.

Historically, scripted or interpreted languages were executed in generally a top-down and line-by-line fashion; there's typically not an initial pass through the program to process it before execution begins (see Figure 1).

<figure>
    <img src="images/fig1.svg" width="650" alt="Interpreting a script to execute it" align="center">
    <figcaption><em>Fig. 1: 인터프리트/스크립트 언어의 실행 과정</em></figcaption>
    <br><br>
</figure>

스크립트 그리고 인터프리트 언어에서 프로그램의 5번째 줄에 있는 오류는 1번째 줄에서 4번째 줄까지 실행될 때까지 발견되지 않습니다. 뚜렷하게도 5번째 줄에 있는 오류는 런타임<sup>Runtime</sup> 상황에서 발생합니다. 예를들어 변수가 값이 작업을 수행하기에 적절하지 않다던가 잘못된 문장이나 명령어로 인한 문제입니다. 그 맥락에 따라 해당 줄에서 오류 처리를 미루는 것이 바람직할 수도 그렇지 않을 수도 있습니다.

In scripted or interpreted languages, an error on line 5 of a program won't be discovered until lines 1 through 4 have already executed. Notably, the error on line 5 might be due to a runtime condition, such as some variable or value having an unsuitable value for an operation, or it may be due to a malformed statement/command on that line. Depending on context, deferring error handling to the line the error occurs on may be a desirable or undesirable effect.

그림 2에 나와있는 것처럼 실행하기 전에 일반적으로 파싱<sup>parsing</sup>이라 부르는 단계를 거치는 언어들과 비교해 봅시다.

Compare that to languages which do go through a processing step (typically, called parsing) before any execution occurs, as illustrated in Figure 2:

<figure>
    <img src="images/fig2.svg" width="650" alt="Parsing, compiling, and executing a program" align="center">
    <figcaption><em>Fig. 2: 파싱, 컴파일, 실행 과정</em></figcaption>
    <br><br>
</figure>

이러한 처리 모델에서는 예를들어 5번째 줄에 있는 문법 오류와 같은 부정확한 문장은 실행되기 전에 파싱 단계에서 잡힐 것이고 프로그램은 실행되지 않을 것입니다. 문법<sup>Syntax</sup> 혹은 "정적"<sup>Static</sup> 오류를 찾아내는 것은 잘못된 부분의 일부를 실행하기 전에 발견하는 것이 일반적으로는 더 좋습니다.

In this processing model, an invalid command (such as broken syntax) on line 5 would be caught during the parsing phase, before any execution has begun, and none of the program would run. For catching syntax (or otherwise "static") errors, generally it's preferred to know about them ahead of any doomed partial execution.

그래서 "파싱되는" 언어와 "컴파일" 언어의 공통점은 무엇일까요? 우선, 모든 컴파일 언어는 파싱됩니다. 얘기인즉슨 파싱된 언어는 이미 컴파일되는 과정으로 향하고 있다는 얘기입니다. 고전 컴파일 이론에서 파싱 이후 가장 마지막 단계는 실행가능한 형태의 코드를 생성하는 단계입니다.

So what do "parsed" languages have in common with "compiled" languages? First, all compiled languages are parsed. So a parsed language is quite a ways down the road toward being compiled already. In classic compilation theory, the last remaining step after parsing is code generation: producing an executable form.

일단 원본 프로그램이 전부 파싱이되면, 일반적으로 프로그램은 보통 추상 구문 트리<sup>Abstract Syntax Tree</sup>(AST) 불리는 파싱된 형태에서 실행가능한 형태로 변경시킵니다.

Once any source program has been fully parsed, it's very common that its subsequent execution will, in some form or fashion, include a translation from the parsed form of the program—usually called an Abstract Syntax Tree (AST)—to that executable form.

다시 말하자면, 파싱된 언어는 그 실행에 앞서 코드 생성을 보통 수행하므로 이를 곧 컴파일 언어라고 얘기하는 것은 그리 어렵지 않습니다.

In other words, parsed languages usually also perform code generation before execution, so it's not that much of a stretch to say that, in spirit, they're compiled languages.

JS 소스 코드는 실행되기 전에 파싱되어집니다. 코드가 실행되기 전에 중복된 매개 변수명이 있는 상황과 같이 정적으로 발견할 수 있는 "조기 오류"<sup>Early error</sup>를 찾아 보고해야하므로 그만큼의 더 많은 명세가 필요합니다. 이러한 오류들은 코드가 파싱되기 전까지는 발견할 수 없습니다.

JS source code is parsed before it is executed. The specification requires as much, because it calls for "early errors"—statically determined errors in code, such as a duplicate parameter name—to be reported before the code starts executing. Those errors cannot be recognized without the code having been parsed.

그러므로 **JS는 파싱된 언어**어지만 *컴파일된 언어*일까요?

So **JS is a parsed language**, but is it *compiled*?

이에 대한 대답은 참에 조금 더 근접합니다. 파싱된 JS는 최적화된 이진법의 형태로 바뀌고 그 후 "코드"의 실행됩니다 (그림 2). 파싱하는 힘든 작업을 모두 끝마친 이후에는 비효율적인 이유로 인해 엔진이 코드를 한 줄씩 실행하는 형태로 돌아가진 않습니다 (그림 1).

The answer is closer to yes than no. The parsed JS is converted to an optimized (binary) form, and that "code" is subsequently executed (Figure 2); the engine does not commonly switch back into line-by-line execution (like Figure 1) mode after it has finished all the hard work of parsing—most languages/engines wouldn't, because that would be highly inefficient.

조금 더 명확하게 "컴파일"은 이진 바이트<sup>Byte</sup> 코드를 생성하고 이 코드들은 "JS 가상 머신"<sup>JS virtual machine</sup>에게 넘깁니다. 누군가는 이 가상 머신은 바이트 코드를 "인터프리트"한다고 얘기하고 싶어할 수도 있습니다. 하지만 이 말은 자바나 자바와 그외의 수십가지의 JVM 중심의 언어 역시도 컴파일이 아닌 인터프리트 된다고 주장하는 것과 같습니다. 물론 이 말은 자바와 같은 언어들이 컴파일 언어라는 일반적인 주장과 상반되어 있습니다.

To be specific, this "compilation" produces a binary byte code (of sorts), which is then handed to the "JS virtual machine" to execute. Some like to say this VM is "interpreting" the byte code. But then that means Java, and a dozen other JVM-driven languages, for that matter, are interpreted rather than compiled. Of course, that contradicts the typical assertion that Java/etc are compiled languages.

흥미롭게도 자바와 자바스크립트는 정말 다른 언어이지만 인터프리트/컴파일과 연관된 논쟁에 관해서는 상호밀접한 관계에 있습니다!

Interestingly, while Java and JavaScript are very different languages, the question of interpreted/compiled is pretty closely related between them!

또다른 불편한 주장은 JS 엔진이 이미 파싱을 통해 생성된 코드에서 각각의 시간에 맞게<sup>JIT</sup>(Just-In-Time) 처리 및 최적화를 여러 단계에 걸쳐 할 수 있다고 얘기하는 것입니다. 그리고 이러한 주장은 또다시 관점에 따라 "컴파일"과 "인터프리트"란 꼬리표를 달게 만듭니다. 이는 실제로 JS엔진의 저면 아래에 있는 몹시 복잡한 상황과 연관이 있습니다.

Another wrinkle is that JS engines can employ multiple passes of JIT (Just-In-Time) processing/optimization on the generated code (post parsing), which again could reasonably be labeled either "compilation" or "interpretation" depending on perspective. It's actually a fantastically complex situation under the hood of a JS engine.

그렇다면 핵심 세부 사항은 무엇일까요? 다시 JS 원본 프로그램의 큰 흐름으로 돌아가 생각해 보겠습니다.

So what do these nitty-gritty details boil down to? Step back and consider the entire flow of a JS source program:

1. 프로그램이 개발자 도구로부터 떠난 뒤로, 이 프로그램은 바벨을 통해 트랜스파일되고 웹팩<sup>Webpack</sup>과 같은 빌드 툴을 통해 포장되어진 후, 매우 다른 형태로 JS 엔진으로 배포된다.

1. After a program leaves a developer's editor, it gets transpiled by Babel, then packed by Webpack (and perhaps half a dozen other build processes), then it gets delivered in that very different form to a JS engine.

2. JS 엔진은 코드를 AST 형태로 파싱한다.

2. The JS engine parses the code to an AST.

3. 엔진은 AST를 이진 중간 표현식<sup>Intermediate representation</sup>(IR)인 바이트 코드의 일종으로 변경시키고, 이는 다시 최적화 JIT 컴파일러를 통해 정제되거나 변경된다.

3. Then the engine converts that AST to a kind-of byte code, a binary intermediate representation (IR), which is then refined/converted even further by the optimizing JIT compiler.

4. 마지막으로, JS 가상 머신은 프로그램을 실행한다.

4. Finally, the JS VM executes the program.

이 과정을 시각화하면 아래와 같습니다.

To visualize those steps, again:

<figure>
    <img src="images/fig3.svg" width="650" alt="Steps of JS compilation and execution" align="center">
    <figcaption><em>Fig. 3: JS에서 파싱, 컴파일 그리고 실행 과정</em></figcaption>
    <br><br>
</figure>

JS는 그림 1에 있는 스크립트 한 줄씩 실행시키는 인터프리트 언어 혹은 그림 2, 3에 나와있듯 실행하기 전 몇몇 단계를 거치는 컴파일 언어에 더 가까울까요?

Is JS handled more like an interpreted, line-by-line script, as in Figure 1, or is it handled more like a compiled language that's processed in one-to-several passes first, before execution (as in Figures 2 and 3)?

그 실체가 어떻던간에 저는 명백하게 **JS는 컴파일 언어**라고 생각합니다.

I think it's clear that in spirit, if not in practice, **JS is a compiled language**.

다시 돌아가, 이러한 논쟁이 중요한 이유는 JS에서 문법 오류와 같은 정적 오류를 컴파일 과정을 통해 코드를 실행하기 전에도 알 수 있다는 것입니다. 이는 전통적인 "스크립트" 프로그램으로 부터 얻는 장점과는 다른 상호 작용할 수 있는 모델이고, 아마도 더 도움이 됩니다!

And again, the reason that matters is, since JS is compiled, we are informed of static errors (such as malformed syntax) before our code is executed. That is a substantively different interaction model than we get with traditional "scripting" programs, and arguably more helpful!

### 웹 어셈블리 (WASM)

JS의 진화를 주도하는 주요 관심사 중 하나는 성능입니다. JS가 얼마나 빠르게 파싱하고 컴파일하며 얼마나 빠르게 컴파일된 코드를 실행시키는지에 관해서죠.

One dominating concern that has driven a significant amount of JS's evolution is performance, both how quickly JS can be parsed/compiled and how quickly that compiled code can be executed.

2013년 모질라 파이어폭스<sup>Mozilla Firefox</sup> 개발자들은 언리얼 3 게임 엔진을 C에서 JS로 포팅<sup>Port</sup>하는데 성공했었습니다. 브라우저의 JS 엔진이 최적화를 통해 최대 60fps 성능으로 이 코드가 작동하리라고 예상됐었습니다. 왜냐하면 언리얼 엔진의 JS 버전은 "ASM.js"라는 JS의 부분 집합에 잘 맞는 코드 형태를 사용했기 때문입니다.

In 2013, engineers from Mozilla Firefox demonstrated a port of the Unreal 3 game engine from C to JS. The ability for this code to run in a browser JS engine at full 60fps performance was predicated on a set of optimizations that the JS engine could perform specifically because the JS version of the Unreal engine's code used a style of code that favored a subset of the JS language, named "ASM.js".

이 부분 집합은 평상시에는 흔히 쓰이지 않는 코딩 스타일이지만 유효한 JS로 쓰였는데 특정 중요한 입력 정보가 엔진에 전달되고 이를 통해 중요한 최적화 되게됩니다. ASM.js는 JS의 런타임 성능에 가해지는 압력을 가하기 위해 도입됐습니다.

This subset is valid JS written in ways that are somewhat uncommon in normal coding, but which signal certain important typing information to the engine that allow it to make key optimizations. ASM.js was introduced as one way of addressing the pressures on the runtime performance of JS.

하지만 중요한 점은 개발자가 ASM.js를 직접 작성할 의도로 만들어지는게 아니고 C와 같은 다른 언어로부터 트랜스파일된 프로그램의 표현식이고 이러한 곳에는 자동으로 "주석<sup>annotations</sup>"이라고 삽입된다.

But it's important to note that ASM.js was never intended to be code that was authored by developers, but rather a representation of a program having been transpiled from another language (such as C), where these typing "annotations" were inserted automatically by the tooling.

수년 후 프로그램을 통해 만들어진 ASM.js가 JS 엔진으로 더 효율적으로 처리될 수 있어 그 유효성이 증명되었고, 다른 기술자들(물론 초기에는 Mozilla에서)이 웹 어셈브리<sup>WASM</sup>을 출시했습니다.

Several years after ASM.js demonstrated the validity of tooling-created versions of programs that can be processed more efficiently by the JS engine, another group of engineers (also, initially, from Mozilla) released Web Assembly (WASM).

웹 어셈블리은 C와 같은 JS가 아닌 프로그램이 JS 엔진에서 실행될 수 있는 형태로 변경시키고자 하는 방향성 자체는 ASM.js과 유사했습니다. 하지만 WASM은 ASM.js와는 다르게 프로그램이 실행되기 전에 JS에서 추가적인 파싱과 컴파일을 과정을 내장해 JS와는 전혀 다른 형태의 프로그램으로 표현하는 방식을 택했습니다.

WASM is similar to ASM.js in that its original intent was to provide a path for non-JS programs (C, etc.) to be converted to a form that could run in the JS engine. Unlike ASM.js, WASM chose to additionally get around some of the inherent delays in JS parsing/compilation before a program can execute, by representing the program in a form that is entirely unlike JS.

웹 어셈블리는 이름에도 드러나는 것과 같이 어셈블리<sup>Assembly</sup>와 유사항 형태로 표현되어 있고 이것은 JS 엔진이 일반적으로 하는 파싱과 컴파일 과정은 건너뛰고 실행되게 됩니다. 웹 어셈블리가 목표로 삼고있는 프로그램의 파싱과 컴파일 단계는 미리<sup>Ahead of time </sup> (AOT) 발생하고 JS 엔진은 최소한의 가공과 함께 이 프로그램을 실행할 수 있는 이진형태로 배포되게 됩니다.

WASM is a representation format more akin to Assembly (hence, its name) that can be processed by a JS engine by skipping the parsing/compilation that the JS engine normally does. The parsing/compilation of a WASM-targeted program happen ahead of time (AOT); what's distributed is a binary-packed program ready for the JS engine to execute with very minimal processing.

웹 어셈블리의 초기 의도는 잠재적인 성능 향상입니다. 초기 목표에 계속해서 집중하는 한 편, 웹 어셈블리는 JS 이외의 언어를 위해 더 많은 동등한 지위<sup>Parity</sup>를 웹 부여하여 웹 플랫폼으로 끌어들이는 것을 추가적인 목표로 삼았습니다. 예를들어 Go와 같은 언어에서 지원되는 스레드 프로그래밍<sup>Threaded programming</sup>은 JS에서는 지원되지 않지만, 웹 어셈블리는 JS 언어 자체에 스레드 관련 기능이 추후에 추가되지 않더라도 Go 프로그램이 JS 엔진에서도 이해 가능한 형태로 변경될 여지를 제공해줍니다.

An initial motivation for WASM was clearly the potential performance improvements. While that continues to be a focus, WASM is additionally motivated by the desire to bring more parity for non-JS languages to the web platform. For example, if a language like Go supports threaded programming, but JS (the language) does not, WASM offers the potential for such a Go program to be converted to a form the JS engine can understand, without needing a threads feature in the JS language itself.

다시 말해, 웹 어셈블리는 JS에 다른 언어로부터 트랜스파일된 프로그램에만 일반적으로 혹은 독점적으로 쓰이는 기능을 추가해야만하는 압박을 덜어주었습니다. 이는 곧 JS 기능 개발은 다른 언어의 이해관계나 요구사항에 의해 왜곡되지 않고도, TC39이 개발 명세서에 관해 결정내릴 수 있으며, 그와 동시에 다른 언어들이 웹으로 오기 위해 독자적인 방법을 채택할 수 있게됐다는 뜻입니다.

In other words, WASM relieves the pressure to add features to JS that are mostly/exclusively intended to be used by transpiled programs from other languages. That means JS feature development can be judged (by TC39) without being skewed by interests/demands in other language ecosystems, while still letting those languages have a viable path onto the web.

웹 어셈블리의 등장에 관한 또다른 관점은 흥미롭게도 웹과 직접적인 연관이 없습니다. 웹 어셈블리는 프로그램이 일단 컴파일되고 다양한 시스템 환경에 실행가능한 형태가 됨으로써 플랫폼 간<sup>Cross-platform</sup>에 가상 머신<sup>Virtual machine</sup> (VM)의 일종으로 진화해 나가고 있습니다.

Another perspective on WASM that's emerging is, interestingly, not even directly related to the web (W). WASM is evolving to become a cross-platform virtual machine (VM) of sorts, where programs can be compiled once and run in a variety of different system environments.

그래서 웹 어셈블리는 단순 웹 혹은 JS만을 위한 것이 아닙니다. 웹 어셈블리는 JS 엔진에서 구동됨에도 불구하고, JS는 웹 어셈블리 프로그램을 위한 가정 적절하지 않은 언어입니다. 왜냐하면 웹 어셈블리는 정적 타입에 지나치게 의존하고 있기 때문입니다. 심지어 표면적으로 JS와 정적 타입의 조합인 타입스크립트<sup>TypeScript</sup>(TS)는 웹 어셈블리로 트랜스파일되기 적절한 언어는 아니지만 어셈블리 스크립트<sup>AssenblyScript</sup>와 같은 변형된 언어는 JS/TS 그리고 웹 어셈블리 간의 간극에 다리를 놓으려고 계속해서 시도하고 있습니다.

So, WASM isn't only for the web, and WASM also isn't JS. Ironically, even though WASM runs in the JS engine, the JS language is one of the least suitable languages to source WASM programs with, because WASM relies heavily on static typing information. Even TypeScript (TS)—ostensibly, JS + static types—is not quite suitable (as it stands) to transpile to WASM, though language variants like AssemblyScript are attempting to bridge the gap between JS/TS and WASM.

이 책은 웹 어셈블리 관한 것이 아니기에 한 가지 마지막 요점에 관해 얘기하며 더 많은 시간을 토론하는데 소비하지 않겠습니다. *몇몇* 사람들은 웹 어셈블리가 JS가 웹에서 비중이 작게 만드는 걸 목표로 하고 있다고 말하고 있습니다. 이런 사람들은 종종 JS에 관한 안 좋은 생각을 가지고 있고 JS를 대체할 다른 언어를 원합니다. 웹 어셈블리는 다른 언어가 JS 엔진에서도 구동될 수 있게 도와주므로 이것의 실상은 완전히 환상적인 동화같은 이야기는 아닙니다.

This book isn't about WASM, so I won't spend much more time discussing it, except to make one final point. *Some* folks have suggested WASM points to a future where JS is excised from, or minimized in, the web. These folks often harbor ill feelings about JS, and want some other language—any other language!—to replace it. Since WASM lets other languages run in the JS engine, on its face this isn't an entirely fanciful fairytale.

제가 간단히 정리해드리겠습니다. 웹 어셈블리는 JS의 대체물이 아닙니다. 웹 어셈블리는 JS를 포함해 웹이 성취할 수 있는 것을 상당부분 강화해줄 수 있습니다. 몇몇 사람들에게는 JS를 사용하는 것으로부터 탈출구 역할을 할 수도 있는 전혀 다른 방향을 제시해주는 대단한 일이 될 수도 있습니다.

But let me just state simply: WASM will not replace JS. WASM significantly augments what the web (including JS) can accomplish. That's a great thing, entirely orthogonal to whether some people will use it as an escape hatch from having to write JS.

## *정확하게* 말하자면

다시 돌아가 2009년 ES5가 배포되던 당시 JS는 더 나은 JS 프로그램을 만들기 위한 사정 동의<sup>Opt-in</sup> 방식으로 *엄격 모드<sup>Strict mode</sup>* 를 추가했습니다.

Back in 2009 with the release of ES5, JS added *strict mode* as an opt-in mechanism for encouraging better JS programs.

엄격 모드의 장점은 그 비용 대비하여 몹시 크지만, 오래된 습관을 버리긴 힘들뿐더러 이미 관성처럼 존재하고 있는 (흔히 "레거시"<sup>Legacy</sup>라고 알려진) 코드 기반은 바꾸기 어렵습니다. 그래서 슬프지만 10년이 지난 후에도 엄격 모드의 *선택성*은 엄격 모드가 JS 프로그래머들을 기본값<sup>Default</sup>이 아님을 뜻합니다.

The benefits of strict mode far outweigh the costs, but old habits die hard and the inertia of existing (aka "legacy") code bases is really hard to shift. So sadly, more than 10 years later, strict mode's *optionality* means that it's still not necessarily the default for JS programmers.

어째서 엄격 모드를 사용할까요? 엄격 모드는 여러분이 할 수 없는 것에 금지시키는 게 아니라 JS 엔진이 코드를 최적화하고 효율적으로 구동하기위한 최선책을 갖게하기위한 최선의 길로 안내해주는 것과 같습니다. 대부분의 JS 코드는 개발자들에 의해 작업되기에 엄격 모드의 *엄격*함은 비엄격 모드에서 발생할 수도 있는 실수를 피하게해줘 협업하는 것을 종종 도와주게 됩니다.

Why strict mode? Strict mode shouldn't be thought of as a restriction on what you can't do, but rather as a guide to the best way to do things so that the JS engine has the best chance of optimizing and efficiently running the code. Most JS code is worked on by teams of developers, so the *strict*-ness of strict mode (along with tooling like linters!) often helps collaboration on code by avoiding some of the more problematic mistakes that slip by in non-strict mode.

대부분의 엄격 모드는 *조기 오류*와 같은 형태로 제어됩니다. 이 말인 즉슨 엄밀하겐 문법 오류는 아니지만 코드가 실행되기 전인 컴파일 단계에서 오류를 발견할 수 있다는 애기입니다. 예를 들어 엄격 모드에서는 두 함수 파라미터를 같은 이름을 갖지 못하고 그 결과를 조기 오류를 발생시킵니다. `this`가 전역 객체 대신 `undefined`로 기본값을 갖고 있는 것처럼 엄격 모드가 런타임에서만 제어되기도 합니다.

Most strict mode controls are in the form of *early errors*, meaning errors that aren't strictly syntax errors but are still thrown at compile time (before the code is run). For example, strict mode disallows naming two function parameters the same, and results in an early error. Some other strict mode controls are only observable at runtime, such as how `this` defaults to `undefined` instead of the global object.

부모님이 하지 말라는 것을 무시하는 아이들처럼 엄격 모드에 관해 토론하고 논쟁하는 것보다, 엄격 모드를 JS가 최상의 품질과 성능을 가지도록 돕는 린터<sup>Linter</sup>와 같이 생각하는 것이 가장 좋은 마음 가짐입니다. 엄격 모드에서 일하려고 노력하는게 마치 자기 자신에게 수갑을 채우는 것처럼만 느껴진다면, 다시 백업하고 전체 접근법에 관해 다시 고려해봐야할 필요가 있다는 빨간 경고 깃발과 같은 것입니다.

Rather than fighting and arguing with strict mode, like a kid who just wants to defy whatever their parents tell them not to do, the best mindset is that strict mode is like a linter reminding you how JS *should* be written to have the highest quality and best chance at performance. If you find yourself feeling handcuffed, trying to work around strict mode, that should be a blaring red warning flag that you need to back up and rethink the whole approach.

특수 프래그마<sup>Pragma</sup>를 이용해 파일별로 엄격 모드로 바꿀 수 있습니다. 이 프래그마 이전에는 주석이나 빈공백<sup>whitespace</sup>을 제외하고는 그 어떠한 것도 있을 수 없습니다.

Strict mode is switched on per file with a special pragma (nothing allowed before it except comments/whitespace):

```js
// 오직 빈공란이나 주석만이 use-strict 프래그마 전에 있을 수 있습니다
// only whitespace and comments are allowed
// before the use-strict pragma
"use strict";
// 엄격 모드가 적용될 파일의 나머지 부분
// the rest of the file runs in strict mode
```

| 경고: |
| :--- |
| 엄격 모드 프래그마 이전에 `;`라도 있다면 이 프래그마는 무용지물이 됩니다. 이 프래그마는 오류도 발생하지 않는데 이는 단지 문자열 리터럴 표현을 가지고 있는 유효한 JS이기 때문입니다. 물론 암묵적으로 엄격 모드로 바꾸지조차 *않습니다*! |

| WARNING: |
| :--- |
| Something to be aware of is that even a stray `;` all by itself appearing before the strict mode pragma will render the pragma useless; no errors are thrown because it's valid JS to have a string literal expression in a statement position, but it also will silently *not* turn on strict mode! |

대신 엄격 모드는 함수의 내부에서 동일한 규치하에 각 함수별로 적용될 수도 있습니다:

Strict mode can alternatively be turned on per-function scope, with exactly the same rules about its surroundings:

```js
function someOperations() {
    // 공란과 주석은 프래그마 이전에 있어도 괜찮습니다
    // whitespace and comments are fine here
    "use strict";

    // 엄격 모드가 적용될 모든 코드들입니다
    // all this code will run in strict mode
}
```

흥미롭게도 한 파일이 엄격 모드로 바뀔 경우 함수 단위의 엄격 모드 프래그마는 사용할 수 없습니다. 그렇기에 여러분은 이 중 하나만 선택해서 사용해야 합니다.

Interestingly, if a file has strict mode turned on, the function-level strict mode pragmas are disallowed. So you have to pick one or the other.

함수별로 엄격 모드를 사용하는 타당한 경우는 **오직** 비엄격 모드의 프로그램 파일을 그 일부를 조금씩 시간에 걸쳐 바꿔야할 때 뿐입니다. 그 외에는 한 파일/프로그램의 전체를 엄격 모드로 바꾸는 게 훨씬 더 낫습니다.

The **only** valid reason to use a per-function approach to strict mode is when you are converting an existing non-strict mode program file and need to make the changes little by little over time. Otherwise, it's vastly better to simply turn strict mode on for the entire file/program.

많은 이들이 JS를 엄격 모드를 기본값으로 만드는 적절한 시기가 있을지 궁금해합니다. 이에대한 대답은 거의 확실하게 할 수 없다입니다. 이미 일전에 하위 호환성에 관해 이야기 했듯이 만약 엄격 모드라고 적혀있지 않더라도 엄격 모드가 적용되게 JS 엔진을 변경하면, 엄격 모드의 규제로 인해 코드가 고장날 수도 있기 때문입니다.

Many have wondered if there would ever be a time when JS made strict mode the default? The answer is, almost certainly not. As we discussed earlier around backwards compatibility, if a JS engine update started assuming code was strict mode even if it's not marked as such, it's possible that this code would break as a result of strict mode's controls.

하지만 엄격 모드가 기본값이 아닌 "모호함"으로 인해 발생하는 미래의 영향들을 제거할 수 있는 몇몇 요소이 있습니다.

However, there are a few factors that reduce the future impact of this non-default "obscurity" of strict mode.

우선 첫번째로, 원본 소스코드에 엄격 모드를 적용하지 않았더라도 트랜스파일된 모든 가상의 코드를 엄격 모드가 적용되게 만들 수 있습니다. 제품에 있는 대부분의 JS 코드는 트랜스파일 되어왔고, 그렇기에 이는 곧 대부분의 JS는 엄격 모드에 기생하고 있다고 볼 수 있습니다. 또한 이러한 가정을 원상태로 돌려놓을수도 있지만 실제로 되돌려야 할 가능성은 매우 낮습니다.

For one, virtually all transpiled code ends up in strict mode even if the original source code isn't written as such. Most JS code in production has been transpiled, so that means most JS is already adhering to strict mode. It's possible to undo that assumption, but you really have to go out of your way to do so, so it's highly unlikely.

게다가 더 많은 그리고 대부분의 새로운 JS 코드를 ES6 모듈을 사용하고자하는 큰 변화가 발생하고 있습니다. ES6 모듈은 엄격 모드 특성을 취하고 있고 그렇기에 이러한 파일들의 모든 코드는 자동으로 엄격 모드를 기본값으로 설정하고 있습니다.

Moreover, a wide shift is happening toward more/most new JS code being written using the ES6 module format. ES6 modules assume strict mode, so all code in such files is automatically defaulted to strict mode.

종합해서, 기술적으로는 엄격 모드가 기본값이 아닐지라도 사실상 기본값이라고 볼 수 있습니다.

Taken together, strict mode is largely the de facto default even though technically it's not actually the default.

## 정의된<sup>Defined</sup>

JS는 ECMAScript 표준(이 시리즈에서는 ES2019 버전)의 구현체이고 이는 ECMA에 의해 주최되는 TC39에 의해 그 방향이 결정되고 있습니다. JS는 브라우저 그리고 Node.js와 같은 환경 모두에서 동작할 수 있습니다.

JS is an implementation of the ECMAScript standard (version ES2019 as of this writing), which is guided by the TC39 committee and hosted by ECMA. It runs in browsers and other JS environments such as Node.js.

JS는 다중 패러다임 언어입니다. 이는 곧 개발자들이 절차지향적, 객체지향 혹은 그리고 함수형 프로그래밍과 같은 다양한 주요 패러다임들의 개념들을 혼합하고 그에 맞춰 유연하게 사용할 수 있는 문법과 사용성을 가지고 있습니다.

JS is a multi-paradigm language, meaning the syntax and capabilities allow a developer to mix and match (and bend and reshape!) concepts from various major paradigms, such as procedural, object-oriented (OO/classes), and functional (FP).

JS는 컴파일 언어입니다. JS는 이것이 실행되기 전에 프로그램 관련한 가공하고 유효성을 검사하는 도구입니다.

JS is a compiled language, meaning the tools (including the JS engine) process and verify a program (reporting any errors!) before it executes.

이제 함께 *정의내린* 이 언어와 함께 이것의 자세한 안과 밖에관해 더 자세히 알아가보도록 하겠습니다.

With our language now *defined*, let's start getting to know its ins and outs.

[^specApB]: ECMAScript 2019 언어 스펙, 부록 B: 웹 브라우저를 위한 ECMAScript의 추가적인 기능들, https://www.ecma-international.org/ecma-262/10.0/#sec-additional-ecmascript-features-for-web-browsers (2020년 1월 기준)

[^specApB]: ECMAScript 2019 Language Specification, Appendix B: Additional ECMAScript Features for Web Browsers, https://www.ecma-international.org/ecma-262/10.0/#sec-additional-ecmascript-features-for-web-browsers (latest as of time of this writing in January 2020)
