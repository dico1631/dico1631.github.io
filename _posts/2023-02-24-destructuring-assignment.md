---
layout: post
title: 구조 분해 할당(Destructuring Assignment)
subtitle: 객체와 배열의 값을 여러 변수에 한번에 할당하는 방법
categories: javascript
tags: [javascript, array, constructor, destructuring assignment]
---

## 구조 분해 할당

배열이나 객체의 속성을 분해해서 그 값을 변수에 담을 수 있게 하는 표현식

### 배열

1. 기본적인 사용법

    ```javascript
    let [num1, num2] = [1, 2]
    console.log(num1, num2) // 1 2
    ```

2. 개수가 안 맞을 경우

    ```javascript
    let users = ['A', 'B', 'C']
    // user1: A, user3: B, user3: C, user4: undefined
    // 없는 항목은 undefined가 됨
    let [user1, user2, user3, user4] = users

    // user1: A, user3: B, user3: C, user4: D
    // 없을 경우에 오류가 나는 것을 방지하기 위해 default값을 넣을 수 있음
    let [user1, user2, user3, user4="D"] = users
    ```

3. 건너뛰기

    ```javascript
    let users = ['A', 'B', 'C']
    // 두번째 값을 건너뜀
    // user1: A, user3: C
    let [user1, , user3 = users
    ```

4. 값 교환에 활용: temp 변수 없이 a, b 값 교환이 가능함

    ```javascript
    let a = 5;
    let b = 10;
    // temp 변수 없이 a, b 값 교환이 가능함
    [a, b] = [b, a]
    ```

### 객체

1. 기본 활용

    ```javascript
    let user = {name: 'Mike', age: 30}
    // key값을 활용하기에 순서가 상관없음
    let {name, age} = user;
    let {age, name} = user;
    ```

2. 새로운 변수 이름으로 할당

    ```javascript
    let user = {name: 'Mike', age: 30}
    // userName, userAge라는 새로운 이름을 넣음
    let {name: userName, age: userAge} = user;
    ```

3. 개수가 안 맞을 경우

    ```javascript
    let user1 = {name: 'Mike', age: 30}
    let user2 = {name: 'Mike', age: 30, gender='female'}

    //없는 항목은 undefined
    // name: Mike, age: 30, gender: undefined
    let {name, age, gender} = user1;

    // 없을 경우 들어갈 default 값 지정
    // name: Mike, age: 30, gender: male
    let {name, age, gender='male'} = user1;

    // default 값이 있어도 객체에 값이 있다면 해당 객체 값이 할당
    // name: Mike, age: 30, gender: female
    let {name, age, gender='male'} = user2;
    ```