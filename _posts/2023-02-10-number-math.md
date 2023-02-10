---
layout: post
title: Symbol
subtitle: Number와 Math 객체
categories: javascript
tags: [javascript, Number, Math]
---

## number
- toString() 함수를 통해 10진수/2진수/16진수 등 진수를 변경할 수 있음

    ```javascript
    let num = 10;
    num.toString(); //"10" : string으로 변경됨
    num.toString(2); //"1010"

    let num2 = 255;
    num2.toString(16); //"FF"
    ```

## Math
- 수학에 관한 property와 method를 가진 js 내장객체

### 1. 올림/내림/반올림

    ```javascript
    let num1 = 5.1;
    let num2 = 5.7;

    //올림
    Math.ceil(num1); //6
    Math.ceil(num2); //6

    //내림
    Math.floor(num1); //5
    Math.floor(num2); //5

    //반올림
    Math.round(num1); //5
    Math.round(num2); //6    
    ```
#### 소수점 자리수 지정 반올림
- 방법 1

    ```javascript
    // 셋째 자리에서 반올림하여 둘째 자리까지만 보기 
    let num3 = 30.1234;
    Math.round(num3 * 100) / 100 //30.12
    ```

- 방법 2
    - toFixed() 함수: 숫자를 인수로 받아 그 숫자만큼 소수점 이하 갯수에 반영
        - return은 string으로 함
        - Number() 함수로 다시 숫자로 변경 가능

    ```javascript
    // 셋째 자리에서 반올림하여 둘째 자리까지만 보기 
    let num3 = 30.1234;
    num3.toFixed(2) //"30.12"
    num3.toFixed(0) //"30" : 소수점 자리 없어짐
    num3.toFixed(6) //"30.123400" : 0으로 채움
    ```

### isNaN()
- nan인지 판단하는 함수
    - nan은 nan과 비교해도 False가 나오기에 이 함수로만 판단이 가능함
    - 사용법: ```isNaN(판단대상)```

### parseInt() / parseFloat()
> parseFloat은 parseInt와 동일한 특징을 가지며, 부동소수점을 반환함

- 문자를 숫자로 변환하는 함수
- Number는 숫자 형태의 문자만 인지하고, 글자가 있으면 Nan을 반환하나, parseInt는 숫자로 시작할 경우 숫자까지는 읽고 글자를 만나면 읽은 숫자를 반환함 
    
    ```javascript
    // 셋째 자리에서 반올림하여 둘째 자리까지만 보기 
    let num = "30px";
    Number(num); //Nan
    parseInt(num); //30

    let num2 = "asd123";
    parseInt(num2); //Nan
    ```

- 2번째 인자로 진수를 입력받아, 해당 진수로 숫자 인지하게 할 수 있음. return은 10진수가 나옴

    ```javascript
    let num = "f3";
    parseInt(num); //Nan
    parseInt(num, 16); //243

    parseInt('11', 2); //3
    ```

### random()
- 0~1까지 숫자를 랜덤하게 출력
    - 1~100까지 숫자에서 뽑을 경우: ```Math.floor(Math.random * 100) + 1```

### 그 외 함수들
- min() / max() : 괄호 속 인수들 중 최소, 최대값을 구함
- abs() : 절대값
- pow() : 거듭제곱 값
    - 2의 10승 : ```Math.pow(2, 10)```
- sqrt() : 제곱근
    - ```Math.sqrt(16)``` : 결과값 4


