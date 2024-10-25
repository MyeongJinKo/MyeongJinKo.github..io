---
title: "절대경로와 상대경로 그리고 Git의 branch"
author : Myeong Jin Ko
date : 2024-10-21 23:46:00 UTC+9
tags: [Codeit_WeeklyPaper]
---

## Weekly-Paper with Codeit! Data_Analyst_4
---
### 절대경로

**절대경로**(absolute path)는 쉽게 말해서 파일이나 폴더의 절대적인 전체 경로를 뜻한다. 
평소 하위폴더 생성 및 수정 작업을 했다면 이 절대경로를 복사했던 경험이 있을 것이다.

먼저 파일 시스템의 **루트 디렉터리**(Root Directory)에 대하여 알아보자. 루트 디렉터리는(`/` 또는 Windows에서 드라이브 문자 `C:\`)라고 표현된다. 즉 파일 시스템의 최상위 디렉터리로
모든 파일 및 폴더의 시작점이다. 운영체제에 따라서 루트 디렉터리가 서로 다르며 **리눅스/유닉스** 계열에서는 /(슬래시)로 표현된다. `/home/user`는 루트 디렉터리에서 시작하여 home 폴더 안의 user 폴더를 나타낸다.
리눅스/유닉스 프롬프트에서 `/`를 입력하면 루트 디렉터리를 확인할 수 있다. **윈도우** 계열에서는 컴퓨터의 각 드라이브마다 루트 디렉터리가 존재한다. `C:\`, `D:\`
처럼 드라이브 문자 뒤에 역슬래시`\`으로 표시된다.

절대경로는 이 루트 디렉터리부터 시작해서 나타내고 싶은 경로까지 전부 지정하는 경로를 말한다. 

**예시**
`C:\Users\gkdis\PythonMLWorkspace\Titanic\data` 은 내가 작업했던 Titanic(캐글데이터)의 경로이며, 같은 컴퓨터 안에서 어떤 폴더에서든 이 경로를 입력하면 data 폴더가 있는 디렉터리로 이동하게 된다.

--------

### 상대경로

**상대경로**(relative path)는 쉽게 말해 현재 내 디렉터리를 기준으로 상대적인 위치를 뜻한다.
상대경로는 절대경로에 비해 폴더 구성이 상대적으로 지정되어 있어 폴더를 옮길 때 폴더 별로 재설정이 필요없다. 대신 폴더의 전체적인 구성을 한눈에 확인하기 어려운 단점이 있다.

**예시** 
현재 내가 열어놓은 폴더는 `data`폴더이고 이 `data`폴더 안의 `train.csv`파일을 참조하는 방법은 `data/train.csv`이다.
만약 `data`의 상위폴더인 `Titanic`폴더에서 `submission.csv`파일을 참조하고 싶을 때에는 `../submission.csv` 를 입력하면 된다.


---------

### branch 브렌치

**branch** 는 쉽게 말해서 하나의 코드를 관리하는 흐름이라고 이해할 수 있다. branch는 나뭇가지라는 단어로 코드를 작성해가며 여러 수정된 버전이 존재한다.

**예시**
만약 오픈소스 프로그램을 만들어 배포하고 싶을 때 유료버전과 무료버전으로 구분할려 한다. 이 때 무료버전까지의 구현된 기능은 당연하게도 유료버전에서도 사용할 수 있다. 여기서 유료버전에서만 사용할 수 있도록 +a 기능을 별도로 구현하는 작업을 새로운 branch를 만든다고 볼 수 있다.

![git_branch](https://github.com/user-attachments/assets/e19bb617-b4e4-489d-a490-212ef8b70c2b)

**branch 관련 명령**
```
- git branch : 현재 존재하는 branch 출력
- git branch (branch 이름) : 새로운 branch 생성
- git checkout (branch 이름) : (branch 이름) branch로 이동 -> <중요> 사실 HEAD가 main과 premium 으로 이동하는 것
- git checkout -b (branch 이름) : 새로운 branch 생성하고 그 생성된 branch로 바로 변경
- git branch -d (branch 이름) : (branch 이름) branch를 삭제
- git add . :
- git commit m "~~~~" : 현재 branch에 커멧
- git merge --abort : 머지를 하다가 conflict가 발생하면, 일단 머지 작업 취소하고 이전 상태로 돌아감
- git merge (기존 branch 이름) : 현재 branch에 다른 branch를 머지 (fast forward merge도 있다)
```

**brance MERGE** 
main에 있는 기능을 premium에도 넣고 싶을 때 merge를 사용하여 합친다.
헤드가 가리키던 커밋에 다른 브랜치가 가리키던 커밋을 합쳐서 새로운 커밋을 만드는 작업

```
- git merge main : 현재 위치인 premium branch에 master branch를 합친다.
- 현재 head가 premium을 가리키고 있을 때 다른 브랜치가 가리키던 커밋과 합쳐서 새로운 커밋을 만든 작업.
```
***merge에 실패하여 CONFLICT(충돌)이 발생하였을 때***
`git merge --abort` 입력
git status를 확인하여 conflict가 발생한 파일을 확인하여 문제가 있는 파일에 checkout하여 접속 후 문제를 해결
