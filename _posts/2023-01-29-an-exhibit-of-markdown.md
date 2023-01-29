---
layout: post
title: 변수, 호이스팅, TDZ
subtitle: let, const, var의 차이
categories: javascript
tags: [javascript, let, const, var, hoisting, TDZ]
---

## 사용법
- var: 자유도가 높은 대신 오류 발생 가능성도 높음
    - 이전에 선언된 변수와 동일한 변수명도 반복 사용 가능
    - 선언 전에도 사용 가능(undefind가 출력됨)
    - 초기화 전에도 사용 가능
    - 함수 스코프
<br/>
- let: 자유도에 제한을 두어 예기치 못한 오류 발생을 막음
    - 이전에 선언된 변수는 재선언 불가
    - 선언과 초기화가 완료된 후에만 사용 가능
    - 블록 스코프
        - 블록: 함수, if, for, while 등
<br/>
- const: 상수값을 할당하여 사용
    - let과 같이 재선언 불가 및 선언, 초기화 후에만 사용 가능
    - 상수값을 위한 예약어이기에 새로운 값 할당 불가
    - 일반적으로 상수임을 알 수 있도록 변수명을 대문자로 작성
    - 블록 스코프
        - 블록: 함수, if, for, while 등

### var
- 선언된 변수를 다시 선언할 수 있음
- 호이스팅이 되기에 선언하기 전에 사용할 수 있음
#### 호이스팅이란?
> 스코프 내부 어디서든 사용된 변수는 자동으로 최상위에 선언된 것처럼 동작되는 것

    ```javascript
    var name; // 호이스팅
    console.log(name); // undefined
    name = 'Mike';
    console.log(name); // Mike
    ```
    위 코드의 ```name```은 자동으로 호이스팅되어 아래와 같이 동작한다.

    ```javascript
    var name; // 호이스팅: 스코프 내부 어디서든 사용된 변수는 자동으로 최상위에 선언된 것처럼 동작되는 것
    console.log(name); // undefined
    name = 'Mike';
    console.log(name); // Mike
    ```

### let, const
- 재 선언시 오류가 남
    - 오류: Identifier "name" has already been declared
- 초기화하기 전에는 사용할 수 없음: let과 const도 호이스팅이 되나, TDZ 영역에서는 사용할 수 없음
#### TDZ (Temporal Dead Zone)
> 변수 선언은 되었으나, 초기화되지 않은 상태의 영역으로 이 영역에서 let과 const 변수를 사용할 경우 오류가 발생한다. (var는 사용 가능)

- case 1
    ```javascript
    console.log(name); // 오류: 초기화되기 전에 사용되는 부분은 TDZ이기에 오류 발생
    let name = 'Mike';
    console.log(name);
    ```

    ```javascript
    console.log(name); // 오류: 초기화되기 전에 사용되는 부분은 TDZ이기에 오류 발생
    const name = 'Mike';
    console.log(name);
    ```
- case 2

    ```javascript
    let name = "Mike";
    function printName(){
        console.log(name); // 밖에 선언된 name이 출력됨
    }
    printName();
    ```
    ```javascript
    let name = "Mike";
    function printName(){
        console.log(name); // 오류
        let name = "Ann";
    }
    printName();
    ```
    호이스팅으로 인해 스코프인 function 최상위에 name이 선언됨.<br/>
    그 결과 name은 선언만 되고 초기화되지 않은 변수가 되어 오류를 일으킴

    ```javascript
    let name = "Mike";
    function printName(){
        // let name > 스코프인 function 최상위에 name 변수가 선언됨(호이스팅)
        console.log(name); // 오류
        let name = "Ann";
    }
    printName();
    ```

## var와 let, const 사용법에 차이가 발생하는 이유
- 변수의 생성 과정이 다르기 때문
    - var: 선언 + 초기화 동시에 진행
        - undefined로 자동 초기화 되기에 초기화 전에 사용하여도 오류가 발생하지 않음
    - let: 선언만
        - 사용 시 초기화가 필요
    - const: 선언 + 초기화 + 할당 모두 동시에 진행
        - 값 할당까지 한번에 해야 함, 값 다시 할당 불가