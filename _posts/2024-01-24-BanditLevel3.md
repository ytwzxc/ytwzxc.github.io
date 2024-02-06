---
title: "Bandit Level 3 → Level 4"
date: 2024-01-24
categories: [Bandit]
tags: [Bandit]
---

## 목표
다음 문제의 패스워드는 inhere 디렉토리에 위치한 숨겨진 파일에 저장되어 있다.

## 풀이
cd inhere 명령으로 inhere 디렉토리로 이동한다.
```shell
bandit3@bandit:~$ cd inhere
```

ls 명령으로 inhere 디렉토리 내 파일 목록을 확인해보니 아무 파일도 확인되지 않는다.
```shell
bandit3@bandit:~/inhere$ ls

```

숨겨진 파일을 확인하기 위해서는 ls 명령어에 -a 옵션을 붙여야 한다.
```shell
bandit3@bandit:~/inhere$ ls -a
.  ..  .hidden
```

cat .hidden 명령으로 파일의 내용을 확인한다.

```shell
bandit3@bandit:~/inhere$ cat .hidden
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
```

**Password : 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe**

## 배운 것
- cd 명령어로 디렉토리의 위치를 이동할 수 있다.
- ls 명령어로 디렉토리 내 파일과 디렉토리의 목록을 확인할 수 있다.
- 숨겨진 파일을 확인하기 위해서는 ls 명령어에 -a 옵션을 붙여야 한다.