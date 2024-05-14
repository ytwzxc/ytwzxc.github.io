---
title: "리눅스 기본 명령어"
date: 2024-01-19
categories: []
tags: [Linux]
---

`ls` : `List Segments`의 약자, 디렉토리와 파일 리스트 출력  
- `-a` : 숨겨진 파일까지 출력  
- `-l` : 세부 정보 출력  

<br>  

`pwd` : Print Working Directory의 약자, 현재 경로 출력  

<br>  

`cd` : Change Directory의 약자, 해당 경로로 이동 
- `cd ..` : 상위 경로로 이동  

<br>  

`mkdir` : `MaKe DIRectory`의 약자, 디렉토리 생성  

<br>  

`rmdir` : `ReMove DIRectory`의 약자, 디렉토리 삭제   

<br>  

`cp` : `CoPy`의 약자, 파일 복사  

<br>  

`rm` : `ReMove`의 약자 : 파일 삭제   

<br>  

`mv` : `MoVe`의 약자 : 파일 이름 변경  

<br>  

`w` : `Write or Word`의 약자, 서버 접속자 정보 출력  

<br>  

`finger` : 리눅스 계정 정보 출력  

<br>  

`tty` : `TeleTYpewriter`의 약자, 자신의 터미널 정보 출력  

<br>  

`ifconfig` : `InterFaceCONFIGuration`의 약자, 서버 IP 출력  

<br>  

`write` : 서버 접속자에게 메시지 전  

<br>  

`wall` : `Write ALL`의 약자, 서버 접속자 모두에게 메시지 전달  

<br>  

`whoami` : 자신의 정보 출력  

<br>  

`id` : `유저 ID`, `그룹 ID` 등 유저의 정보 출력   

<br>  

`uname` : `Unix NAME`의 약자, 유닉스 시스템 정보, 커널 정보 출력  

<br>  

`cat` : `CATenate`의 약자, 파일 내용 출력 
- `cat > a.txt` : 파일 생성  

<br>  

`tar` : `Tape ARchiver`의 약자, 여러 개의 파일을 합치거나 해제하는 명령어
- `-cvf` : 압축
- `-xvf` : 해제
- `-c` : 파일 생성
- `-x` : 압축 해제
- `-v` : 과정 출력
- `-f` : 백업  

<br>  

`gzip` : `GnuZIP`의 약자, 파일을 압축하거나 해제하는 명령어  

<br>  

`find` : 경로에 있는 모든 파일을 찾아 출력
- `-perm` : 권한과 일치하는 파일
- `-name` : 이름과 일치하는 파일
- `-user` : 유저와 일치하는 파일
- `-group` : 그룹과 일치하는 파일  

<br>  

`touch` : 비어있는 새 파일 만들기  

<br>  

`file` : 파일의 유형 출력  

<br>  

`echo` : 유저가 입력한 텍스트 출력 (뒤에 "" > 파일명 으로 내용 저장 가능)  

<br>  

`grep` : 특정 문자열 찾기  

<br>  

`man` : MANual의 약자, 특정 명령어의 매뉴얼 출력  

<br>  

`curl` : Client URL의 약자, 서버에 데이터를 보내거나 받음  

<br>  

`chmod`  : 파일 권한 변경 명령어 (chmod 권한 파일명)  

<br>  

`chown` 파일 소유자, 그룹 변경 (chown 사용자명[.그룹명] 파일명)

