---
title: JavsScript 함수와 배열의 기초
date: "2019-08-06T20:30:37.121Z"
template: "post"
draft: false
slug: "/posts/til-javascript-basic/"
category: "JavsScript"
tags:
  - "TIL"
  - "JAVASCRIPT"
description: "JavsScript 함수와 배열의 기초"
---

## 1. Javascript의 함수

### 1. 함수정의

```js
function sum(a, b) {
  return a * b;
}
```

### 2. 함수호출

함수가 정의되면 바로 실행되는 것이 아니다. 함수를 무조건 호출해야 함

```js
sum();
```

### 3. 참고사항

- parameter는 매개변수로 데이터를 기다리는 값이다!
  값을 가지고 있지않은 그냥 빈 데이터 상자라고 생각하면 된다.
  함수의 정의에서 전달받은 인수를 함수 내부로 전달하기 위해 사용하는 변수이며,매개변수는 함수 내에서만 사용됨
  parameter에 들어가는 value값을 우리는 argument(인자)라고 부른다.
  호출할 때 괄호 값에 arugment가 들어가고, 함수로 값을 전달해준다.

- 함수는 return을 하게 되면 함수가 종료된다. 함수는 이름으로 정의하게 되면, 윈도우 안에 메모리 키워드로 저장된다.함수가 상황에 맞게 값이 달라지게 하고 싶으면,parameter와 argument를 사용한다.
  parameter로 변수이름을 지정해서 빈 저장소를 만들어주고, 그에 해당하는 argument값을 넣어줘서 해당 argument값이 출력될 수 있도록 한다.

```javascript
	function alretSuccess(name) {
	   alert(name + “님 로그인 성공!”)
}

	alretSuccess(“김개발”);
```

- alert msg로 “김개발님 로그인성공!” 이라는 메세지가 뜬다.
  여기서 name이 parameter / 함수호출때 사용된 “김개발”은 argument !

- 함수에는 return이라는 게 있는데, return ~ 설정하면 함수가 실행되면
  return하라는 값을 함수실행이 끝나면 리턴해준다.
  모든 함수가 return하는 것은 아님! 리턴하는 것도 있고 아닌 것도 있다.
  함수 안에서 또 함수를 호출할 수도 있다 !(콜백함수라고하는데,,나중에 더자세히 설명을^^!!)
  알고리즘에서 반환한다~가 나오면 return을 활용하는 것이라고 생각하면 됨

## 2. Javascript의 배열

:변수가 몇천개 되어야하는 값이 있을 때, 변수를 그렇게 많은 수로 지정할 수는 없음
여러개의 값을 넣을 수 있는 저장소같은 게 바로 배열!

### 1. 배열 정의

```javascript
let 변수명(name) = [];
const 변수명(name) = [];
```

이렇게 만들어주면 데이터값이 빈 배열이 생성된다.

### 2. 배열의 데이터

배열은 데이터로 다양한 데이터들을 가져올 수 있다.
숫자, string, 다른 배열까지 배열 안으로 들어 올 수 있고, 배열 안에 들은 데이터 요소들도 element라고 부른다.

### 3. 배열의 특징

- 배열은 [ ] 배열 안에 들어있는 element들에게 index를 부여해준다!
- index는 순서라고 생각하면 되고, 0부터 시작한다!

```javascript
let arr = [‘a’, ‘b’, ‘c’ ]
arr[0] = ‘a’
// arr라는 배열에는 ‘a’, ‘b’, ‘c’ 3개의 요소가 있으며, 순서는 0, 1, 2로 정해짐
```

- 배열의 요소를 가져올 때는 배열이름[index] 를 하면 data값이 옴
- 배열은 index로 데이터 값을 가져올 수 있음 ! b는 1번째, c는 2번째 !
- 배열은 요소가 몇개들어있는지도 알 수 있음

```js
arr.length = 3;
// 실제 순서는 0부터 시작하지만 개수를 셀 때는 length는 1부터 시작 !
```

### 4. 배열 조작방법

(1) 배열에 요소추가하는 법
: 배열은 아무데이터도 없이 빈값으로 정의할 수 있다. 데이터를 넣어주는
방법이 다양하다!

- 가장 기본적인 방법

```javascript
let cities = [];
// 배열정의 완료
// 배열을 추가할 때는 배열변수이름[index] = “data value” 이런식으로 추가해주면 된다.
cities[0] = “서울”
cities[1] = “제주도”
console.log(cities);
// 출력: cities = [“서울”, “제주도” ]
// index 순서와 상관없이 순서대로 지정하지않아도 데이터값 넣을 수 있음
```

- array.push

  array.push를 사용하면 배열의 맨 끝자리에 데이터 값을 넣을 수 있음

```js
let cities = [] ;
cities.push(“경주”, “전주”);
// 출력: cities = [“경주”, “전주”]
```

- array.unshift

  array.unshift를 사용하면 배열의 맨 앞자리에 데이터 값을 넣을 수 있음

```javascript
  let cities = [“경주”,”전주”];
  cities.unshift(“인천”);
  console.log(cities) ;
  //출력: [“인천”, “경주”, “전주”]
```

(2) 배열에서 요소삭제하는 법

- array.pop()

  pop method를 사용하면 맨 뒤에 있는 element 제거 가능

```javascript
let cities = [ “서울”, ”부산”, ”제주도”] ;
cities.pop();
console.log(cities) ;
//출력: [“서울”,”부산” ]
```
