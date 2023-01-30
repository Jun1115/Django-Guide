# Django-boot

## Django 기초

Djano란 보안이 우수하고 유지보수가 편리한 웹사이트를 신속하게 개발하는 하도록 도움을 주는 파이썬 웹 프레임워크이다.

### 1. MVC & MTV 
[<img src = "https://tecoble.techcourse.co.kr/static/c73f913a7c220ec8cb3ee9a8579468b4/91709/mvc.png" width="400px">](https://tecoble.techcourse.co.kr/post/2021-04-26-mvc/)
 - Model: 안전하게 데이터를 저장
 - View: 데이터를 적절하게 유저에게 보여줌
 - Control, Template(Django): 사용자의 입력과 이벤트에 반응하여 Model과 View를 업데이트
 
### 2. Django 개념
[<img src = "https://velog.velcdn.com/images%2Fmini_y%2Fpost%2Ff57ba915-4f63-427b-9482-95e97dd5d12e%2F%E1%84%8C%E1%85%A1%E1%86%BC%E1%84%80%E1%85%A9.png" width="800px">](https://velog.io/@mini_y/Django-%EA%B0%9C%EB%85%90%EC%A0%95%EB%A6%AC)

 - 녹색: 실질적으로 사용할 파일&nbsp;
 - 회색: 장고가 뒤에서 다양한 처리를 도와줌
 - WSGI(Web Server Gateway Interface): 웹서버와 장고를 적절하게 결합시켜주는 역할
 - MODEL : DATABASE에서 쿼리를 따로 작성할 필요가 없이 변수만 다루면 알아서 데이터를 받는 역할
 - 구성이 복잡한 이유: 다수의 사람이 한번의 작업을 하게될 경우 문제가 발생할 가능성이 높았음. 이를 단계를 분리하는 방법으로 해결

### 3. Project와 APP
 - Project 는 하나의 웹사이트
 - APP 은 웹사이트 속에 다양한 기능들 Ex) 블로그, 게시판, 전자상거래와 관련된 기능들 등
 - APP 은 다른 프로젝트에서 활용 가능

## Django 설치

(<>(화살괄호)는 명령어 구분선, 터미널에 명령어 입력 시 괄호 제외하고 입력 )

1. 터미널에 < pip install django > ▶ django 설치 (설치 완료 시 django-admin 명령어 사용 가능)
2. < django-admin > ▶ 사용가능 명령어 출력
3. < django-admin startproject myproject(폴더명) . > ▶ . 은 현재 위치, 폴더 지정 안해주면 myproject 폴더 안에 myproject 폴더 생성
   <img src = "https://user-images.githubusercontent.com/114639257/215416131-8c5a46e7-f90e-4c8c-ad34-7867dde38d01.PNG" width="200px">

4. < python manage.py > ▶ 사용가능 명령어 출력 (myproject 폴더에 __pycache__ 파일 자동생성)

   <img src = "https://user-images.githubusercontent.com/114639257/215417529-a20d677e-6351-459e-afef-2deed637689c.PNG" width="400px">

5. < python manage.py runserver > ▶ runserver 입력 시 django 기본 서버 실행 (디폴트 8000번 포트)
   <img src = "https://user-images.githubusercontent.com/114639257/215418829-4c5755e9-d8d1-401f-9662-73dad68b174f.PNG" width="400px">
   
   <img src = "https://user-images.githubusercontent.com/114639257/215418834-f5d4d5b6-87a0-4f3c-974c-85c2222bd6a0.PNG" width="400px">
6. 서버 실행 취소 ▶ < ctrl(컨트롤) + c >

7. 이미 8000번 포트를 사용중이라면 실행 X ▶ runserver 뒤에 다른 포트 번호 입력 Ex) < python manage.py runserver 8888 >

   <img src = "https://user-images.githubusercontent.com/114639257/215419855-2d1157be-ce48-4bab-8334-0c8fad549778.PNG" width="400px">


