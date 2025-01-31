중간고사 내용 약간하고 git stash부터 기말고사 임
-------------------------------------------------------------------------------------------------------------------------
기말고사
============

stash:
---------------
>놓다, 남겨두다, 감추다, 안전한 곳에 숨겨두다
>
>커밋할 필요 없이 파일의 변경사항을 숨기건 비밀리에 저장할 수 있는 도구
>
>WD, SA의 원래의 내용을 stash 스택에 저장
>
>WD, SA -> GR의 마지막 커밋으로
>
>따로 저장했다가 다시 가져올 수 있는 기능
>
>저장내용: 작업 디렉토리 내용과 스테이지 내용

깃에서 임시저장소(스택구조)에 저장: 
--------------------------------
>-Stack of git stashes
>
>가장 최근의 내용이 가장 위에 저장되는 구조

작업 디렉토리가 정리(클린)되고 git이 추적한 모든 파일이 스택에 저장됨

마지막 저장냉용이 워킹디렉토리와 스테이징 에어리어의 냉용이 같은 상태를 클린하다 함
   워킹디렉토리 클린상태면 소스트리에 '커밋되지 않은 변경사항'이 뜨지 않음

stash는 WD와 SA의 내용을 stash라는 장소에 저장한다
Stash로 저장되는 내용은 작업 디렉토리 내용과 스테이지 내용이다

git stash:
-------------------
>WD아 SA의 내용을 stash에 저장한다

git stash apply: 
----------------------
>index 스테이지 영역의 냉용도 저장

git stash list: 
----------------------
>stash의 몇개의 stash파일이 있는지 뛰움

git stash show: 
--------------------
>stash에 몇줄이 추가 됬는지 간단하게 표시

git stash show -p: 
-----------------------
>stash에 몇줄이 추가됬는지 자세하게 표시

git stash show -p stash@{N}: 
-----------------------
>stash에 추가된 파일중 N번째 파일의 추가 내용을 자세하게 표시

touch [파일이름].py: 
---------------------
>리누스 명령어
>
>내용이 없는 파일을 생성

git stash -m '쓸 내용':
--------------------------
>git stash list에 stash@{N}: On master: 쓴내용 이뜸

git stash apply --index :
------------------------
>index로 저장되어있던 것을 다시 스테이지에 반영

git stash --keep-index: 
-----------------------
>현재 상태에서 스테이징 에어리어는 그대로 남기고 WD만 임시저장에 저장
>스테이징 에어리어는 임시저장에 제외하고 저장

git stash -u:
--------------------
>언트렉티드파일은 stash에 일반적으로 저장이 안됨
>
>이 명령어는 언트렉티드파일을  stash에 저장

git stash branch [브랜치이름]: 
---------------------------
>브랜치를 만들고 임시저장을 적용하고 적용된 임시저장은 삭제
>
>git stash list를 확인해보면 한줄이 사라진걸 볼 수 있음

git stash pop: 
----------------------
>가장 최근의 임시저장을 적용하고 임시저장 목록에서 제거
>
>git stash list를 확인하면 한줄이 사라진걸 볼 수 있음

git stash drop: 
-----------------
>가장 최근 임시저장 삭제

git stash drop stash@{N}: 
-------------------------
>N번째 저장된 임시저장 삭제

git clean -f: 
------------------
>언트렉티드파일은 그냥 git clean으로는 안지워짐, 강제 삭제인 -f를 써야됨

git clean -n: 
----------------------
>내가 지울 수 있는 언트렉티드 파일들을 보여줌

git clean -i: 
-----------------------
>언트렉티드파일에 대해 할 수 있는 6가지의 선택지를 뛰움
>
>숫자가 아닌 컬러로 표시된 알파벳을 입력해야 그 동작을 실행



