---
title: "Bandit Level 6 → Level 7"
date: 2024-01-25
categories: [Bandit]
tags: [Bandit]
---

## 문제
<https://overthewire.org/wargames/bandit/bandit7.html>

## 목표
다음 조건을 따르는 서버 어딘가에 있는 파일에 저장되어 있는 패스워드를 찾는다.  
- bandit7 유저가 소유한다.
- bandit6 그룹이 소유한다.
- 크기가 33 바이트다.

## 풀이
조건에 해당하는 유저와 그룹이 소유하는 파일을 찾으려면 `find` 명령어의 `-user`, `-group` 옵션을 사용해야 한다.  

`find -user bandit7 -group bandit6 -size 33c` 명령으로 조건에 해당하는 파일을 찾을 수 있다.

```shell
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c
find: ‘/etc/ssl/private’: Permission denied
find: ‘/etc/polkit-1/localauthority’: Permission denied
.
.
.
find: ‘/run/systemd/inaccessible/dir’: Permission denied
find: ‘/run/lock/lvm’: Permission denied
```
수많은 권한 거부 메시지들이 출력된다.  

이 중 권한이 승인된 파일만 찾아야 하므로 권한 거부 메시지들은 안 보이게 해야 한다.  

&nbsp;  

명령어 뒤에 `2>/dev/null`를 붙여 권한 거부 메시지들이 안 보이게 해준다.
> '2>/dev/null'는 표준 에러 메시지를 `/dev/null`로 보낸다는 의미이다.

```shell
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
```  

&nbsp;  

`cat /var/lib/dpkg/info/bandit7.password` 명령으로 파일의 내용을 확인한다.

```shell
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
```  

&nbsp;  

**Password : z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S**

## 배운 것
- `find` 명령어에서 `-user`, `-group` 옵션을 사용해 파일을 찾을 수 있다.
- `2>/dev/null`로 에러 메시지를 안 보이게 할 수 있다.