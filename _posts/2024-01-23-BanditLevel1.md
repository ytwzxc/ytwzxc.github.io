---
title: "Bandit Level 1 → Level 2"
date: 2024-01-23
categories: [Bandit]
tags: [Bandit]
---

## 문제
<https://overthewire.org/wargames/bandit/bandit2.html>

## 목표
홈 디렉토리에 위치한 `-` 파일에 저장되어 있는 패스워드를 찾는다.

## 풀이
`cat -` 명령을 시도해보니 파일의 내용은 보이지 않고 입력을 받아 다시 출력한다.

```shell
bandit1@bandit:~$ cat -
a
a
asdf
asdf
```

`cat` 명령어는 파일 이름이 `-` 일 경우 표준 입력을 읽는다.

그렇다면 다른 방법으로 `-` 파일을 읽어야 한다.  
&nbsp;  

파일 이름인 `-` 앞에 현재 디렉토리를 의미하는 `./`를 붙인다.

```shell
bandit1@bandit:~$ cat ./-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
```  
&nbsp;  

**Password : rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi**

## 배운 것
- `cat` 명령어는 파일 이름이 `-`일 경우 표준 입력을 읽는다.
- `./` 는 현재 디렉토리를 의미한다.