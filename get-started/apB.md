# You Don't Know JS Yet: Get Started - 2nd Edition
# 부록 B: 연습, 연습, 그리고 또 연습!
# Appendix B: Practice, Practice, Practice!

이 부록에서는 몇몇 예제와 제시되는 답안들에 관해 살펴보도록 하겠습니다. 이 예제들은 이 책에서 다룬 개념들을 연습하는 *시작하기*일 분입니다.

In this appendix, we'll explore some exercises and their suggested solutions. These are just to *get you started* with practice over the concepts from the book.

## 비교 연습하기

## Practicing Comparisons

챕터 4, 기반 3에서 다루었던 강제 변환이 필요한 값 타입과 비교하는 것을 연습해보도록 하겠습니다.

Let's practice working with value types and comparisons (Chapter 4, Pillar 3) where coercion will need to be involved.

`scheduleMeeting(..)`은 미팅 시작 시간과 미팅 시간을 취하는 함수입니다. 미팅이 전적으로 `dayStart`와 `dayEnd`에 따라 일하는 시간내에 미팅이 잡힌다면 `true`를 반환합니다. 반면 일하는 시간을 넘어선다면 `false`를 반환하게 됩니다.

`scheduleMeeting(..)` should take a start time (in 24-hour format as a string "hh:mm") and a meeting duration (number of minutes). It should return `true` if the meeting falls entirely within the work day (according to the times specified in `dayStart` and `dayEnd`); return `false` if the meeting violates the work day bounds.

```js
const dayStart = "07:30";
const dayEnd = "17:45";

function scheduleMeeting(startTime,durationMinutes) {
    // ..TODO..
}

scheduleMeeting("7:00",15);     // false
scheduleMeeting("07:15",30);    // false
scheduleMeeting("7:30",30);     // true
scheduleMeeting("11:30",60);    // true
scheduleMeeting("17:00",45);    // true
scheduleMeeting("17:30",30);    // false
scheduleMeeting("18:00",15);    // false
```

먼저 풀어보십시오. 동일함과 관계형 비교 연산자의 이용법 그리고 강제 변환이 코드에 어떤 영향을 어떻게 미치는지 고려해보시기 바라겠습니다. 일단 코드가 작동하면 여러분의 답안을 부록 마지막에 있는 "제시된 답안"과 *비교해 보시기 바랍니다.*

Try to solve this yourself first. Consider the usage of equality and relational comparison operators, and how coercion impacts this code. Once you have code that works, *compare* your solution(s) to the code in "Suggested Solutions" at the end of this appendix.

## 클로져 연습하기

## Practicing Closure

이제 챕터 4 기반 1에서 다룬 클로져를 한 번 연습해보겠습니다.

Now let's practice with closure (Chapter 4, Pillar 1).

`range(..)` 함수는 반환될 배열에서 첫 번째로 나타나는 숫자를 첫 번째 인수로 받습니다. 두 번째 인수는 배열에서 마지막으로 나올 숫자를 나타냅니다. 두 번째 인수가 빠진채 호출이 되면 나머지 하나 인수를 받을 수 있는 또다른 함수가 반환됩니다.

The `range(..)` function takes a number as its first argument, representing the first number in a desired range of numbers. The second argument is also a number representing the end of the desired range (inclusive). If the second argument is omitted, then another function should be returned that expects that argument.

```js
function range(start,end) {
    // ..TODO..
}

range(3,3);    // [3]
range(3,8);    // [3,4,5,6,7,8]
range(3,0);    // []

var start3 = range(3);
var start4 = range(4);

start3(3);     // [3]
start3(8);     // [3,4,5,6,7,8]
start3(0);     // []

start4(6);     // [4,5,6]
```

먼저 직접 풀어보시기 바랍니다.

Try to solve this yourself first.

일단 코드가 작동하면 여러분의 답안을 부록 마지막에 있는 "제시된 답안"과 *비교해 보시기 바랍니다.*

Once you have code that works, *compare* your solution(s) to the code in "Suggested Solutions" at the end of this appendix.

## 프로토타입 연습하기

## Practicing Prototypes

마지막으로 챕터 4 기반 2에서 보았던 프로토타입을 통해 `this`와 객체를 연결하는 것을 연습해보겠습니다.

Finally, let's work on `this` and objects linked via prototype (Chapter 4, Pillar 2).

각각 `spin()`을 가지고 있는 릴 세개와 이를 가지고 있는 슬롯 머신을 정의하십시오. 이 슬롯 머신은 `display()`을 가지고 있으며 모든 릴의 현재 내용물을 보여줍니다.

Define a slot machine with three reels that can individually `spin()`, and then `display()` the current contents of all the reels.

릴의 기본 동작은 `reel` 객체 아래에 정의됩니다. 하지만 슬롯 머신은 개별 릴 객체들이 필요하며 릴 객체에게 동작을 위임할 수 있습니다. 각 릴은 `position` 프로퍼티를 가지게 됩니다.

The basic behavior of a single reel is defined in the `reel` object below. But the slot machine needs individual reels—objects that delegate to `reel`, and which each have a `position` property.

릴은 단지 `display()` 자신의 슬롯 문양을 보여주는 *방법을 알지만* 슬롯 머신은 현재 슬롯 `position`, 위에 있는 슬롯 `position - 1`, 아래 슬롯 `position + 1` 이렇게 세 개의 문양을 각 릴별로 보여줄 수 있습니다. 그러므로 슬롯 머신은 3 x 3 그리드의 슬롯 문양을 보여줄 수 있습니다.

A reel only *knows how* to `display()` its current slot symbol, but a slot machine typically shows three symbols per reel: the current slot (`position`), one slot above (`position - 1`), and one slot below (`position + 1`). So displaying the slot machine should end up displaying a 3 x 3 grid of slot symbols.

```js
function randMax(max) {
    return Math.trunc(1E9 * Math.random()) % max;
}

var reel = {
    symbols: [
        "♠", "♥", "♦", "♣", "☺", "★", "☾", "☀"
    ],
    spin() {
        if (this.position == null) {
            this.position = randMax(
                this.symbols.length - 1
            );
        }
        this.position = (
            this.position + 100 + randMax(100)
        ) % this.symbols.length;
    },
    display() {
        if (this.position == null) {
            this.position = randMax(
                this.symbols.length - 1
            );
        }
        return this.symbols[this.position];
    }
};

var slotMachine = {
    reels: [
        // this slot machine needs 3 separate reels
        // hint: Object.create(..)
    ],
    spin() {
        this.reels.forEach(function spinReel(reel){
            reel.spin();
        });
    },
    display() {
        // TODO
    }
};

slotMachine.spin();
slotMachine.display();
// ☾ | ☀ | ★
// ☀ | ♠ | ☾
// ♠ | ♥ | ☀

slotMachine.spin();
slotMachine.display();
// ♦ | ♠ | ♣
// ♣ | ♥ | ☺
// ☺ | ♦ | ★
```

먼저 직접 풀어보시기 바랍니다.

Try to solve this yourself first.

힌트:

Hints:

* 릴의 문양을 순환하며 접근하기위해 `position`을 `%` 모듈로 연산자를 사용하여 감싸 안으십시오.

* Use the `%` modulo operator for wrapping `position` as you access symbols circularly around a reel.

* `Object.create(..)`을 이용하여 객체를 만드시고 다른 객체와 프로토타입 결합하십시오. 일단 결합이되면 메서드 호출 도중 위임은 객체가 `this` 컨텍스트를 공유할 것입니다.

* Use `Object.create(..)` to create an object and prototype-link it to another object. Once linked, delegation allows the objects to share `this` context during method invocation.

* 각 세 개의 위치를 보여주기 위해 reel 객체를 직접 수정하는 대신 자체적으로 `position`을 가지고 있을 임시 객체를 `Object.create(..)` 이용할 수도 있습니다.

* Instead of modifying the reel object directly to show each of the three positions, you can use another temporary object (`Object.create(..)` again) with its own `position`, to delegate from.

일단 코드가 작동하면 여러분의 답안을 부록 마지막에 있는 "제시된 답안"과 *비교해 보시기 바랍니다.*

Once you have code that works, *compare* your solution(s) to the code in "Suggested Solutions" at the end of this appendix.

## 제시된 답안

## Suggested Solutions

단지 제시된 답안일 뿐임을 명심해주기 바랍니다. 연습 문제를 풀 수 있는 다양한 방법이 있습니다. 여러분의 접근법을 여기 보이는 답안들과 비교해보시고 각각의 장단에 관해 곰곰히 생각해보십시오.

Keep in mind that these suggested solutions are just that: suggestions. There's many different ways to solve these practice exercises. Compare your approach to what you see here, and consider the pros and cons of each.

기반 3과 연관된 "비교" 연습하기를 위한 제시된 답안:

Suggested solution for "Comparisons" (Pillar 3) practice:

```js
const dayStart = "07:30";
const dayEnd = "17:45";

function scheduleMeeting(startTime,durationMinutes) {
    var [ , meetingStartHour, meetingStartMinutes ] =
        startTime.match(/^(\d{1,2}):(\d{2})$/) || [];

    durationMinutes = Number(durationMinutes);

    if (
        typeof meetingStartHour == "string" &&
        typeof meetingStartMinutes == "string"
    ) {
        let durationHours =
            Math.floor(durationMinutes / 60);
        durationMinutes =
            durationMinutes - (durationHours * 60);
        let meetingEndHour =
            Number(meetingStartHour) + durationHours;
        let meetingEndMinutes =
            Number(meetingStartMinutes) +
            durationMinutes;

        if (meetingEndMinutes >= 60) {
            meetingEndHour = meetingEndHour + 1;
            meetingEndMinutes =
                meetingEndMinutes - 60;
        }

        // 시간 문자열을 비교하기 쉽게 재구성합니다
        // re-compose fully-qualified time strings
        // (to make comparison easier)
        let meetingStart = `${
            meetingStartHour.padStart(2,"0")
        }:${
            meetingStartMinutes.padStart(2,"0")
        }`;
        let meetingEnd = `${
            String(meetingEndHour).padStart(2,"0")
        }:${
            String(meetingEndMinutes).padStart(2,"0")
        }`;

        // 노트: 표현식 모두가 문자열이기때문에 여기에 있는
        // 비교식은 알파벳 순서대로 하게됩니다. 하지만
        // 이 역시 안전한데 그 이유는 문자열 비교가
        // 시간 비교를 위해 충분하기 때문입니다.
        // (예시: "07:15" < "07:30")
        // NOTE: since expressions are all strings,
        // comparisons here are alphabetic, but it's
        // safe here since they're fully qualified
        // time strings (ie, "07:15" < "07:30")
        return (
            meetingStart >= dayStart &&
            meetingEnd <= dayEnd
        );
    }

    return false;
}

scheduleMeeting("7:00",15);     // false
scheduleMeeting("07:15",30);    // false
scheduleMeeting("7:30",30);     // true
scheduleMeeting("11:30",60);    // true
scheduleMeeting("17:00",45);    // true
scheduleMeeting("17:30",30);    // false
scheduleMeeting("18:00",15);    // false
```

----

기반 1과 연관된 "클로져" 연습하기를 위한 제시된 답안:

Suggested solution for "Closure" (Pillar 1) practice:

```js
function range(start,end) {
    start = Number(start) || 0;

    if (end === undefined) {
        return function getEnd(end) {
            return getRange(start,end);
        };
    }
    else {
        end = Number(end) || 0;
        return getRange(start,end);
    }


    // **********************

    function getRange(start,end) {
        var ret = [];
        for (let i = start; i <= end; i++) {
            ret.push(i);
        }
        return ret;
    }
}

range(3,3);    // [3]
range(3,8);    // [3,4,5,6,7,8]
range(3,0);    // []

var start3 = range(3);
var start4 = range(4);

start3(3);     // [3]
start3(8);     // [3,4,5,6,7,8]
start3(0);     // []

start4(6);     // [4,5,6]
```

----

기반 2과 연관된 "프로토타입" 연습하기를 위한 제시된 답안:

Suggested solution for "Prototypes" (Pillar 2) practice:

```js
function randMax(max) {
    return Math.trunc(1E9 * Math.random()) % max;
}

var reel = {
    symbols: [
        "♠", "♥", "♦", "♣", "☺", "★", "☾", "☀"
    ],
    spin() {
        if (this.position == null) {
            this.position = randMax(
                this.symbols.length - 1
            );
        }
        this.position = (
            this.position + 100 + randMax(100)
        ) % this.symbols.length;
    },
    display() {
        if (this.position == null) {
            this.position = randMax(
                this.symbols.length - 1
            );
        }
        return this.symbols[this.position];
    }
};

var slotMachine = {
    reels: [
        Object.create(reel),
        Object.create(reel),
        Object.create(reel)
    ],
    spin() {
        this.reels.forEach(function spinReel(reel){
            reel.spin();
        });
    },
    display() {
        var lines = [];

        // display all 3 lines on the slot machine
        for (
            let linePos = -1; linePos <= 1; linePos++
        ) {
            let line = this.reels.map(
                function getSlot(reel){
                    var slot = Object.create(reel);
                    slot.position = (
                        reel.symbols.length +
                        reel.position +
                        linePos
                    ) % reel.symbols.length;
                    return reel.display.call(slot);
                }
            );
            lines.push(line.join(" | "));
        }

        return lines.join("\n");
    }
};

slotMachine.spin();
slotMachine.display();
// ☾ | ☀ | ★
// ☀ | ♠ | ☾
// ♠ | ♥ | ☀

slotMachine.spin();
slotMachine.display();
// ♦ | ♠ | ♣
// ♣ | ♥ | ☺
// ☺ | ♦ | ★
```

이 책은 여기까지입니다. 하지만 진짜 이러한 개념들을 연습할 현장의 프로젝트를 살펴볼 시간입니다. 계속해서 코딩하십시오. 왜냐하면 그것이 학습하는데 최선의 방법이기 때문입니다.

That's it for this book. But now it's time to look for real projects to practice these ideas on. Just keep coding, because that's the best way to learn!
