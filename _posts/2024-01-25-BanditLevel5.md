---
title: "Bandit Level 5 → Level 6"
date: 2024-01-25
categories: [Bandit]
tags: [Bandit]
---

## 문제
<https://overthewire.org/wargames/bandit/bandit6.html>

## 목표
다음 조건을 따르는 `inhere` 디렉토리 안 어딘가에 저장되어 있는 패스워드를 찾는다.  
- 사람이 읽을 수 있다.
- 크기가 1033 바이트다.
- 실행할 수 없다.

## 풀이
`cd inhere` 명령으로 `inhere` 디렉토리로 이동한다.
```shell
bandit5@bandit:~$ cd inhere
```  

&nbsp;  

`ls` 명령으로 디렉토리 내 파일 목록을 확인해보니 20개의 파일들이 있다.  
```shell
bandit5@bandit:~/inhere$ ls
maybehere00  maybehere04  maybehere08  maybehere12  maybehere16
maybehere01  maybehere05  maybehere09  maybehere13  maybehere17
maybehere02  maybehere06  maybehere10  maybehere14  maybehere18
maybehere03  maybehere07  maybehere11  maybehere15  maybehere19
```  
&nbsp;  

문제에 제시된 조건을 이용해 파일을 찾아야 한다. 

find 명령어를 사용하면 조건에 맞는 파일을 찾을 수 있다.  

> `find -size N` : N 크기의 파일을 검색한다.  

> 사이즈 단위  
b : 블록단위  
c : byte  
k : kbyte  
w : 2byte 워드  
m : mbyte  
g : gbyte  

&nbsp;  

`find -size 1033c` 명령으로 크기가 1033byte인 파일을 찾을 수 있다.

```shell
bandit5@bandit:~/inhere$ find -size 1033c
./maybehere07/.file2
```  

&nbsp;  

`cat ./maybehere07/.file2` 명령으로 파일의 내용을 확인한다.

```shell
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```  

&nbsp;  

**Password : P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU**

## 배운 것
- find 명령어로 조건에 맞는 파일을 찾을 수 있다.
- 사이즈 단위의 종류