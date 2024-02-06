---
title: "Bandit Level 2 → Level 3"
date: 2024-01-24
categories: [Bandit]
tags: [Bandit]
---

## 목표
다음 레벨의 패스워드는 홈 디렉토리에 위치한 spaces in this filename 파일에 저장되어 있다.

## 풀이
cat space in this filename 명령을 시도해보니 띄어쓰기 때문에 4개로 나뉘어 각각 실행된다.

```shell
bandit2@bandit:~$ cat spaces in this filename
cat: spaces: No such file or directory
cat: in: No such file or directory
cat: this: No such file or directory
cat: filename: No such file or directory
```

따옴표를 사용해 하나로 묶어주면 명령이 잘 실행된다.

```
bandit2@bandit:~$ cat 'spaces in this filename'
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```

**Password : aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG**

## 배운 것
- 파일 이름에 띄어쓰기가 포함된 경우 따옴표로 묶는다.