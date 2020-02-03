---
title: CSS MediaQuery
date: "2019-08-20T15:30:37.121Z"
template: "post"
draft: false
slug: "/posts/til-css-mediaquery/"
category: "CSS"
tags:
  - "TIL"
  - "CSS"
  - "Media Query"
description: "CSS MediaQuery"
---

### Media Qurey란 ?

Responsive Web을 구현하는 CSS Technique

- '특정조건(주로 화면크기)에는 어떤 CSS를 적용해라 라'는 규칙을 줄 수 있음

```css
@media only screen and (max-width: 480px) {
  body {
    font-size: 12px;
  }
}
// 480px 이하 값에는 font-size를 12p 로 하겠다.
```

#### Media Query 세부설명

- @media : 미디어 쿼리를 시작하겠다
- only (device종류) : 어떤 디바이스에서 적용하는지 알려준다
- and (조건 max-width 혹은 min-width가 옴 ) : 어떤 media feature 라고 불리는 부분, 어느 조건에 아래의 css 를 적용할지 나타내줌

```css
@media only screen and (min-width: 320px) and (max-width: 480px) {
  /* ruleset for 320px - 480px */
}
/* ' 미디어쿼리를 320px 과 480px 화면(device) 크기 사이 값일 때만 적용하겠다. ' 라는 의미 ! */
```

- Media Query를 사용할 때는 스크린이 ~보다 작을 때의 경우는 max-width 를 , ~보다 클때의 경우는 min-width 를 사용하여 조건을 정해준다.
- 보통은 미디어쿼리를 사용한다는 명령어를 사용한 후에 해당되는 selector에 적용 style을 적어준다.

#### SCSS 에서 Media Query를 조금 더 쉽게 사용할 수 있다!

- SCSS는 CSS의 상위집합으로서 CSS와 동일한 문법으로 SASS의 특별한 기능들이 추가되어있음
- Sass라고도 하며, 풀어쓰자면 Syntactically Awesome Style Sheets / CSS pre processor !
- SCSS는 다양한 기능이 있음 (변수활용 가능, nesting 가능, impoting 가능 등 !)

```css
$Phone: "Only screen and (max-width : 768px) ";
$desktop: "screen and (min-width : 769px)";

@import "./mediaQuery.scss";
@media #{$phone} {
  .big-box {
    display: none;
  }
}

@media #{$desktop} {
  .big-box {
    dispaly: block;
  }
}

/* phone 과 desktop 이라는 변수에 해당 screen 조건 값을 담음
Media query를 import 해오고, 변수를 활용해서 big-box라는 클래스에 css 효과를 적용함 !
@media 를 쓰고 selector를 지정해서 스타일 효과를 적어주어도 되지만, scss 파일에 있는 각 태그에 @media 를 직접 적어줌으로써 각 태그마다 style 효과를 지정해도 됨 ! */

//scss 파일

$break-small: 740px;
/*모바일 화면으로 깨지는 순간의 px을 변수로 담음 */

.LoginWrapper {
  position: absolute;
  font-size: 13px;
  line-height: 18px;
  right: 12px;
  top: -1px;
  @media screen and (max-width: $break-small) {
    display: none;
  }
}

/*  $break-small : 740px로 이미 지정된 변수를 활용해서  클래스 style 효과 부분에 미디어쿼리를 직접 넣어줄 수도 있음!
break-mobile, break-tablet 이런식으로 조건 값을 변수에 담아 scss파일에 정의하고 유용하게 사용하는 경우가 많음! */
```

참고: 레플릿 미디어쿼리 / 벨로퍼트님 블로그
