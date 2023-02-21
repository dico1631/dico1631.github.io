---
layout: post
title: String Method
subtitle: 유용한 string 메소드
categories: javascript
tags: [javascript, string, method]
---

## string method

> 하단 desc는 문자열을 담은 변수입니다.

- 문자열 길이: desc.length
- 특정 위치에 접근: desc[idx] 으로 접근 가능, 다만 한글자만 바꾸는 것은 불가능
- 대소문자: desc.toUpperCase() / desc.toLowerCase()
- 인덱스: desc.indexOf(’찾길원하는문자열’)
    - 여러개가 있을 경우 제일 첫 번째 인덱스만 나옴
    - 없을 경우 -1 반환
    - if 문의 조건으로 사용할 경우 첫 번째 단어의 index가 0이므로, -1보다 클 경우/ 작을 경우 조건을 작성해야 함

### 서브 스트링 만들기

- 슬라이스: str.slice(n,m)
    - n: 시작점
    - m: 끝 지점(단 양수일 경우 해당 idx는 포함하지 않음) , 없을 경우 문자열 끝까지 잘라냄, 음수일 경우 뒤쪽부터 셈
- 서브 스트링1: str.substring(n, m)
    - n과 m 사이의 숫자만 뽑아냄(해당 숫자 사이의 str을 뽑은 것이기에, n이 m보다 작아도 동일한 결과가 나옴)
    - 음수는 무조건 0으로 인식함
- 서브 스트링2: str.substr(n, m)
    - n부터 시작해서 m개를 가져옴
    - n에 음수 가능

- 앞뒤 공백 제거: str.trm()
- 반복: str.repeat(n)
    - 문자열을 n번 반복함
- 문자열 비교
    - 아스키 코드 숫자에 따라 대소 비교가 됨

<details>
<summary>프로그래머스 String 문제 모음</summary>
<div markdown="1">

**문자열 뒤집기**

[https://school.programmers.co.kr/learn/courses/30/lessons/120822](https://school.programmers.co.kr/learn/courses/30/lessons/120822)

**문자 반복 출력하기**

[https://school.programmers.co.kr/learn/courses/30/lessons/120825](https://school.programmers.co.kr/learn/courses/30/lessons/120825)

**특정 문자 제거하기**[https://school.programmers.co.kr/learn/courses/30/lessons/120826](https://school.programmers.co.kr/learn/courses/30/lessons/120826)

**문자열안에 문자열**
[https://school.programmers.co.kr/learn/courses/30/lessons/120908](https://school.programmers.co.kr/learn/courses/30/lessons/120908)

**모음 제거**
[https://school.programmers.co.kr/learn/courses/30/lessons/120849](https://school.programmers.co.kr/learn/courses/30/lessons/120849)

**대문자와 소문자**
[https://school.programmers.co.kr/learn/courses/30/lessons/120893](https://school.programmers.co.kr/learn/courses/30/lessons/120893)

**암호 해독**
[https://school.programmers.co.kr/learn/courses/30/lessons/120892](https://school.programmers.co.kr/learn/courses/30/lessons/120892)

**문자열 뒤집기**
[https://school.programmers.co.kr/learn/courses/30/lessons/120822](https://school.programmers.co.kr/learn/courses/30/lessons/120822)

**문자열 정렬하기 (1)**
[https://school.programmers.co.kr/learn/courses/30/lessons/120850](https://school.programmers.co.kr/learn/courses/30/lessons/120850)

**인덱스 바꾸기**
[https://school.programmers.co.kr/learn/courses/30/lessons/120895](https://school.programmers.co.kr/learn/courses/30/lessons/120895)

**외계행성의 나이**
[https://school.programmers.co.kr/learn/courses/30/lessons/120834](https://school.programmers.co.kr/learn/courses/30/lessons/120834)

**문자열 정렬하기 (2)**
[https://school.programmers.co.kr/learn/courses/30/lessons/120911](https://school.programmers.co.kr/learn/courses/30/lessons/120911)

**모스부호 (1)**
[https://school.programmers.co.kr/learn/courses/30/lessons/120838](https://school.programmers.co.kr/learn/courses/30/lessons/120838)

**중복된 문자 제거**
[https://school.programmers.co.kr/learn/courses/30/lessons/120888](https://school.programmers.co.kr/learn/courses/30/lessons/120888)

**A로 B 만들기**
[https://school.programmers.co.kr/learn/courses/30/lessons/120886](https://school.programmers.co.kr/learn/courses/30/lessons/120886)

**한 번만 등장한 문자**
[https://school.programmers.co.kr/learn/courses/30/lessons/120896](https://school.programmers.co.kr/learn/courses/30/lessons/120896)

**영어가 싫어요**
[https://school.programmers.co.kr/learn/courses/30/lessons/120894](https://school.programmers.co.kr/learn/courses/30/lessons/120894)

**컨트롤 제트**
[https://school.programmers.co.kr/learn/courses/30/lessons/120853](https://school.programmers.co.kr/learn/courses/30/lessons/120853)

**문자열 계산하기**
[https://school.programmers.co.kr/learn/courses/30/lessons/120902](https://school.programmers.co.kr/learn/courses/30/lessons/120902)

**외계어 사전**
[https://school.programmers.co.kr/learn/courses/30/lessons/120869](https://school.programmers.co.kr/learn/courses/30/lessons/120869)

**로그인 성공?**

[https://school.programmers.co.kr/learn/courses/30/lessons/120883](https://school.programmers.co.kr/learn/courses/30/lessons/120883)

**문자열 밀기**
[https://school.programmers.co.kr/learn/courses/30/lessons/120921](https://school.programmers.co.kr/learn/courses/30/lessons/120921)

**옹알이 (1)**
[https://school.programmers.co.kr/learn/courses/30/lessons/120956](https://school.programmers.co.kr/learn/courses/30/lessons/120956)

</div>
</details>