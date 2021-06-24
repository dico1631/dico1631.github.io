---
layout: post
title:  "css 크기 단위의 종류"
date:   2021-06-24
categories: [front, css]
---

# px
- ***해상도에 따라*** 영향을 받는 단위
- 주변 태그에 영향을 받지 않는 ***고정 단위***
- px의 크기 = 입력한 그 숫자 그대로

```HTML
<div class="container">
  container
  <div class="parent">
    parent
    <div class="chlid">child1</div>
    <div class="chlid">child2</div>
  </div>
</div>
```

```css
.container{
  width: 600px;
}
.parent{
  width: 300px
}
.chlid{
  width: 150px
}
```

# %
- ***부모자의 크기를 기준으로*** 비율을 정하는 상대적인 단위
- 부모자의 크기와 같은 크기이면 100% 이다.
- %의 크기 = 부모자 크기 * 비율(%)

```css
.container{
  width: 600px;
}
.parent{
  width: 50%; /* 300px */
}
.chlid{
  width: 50%; /* 150px */
}
```

# em /rem
## em: 자기 자신의 폰트 사이즈에 영향을 받음
- ***폰트 사이즈는*** 상속되는 속성이기 때문에 명확히 선언된 나의 폰트 사이즈가 없다면, 부모의 폰트 사이즈를 내 폰트 사이즈로 여긴다.
- 조상을 기준으로 다 상대적인 크기로 지정할 때 사용
- 너무 많이 상속받아 여러 단계가 서로 영향을 주면 관리하기 어려워짐 > 그래서 rem을 사용
- em의 크기 = 내 폰트 크기 * em

```css
/* em으로 div 크기 지정 */
body * {
  border: 2px solid;
}
.container{
  width: 60em; /* 60*10 = 600px */
  font-size: 10px;
}
.parent{
  width: 30em; /* 30*10 = 300px */
   /* font-size: 10px 상속받음 */
}
.chlid{
  width: 15em; /* 15*10 = 150px */
}
```

```css
/* font-size도 em으로 지정되어 있다면? */
body * {
  border: 2px solid;
}
.container{
  width: 60em; /* 60*10 = 600px */
  font-size: 10px; /* 이 숫자가 늘어나면 parent와 chlid도 같이 늘어난다. */
}
.parent{
  width: 30em; /* 30*20 = 600px */
  font-size: 2em; /* 10*2 = 20px */
}
.chlid{
  width: 15em; /* 15*40 = 600px */
  font-size: 2em; /* 20*2 = 40px */
}
```

## rem
- root + em 의 약자
- 제일 조상요소인 ***html에 지정된 font-size를 기준으로*** 크기가 정해지는 em이다.
- em의 기준은 조상과 부모의 font-size에 따라 정해지지만, rem의 기준은 html의 font-size만 이다.

```css
html{
  font-size: 10px;
}
body * {
  border: 2px solid;
  font-size: 15px;
}
/* em */
.container{
  width: 60em; /* 60*15 = 900px */
}
.parent{
  width: 30em; /* 30*30 = 900px */
  font-size: 2em; /* 15*2 =30px */
}
/* rem */
.chlid{
  width: 20rem; /* 20*10 = 200px */
  font-size: 2rem; /* 10*2 = 20px */
}
```

# vw, vh
- viewport + width/height
- ***화면 전체를 기준으로*** 화면의 어느 정도를 차지할 지를 나타내는 단위
- 1-100 사이의 숫자를 쓴다. (50vw/50vh는 화면의 절반 너비/높이를 의미)

```html
<div class="container"></div>
```

```css
.container{
  /* 범위: 1-100 */
  width: 50vw; /* 화면의 절반 */
  height: 30vh; /* 화면의 30% */
  background: red;
}
```

# vmin, vmax
- vmax: 가로, 세로 중 ***더 긴 너비를 기준으로*** 크기를 지정
- vmin: 가로, 세로 중 ***더 짧은 너비를 기준으로*** 크기를 지정

```html
<div class="container"></div>
```

```css
.container{
  width: 50vmax;
  height: 100px;
  background: red;
}
```

```css
.container{
  width: 50vmin;
  height: 100px;
  background: red;
}
```