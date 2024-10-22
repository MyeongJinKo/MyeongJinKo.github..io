---
title: "절대경로와 상대경로는 무엇인가?"
author : Myeong Jin Ko
date : 2024-10-22 23:46:00 UTC+9
tags: [Codeit_WeeklyPaper]
---

## Weekly-Paper with Codeit! Data_Analyst_4
---
### 절대경로

**절대경로**(absolute path)는 쉽게 말해서 파일이나 폴더의 절대적인 전체 경로를 뜻한다. 
평소 하위폴더 생성 및 수정 작업을 했다면 이 절대경로를 복사했던 경험이 있을 것이다.

먼저 파일 시스템의 **루트 디렉터리**(Root Directory)에 대하여 알아보자. 루트 디렉터리는(<span style="color: gray;">/</span> 또는 Windows에서 드라이브 문자 C:\)라고 표현된다. 즉 파일 시스템의 최상위 디렉터리로
모든 파일 및 폴더의 시작점이다. 운영체제에 따라서 루트 디렉터리가 서로 다르며 **리눅스/유닉스** 계열에서는 /(슬래시)로 표현된다. /home/user는 루트 디렉터리에서 시작하여 home 폴더 안의 user 폴더를 나타낸다.
리눅스/유닉스 프롬프트에서 <span style="color: gray;">/</span>를 입력하면 루트 디렉터리를 확인할 수 있다. **윈도우** 계열에서는 컴퓨터의 각 드라이브마다 루트 디렉터리가 존재한다. <span style="color: gray;">C:\</span>, <span style="color: gray;">D:\</span>
처럼 드라이브 문자 뒤에 역슬래시"\"으로 표시된다.

절대경로는 이 루트 디렉터리부터 시작해서 나타내고 싶은 경로까지 전부 지정하는 경로를 말한다. 
**예시** <span style="color: gray;">C:\Users\gkdis\PythonMLWorkspace\Titanic\data</span> 은 내가 작업했던 Titanic(캐글데이터)의 경로이며, 같은 컴퓨터 안에서 어떤 폴더에서든 이 경로를 입력하면 data 폴더가 있는 디렉터리로 이동하게 된다.
