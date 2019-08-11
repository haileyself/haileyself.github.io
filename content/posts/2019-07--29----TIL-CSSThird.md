---
title: 20190729 TIL - 3 
date: "2019-08-11T21:25:37.121Z"
template: "post"
draft: false
slug: "/posts/til-htmlandcss_3/"
category: "TIL"
tags:
  - "TIL"
  - "CSS"
description: "HTML과 CSS 기초내용 복습_3"
---
안녕하세요 hailey입니다  
현재 저는 비전공자로서 '위코드'라는 코딩부트캠프에서 
프론트엔드 개발을 배우고 있습니다.


제가 부트캠프를 시작하며
배운 내용들을 정리하고자 만든 블로그이니,
잘못된 정보가 있다면 언제든지 조언 및 충고 부탁드립니다.

첫째날 배우고 복습한 내용이 많아서 나눠서 올리려고 합니다.
3개가 마지막이 될 것 같아요 !


## 18. img 태그 
**웹사이트에 이미지를 추가하는 방법 중 가장 많이 쓰이는 방법이 img 태그를 활용하는 것**
~~~
Ex.
<img alt="HTML" src="https://www.w3schools.com/whatis/img_js.png">

- alt : 이미지가 뜨지 않았을 때(서버에서 이미지가 삭제되었거나, 잘못된 이미지 주소일때) 이미지 대신 보여줄
텍스트
- src : 이미지 파일 경로 or 이미지 url 주소를 적는다
~~~

* 참고
    1. CSS 로 배경이미지 넣는 법
	```css
    .bg-img {
  		background-color: yellow;
  		background-image: url("https://upload.wikimedia.org/wikipedia/commons/thumb/6/61/HTML5_logo_
		and_wordmark.svg/1280px-HTML5_logo_and_wordmark.svg.png");
		}
    ```
	
        bg-img라는 class를 div 태그를 사용하여 공간을 잡아준다.
        div태그는 block element로 가로는 전체 잡고, 세로는 해당 요소의 크기만큼 잡는다.
        content를 없애면 배경이미지는 나타나지않는다.
        그래서 css파일에 width랑 height을 지정해주어야한다, 
        block 요소지만 크기를 잡아주면 
        그 크기가 배경이미지가 화면에 맞춰서 잘 보여지게 하기 위해서는 background-size: 100% 속성을 주면 됨


    2. 이미지 크기를 지정하는 방법
    : 이미지 크기는 px뿐만 아니라, %로 지정가능하다
    이미지 크기에 %를 쓰는 경우에는, 부모의 사이즈에 대한 %로 크기를 결정하는 것이다.%를 쓰면 바로 위에 있는 부모에 의해 크기가 결정된다
    ```CSS
    Ex. 
    <div width = "300px">
    <img width = 100%> </div>
    ```
    부모인 div 태그의 가로는 300px이며, img 태그가 100%로 설정하면 부모의 크기를 그대로 가진다는 의미. 여기서는 img의 width도 300px 되는 것, 만약에 50%라고 써있으면 150px 이 됬을 것 !


    3. 자식태그가 없는 태그 : p tag 
 

## 19. Inline 성질을 갖도록 하는 CSS property는 display & float 
     -  display : inline-block;
     -  float : right; 
     -  float : left;

이렇게 쓰면 block element인데도, inline element로 쓰일 수 있음 

## 20. element에 두개의 class를 주는 방법

    <div class="has-width center> 내용 </div>
    

해당 div태그는 has-width랑 center 라는 2개의 클래스를 가지고 있다.


## 21. ul 사용 시 list 아이템에 점자를 없애는 방법
**list-style : none property를 적용하면 된다!**


##22. List Item 사이에 공간을 만드는 방법
**list Item 아래에 여백을 추가하면 된다.**
 -  padding-bottom or margin-bottom을 주면됨 
- li Tag사용 !
- 왜 ? List는 테두리가 없기때문에 여백이 padding인지 margin쪽인지 알기 어려워서 아래에만 여백!

##23. CSS Selector 선택하면서 특정태그에만 style주는 법 
 * 방법
    1.  selector:first-child {} 선택자로 선택된 태그의 첫번째 태그를 선택해서 스타일적용
    2.  selector:last-child {} 선택자로 선택된 태그의 마지막 태그를 선택해서 스타일 적용
    3. selector:nth-child(odd) {} 선택자로 선택된 태그의 홀수태그들을 선택해서 스타일 적용
    4. selector:nth-child(even) {} 선택자로 선택된 태그의 짝수태그들을 선택해서 스타일 적용

* selector로는 tag / class / id 다 가능 !
    ```css
    li.first-child {
            color:red;
    }
    ```

    * Li태그의 첫번째 태그를 선택해서 글씨를 빨간색으로 만들어주는 스타일을 적용 ! 


## 24. Table Tag
**표를 만드는 태그**
    (친구로 tr  / td  / th가 있다.)
~~~
* 같이 쓰이는 태그들
    1) tr : 1행 생성(1줄을 만든다, 가로줄)
    2) td : 생성된 행에 셀(칸)을 1개씩 만드는 것
    3) th : 셀제목, 글씨가 굵게변하고 가운데 정렬된다 /역할을 td와 똑같이 됨
    
무조건 먼저 table 태그를 써주고, tr 태그를 활용해서 가로행을 만든 후에 
td로 세로열을 하나씩 추가하는 방식으로 표는 작성된다.
셀을 만들면서 셀병합도 가능하다
td 태그에 rowspan 이라는 어트리뷰트 사용하면 가로행병합 , colspan 쓰면 세로행 병합

 td rowspan="n"
 n 행만큼 병합 (행병합 , 가로 줄 합침) 

 td colspan="n"
 n 열만큼 병합 (열병합, 세로 줄 합침)
    

<th rowspan="3"> 내용 </th>
3개의 가로행을 내용이라는 content 넣어서 병합한다 !
~~~

##25. input 과 textare Tag
**사용자가 직접 텍스트를 입력할 수 있는 태그들**

####1) input 
```html
<input type = "text" palceholder = "ID">

    text를 입력하는 속성, 어느 테스트나 입력가능 / 이름, id 주소, 닉네임 등을 입력받을 때 사용함
````    
```html
<input type="password" placeholder = "비밀번호"> 
    stext 와 비슷하지만 뭔가를 입력하면 가려져서 나옴, 화면에는 출력 X 
````
``html
<input type="number" placeholer = "학번" > 
type이 number 가 되면 숫자만 입력가능 
``

* placeholer : 도움말을 넣어주는 부분 (어떤 값을 입력하면 되는 지 사용자에게 안내) 

#### 2) textarea
>**input 보다는 더 긴 텍스트를 입력받고 싶을 때 만드는 text 입력 상자**
 - 참고: textarea에 resize라는 속성은 default값으로 정해짐, 그래서 resize싫으면 none으로 설정하기
 (resize 속성이란 ? 사용자가 직접 width나 height 의 사이즈를 재조정할 수 있는 속성) 

*input는 시작태그만 있다. 하나의 태그가 하나의 요소 , input값에 미리 값을 세팅해놓을 때는 'value' 어트리뷰트를 사용 !*


##26. 어트리뷰트를 CSS 선택자로서 표현하는 방법
**CSS 작성할 때 선택자 뒤에 콜론 2개를 붙이고 속성주기**
```html
	 tag::어트리뷰트명 { 
  	CSS 속성 
	}
```

```css
	input::placeholder {
 	color : powderblue; 
 	}

* input 태그 내의 placeholder라는 어트리뷰트에 파우더블루라는 스타일 속성을 준다.
```


* 주의할 점, 모든 어트리뷰트를 콜론 2개를 활용해서 선택자로 표현할 수 있는 것은 아님!

***input 태그가 여러개 일때, 특정 타입에게만 스타일을 입히고 싶다면? ***
```css
 input[type="text] {
	CSS 속성 : 속성값
}
```
```css
	input[type="text"]::placeholder {
		color : red ;
		}
```     
input tag의 text 타입에 placeholer 어트리뷰트에 color:red라는 스타일 속성을 준다.


## 27. :hover
**마우스가 elment에 올려진 상태를 선택하는 선택자는 :hover이다.**

* 태그명:hover // 태그에 마우스가 올려진 상태를 선택하는 것
이러한 상태로 여러개를 선택할 수 있음

```css
span:hover , input:hover, textarea:hover {
				    border: 1px solid green ;
}
```

~~~
span 태그, input 태그, textarea 태그에 마우스가 올려졌을 때 3가지 상황을 선택자로 잡아서  이러한 상황이 발생하면 테두리가 1px 의 초록색이 된다.
~~~~
**참고**
- cursor의 종류는 여러가지이므로 상황에 맞게 쓰자.
- opacity 투명도는 백분율로 표시됨, 0으로하면 아예 안보인다->완전투명
 Ex. opacity : 80%
    80프로 만큼 흐리게 해준다 !


