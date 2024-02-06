---
title: "Bandit Level 0 → Level 1"
date: 2024-01-23 13:23:00 +0800
categories: [Bandit]
tags: [Bandit]
---

## 목표
다음 레벨의 패스워드는 홈 디렉토리에 위치한 readme 파일에 저장되어 있다.

## 풀이
cat readme 명령으로 readme 파일의 내용을 확인한다.
```shell
bandit0@bandit:~$ cat readme
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
```

**Password : NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL**

## 배운 것
- cat 명령어로 파일의 내용을 확인할 수 있다.