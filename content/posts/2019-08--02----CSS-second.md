---
title: HTML & CSS 기초내용 복습 - Second
date: "2019-08-02T22:25:37.121Z"
template: "post"
draft: false
slug: "/posts/til-htmlandcss_2/"
category: "HTMLandCSS"
tags:
  - "TIL"
  - "CSS"
  - "HTML"
description: "CSS 기초내용 복습 - Second"
---

# CSS

## 9. font style

###(1) font-family : 폰트1, 폰트2, 폰트3
폰트1 있으면 폰트1 적용 // 없으면 폰트 2 적용 // 그다음 없으면 폰트3 적용
마지막에는 그래서 특정폰트가 아닌 '글씨체'를 지정해준다

###(2) font color
**content에 색을 주고 싶을 때는 color property를 써서 색상을 정해준다**

- 색상을 표현하는 방법에는 여러가지가 있다.(hex 색상코드, rgb값, hsl )
  모든 색상을 기억할 수 없기때문에 color picker hex color / color picker 를 구글에 검색 하면
  내가 원하는 색상을 알 수 있음!  
   hex에서 rgb로 색상표현법을 바꾸고 싶으면 color hex to rgb 를 구글링 !

## 10. Text align

**글씨를 정렬하는 방법**
html에서 기본적인 정렬위치는 왼쪽정렬
left, right, center 이런식으로 property를 줄 수 있음

- span 태그의 경우 inline element이기때문에 오른쪽 정렬을 줬음에도 불구하고 적용이 안된다.
  왜냐면 element는 요소가 차지하는 영역안에서 정렬을 하게 된다.
  그러므로 block element를 정렬시에 사용(대표적으로 div 나 p로 묶어준다)

## 11. Text-indent

**글자들여쓰기**

```css
text-indent: 50px;
//50px만큼 글씨가 들여쓰기된다.
```

해당 indent 속성을 주지 않을 경우에는 스페이스를 직접 html에 추가하면 된다.
html에서는 아무리 스페이스바로 띄어쓰기를 만들어도 적용이 안된다.

- &nbsp; : html에서 스페이스를 뜻하는 의미이기때문에, 이 값을 추가해주면된다.

## 12. blockquote

**인용구문을 넣을 때 주로 쓰는 태그 (들여쓰기 및 양쪽여백 자동적용)**

## 13. 레이아웃 관련 표현들

### (1) padding : element 와 border 사이에 있는 공간

padding 과 margin 값은 위/오른/아래/왼 순서대로 크기를 지정해서 써주면 된다.

```css
padding: 10px 5px 10px 5px;
```

### (2) border : 테두리 - 테두리의 style 효과를 줄때는 '두께 선스타일 선색' 순서로 속성 값을 준다.

```css
border: 1px solid red;
```

solid는 기본적인 선을 말하며 거의 기본적으로 solid 선 스타일을 가장 많이 사용함
underline 효과를 줄 때 보통 text-decoration 보다는 border - bottom을 이용해서 다양한 선스타일을 주기도 함

### (3) margin : 테두리바깥 요소와 요소 사이의 공간

margin 값도 padding값과 마찬가지로 위 오른쪽 아래 왼쪽 이순서대로 크기를 지정해서 써주면 된다.

```css
margin: 10px 5px 10px 5px;
margin: 20px auto; //(위아래는 20px / 좌우로는 auto로 준다는 뜻)
margin: 10px; // (사방으로 같은 10px 값을 준다는 뜻)
```

### (4) box-sizing property

눈으로 보이는 너비와 개발자가 코딩하는 넓이가 다르면 안되니때문에
거의 대부분의 웹페이지는 box-sizing : border-box; 라는 프로퍼티와 속성을 준다.
해당 속성을 주면 / padding과 border 를 합친 값을 전체 width / height으로 볼 수 있다.

```css
* {
  box-sizing: border-box;
}
// 해당 값은 일일히 주기 힘들기때문에, 한번에 적용
// 여기서 '*'는 html내의 전체모든 요소를 의미한다.
```

## 14. 상속

상속이라는 말은 말그대로 CSS가 가진 특성 그대로 적용한 스타일이 상속되어 자식tag에게도 같은 스타일이 적용된다는 것이다.

```css
body {
  color: red;
  font-size: 14px;
}
```

```html
<body>
  <p>내용</p>
</body>
```

body에 빨간색글자와 14px 의 글자크기라는 스타일이 적용되면 <p> tag에는 아무 속성도 주지않았으나 부모에게 적용한 속성이 적용되는 것이다.
만약 부모에게 속성이 주어져도, 해당 요소가 자신만의 스타일속성을 가지고 있다면 본인 스타일이 적용된다.

## 15. 선택자 지정의 다양한 방법

### (1) 여러개의 선택자 지정방법

앞서 설명했듯이 여러개의 선택자를 지정하기 위해서는 ','로 구분해서 selector를 적으면 된다.

```css
p,
.search_box {
  color: gray;
}
```

### (2) 조건을 여러개가진 선택자 지정방법

예를들어 p 태그 이면서 p-tag 라는 클래스 이름을 가진 요소를 특정하기 위해서는 아래와 같이 CSS를 작성하고 적는다.

```css
p.name {
  color: gray;
}
```

이렇게 적은 내용은 p태그이면서 name이라는 클래스를 가진 (즉, 두개에 다 해당되는) 요소를 선택해서
글자색을 회색으로 주는 style 속성을 준다는 것이다.

```css
.top-header.search-box {
  background-color: powderblue;
}
```

태그랑 클래스값을 띄어쓰기 안하고 쓰면 태그이면서 클래스인 요소를 찾아서 style 주는 것!

```html
<div class="top-header" "search-box"> // 이렇게 top-header 이면서 search-box라는
클래스를 2개 가지고 있는 요소를 선택해서 backgroundcolor 효과를 주는 것이다.
```

### (3)선택자 아래에 있는 요소를 선택하는 방법

top_header 클래스 아래에 있는 search_box 클래스를 특정해서 지정하기 위해서는
부모선택자(띄어쓰기)자식선택자 순서로 적어주면 된다.

```css
.pre span {
  font-size: 22px;
}

/* pre 라는 이름을 가진 클래스에 아래에 있는 span 태그에게 font-size 22px이라는 속성을 적용한다는 뜻
    pre 클래스의 내부의 span 태그에 해당 속성이 적용되는데, CSS작성할 때 {} 중괄호 바로 앞에 나오는 요소에 해당 속성이 적용된다. span 태그가 per class에 아주 아래쪽에 위치하고 있다고 하더라도 적용이 된다. */
```

## 16. 선택자의 우선순위

- 우선순위의 차이
  inline CSS >>> id >>>>>> class >>> tag
  이 우선순위에 따라 스타일 값이 지정된다. 대부분의 요소에 class 를 부여해주고 중복을 피해 스타일링해주면 된다.

## 17.Assignment 참고사항

```css
.container header p.title {
  font-size: 50px;
}
```

container 클래스아래에 있는 header tag 아래에 있는 **p tag 이면서 title 이라는 클래스** 를 가진
element에 font-size 50px라는 효과를 준다.
여기서 주의할 점은 container 클래스 바로 아래에 header 태그가 있어야 될 필요는 없다는 것이다.
어쨌든 안에만 들어오면 된다.

**기억해야 될 부분**

- 띄어쓰기가 선택자와 선택자 사이에 없으면 동시에 가진 요소를 찾는 것
- 띄어쓰기가 선택자와 선택자 사이에 있으면 앞 선택자에 포함된 선택자를 찾는 것
