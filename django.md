csrf

auto now - 데이터 필드 

admin site register

mtv

user model

modelform / form

url

url variable



위임하려면

from django.urls import include 

path('app/', include('myapp.urls'))

view.py

def index(request):

​	return HttpResponxe('Welcom!')

바뀔수있을것 같은건 <id> 꺽세 

def read(request, id):

​	return HttpResponse('Read!' + id)

mtv

- 장고는 mvc패턴을 기반으로한 mtv model template view

- model: 데이터 로직
- template : 레이아웃과 화면처리, 화면상의 사용자 인터페이스 구조와  레이아웃 정의
- view: model 과 template 과 관련한 로직을 처리해서 응당ㅂ을 반환
  - 데이터가 필요하다면 model에 접근헤서 데이터터를 가져오고
  - mvc에서 컨트롤러 



## url namespace

url namespace : url  tag 변화 {% url 'idex' %} 에서 {% url 'articles:index'%}

app_name = 'articles'

URL namespace를 사용하면 서로 다른 앱에서 동일한 URL 이름을 사용하는 경우에도 이름이 지정된 URL을 고유하게 사용할 수 있음 

문제 발생: articles app index 페이지에 작성한 두번째 앱 index로 이동하는 하이퍼 링크를 클릭시 페이지로 다시 이동하는 문제를 url namespace로 해결가능 

## template namespace

app_name/templates/app_name/

django templates의 기본 경로 자체를 변경할 수는 없기 때문에 물리적으로 이름 공간을 만드는 것

articles/view.py 에서 

'articles/index.html'

templates namespace를 고려해야할까?

- 만약 단일 앱으로만 이루어진 프로젝트라면 상관없음
- 여러앱이 되어있을때에도 탬플릿 파일 이름이 겹치징낳게 하면 되지만 앱이 많아지면 대부분 같은 이름의 템플릿 파일이 존자해기 마련이다. 

## model

- 장고는 웹 애플리케이션 데이터를 구조화 하고 조작하기 위한 추상적인 계층을 제공한다. 
- 단일한 데이터에 대한 정보를 가진다
- 사용자가 저장하는 데이터들의 필수적인 필드들과 동작을 포함한다. 
- 일반적으로 각각 모델은 하나의 데이터 베이스 테이블에 매핑한다. 모델 클래스 1개 = 데이터 베이스 테이블 1개 
- 저장된 데이터 베이스의 구조 
- 모델을 통해서 데이터 관리 
- 매핑: 하나의 값을 다른값으로 대응시키는 것 
- 모델 클래스를 작성하는 것은 데이터 베이스 테이블의 스키마를 저으의하는 것이다.
- 모델 클래스 == 테이블 스키마 
- 각모델은 django.models.Model 클래스의 서브 클래스로 표현된다. 
- 클래스 상속 기반 형태의 장고 프레임워크 개발 - 프레임워크에서는 잘 만들어진 도구를 가져다가 잘쓰는것 

### charField

- 길이의 제한이 있는 문자열을 넣을때 사용 
- max_length: 필드의 최대 길이, 데이터 베이스와 장고의 유효성 검사에서 활용됨 , charfield의 필수인자
- textfield: 글자수가 많을때 사용 , 모델과 데이터 베이스 단계에는 적용되지 않음. 실제로 저장될때 길이에 대한 유효성 검증하지 않는다. 

database

- 체계화된 데이터의 모임
- 검색및 구조화 같은 작업을 보다 쉽게 하기 위해 조직화된 데이터를 수집하는 저장 시스템 
- 스키마, 테이블 기본구조

- 스키마 뼈대 
- 필드 컬럼 , 레코드 튜플 혹은 행 
- pk 프라이머리키 레코드의 고유한 값 , 다른항목과 절대 중복되어 나타날수 없는 단일 값이다.
- 쿼리: 데이터르 ㄹ조회하기 위한 명령어 조건에 맞는 데이터르 ㄹ추출하거나 조작하는 명령어  

## Migrations

- makemigrations 
  - 모델을 작성 혹은 변경한 것에 기반한 새로운 migration 설꼐도 를  만들때 사용 
  - 테이블을 만들기 위한 설계도 
  - python manage.py makemigrations



- migrate
  - makemigrations로 만든 설계도를 실제 db.sqlite3 db파일에 반영하는 과정
  - 결과적으로 모델에서 의 변경사항들과 db 의 스키마가 동기화를 이룬다
    - 모델과 db의 동기화 
    - python manage.py migrate

- ORM

  - 설계도 해석 
  - Object-Relational-Mapping
  - 객체 지향 프로그래밍 언어를 사용하여 호환되지않는 유형의 시스템 간에 데이터를 변환하는 프로그래밍 기술
  - 객체 지향 프로그래밍에서 데이터 베이스를 연동할때 데이터 베이스와 객체 지향 프로그램이 언어 간의 호환되지 않는 데이터를 변환하는 프로그래밍 기법
  - 객체 지향 프로그래밍에서 데이터베이스을 연동할때, 데이터베이스와 객체 지향 프로그래밍 언어 간의 호환되지않는 데이터를 변환하는 프로그래밍 기법 
  - django 내장 django orm을 사용 
  - 장점
    - sql을 잘 알지 못해도 객체 지향 언어로 db 조작 가능
    - 객체 지향적 접근으로 인한 높은 생산성
  - 단점
    - ORM만으로 완전한 서비스를 구현하기 어려운 경우가 있음
  -  ORM을 사용하는 이유
    - 생산성
    - 현시대 개발에서 가장 중요한 키워드는 바로 생산성 
    - DB를 객체로 조작하기 위해 ORM을 사용할 것 

  ### 추가 필드 정의

  - 추가 모델 필드 작성후 다시 한번 makemigrations 진행 

- 반드시 기억해야할 migration 3단계 
  - models.py에서 변경사항이 발생하면
  - migrations 파일 생성 (설계도 생성)
    - makemigrations
  - db 반영 모델과 db의 동기화 
    - migrate

### DateTimeField()

- 날짜 및 시간을 값으로 사용하느 ㄴ필드

- DataField를 상속받는 클래스

  - auto_now_add

    - 최초 생성일자 
    - orm 최초 insert 시에만 현재 날짜와 시간으로 갱신 테이블에 어떤값을 최초로 넣을때 

  - auto_now

    - 최종 수정날짜 

    - orm이 save 할때마다 현재 날짜와 시간으로 갱신 

      

- 즉 model은 웹애플리케이션의 데이터를 구조화 하고 조작하기 위한 도구이다. 

- object manager
  - 데이터 베이스 쿼리 작업을 간으하게 하는 인터페이스
  - db를 python class로 조작할 수 있도록 여러 메서드를 제공하눈 manager
- query 
  - 데이터 베이스에 특정한 데이터를 보여달라고 요청 
  - 데이터 베이스의 응답데이터를 orm이 queryset이라는 자료형태로 변환하여 우리에게 전달한다. 
- queryset
  - 데이터 베이스에게서 전달받은 객체 목록 데이터 모음
  - 순회가 가능한 데이터로써 1개 이상의 데이터를 불러와 사용할 수 있음.
  - 단 데이터베이스가 단일한 객체를 반환 할때 는 queryset이 아닌 모델의 인스턴스로 반환됨



## Create

- 저장방법 article.save()
- 전체 데이터 다 보자 Article.objects.all()
- article = Article(title = 'second', content = 'django!')
- article.save()
  - save는 데이터 생성시 save를 호출하기 전에는 객체의 id값은 None이다 
  - save를 호출해야 테이블에 레코드가 생성된다.. 

- 마지막 방법 : Article.objects.create(title = 'third', content= 'django!')

### READ

- get()

  - 단일 데이터 조회 

  - 객체를 찾을 수 없으면 DoesNotExist 예외를 발생 

  - 둘이상 객체를 찾으면 MultipleObjectsReturned 예외를 발생시킨다

  - 위와 같은 특징을 가지고 있기 때문에 primarykey와 같이 고유성을 보장하는 조회에서 사용 

    



- filter 
  - 지정된 조회 매개변수와 일치하는 객체를 포함하는 새 queryset을 반환 
  - 특정 레코드에 대한 조건 설정
    - content__contains = 'dj'

- update 
  - 수정하고자 하는 article 인스턴스 객체를 조회 후 반환 값을 저장 article = Article.objects.get(pk=1)
  - article 인스턴스 객체의 인스턴스 변수 값을 새로운 값으로 할당
  - save() 인스턴스 메서드 호출

- create 두번째 생성방식 사용 이유
  - create 메서드가 더 간단해 보이지만 추후 데이터가 저장되기 전에 유효성 검사과정을 거치게 될 예정
  - 유효성 검사가 진행 된 후에 save메서드가 호출되는 구조를 택하기 위함 
  - redirect('articles:index')
    - 인자에 작성된 곳으로 요청을 보냄 

### http request method

- get
  - 특정 리소스를 가져오도록 요청
  - 반드시 데이터를 가져올때만 사용 
  - db에 변화를 주지않음
  - crud에서 r  역할을 담당
- post
  - 서버로 데이터를 전송할 때 사용 
  - 서버에 변경 사항을 만듦
  - 리소스를 생성 / 변경 하기 위해 데이터를 http body에 담아 전송
  - get 쿼리 스트링 파라미터와 다르게 url 로 보내지지않음
  - crud에서 c/u/d 역할을 담당
- 그럼 왜 검색엔서는 get을 사용할까
  - 검색은 서버에 영향을 미치는 것이 아니 ㄴ특정 데이터를 조회만 하는 요청이기 때문
  - 특정 페이지를 조회 하는 요청을 보내느 html의 a tag또한 get을 사용

### CSRF

- Cross-Site-Request-Forgery
- 사이트 간 요청 위조
- 사용자가 자신의 의지와 무관하게 공격자가 의도한 행동을 하여 특정 웹페이즈를 보안에 취약하게 하거나 수정 및 삭제등의 작업을 하게 만드는 공격 방법 

- 공격 방어

  - CSRF Token  securyty token 사용방식
  - 사용자의 데이터에 임의의 난수 값을 부여해 매 요청마다 해당 난수 값을 포함시켜서 전송시키도록 한다. 
  - 이후 서버에서 요청을 받을때마다 전다로디는 토큰값이 유효한지 검증한다. 
  - 일반적으로 데이터 변경이 가능한 POST, PATCH, DELETE Method 등에 적용
  - csrf_token 템플릿 태그 제공
    - csrf_token 은 해당 POST 요청이 내가 보낸것인지를 검증하는 거쇼
    - 마지막으로 게시글을 작성하고 문제없이 저장되는지 확인해보는것 

  ### FORM

  - 사용자가 입력한 데이터가 우리가 원하는 데이터 형식이 맞는지에 대한 유효성 검증이 필요
  - 이러한 유효성 검증은 많은 부가적인 것들을 고려해서 구현해야하는데 이는 개발 생산성을 늦출ㅃ누더러 쉽지않은 작업
  - django form 은 이과정에서 과중한 작업과 반복코드를 줄여줌으로써 훨씬 쉽게 유효성 검증을 진행할 수 있도록 만들어 준다. 
  - 단순화하고 잔동화 할수 있는 기능들을 제공해서 개발자가 직접 작성하는 코드보다 더 안전하고 빠르게 수행하는 코드를 작성 할 수 있다. 

form에 관련한 작업의 세부분 처리

- 렌더링을 위한 데이터 준비 및 재구성

- 데이터에 대한 html forms 생성

- 클라이언트로부터 받은 데이터 수신 및 처리

  

class ArticleForm(forms.Form)

form 에서는 model field와 달리 text field가 존재하지 않는다.. charfield 에 그냥 사용 



widgets 

웹페이지 html input 요소 렌더링을 담당한다

- input 요소의 단순한 출력부분 담당
- widgets 은 반드시 formfields에 할당 된다. 
- 유효성 검사랑은 아무런 관련이 없다
- raw한 렌더링만을 처리하는 것일뿐

 form fields

- 입력에 대한 유효성 검사 로직을 처리
- 템플릿에서 직접 사용됨 

### modelform class

- model을 통해 form class를 만들 수 있느 helper class 

- model form은 form과 똑같은 방식으로 view 함수에서 사용 

- 정의한 modelform 클래스 안에 meta 클래스 생성

- fields = '__all__'은 모두  

- exclude를 통해 포함하지 않느 ㄴ필드를 지정할 수 있음 

- model = Article

- 언제 참조값을 활용할까?

  - 함수를 호출하지 않고 함수 자체를 그대로 전달하여 다른함수에서 필요한 시점에 호출하는 경우.

- form.is_vailid

  - 유효성 검사를 실행하고 데이터가 유효한지 여부를 bolean으로 반환

- form.errors

  - is_valid 반환값이 false일때 errors에서 값이 작성. 딕셔너리 형태로 저장

-  context = {

  ​	'form' : form

  } -> 실패 결과 메세지 출력 

form 

- 사용자 입력을 필요로 하며 직접 입력데이터가 db에 사용되지 않거나 일부 데이터만 사용될때 로그인 

modelform

- 사용자의 입력을 필요로 하며 입력을 받은 것을 그대로 db필드에 맞춰 저장할 때 

- 데이터의 유효성 검사가 끝나면 데이터를 각자 어떤 레코드에 맵핑해야할지 이미 알고 있기 때문에 save() 호출이 가능

  

- widgets 작성방법
- title = forms.charField(
- label = '제목',
- widget = forms.Textinput(
- attrs = {
- 'class' : 'my-title',
- 'placeholder': 'Enter the title'
- }
- )

- contexxt 들여쓰기 위치 
  - 에러 정보 넘기기

- 데코레이터 
  - 기존에 작성된 함수에 기능을 추가하고 싶을때 해당 함수를 수정하지 않고 기능을 추가하는 함수 
  - require_http_methods()
  - require_POST()
  - require_safe() : require_GET이 있지미나 장고에서는 require_safe 사용을 권장

http 특징

비연결성 지향

서버는 요청에 대한 응답을 보낸 후에 연결을 끊음

무상태

쿠키사용목적 세션화 개인화 트래킹