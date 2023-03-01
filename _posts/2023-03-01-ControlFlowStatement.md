---
title: "[Javascript] 9장 제어문"
excerpt: "블록문, 조건문 (if else, switch), 반복문(for, while, do while), break, continue 문"

categories:Javascript

permalink: categories/javascript/control/

toc: true
toc_sticky: true

date: 2022-03-01
last_modified_at: 2022-03-01
---

# 8장 제어문

*블록문, 조건문 (if else, switch), 반복문(for, while, do while), break, continue 문*

8.1 제어문(control flow statement)

조건에 따라 코드 블록을 실행(조건문)하거나 반복 실행(반복문)할 때 사용함. 일반적으로 코드는 위에서 아래 방향으로 실행되지만, 재어문을 사용하면 코드의 실행 흐름을 인위적으로 제어할 수 있음.

블록문(block statement / compound statement)

0개 이상의 문을 중괄호로 묶은 것. 자바스크립트에서 블록문은 하나의 실행 단위

블록문 사용 예시:

```jsx
// 블록문
{
  var foo = 10;
}

// 제어문
var x = 1;
if (x < 10) {
  x++;
}

// 함수 선언문
function sum(a, b) {
  return a + b;
}
```

8.2 조건문(conditional statement)

주어진 조건식(conditional expression)의 평가 결과에 따라 코드 블록의 실행을 결정.

8.2.1 if…else문:

```jsx
if (조건식1) {
  // 조건식1이 참일때 실행되는 코드 블록
} else if (조건식2) {
  // 조건식2가 참일때 실행되는 코드 블록
} else {
  kind = '영';
}
console.log(kind); // 양수
```

만약 코드 블록내의 문이 하나라면 중괄호 생략가능

```jsx
var num = 2;
var kind;

if (num > 0)      kind = '양수';
else if (num < 0) kind = '음수';
else              kind = '영';

console.log(kind);
```

위 예제를 삼항 조건 연산자로 바꿔 쓴다면?

```jsx
var x = 2;

// 0은 false로 취급된다.
var result = x % 2 ? '홀수' : '짝수';
console.log(result);

//경우의 수가 세가지인 경우

// 0은 false로 취급된다.
var kind = num ? (num > 0 ? '양수' : '음수') : '영';

console.log(kind); // 양수
```

삼항 조건 연산자와 if else문의 차이는?

삼항 조건 연산자는 값으로 평가되는 표현식이라서 변수에 할당 가능. if else는 표현식이 아닌 문임.

8.2.2 switch문
switch문은 주어진 표현식을 평가하여 그 값과 일치하는 case문으로 실행 흐름을 옮김.

표현식과 일치하는 case가 없다면, 실행 순서는 default문으로 이동 (선택 사항)

if else문이 불리언 값으로 평가된다면(논리적 참, 거짓), switch문은 문자열이나 숫자 값인 경우가 많음(다양한 상황).

예시)

케이스 사이에 break를 주지 않으면, 모든 케이스 문을 질행하는 풀스루를 하게 됨.

조건이 너무 많은 경우에는 if else보다 가독성이 더 좋음.

```jsx
// 월을 영어로 변환한다. (11 → 'November')
var month = 11;
var monthName;

switch (month) {
  case 1: monthName = 'January';
    break;
  case 2: monthName = 'February';
    break;
  case 3: monthName = 'March';
    break;
  case 4: monthName = 'April';
    break;
  case 5: monthName = 'May';
    break;
  case 6: monthName = 'June';
    break;
  case 7: monthName = 'July';
    break;
  case 8: monthName = 'August';
    break;
  case 9: monthName = 'September';
    break;
  case 10: monthName = 'October';
    break;
  case 11: monthName = 'November';
    break;
  case 12: monthName = 'December';
    break;
  default: monthName = 'Invalid month';
}

console.log(monthName); // November
```

8.3 반복문

8.31 for문:
반목문 loop statement는 조건식의 평가 결과가 참인 경우 코드 블록을 실행함. 조건식이 거짓일 때까지. 어떤 식도 선언하지 않으면 무한루프가 됨. 이중중첩 for문 사용가능

```jsx
for (var i = 0; i < 2; i++) {
  console.log(i);
}
```

8.32 while 문:

평가 결과가 거직이 되면 종료. 주로 반복횟수가 불명확할 때 사용

```jsx
// 무한루프
while (true) {
  console.log(count);
  count++;
  // count가 3이면 코드 블록을 탈출한다.
  if (count === 3) break;
} // 0 1 2
```

8.33 do while 문:
코드 블록을 먼저 실행하고, 조건식을 실행하는 경우.

```jsx
var count = 0;

// count가 3보다 작을 때까지 코드 블록을 계속 반복 실행한다.
do {
  console.log(count);
  count++;
} while (count < 3); // 0 1 2
```

8.4 break문

레이블문, 반복문을 탈출.

```jsx
// foo라는 식별자가 붙은 레이블 블록문
foo: {
  console.log(1);
  break foo; // foo 레이블 블록문을 탈출한다.
  console.log(2);
}

console.log('Done!');
```

8.5 continue문

반복문의 코드 블록을 해당 지점에서 중단하고, 반복문의 증감식으로 실행 흐름을 이동 시킴. (break문처럼 반복문 탈출하지 않음)

```jsx
var string = 'Hello World.';
var search = 'l';
var count = 0;

// 문자열은 유사배열이므로 for 문으로 순회할 수 있다.
for (var i = 0; i < string.length; i++) {
  // 'l'이 아니면 현 지점에서 실행을 중단하고 반복문의 증감식으로 이동한다.
  if (string[i] !== search) continue;
  count++; // continue 문이 실행되면 이 문은 실행되지 않는다.
}

console.log(count); // 3

// 참고로 String.prototype.match 메서드를 사용해도 같은 동작을 한다.
const regexp = new RegExp(search, 'g');
console.log(string.match(regexp).length); // 3
```
