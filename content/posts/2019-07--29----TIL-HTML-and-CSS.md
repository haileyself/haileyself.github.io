---
title: HTML과 CSS 기초내용 복습
date: "2019-07-31T22:33:37.121Z"
template: "post"
draft: false
slug: "/posts/til-htmlandcss/"
category: "TIL"
tags:
  - "TIL"
  - "HTML"
description: "HTML과 CSS 기초내용 복습"
---

Wecode 시작하고 배운 기초내용들을 복습하고자, 작성하는 정리 글 !

# HTML

## 1. !DOCTYPE html

**웹페이지에게 해당 문서는 html을 통해 작성되어있다고 알려주는 태그**

모든 html 파일은 해당 태그로 시작되어야 한다.
html 문서의 모든 요소는 html 태그로 묶인다.

## 2. head Tag

**html의 문서타입을 정해준 이후에 등장하는 태그**

html의 `<head>` 태그에는 본문에는 들어나지 않는 내용들이 적혀있다.
본문에는 나타나지 않지만, 해당 페이지에 대한 정보를 주는 부분이다.

## 3. content 어트리뷰트

**viewport(meta tag)로 name 을 지정한 후 , content로 해당 부분의 크기를 지정해서 넣어줌**

```html
<meta content="width=device-width" /> content 의 넓이가 device의 스크린 넓이로
세팅된다는 뜻 모바일에서 웹사이트가 예쁘게 보이려면 해당 내용을 추가해야 함,
이걸 안하면데스크탑 버전의 웹페이지가 축소되어 보이는 현상이 나타난다)
```

## 4. body Tag

**웹페이지를 볼 때 우리눈에 보이는 부분들이 주로 적혀있는 html의 요소**

## 5. 자주쓰이는 tag들을 정리 !

###(1) span
: 아무의미가 없는 tag로 텍스트의 한부분에 색깔을 줄 때 주로 사용(Inline element)

###(2) a
: link를 걸어주는 태그 / 해당 태그의 어트리뷰트로 target="\_blank"가 사용되면 걸린 링크가 새 창에서 뜬다

###(3)div
span과 비슷한 태그 / 정말 자주 사용 되는 태그 !(block element)

```
* div tag를 사용하는 이유
 - 그룹핑
 - 디자인에 맞게 레이아웃을 분리
 - 각 div에 class 나 id라는 어트리뷰트를 부여하여 css스타일을 구분해서 입혀줄 수 있음
 - 보통 웹페이지 레이아웃을 짤 때 헤더/메뉴/주요내용/푸터 이렇게 div로 나눠서 묶어주고 레이아웃에 css 효과를 준다.
```

## 6. Arrtibutes

**태그에 주는 속성값 같은 것 / tag에 따라서 적용할 수 있는 Attribute도 달라진다.**

###(1) id
: id도 어트리뷰트 종류의 하나다! 각 태그에 이름을 부여해주는 속성이 있다.
id는 이름 그대로 id card처럼 고유한 값으로 한 html 웹페이지에는 같은 id값이
두개 나올 수 없다. 그러므로 중복된 id값은 존재 불가하다!

> id는 해당 element에만 넣고싶은 디자인을 적용할 때 주로 사용한다.

###(2) class
class도 이름을 붙여주는 속성이 있다. id와 비슷하지만 여러 element에
같은 class 값을 줄 수 있다. 중복된 class명 가능 !
하나의 태그에도 여러개의 class 값을 주는 것도 가능하다

```html
<div class="color_box text_box">내용</div>
`
```

해당 element는 color_box 와 text_box 라는 두 개의 클래스를 가졌다 !
하나의 태그에 2개이상의 속성을 부여할 수 있다.
속성추가를 위해서는 한칸 띄어쓰기 한 후 추가하면 된다.
한 element가 여러개의 class값을 가질 때는 **공백**으로 구분한다.

# CSS

## 1. CSS 적용법

###(1) inline style
태그에 직접 style속성을 넣어서 CSS작성 (가장 강력함)
###(2) style tag
html 파일 내에 style 태그를 삽입하여 스타일 작성(head태그에 주로함)
###(3) css 파일에 작성해서 html에 불러오기
3번 방식을 사용할 경우, html에 내가 css를 파일로 가져올 거라고 알려줘야한다.

```html
Ex.<link href="index.css" rel="stylesheet" type="text/css" />
```

- link 태그 사용
- href="" : 가져올 css 파일 이름 (주소)
- rel="" : rel은 html file과 css file과의 관계를 설명하는 속성 (css파일을 링크할 때는 항상 "stylesheet" 값을대입)
- type="" : text/css link태그로 연결되는 파일이 어떤 것인지 알려준다. (cssfile을 연결하므로 type값은 항상 text/css로 입력한다.)

**CSS를 웹페이지에 적용할 때는 3번 파일에 작성하여 하는 것이 가장 좋다**

- **why?**
  1번 적용시에는 코드가 길어지고, 2번도 좋은 방법이나 기능적으로 html의 구조와 디자인이 분리되어있지않기때문에 유지보수에 적합하지않다!

## 2. CSS 작성법

```css
Selector {
  property: property value;
}

#special {
  color: red;
}
/* special이라는 id로 지정된 tag에 color가 red라는 css속성이 들어간다! */
```

만약, 여러개의 태그와 클래스에 한꺼번에 같은 스타일을 적용하고 싶을때는 선택자를 ','로 구분하여 적고
{} 속성을 주면 한꺼번에 CSS 스타일을 적용할 수 있다.

```css
.class,
p,
.style {
  color: red;
}
```
