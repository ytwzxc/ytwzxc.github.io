---
title: "Bandit Level 11 → Level 12"
date: 2024-01-29
categories: [Bandit]
tags: [Bandit]
---

## 문제
<https://overthewire.org/wargames/bandit/bandit12.html>

## 목표
`data.txt` 파일에 저장되어 있는 패스워드를 찾는다.
> 패스워드는 대소문자가 13자씩 밀려있다.

## 풀이
`cat data.txt` 명령으로 파일의 내용을 확인해보니 어떤 메시지가 13자씩 밀려있다.

```sh
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
```  

&nbsp;  

`tr` 명령어를 사용하면 알파벳의 순서를 바꿀 수 있다.  

13자씩 밀렸으니 알파벳의 순서를 `A-Za-z`에서 `N-ZA-Mn-za-m`으로 바꿔야 한다.  

&nbsp;  

`cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'` 명령으로 알파벳의 순서를 바꿔서 출력한다.

```sh
bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
```  

&nbsp;  

**Password : JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv**


## 배운 것
- `tr` 명령어로 문자를 변환할 수 있다.