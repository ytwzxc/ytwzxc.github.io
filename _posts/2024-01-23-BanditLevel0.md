---
title: "Bandit Level 0 → Level 1"
date: 2024-01-23
categories: [Bandit]
tags: [Bandit]
---

## 문제
<https://overthewire.org/wargames/bandit/bandit1.html>

## 목표
홈 디렉토리에 위치한 `readme` 파일에 저장되어 있는 패스워드를 찾는다.

## 풀이
`cat readme` 명령으로 `readme` 파일의 내용을 확인한다.
```shell
bandit0@bandit:~$ cat readme
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
```  
&nbsp;  

**Password : NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL**

## 배운 것
- `cat` 명령어로 파일의 내용을 출력할 수 있다.