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


## Django Form

### 1. Form을 사용하는 이유

1. 유효성 검사 및 데이터 손상의 방어 수단
2. 코드의 재사용 

### 2. Form Class

- Form 관리 시스템의 핵심
  - field, widget
  - 렌더링 방식 (as_p, as_table, as_ul)
- model을 정의하는 것과 유사하지만 목적과 용도가 분명히 다름


### 3. Form vs. ModelForm

### Form

- **어떤 모델에 저장해야할지 알지 못함**
- 유효성 검사를 한 뒤, 실제로 DB에 저장할 때는 **cleaned_data** 그리고 Article.objects.create()를 사용해서 따로 **`save()`** 를 진행 

### ModelForm

- **어떤 모델을 참고해야할지 이미 알고있음**

- forms.py에 Meta 정보(클래스)로 `models.py`에 정의한 Article을 넘겼기 때문에, 어떤 모델에 저장해야할지 알고 있어서 **바로 `form.save()`가 가능**


### STATIC_ROOT

- 배포할 때 사용
- 개발할 때는 사용할 일 X
- python manage.py collectstatic => 모든 static 파일을 한 곳으로 모아주는 명령어
- **그 모든 파일을 "어디에" 모을 건지 지정하는 변수**



### STATIC_URL

- 내 컴퓨터에 있는 정적 파일(JS, CSS, images)을 **외부에서 접근할 수 있게끔**

  **URL을 부여해줄 때** 사용하는 prefix 

- `http://localhost:8000/static/abc.png`


### STATICFILES_DIRS

> TEMPLATES => DIRS = [ ]

- 장고는 기본적으로 모든 정적 파일을 찾을 때 

  각 앱의 static이라는 이름의 폴더를 찾는다.

- **앱 안의 static 폴더 말고, 외부에 별도의 경로를 지정해주고 싶을 때**

  **사용하는 리스트 (또는 변수)**


### MEDIA_ROOT

- 사용자가 올리는 파일을 저장하는 경로를 지정하는 변수


### MEDIA_URL

- static_url과 동일
- 사용자가 올린 파일들에만 적용됨








