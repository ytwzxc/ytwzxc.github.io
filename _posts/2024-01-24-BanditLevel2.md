---
title: "Bandit Level 2 → Level 3"
date: 2024-01-24
categories: [Bandit]
tags: [Bandit]
---
## 문제
<https://overthewire.org/wargames/bandit/bandit3.html>

## 목표
홈 디렉토리에 위치한 `spaces in this filename` 파일에 저장되어 있는 패스워드를 찾는다.

## 풀이
`cat space in this filename` 명령을 시도해보니 띄어쓰기 때문에 명령이 4개로 각각 나뉘어 실행된다.

```shell
bandit2@bandit:~$ cat spaces in this filename
cat: spaces: No such file or directory
cat: in: No such file or directory
cat: this: No such file or directory
cat: filename: No such file or directory
```  
&nbsp;  

따옴표를 사용해 하나로 묶어준다.

```
bandit2@bandit:~$ cat 'spaces in this filename'
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
```  
&nbsp;  

**Password : aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG**

## 배운 것
- 파일 이름에 띄어쓰기가 포함된 경우 따옴표로 묶는다.