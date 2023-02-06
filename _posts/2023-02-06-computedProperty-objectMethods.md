---
layout: post
title: 객체 메소드와 Computed property
subtitle: 객체 메소드와 Computed property
categories: javascript
tags: [javascript, ObjectMethods, ComputedProperty]
---

## Computed Property
- 객체의 key 값으로 변수값이나 식으로 넣을 수 있는 속성
  
    ```javascript
    let a = 'age';
    let user = {
      name : "Mike",
      [a] : 30, // [a]에 변수 a에 들어간 값인 'age'가 들어감
    }
    ```

    ```javascript
    // 계산값도 가능
    let user = {
      ["이" + "름"] : "Mike",
      [1+3] : 4, 
    }
    ```
## Object Methods
1. Object.assign() : 객체 복제(Call of value)
- ```user2 = user1;```를 할 경우 객체가 복제되는 것이 아니라 address만 복사됨(Call of reference)
2. Object.keys() : key 반환
3. Object.values() : value 반환
4. Object.entries() : key, value 반환
5. Object.fronEntries() : 키/값 배열을 넣으면 객체로 만들어 줌

  ```javascript
  let arr = [
    ['name', 'Mike'],
    ['age', '30'],
  ]

  //{'name': 'Mike', 'age': '30'}
  let result = Object.fromEntries(arr);
  ```