---
title: "[Dreamhack] addition-quiz | write-up"
date: 2024-10-30
categories: [Wargames]
tags: [Wargames, Dreamhack]
---

## 문제 설명

랜덤한 2개의 숫자를 더한 결과가 입력 값과 일치하는지 확인하는 과정을 50번 반복하는 프로그램입니다. 모두 일치하면 flag 파일에 있는 플래그를 출력합니다. 알맞은 값을 입력하여 플래그를 획득하세요.

## 문제 파일
```c
// Name: chall.c
// Compile Option: gcc chall.c -o chall -fno-stack-protector

#include <stdio.h>
#include <signal.h>
#include <stdlib.h>
#include <fcntl.h>
#include <unistd.h>
#include <time.h>

#define FLAG_SIZE 0x45

void alarm_handler() {
    puts("TIME OUT");
    exit(1);
}

void initialize() {
    setvbuf(stdin, NULL, _IONBF, 0);
    setvbuf(stdout, NULL, _IONBF, 0);

    signal(SIGALRM, alarm_handler);
}

int main(void) {
    int fd;
    char *flag;

    initialize();
    srand(time(NULL)); 

    flag = (char *)malloc(FLAG_SIZE);
    fd = open("./flag", O_RDONLY);
    read(fd, flag, FLAG_SIZE);
    close(fd);

    int num1 = 0;
    int num2 = 0;
    int inpt = 0; 

    for (int i = 0; i < 50; i++){
        alarm(1);
        num1 = rand() % 10000;
        num2 = rand() % 10000;
        printf("%d+%d=?\n", num1, num2);
        scanf("%d", &inpt);

        if(inpt != num1 + num2){
            printf("Wrong...\n");
            return 0;
        }
    } 
    
    puts("Nice!");
    puts(flag);

    return 0;
}
```

## 풀이

```python
from pwn import *
import re

r = remote("host3.dreamhack.games", 15125)

for i in range(52):
    res = r.recvline().decode()
    print(res)

    match = re.search(r'(\d+)\+(\d+)=\?', res)

    if match:
        fst = int(match.group(1))
        snd = int(match.group(2))

    ans = str(fst + snd)

    r.send(ans.encode('utf-8') + b'\n')
        
r.close()
```

`pwntools`와 정규식 연산 모듈인 `re`를 사용하였다.

`r.recvline()`로 한 줄씩 저장 후 `r'(\d+)\+(\d+)=\?'`을 통해 연산한 값을 전송하는 코드이다.

문제는 50문제이지만, 추가로 출력되는 메시지와 flag 때문에 52번 반복하였다.

## 배운 것
- `pwntools` 라이브러리를 통해 익스플로잇 코드를 작성할 수 있다.
- `re` 모듈 통해 정규식 연산을 할 수 있다.