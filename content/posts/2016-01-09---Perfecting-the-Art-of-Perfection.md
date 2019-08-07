---
title: 20190807 TIL 
date: "2019-08-07T17:32:37.121Z"
template: "post"
draft: false
slug: "/posts/haileyself/github/"
category: "TIL"
tags:
  - "TIL"
  - "Arrow Function"
description: "Arrow function과 연산자에 대한 복습내용"
---
안녕하세요 hailey입니다  
현재 저는 비전공자로서 위코드라는 코딩부트캠프에서 
프론트엔드 개발 관련 학습을 진행하고 있습니다.


제가 하루에 배운 내용들을 정리하고자 만든 블로그이니,
잘못된 정보가 있다면 언제든지 조언 및 충고 부탁드립니다.
## Arrow Fucntion
ES6에 들어오면서 새롭게 추가된 문법 중 Arrow function이 존재한다.
내가 아는 바로는, 
function을 자꾸 정의하는 게 굉장히 귀찮았기때문에 
해당 문법을 만들어서 함수정의를 안하게끔 만든 것 같다...

기존 ES5의 문법과 ES6 문법을 간략하게 비교해보자

#### 1.ES5에서의 함수정의
function getName( ) {
}

#### 2. ES6 함수정의
 const getName = () {
 }

 ES6에서는 함수를 변수에 저장할 수 있다.
 * 참고 : 원래 ES5에서도 변수에 저장할 수 있긴 했다고 한다..
 Ex. Function Declaration-> function getName(){}
     Function Expression -> const getNAme = function (){}

 * Arrow 함수를 사용하면서 우리는 anonymous 함수를 사용할 수 있게 되었다.
  Ex.
   const moreThan 100 = nums => {
     return nums.map(el=> el >= 100);
   }

![Nulla faucibus vestibulum eros in tempus. Vestibulum tempor imperdiet velit nec dapibus](/media/image-2.jpg)

## 연산자
 : 연산자를 활용한 조건들의 return값은 boolean (true or false) 값이 나온다.
 그래서 저기 위에 Arrow 함수 쓴 코드에서 el >= 100 이부분을 보면,
 nums라는 배열에 요소 값이 100보다 크거나 같으면 true값을 
 해당 조건이 아니면 false값을 반환한다.

#### 1. 동등연산자 ('==')
 ## 동등연산자는 피연산자들이 서로 다르면 같은 타입으로 바꿔서 비교한다.

  ```js 
   Ex.
    1 == 1 // True ;
    1 == '1' // True ; 
  ```

#### 2. 일치연산자 - 엄격한 연산자 ('===')
  ## 피연산자들이 동일한 타입과 내용을 갖고 있을 때만 true 

  ```js 
   Ex.
    1 === '1' // False; 


    3 === 3 // True;
  ```



#### 3. 부등연산자 ('!=')
  : 부등연산자는 피연산자들이 같지 않으면, 참을 반환한다. 
    만약 두 피연산자가 같은 타입이 아니라면, 자바스크립트가 두 피연산자를 비교하기에 적당한 타입으로 바꾼다.

  ```js
    Ex. 
      x != y 
      console.log( 1 != 2) //True ; 


      console.log( 1 != '1') // False; 
  ```


* if 문을 쓸 때 if ( a = b) {
  실행할 코드
}

이럴때도 참 / 거짓을 따져서 조건문이 실행되는데.. a =b 라고 그냥 나오니깐
왜 true가 나오는지 false가 나오는지 몰라서 문제를 잘못풀고 헤맸다..
역시 개발에서는 개념을 정확히 아는 거랑 기초가 중요하다.
기초 개념 정리를 잘해야지 !

끝~~~