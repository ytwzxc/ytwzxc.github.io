---
title: "Bandit Level 12 → Level 13"
date: 2024-01-30
categories: [Bandit]
tags: [Bandit]
---

## 문제
<https://overthewire.org/wargames/bandit/bandit13.html>

## 목표
여러 번 압축된 hexdump인 `data.txt` 파일에 저장되어 있는 패스워드를 찾는다.
> 이 레벨에서는 /tmp에 `mkdir` 명령어를 사용해 디렉토리를 만드는 것이 유용하다.

## 풀이
목표에 있는 설명대로 `mkdir /tmp/new_dir` 명령으로 디렉토리를 만든다.

```sh
bandit12@bandit:~$ mkdir /tmp/new_dir
```  

&nbsp;  

`cp data.txt` 명령으로 파일을 새로 만든 디렉토리로 복사해준다. 

```sh
bandit12@bandit:~$ cp data.txt /tmp/new_dir
```

&nbsp;  

`cd /tmp/new_dir` 명령으로 `new_dir`로 이동한다.

```sh
bandit12@bandit:~$ cd /tmp/new_dir
```  

&nbsp;  

`cat data.txt` 명령으로 파일을 확인해보니 hexdump인 것을 알 수 있다.

```sh
bandit12@bandit:/tmp/new_dir$ cat data.txt
00000000: 1f8b 0808 6855 1e65 0203 6461 7461 322e  ....hU.e..data2.
00000010: 6269 6e00 013d 02c2 fd42 5a68 3931 4159  bin..=...BZh91AY
00000020: 2653 5948 1b32 0200 0019 ffff faee cff7  &SYH.2..........
.
.
.
00000230: 003c a584 d4c1 61ef eb02 3f65 3a54 a3a2  .<....a...?e:T..
00000240: a565 c154 34c2 b162 d206 1ff8 bb92 29c2  .e.T4..b......).
00000250: 8482 40d9 9010 b3a9 e478 3d02 0000       ..@......x=...
```  

&nbsp;  

`xxd data.txt > data` 명령으로 새 파일에 바이너리 파일로 저장한다.

```sh
bandit12@bandit:/tmp/new_dir$ xxd -r data.txt > data
```

> `xxd -r data.txt > data`는 `xxd -r data.txt`의 출력을 `data` 파일에 저장한다는 의미이다.  

&nbsp;  

`file data` 명령으로 파일의 형식을 확인한다.  

```sh
bandit12@bandit:/tmp/new_dir$ file data
data: gzip compressed data, was "data2.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 573
```

`gzip`으로 압축된 파일인 것을 알 수 있다.

압축을 풀려면 확장자를 변경해줘야 한다.

파일의 이름은 `mv` 명령어를 사용해 변경할 수 있다.

`mv data data.gz` 명령으로 압축을 푼다.


