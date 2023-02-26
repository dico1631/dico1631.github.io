---
layout: post
title: setTimeout/setInterval
subtitle: 코드 실행에 시간 조건을 주는 방법
categories: javascript
tags: [javascript, setTimeout, setInterval, clearTimeout, clearInterval, 비동기함수]
---

## setTimeout

- 일정 시간이 지난 뒤 코드 실행(1회 수행)
- setTimeout(함수(, 함수의 인수), 시간) : 시간은 1000마다 1초
    - 시간이 0이어도 브라우저 대기시간이 약 4ms가 있으며, js는 현재 실행 중인 코드가 끝난 후 스케쥴링 함수를 실행하기에 바로 실행되지는 않음
- clearTimeout(tId) : setTimeout 해제, tId는 setTimeout이 return하는 값

## setInterval

- 일정 시간마다 코드 실행(반복 수행)
- setInterval(함수(, 함수의 인수), 시간) : 시간은 1000마다 1초
- clearInterval(tId) : setInterval해제, tId는 setInterval이 return하는 값

### 실행방법

    ```jsx
    function showName(name){
        console.log(name)
    }

    setTimeout(showName, 'mike', 4000); //4초뒤에 찍힘
    setInterval(showName, 'mike', 4000); //4초마다 찍힘
    ```

- 상단 코드와 동일한 기능

    ```jsx
    setTimeout(function(){
        console.log('mike');
    }, 4000); //4초뒤에 찍힘

    setInterval(function(){
        console.log('mike');
    }, 4000); //4초마다 찍힘
    ```