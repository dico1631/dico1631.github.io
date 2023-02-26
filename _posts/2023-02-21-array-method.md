---
layout: post
title: Array Method
subtitle: 유용한 string 메소드
categories: javascript
tags: [javascript, array, method]
---

## 배열 삽입, 삭제, 통합 method

- push(): 뒤에 삽입
- pop(): 뒤에 삭제
- unshift(): 앞에 삽입
- shift(): 앞에 삭제
- arr.splice(n,m): n부터 시작해서 m개의 요소를 삭제
    - m이 0이면 삭제되지 않음
    - splice는 잘려진 부분을 arr로 return한다.
    - arr.splice(n,m, x): n부터 시작해서 m개의 요소를 삭제 후 x를 해당 자리에 넣음
        - ex. arr.splice(1,3, 2,4) > 1번째부터 3개 삭제 후, 2와 4를 해당 자리에 넣음
- arr.slice(n,m): n부터 m까지 반환(m은 포함 X, 안 쓰면 끝까지)
    - ()에 아무것도 없으면 배열이 복사됨
- arr.concat(arr2, arr3, …): arr들을 합침
- arr.reverse(): arr를 역순으로 만듦

## 배열 탐색 method

- arr.indexOf(item, 시작위치): 시작위치부터 탐색(없으면 시작부터), 첫 번째 요소의 idx만 반환, 없으면 undefined
- arr.lastIndexOf(item): 뒤부터 탐색, 없으면 undefined
- arr.includes(item): arr안에 item이 있으면 True, 없으면 False
- arr.find(fn): fn을 요소로 넣어서 연산을 통해 해당되는 요소 찾기 가능(ex. 짝수 찾기 등), 해당되는 첫 번째 요소만 반환, 없으면 undefined
    - arr.findIndex(fn): 조건에 만족하는 요소의 idx를 반환
- arr.filter(item): 해당되는 모든 요소를 반환

## 배열 <> String

- arr.join(””): arr을 “”을 넣어서 합친 뒤 string으로 반환
- atring.split(””): string을 “”을 기준으로 쪼갠 뒤 arr로 반환

## 배열 여부 판단

- arr.isArray(): arr이면 True, 아니면 False

## 배열 정렬

- arr.sort(fn): 배열의 요소를 fn에 따라 정렬, 인자가 없을 경우 string으로 item을 인식 후 아스키 코드로 반환
    - 해당 배열 자체가 변경됨
    
    ```javascript
    let arr = [27, 8, 5, 13];
    arr.sort((a,b) => {
    	return a-b;
    });
    ```
    
    - 주로 lodash lib를 사용하여 정렬을 사용함(ex: _.sortBy(arr).)

## 배열 item 조작 method

- arr.map(fn): 하나씩 꺼내서 fn에 input함
- arr.forEach((item, index, arr) ⇒ (return)): 인자로 함수를 받음

## 배열 reduce

- arr.reduce(fn(누적계산값, 현재값, 초기값)): 누적계산값에 현재값을 연산해서 누적계산값에 넣는 작업을 반복, 이를 return
    - arr.reduceRight(): 기능은 동일, arr의 오른쪽부터 시작함

    ```javascript
    // arr의 값을 다 더하는 작업, prev의 초기값은 0
    arr.reduce((prev, current) ⇒ {
        return prev + cur;
    }, 0)
    ```

<details>
<summary>프로그래머스 arr 문제 모음</summary>
<div markdown="1">

• 배열의 평균값

[https://school.programmers.co.kr/learn/courses/30/lessons/120817](https://school.programmers.co.kr/learn/courses/30/lessons/120817)

• 배열 원소의 길이

[https://school.programmers.co.kr/learn/courses/30/lessons/120854](https://school.programmers.co.kr/learn/courses/30/lessons/120854)

• 머쓱이보다 키 큰 사람

[https://school.programmers.co.kr/learn/courses/30/lessons/120585](https://school.programmers.co.kr/learn/courses/30/lessons/120585)

• 배열 뒤집기

[https://school.programmers.co.kr/learn/courses/30/lessons/120821](https://school.programmers.co.kr/learn/courses/30/lessons/120821)

• 짝수 홀수 개수

[https://school.programmers.co.kr/learn/courses/30/lessons/120824](https://school.programmers.co.kr/learn/courses/30/lessons/120824)

• 최댓값 만들기 (1)

[https://school.programmers.co.kr/learn/courses/30/lessons/120847](https://school.programmers.co.kr/learn/courses/30/lessons/120847)

• 배열 자르기

[https://school.programmers.co.kr/learn/courses/30/lessons/120833](https://school.programmers.co.kr/learn/courses/30/lessons/120833)

• 중복된 숫자 개수

[https://school.programmers.co.kr/learn/courses/30/lessons/120583](https://school.programmers.co.kr/learn/courses/30/lessons/120583)

• 배열의 유사도

[https://school.programmers.co.kr/learn/courses/30/lessons/120903](https://school.programmers.co.kr/learn/courses/30/lessons/120903)

• 삼각형의 완성조건 (1)

[https://school.programmers.co.kr/learn/courses/30/lessons/120889](https://school.programmers.co.kr/learn/courses/30/lessons/120889)

• 배열 두배 만들기

[https://school.programmers.co.kr/learn/courses/30/lessons/120809](https://school.programmers.co.kr/learn/courses/30/lessons/120809)

• 중앙값 구하기

[https://school.programmers.co.kr/learn/courses/30/lessons/120811](https://school.programmers.co.kr/learn/courses/30/lessons/120811)

• n의 배수 고르기

[https://school.programmers.co.kr/learn/courses/30/lessons/120905](https://school.programmers.co.kr/learn/courses/30/lessons/120905)

• 주사위의 개수

[https://school.programmers.co.kr/learn/courses/30/lessons/120845](https://school.programmers.co.kr/learn/courses/30/lessons/120845)

• 최댓값 만들기 (2)

[https://school.programmers.co.kr/learn/courses/30/lessons/120862](https://school.programmers.co.kr/learn/courses/30/lessons/120862)

• 가장 큰 수 찾기

[https://school.programmers.co.kr/learn/courses/30/lessons/120899](https://school.programmers.co.kr/learn/courses/30/lessons/120899)

• 배열 회전시키기

[https://school.programmers.co.kr/learn/courses/30/lessons/120844](https://school.programmers.co.kr/learn/courses/30/lessons/120844)

• 2차원으로 만들기

[https://school.programmers.co.kr/learn/courses/30/lessons/120842](https://school.programmers.co.kr/learn/courses/30/lessons/120842)

• 가까운 수

[https://school.programmers.co.kr/learn/courses/30/lessons/120890](https://school.programmers.co.kr/learn/courses/30/lessons/120890)

• 진료 순서 정하기

[https://school.programmers.co.kr/learn/courses/30/lessons/120835](https://school.programmers.co.kr/learn/courses/30/lessons/120835)

• 7의 개수

[https://school.programmers.co.kr/learn/courses/30/lessons/120912](https://school.programmers.co.kr/learn/courses/30/lessons/120912)

• 공 던지기

[https://school.programmers.co.kr/learn/courses/30/lessons/120843](https://school.programmers.co.kr/learn/courses/30/lessons/120843)

• 잘라서 배열로 저장하기

[https://school.programmers.co.kr/learn/courses/30/lessons/120913](https://school.programmers.co.kr/learn/courses/30/lessons/120913)

• 외계어 사전

[https://school.programmers.co.kr/learn/courses/30/lessons/120869](https://school.programmers.co.kr/learn/courses/30/lessons/120869)

• 캐릭터의 좌표

[https://school.programmers.co.kr/learn/courses/30/lessons/120861](https://school.programmers.co.kr/learn/courses/30/lessons/120861)

• 직사각형 넓이 구하기

[https://school.programmers.co.kr/learn/courses/30/lessons/120860](https://school.programmers.co.kr/learn/courses/30/lessons/120860)

• 로그인 성공?

[https://school.programmers.co.kr/learn/courses/30/lessons/120883](https://school.programmers.co.kr/learn/courses/30/lessons/120883)

• 등수 매기기

[https://school.programmers.co.kr/learn/courses/30/lessons/120882](https://school.programmers.co.kr/learn/courses/30/lessons/120882)

• 특이한 정렬

[https://school.programmers.co.kr/learn/courses/30/lessons/120880](https://school.programmers.co.kr/learn/courses/30/lessons/120880)

• 최빈값 구하기

[https://school.programmers.co.kr/learn/courses/30/lessons/120812](https://school.programmers.co.kr/learn/courses/30/lessons/120812)

• OX퀴즈

[https://school.programmers.co.kr/learn/courses/30/lessons/120907](https://school.programmers.co.kr/learn/courses/30/lessons/120907)

• 다음에 올 숫자

[https://school.programmers.co.kr/learn/courses/30/lessons/120924](https://school.programmers.co.kr/learn/courses/30/lessons/120924)

• 안전지대

[https://school.programmers.co.kr/learn/courses/30/lessons/120866](https://school.programmers.co.kr/learn/courses/30/lessons/120866)

• 겹치는 선분의 길이

[https://school.programmers.co.kr/learn/courses/30/lessons/120876](https://school.programmers.co.kr/learn/courses/30/lessons/120876)

• 평행

[https://school.programmers.co.kr/learn/courses/30/lessons/120875](https://school.programmers.co.kr/learn/courses/30/lessons/120875)

• 옹알이 (1)

[https://school.programmers.co.kr/learn/courses/30/lessons/120956](https://school.programmers.co.kr/learn/courses/30/lessons/120956)

</div>
</details>