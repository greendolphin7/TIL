## 장고 튜토리얼

장고는 MTV (Model — Template — View) 을 하게 도와주는 웹 프레임워크


### 시작하기

1. 폴더 만들어주기
2. 가상환경 만들기, 실행
3. 터미널에서 django 설치
4. django-admin 으로 기본적인 앱 설치

### Model
5. setting.py에 앱 추가
6. model.py에서 데이터 필드와 속성 정하기
7. manage.py를 실행시켜 makemigrations, migrate 두 명령어로 DB 생성
8. sqlite와 어떻게 연동시킬지는 더 찾아봐야 함.

---------------------------------------------------------------------------


### 프로젝트 생성
```
$ django-admin startproject 프로젝트 이름
```

### 앱 생성
```
$ python manage.py startapp 앱이름
```

앱 만들고 settings.py 에 앱 등록 / + 언어, 시간 등록

만드는 순서 : urls.py -> views.py -> index.html

---------------------------------------------------

{% extends '파일이름.html' %}  # 템플릿 상속 받기

{% block content %} {% endblock content %} 로 상속받는 템플릿에 내용 추가하는 부분

### 동적 라우팅
```
path('내url/<int:아이디>/', views.내url, name='url별명')
```

```html
<form action="{% url 'articles:create' %}" method="POST">
```
위와 같이 form을 통해 데이터를 주고 views에서 request로 받는다. (POST 요청)
