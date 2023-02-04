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

## app이란

- 애플리케이션을 project 안에서 구현하는 것이 아닌 app 이라는 더 작은 단위를 만들어 그곳에서 구현함
- 프로젝트를 하다보면 복잡해질 수 있는데 서로 연관된 로직들을 모아서 그룹핑 하고 싶을 때 여러개의 앱을 만들어 정리정돈 하게 됨
- 각 app 에는 urls.py 파일이 담겨질 것, app 안에는 view 라는 것을 만들게 됨.
- view 안에는 여러가지 def(함수) 들을 만들어서 애플리케이션의 구체적인 구현을 하게 될 것임 
### 전체적인 맥락
<img src = "https://user-images.githubusercontent.com/114639257/216614950-b4bcb119-7cd9-42a4-9365-acfa714c08fe.PNG" width="400px">

## app 만들기

~~~
django-admin startapp myapp
~~~

<img src = "https://user-images.githubusercontent.com/114639257/216616244-096787d7-fbf1-4a2b-9db0-241a429cad31.PNG" width="200px">

## Routong
- 어떤 웹 프레임워크를 사용하든 제일 먼저 하는 작업
- Route = 경로
- 사용자가 접속한 각각의 Route 를 누가 처리할 것인가를 지정하는 것

<img src = "https://user-images.githubusercontent.com/114639257/216617456-e7b58fcb-8c00-4898-a7ce-0e4ab2ea1394.PNG" width="400px">

## Routong 해보기
- http://127.0.0.1/ 의 접속을 myapp/views 로 import(위임)해보기
### myproject/urls.py
~~~
myproject URL Configuration

The `urlpatterns` list routes URLs to views. For more information please see:
    https://docs.djangoproject.com/en/4.1/topics/http/urls/
Examples:
Function views
    1. Add an import:  from my_app import views
    2. Add a URL to urlpatterns:  path('', views.home, name='home')
Class-based views
    1. Add an import:  from other_app.views import Home
    2. Add a URL to urlpatterns:  path('', Home.as_view(), name='home')
Including another URLconf
    1. Import the include() function: from django.urls import include, path
    2. Add a URL to urlpatterns:  path('blog/', include('blog.urls'))
~~~
~~~
from django.contrib import admin
from django.urls import path, include
# http://127.0.0.1/ 
# http://127.0.0.1/app/

# http://127.0.0.1/create/
# http://127.0.0.1/read/1/

urlpatterns = [
    path("admin/", admin.site.urls),
    path('', include('myapp.urls'))
]
~~~

### myapp/urls.py

- myapp 폴더에 urls.py 파일 생성

~~~
from django.urls import path
from myapp import views
urlpatterns = [
    path('', views.index),
    path('create/', views.create),
    path('read/<id>/', views.read)
]
~~~

### myapp/views.py

~~~
from django.shortcuts import render, HttpResponse

def index(request):
    return HttpResponse('Welcome!')
    
def Create(request):
    return HttpResponse('Create')
    
def Read(request, id):
    return HttpResponse('Read'+id)
~~~

###결과
- Ex) /read/1 으로 접속했다면?
<img src = "https://user-images.githubusercontent.com/114639257/216767781-199c6b6b-bc3b-4677-bbe4-33e2bc0042ca.PNG" width="600px">
<img src = "https://user-images.githubusercontent.com/114639257/216767575-fa6e0df7-16d3-456e-a146-83eacaad89fa.PNG" width="200px">
<img src = "https://user-images.githubusercontent.com/114639257/216767582-40be8dd6-500b-4794-bd4d-88479334b755.PNG" width="200px">
<img src = "https://user-images.githubusercontent.com/114639257/216767579-8a72c826-3df5-4086-9c92-3fdc13cdfdbe.PNG" width="200px">
<img src = "https://user-images.githubusercontent.com/114639257/216767581-9de883f7-e980-4146-a019-5e198071ed72.PNG" width="200px">

