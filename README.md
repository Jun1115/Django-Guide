# Django

Djano란 보안이 우수하고 유지보수가 편리한 웹사이트를 신속하게 개발하는 하도록 도움을 주는 파이썬 웹 프레임워크이다.

## 1. Design Pattern MVC & MTV 
[<img src = "https://tecoble.techcourse.co.kr/static/c73f913a7c220ec8cb3ee9a8579468b4/91709/mvc.png" width="400px">](https://tecoble.techcourse.co.kr/post/2021-04-26-mvc/)
 - Model: 안전하게 데이터를 저장
 - View: 데이터를 적절하게 유저에게 보여줌
 - Control, Template(Django): 사용자의 입력과 이벤트에 반응하여 Model과 View를 업데이트
 
## 2. Django 개념
[<img src = "https://velog.velcdn.com/images%2Fmini_y%2Fpost%2Ff57ba915-4f63-427b-9482-95e97dd5d12e%2F%E1%84%8C%E1%85%A1%E1%86%BC%E1%84%80%E1%85%A9.png" width="800px">](https://velog.io/@mini_y/Django-%EA%B0%9C%EB%85%90%EC%A0%95%EB%A6%AC)

 - 녹색: 실질적으로 사용할 파일&nbsp;
 - 회색: 장고가 뒤에서 다양한 처리를 도와줌
 - WSGI(Web Server Gateway Interface): 웹서버와 장고를 적절하게 결합시켜주는 역할
 - MODEL : DATABASE에서 쿼리를 따로 작성할 필요가 없이 변수만 다루면 알아서 데이터를 받는 역할
 - 구성이 복잡한 이유: 다수의 사람이 한번의 작업을 하게될 경우 문제가 발생할 가능성이 높았음. 이를 단계를 분리하는 방법으로 해결

## 3. Project와 APP
 - Project 는 하나의 웹사이트
 - APP 은 웹사이트 속에 다양한 기능들 Ex) 블로그, 게시판, 전자상거래와 관련된 기능들 등
 - APP 은 다른 프로젝트에서 활용 가능

<br/><br/><br/>

# Django 설치방법

- 설치 영상
[https://www.youtube.com/watch?v=xGdUNyVkAto] - Django 설치방법

## Django 설치

~~~
python pip -m install django 
~~~

## Django 사용가능 명령어 출력

~~~
django-admin
~~~

## 프로젝트 생성

~~~
django-admin startproject myproject(폴더명) .
~~~

- . 은 현재 위치, 폴더 지정 안해주면 myproject 폴더 안에 myproject 폴더 생성

<img src = "https://user-images.githubusercontent.com/114639257/215416131-8c5a46e7-f90e-4c8c-ad34-7867dde38d01.PNG" width="200px">

## manage.py 사용가능 명령어 출력

~~~
python manage.py
~~~

- myproject 폴더에 __pycache__ 파일 자동생성

<img src = "https://user-images.githubusercontent.com/114639257/215417529-a20d677e-6351-459e-afef-2deed637689c.PNG" width="400px">

## Django 기본 서버 실행
 
~~~
python manage.py runserver
~~~

- Default 8000번 포트

<img src = "https://user-images.githubusercontent.com/114639257/215418829-4c5755e9-d8d1-401f-9662-73dad68b174f.PNG" width="400px">
<img src = "https://user-images.githubusercontent.com/114639257/215418834-f5d4d5b6-87a0-4f3c-974c-85c2222bd6a0.PNG" width="400px">

## 서버 실행 취소

~~~
ctrl(컨트롤) + c
~~~

## 이미 특정 포트를 사용중이라면 실행 X
- runserver 뒤에 다른 포트 번호 입력
~~~
python manage.py runserver 8888
~~~

<img src = "https://user-images.githubusercontent.com/114639257/215419855-2d1157be-ce48-4bab-8334-0c8fad549778.PNG" width="400px">

## 포트의 개념

<img src = "https://user-images.githubusercontent.com/114639257/215434523-d69d32d7-8d6f-4002-b1be-0bff6ee0cfb3.jpg" width="400px">

### A 컴퓨터
- 내 컴퓨터

### B 컴퓨터
- IP Address : 127.0.0.1 를 가진 서버 컴퓨터 (3개의 서버소프트웨어가 설치되어 동작중)

### A 에서 B 로 접속하려면 

~~~
http://127.0.0.1
~~~

- 이 주소에는 여러가지 서버소프트웨어가 동작중이라 어떤 것이 통신할지 알수 없음
- 이러한 문제를 해결하기 위해 PORT 존재

### Port Listening 
Ex) 1번 서버는 80번 PORT 에 접속해 있다.

<img src = "https://user-images.githubusercontent.com/114639257/215435737-0bc68544-20df-45e5-8223-fce568bcad55.jpg" width="400px">

### 특정 서버에 Listening 하려면 그에 맞는 PORT 에 접속

~~~
http://127.0.0.1.8888
~~~

<img src = "https://user-images.githubusercontent.com/114639257/215436937-e5ec369c-663e-468b-83f9-f2e288cd111e.PNG" width="400px">


<br/><br/><br/>

## app 만들기

- 애플리케이션을 project 안에서 구현하는 것이 아닌 app 이라는 더 작은 단위를 만들어 그곳에서 구현함
- 프로젝트를 하다보면 복잡해질 수 있는데 서로 연관된 로직들을 모아서 그룹핑 하고 싶을 때 여러개의 앱을 만들어 정리정돈 하게 됨
- 각 app 에는 urls.py 파일이 담겨질 것, app 안에는 view 라는 것을 만들게 됨.
- view 안에는 여러가지 def(함수) 들을 만들어서 애플리케이션의 구체적인 구현을 하게 될 것임 

