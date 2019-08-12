---
title: TIL - CSS Layout
date: "2019-08-12T20:30:37.121Z"
template: "post"
draft: false
slug: "/posts/til-csslayout/"
category: "TIL"
tags:
  - "TIL"
  - "CSS"
description: "CSS Layout"
---
안녕하세요~ 
현재 프론트엔드 개발자를 꿈꾸며
개발공부를 하고 있습니다 

제가 공부한 내용을 여기에 조금씩 정리해보려고 합니다! 
1일차 정리가 완료되어 이제 파트로 나눠서 정리하려고 합니다!


CSS Layout

## 1. Position property
**position property는 element의 위치를 정하는데 사용함
기본적인(statcic)을 제외하고 나머지 부분 정리**

1.	relative 
그자체로는 특별한 의미가 없지만 원래 위치를 기준으로 배치됨.
상대적으로 배치 된 요소의 top, right, bottom, left  속성을 설정하면 일반위치에서 멀어지도록 조정됨.
보통위치에서 상대적으로 요소가 자리를 잡기때문에 top과 같은 프로퍼티가 필요하다

    ```
    Ex.
        div {
        position : relative;
        top: -20px; left: 40px;
        }
    ```
	*top에 - 값을 주면 위쪽으로 20px만큼 이동*	

  * top, right, left, bottom 과 같은 프로퍼티 값을 주지않으면 static과 별 차이가 없는 것이 relative다.

2. absolute 
부모요소의 position이 fixed, relative, absolute이면 부모 기준으로 절대적으로 위치가 배치된다.
(부모요소가 static이면 해당 position 적용 X) 
일반적으로 absolute를 쓸 경우 절대적으로 움직이고 싶은 부모에게 position : relative 를 부여한다.
absolute position을 가지게되면, block element 가로크기는 content의 크기만큼이다! 
	* 만약 position된 부모태그가 없으면, 해당 element 는 document body를 부모로 사용해서, 페이지가 스크롤링 될때마다 따라다닌다.

    ````
    <style>
    div.relative {
      position: relative;
      width: 400px;
      height: 200px;
      border: 3px solid #73AD21;
    } 

    div.absolute {
      position: absolute;
      top: 40px;
      right: 0;
      width: 200px;
      height: 100px;
      border: 3px solid #73AD21;
    }
    </style>
    ````

	div.absolute의 위치는 부모element로 부터 위에서 부터 		40px 떨어져있고, 오른쪽에는 아주 딱 붙어있는 자리임!

	* top:-20px 이렇게 마이너스 값을 주니깐 element가 부모 	element 위쪽으로 이동했다 ! 

3. fixed
고정된 위치에 계속 배치되어있는 element 
absolute는 relative나 이런 속성을 가진 부모가 필요했으나, fixed 는 필요없음
*스크롤을 내리든지, 안내리든지 간에 계속 화면에 고정된 부분에 뜨는 것  !*
top, right, bottom, left 값을 주어서 위치를 지정하고 거기에 고정시키는 것 
  ~~~
  <참고>
  이미지위치를 픽셀이 아닌 %로도 줄 수 있다.
  어떤 element 기준으로 위치시킬 때, left :  10px 이렇게가 아닌 %값을 주면 
  부모element 너비의 기준으로 이동하는 것.
  예를 들어, 부모element의 너비가 100px 이었다면 내가 left : 50% 값을 주면 left로 50px만큼 이동했다는 것  !
  [해당내용 repl it : CSS 17에 나옴] 
  ~~~


## 2. HTML Layout

**HTML 웹페이지는 주로 이러한 layout을 가지고 있다.**
![html layout](https://www.w3schools.com/html/img_sem_elements.gif)
각 태그는 semantic tag들로서 각 태그 이름자체가 의미를 가지고 있는 tag들이다.

 1. section
  **주로 제목을 포함한 내용의 그룹들을 section이라는 태그를 사용하여 제어한다.**
  홈페이지는 보통 컨텐트, 내용정보, 소개 등의 섹션들로 나누어진다.


2. article 
**독립적이고 혼자만의 정보를 가지고 있는 요소들을 특정할 때, article을 쓴다.**


3. nav
**navigation bar 나 , link들을 정의할 때 사용**

4. aside 
**적혀있는 내용 이외에 내용을 넣는 컨텐트를 표현할 때 사용**

* 레이아웃은 한번에 잘짜기보다는 경험을 통해서 늘리고, 좋은 레이아웃을 가진 사이트에서 개발자도구를 보면서 어떻게 레이아웃을 잡았는지 알아가는 것이 중요 !

## 3. Layout 잡을 때 주로 쓰이는 Property

1. float 
	이미지 주위를 텍스트로 감싸기 위해 만들어짐, 이미지를 떠있는 것처럼 만들고 그 주변으로 글씨가 나타나게끔 해준다.잡지를 보면서 사진이 한쪽에 있고 그 주변으로 글이 있는 거를 볼 수 있는데 그런 효과를 준다고 보면된다.

  * float: left 하면 왼쪽으로 element가 뜨고, 그 주변으로 다른 요소들이 잡지의 사진 + 글형식으로 붙는다.
  * float: right 하면 오른쪽으로 element가 뜨고, 그 주변으로 다른 요소들이 잡지의 사진 + 글형식으로 붙는다.

  * float속성을 주면 뜨는 값이여서 부모element가 자식element의 높이를 인지 못해서 부모element보다 해당 element가 더 커지는 경우가 있다. 그럴 때 문제를 해결하기 위해서 overflow: hidden 속성이나, clear 를 사용해서 문제를 해결한다.


2. clear 
	float의 동작방식을 제어하는데 사용 
*  clear 속성은 쓰여지는 요소에 해당 element float 의 영향을 안받겠다고	말하는 것. float속성을 위에있는 element 가 쓰면 자연스럽게 다음 tag들이 그 element 주변을 둘러싸게 되는데 나는 그런 속성을 받지않을 거면 clear : both를 주면된다.(float property가 상속되는 것은 아님)
  ````css	
  Ex. 
    .after-box {
      clear : left;
   }
	````

  *after-box 라는 클래스이름을 가진 element는 float:left라	는 영향을 받지않을 것이다! 라고 말하는 것
  	그러면 float : left를 준 element 옆쪽으로 글이 붙는 게 	아니라, 아예 새로운 줄에서 element 시작할 수 있음*

* clear : both 오른쪽왼쪽 float 둘다 영향 안받음

* 원래 float 효과를 준 다음 element로 오면, float속	성이 붙어서 왼쪽 혹은 오른쪽 정렬이 되고,다음 요소도 		float 효과 영향 주기 위해서 자기 너비를 최소화하고, 다		음 요소가 올 수 있게 끔 해주는데 float 속성이 없는 		객체는 나머지 공간을 모두 차지한다! 
