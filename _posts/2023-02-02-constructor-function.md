---
layout: post
title: 생성자 함수
subtitle: 생성자 함수 선언 및 사용 기초
categories: javascript
tags: [javascript, constructor]
---

## 생성자 함수
- 객체의 형식이 정의된 함수로, 동일한 형태의 객체를 여러 개 생성할 경우 사용됩니다.
    - 객체를 각각 만드는 것보다 가독성과 속도면에서 좋으며, 또한 차후 유지보수에 용이한 장점이 있습니다.

### 동작 원리
1. 빈 객체를 만들어 this에 할당
2. 함수 본문을 실행하면서 this에 새로운 프로퍼티를 추가함
3. this를 반환
```javascript
function User(name, age) {
  // this = {};  (빈 객체가 암시적으로 만들어짐)

  // 새로운 프로퍼티를 this에 추가함
  this.name = name;
  this.age = age;

  // return this;  (this가 암시적으로 반환됨)
}
```
### 사용방식
1. 함수 이름의 첫 글자는 대문자로 작성
2. 반드시 `new` 연산자를 붙여서 실행
```javascript
function User(name, age) {
  this.name = name;
  this.age = age;
}

let user1 = new User('Mike', 25);
let user2 = new User('Anne', 35);
```

### 특징
1. 객체 값에 함수도 할당할 수 있음.
2. new를 붙이지 않을 경우 명시적 return값이 없기에 undefined를 return하게 됨.
    
```javascript
function User(name, age) {
  this.name = name;
  this.age = age;
  this.sayName = function () {
    console.log(this.name);
  };
}

// 생성자 함수를 통해 객체 생성
let user1 = new User("Mike", 20);
let user2 = new User("Anne", 25);
let user3 = new User("June", 30);
let user4 = User("June", 30);

// 생성된 객체 사용
document.write(user1, user2, user3);
user2.sayName();

// new가 없을 경우
document.write(user4);
```
- 출력된 결과
- ![생성자 함수 코드 결과 console 화면](/assets/images/javascript/post/constructor_1.png)

