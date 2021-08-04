# 과제 내용

>- 스프링 시큐리티와 jpa를 이용한 Docker 프로젝트입니다.
>- 프로그램 완성도 중요하지만, 그 과정이 더 중요하기 때문에 git commit 은 단위 작업 별로 자주 해주시길 바랍니다.
>- 별도의 개인 github 비공개 repository를 생성하고 비공개로 리뷰어 email 주소를 초대 해주시길 바랍니다.
>- 리뷰가 끝나면 해당 repository는 삭제 해주시면 감사하겠습니다.
>- thymeleaf 사용의 문제가 있다면 다른 기술을 사용하셔도 됩니다.
>- 시험 도중 급한 사정이 생기면 알려주시길 바랍니다. 경우에 따라 일정 조정이 가능합니다.

## 개인 github 가입 및 설정
### 계정 만들기(선택)
>- "Choose your personal plan" 에서 Free(무료)를 선택하거나, 사용중인 플랜을 이용하시면 됩니다.

### 저장소 만들기
>- Private 저장소를 만들어 주세요

### git clone 후 신규 git repository 로 변경
>- git clone 후 origin 저장소를 신규로 만드신 저장소로 바꿔 주세요

### 권한 추가
>- Setting > Manage access 로 이동하여 회사에서 안내받은 리뷰어 email 주소를 추가 합니다.

## 사전 확인 
### 프로젝트 설정 정보 확인하기
>- gradle 명령어를 이용해서 build 을 동작 시켜 보세요
>- 기본으로 설정된 포트를 확인하시고 docker-compose 동작 시켜서 서버를 동작 시켜 보세요  


### DB 확인 
>- MySQL 접속 후 데이터 확인
>- 로컬 Path와 Docker Mysql Data Volume 연결해보세요
>- 데이터 초기화 부분을 제거 하시고, 다시 시작해도 데이터가 초기화 안되는지 확인해 보세요 

### 로그인 시도 및 설정 변경
>- 기본으로 사용된 사용자를 확인해보시고 로그인을 시도 해보세요


## 페이징 및 데이터 생성 프로세스 구현

### 회원 목록 페이지를 만들어 주세요
>- /user/list 으로 작업 하시면 됩니다.
>- 저장된 모든 사용자를 출력해주세요
>- /user/list?name=검색어  로 호출하면 검색된 결과를 보여주세요
>- 공통 메뉴 파일 생성 후 아래 링크를 추가해주세요.
>>- 메인 : /index
>>- 회원가입 : /join
>>- 로그인 : /login or 로그아웃 : /logout
>>- 사용자 목록 : /user/list
>>- 관리자회원 생성 /admin/createMember

### 회원 추가 페이지를 만들어보세요
>- /admin/createMember 으로 회원 가입 페이지를 만들어 주세요
>- /admin/createMember 을 만들어서 회원을 생성해주세요
>- 기본 사용자를 20건으로 만들어 보세요
>- /user/list으로 아래 조건을 만족하도록 구현해 주세요
>>- Page 당 5건씩, 조건이 없을 때는 1Page
>>- 검색어를 입력 받아 이름 검색결과로 필터 보여주기
>>- 첫 페이지 마지막 페이지 바로가기 추가

## 권한 및 회원 가입 프로세스 구현

### Spring Security 를 이용한 필터를 구성 하세요
>- /, /index, /join, /login 는 누구나 다 접근 가능하게 해주세요
>- /user/* 는 로그인 한 사람만 접근하게 수정 해주세요
>- /admin/* 은 관리자로 설정한 사람

### 회원 가입 (Member를 수정해도 됩니다.)
>- /join으로 아래 조건을 만족하는 회원 가입 페이지를 만들어 주세요
>>- 동일한 ID로 회원 가입을 할 수 없습니다.
>>- 정규 표현식을 이용해서 비밀번호는 영문 대문자, 영문 소문자, 숫자, 특수문자 모두 1개 이상 포함 하도록 체크 해주세요
>>- /admin/createMember 에도 동일한 조건 적용
>- /login, /logout 아래 조건을 만족하는 로그인 페이지를 만들어 주세요
>>- 3번 이상 비밀번호가 틀릴 경우 10분뒤 로그인이 가능 하도록 해주세요
>>- /logout 으로 로그아웃후 / 으로 이동하도록 해주세요 
