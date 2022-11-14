# Vue-Django

- 서버란
  - 정보를 제공 == DRF API 서비스 : django 

- 클라이언트란
  - 서버가 제공하는 서비스에 적절한 요청

- 서버는 정보와 서비스를 제공
  - db와 통신하며 데이터를 생성 조회 수정 삭제를 담당
  - 요청을 보낸 클라이언트에게 정상적인 요청이었다면 처리한 결과를 응답

- 클라이언트는 사용자의 정보 요청을 처리, 서버에게 응답받은 정보를 표현
  - 서버에게 정보를 요청

- 확인해야할 사항

  - django 

    - 모델, url 확인

  - vue

    - 어떤 구조인지 확인
    - 라우터 확인

  - 그다음 둘을 연결하기 

    - **vue**

      - 일단 둘 연결하기 전에 ==데이터 없이 최소한의 기본 구조만 확인== (이렇게 해야 시간 단축가능)

      - ==더미데이터==를 넣어서 일단 구조 확인

      - 그다음 장고에서 api 받을 준비 ajax 준비/ axios 설정 , store/index.js 에서 

        - `const API_URL ='http://127.0.0.1:8000'`

        - ```
           actions: {
              getArticles(context){
                axios({
                  method:'get',
                  url:`${API_URL}/api/v1/articles/`,
                })
                .then((res)=>{
                  console.log(res, context)
                })
                .catch((err)=>{
                  console.log(err)
                })
              }
          ----------------------------------------------------------------------  
           created() {
              this.getArticles()
            },
            methods: {
              getArticles(){
                this.$store.dispatch('getArticles')
          ```

          

==하지만!==

- 장고는 서버 요청에 응답을 200 정상 반환 으로 했으나 클라이언트 부분에서는 에러 발생

- 페이지 콘솔창 에러 발생 

- `CORS`

  `GET http://127.0.0.1:8000/api/v1/articles/ net::ERR_FAILED 200`

#### CORS

- 동일 출처 정책

- 다른 출처에서 가져온 리소스와 상호 작용하는것을 제한하는 보안방식

- 공격받을 수 있는 경로를 줄임

- 교차 출처 리소스 공유

  - 서버가 자원에 접근할수있는 권할을 브라우저에게 알려주는 체제

  - 접근해도 돼! CORS POLICY

  - django에서 cors 라이브러리 설치

    - `pip install django-cors-header`  or `python -m pip install django-cors-headers`

    - `pip freeze > requirements.txt  `

    - ```
      INSTALLED_APPS = [
      # CORS policy
          "corsheaders",
          ]
      ```

    - ```
      # 순서 중요! 미들 웨어를 위에 넣기 
      MIDDLEWARE = [
        "corsheaders.middleware.CorsMiddleware",
        'django.middleware.common.CommonMiddleware',
          ]
      ```



- DRF

  - 인증, 입증

    - 자신이라고 주장하는 사용자가 누구인지 확인하는 행위
    - 모든 보안 프로세스의 첫번째 단계 
    - 즉 내가 누구인지 확인하는 과정
    - 401 Unauthorized - 비인증

  - Authorization 권한 부여, 허가 

    - 권한은 인증이후에 하는 것이다. 
    - 자신의 id가 진짜인지 먼저 확인해야함 
    - 서류의 등급 , 웹페이지에서 글을 조회, 삭제, 수정 할 수 있는 방법 , 제한 구역 

    - 403 Forbidden

      - 누구인지는 알지만 접근 권한은 없다는 뜻..! 

      

  - **TokenAuthentication**

    - 토큰 방식
    - settings 에
    -  `'rest_framework.authtoken',` 추가하고 `마이그레이트`
    - ==공백주의==
    - `Authorization: Token 9944b09199c62bcf9418ad846dd0e4bbdfc6ee4b`

    - dj-rest-auth
      - 회원가입 인증 비밀번호 재설정 사용자 세부정보 검색 회원정보 수정을 위한 restapi end point 제공
      - `pip install dj-rest-auth`
      - 앱등록
      - ` path('accounts/', include('dj_rest_auth.urls')),`  url 등록 
      - 그다음 유저 대체 

- 회원가입하려면 이부분 추가해줘야함! 밑에 부분 다하고 post man으로 확인 !

`pip install 'dj-rest-auth[with_social]'`

```
settings

    'django.contrib.sites',
    'allauth',
    'allauth.account',
    'allauth.socialaccount',
    'dj_rest_auth.registration',
    
REST_FRAMEWORK = {
    # Authentication
    'DEFAULT_AUTHENTICATION_CLASSES': [
        'rest_framework.authentication.TokenAuthentication',
    ],
 ----------------------------------------

url
    path('accounts/signup/', include('dj_rest_auth.registration.urls'))



```

- 마이그레이트도 또 다시 해줘야함! 하고나니 singn up이 생김 

- 인증 끝났으니까 권한 설정

- permission

- ```
    'DEFAULT_PERMISSION_CLASSES': [
          # 'rest_framework.permissions.IsAuthenticated',
          'rest_framework.permissions.AllowAny',
      ],
  
  ```

- view 함수

- ```
  # permission Decorators
  from rest_framework.decorators import permission_classes
  from rest_framework.permissions import IsAuthenticated
  
  데코레이터
  @permission_classes([IsAuthenticated])
  ```

- ==js  요청==

- ==postman 요청 확인== 

```
axios({
        method:'get',
        url:`${API_URL}/api/v1/articles/`,
        // 인증을 같이 보내줘야한다. 
        headers:{
          Authorization: `Token ${context.state.token}`
        }
```

`pip install drf-spectacular`



