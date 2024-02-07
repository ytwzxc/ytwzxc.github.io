---
title: "Bandit Level 7 → Level 8"
date: 2024-01-26
categories: [Bandit]
tags: [Bandit]
---

## 문제
<https://overthewire.org/wargames/bandit/bandit7.html>

## 목표
`data.txt` 파일 안 `millionth`라는 단어 옆에 저장되어 있는 패스워드를 찾는다.

## 풀이
`cat data.txt` 명령으로 파일을 확인해보니 수많은 문자열들이 출력된다.

```shell
bandit7@bandit:~$ cat data.txt
gallop  hu3ZhCrGRvfaO5jsY6ttvApzVCA2Hjvs
Aurelia         ikl4F3cK5m6Cl6HAxva6zUAVJhI2Cvc6
stoicism        JiW9ts44udf20bJHe8H5dS1c99Muwz42
.
.
.
recollects      5Nxh0y1iriFuzQviW8U1c8tU57go9RG8
prorate 15BfjYyMWxWmhySahWKklw4zgNXm3VCS
Dodge   tdDwHTSmw7cf2ZvO5oMGuLUpnE5f8Gth
```  

&nbsp;  

특정 문자열이 포함된 행을 출력하기 위해서는 `grep` 명령어를 사용해야 한다.  

`grep millionth data.txt` 명령으로 `data.txt` 파일에서 `millionth`라는 문자열이 포함된 행을 출력할 수 있다.

```shell
bandit7@bandit:~$ grep millionth data.txt
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
```  

&nbsp;

**Password : TESKZC0XvTetK0S9xNwm25STk5iWrBvP**

## 배운 것
- `grep` 명령어로 특정 문자열이 포함된 행을 출력할 수 있다.