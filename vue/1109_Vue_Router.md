### Vue

- 체계적인 설계를 통해 기획해야한다. 

- UX

  - 유저와 가장 가까이에 있는 분야, 데이터를 기반으로 유저를 조사하고 분석해서 개발자 디자이너가 이해할 수 있게 소통
  - 유저가 느끼는 느낌 태도 그리고 행동을 디자인

  - 유저 리서치, 데이터 설계 및 정제, 유저 시나리오, 프로토 타입 설계

- UI

  - 유저에게 보여지는 화면을 디자인
  - UX를 고려한 디자인을 반영, 이 과정에서 기능 개선 혹은 추가가 필요한 경우 프론트 앤드 개발자와 가장 많이 소통 -
  - CLI GUI

- Figma

  - 실시간으로 팀웜들이랑 협업
  - 웹 기반 시스템
  - 대부분 기능을 무료로 사용 

- 프로젝트 시작하기 전에

  - 개발부터 시작하지 말고 반드시 충분한 기획을 거칠 것
  - 우리가 완성하고자 하는 대략적인 모습을 그려보는 과정이 필요(프로토타입)
  - 이러한 과정을 통해 기획에서 빠진 화면이나 API등을 확인할 수 있음
  - 설꼐와 기획이 끝난 후 개발을 시작해야 체계적인 진행이 가능함

#### Vue Router

- **Routing** 
  - **네트워크에서 경로를 선택하는 프로세스**
  - 웹 서비스에서의 라우팅
    - **유저가 방문한 URL에 대해 적절한 결과를 응답**하는 것 
  - 예시
  - /articles/index/에 접근하면 articles의 index에 대한 결과를 보내줌 
- Routing in SSR 
  - Routing에 대한 결정권을 서버가 가짐 
- **하지만 Vue는 Routing in SPA/CSR**
  - 서버는 하나의 html만을 제공
  - 이후 모든 동장은 하나의 html 문서 위에서 js 코드를 활용
    - dom을 그리는데 필요한 추가적인 데이터가 있다면
    - axios와 ajax 요청을 보낼 수 있는 도구를 사용하여 데이터를 가져옴 
- why routing?
  - 유저의 사용성 관점에서는 필요함 
  - Routing 이 없다면
    - 유저가 URL을 통한 페이지의 변화를 감지할 수 없음
    - 페이지가 무엇을 렌더링 중인지에 대한 상태를 알 수 없음 
    - 브라우저의 뒤로가기 기능을 사용할 수없음

##### Vue Router

- Vue의 공식 라우터

- SPA 상에서 라우팅을 쉽게 개발 할 수 있는기능을 제공

- 라우트에 컴포넌트를 매핑 후 어떤 URL에서 렌더링 할지 알려줌

  - 즉 SPA를 MPA처럼 URL을 이동하면서 사용가능
  - SPA 단점 중 하나인 "URL이 변경 되지 않는다"를 해결 

  - MPA
    - 여러개의 페이지로 구성된 애플리케이션
    - SSR 방식으로 렌더링

- 시작

  - `vue add router`

- History mode
  - 브라우저 히스토리 api를 활용한 방식
    - 새로고침 없이 url 이동 기록을 남길 수 있음 
    - 우리에게 익숙한 형식으로 url 구조로 사용가능

- **router-link**

  - a 태그와 비슷한 기능 >  url을 이동시킴
    - 페이지를 새로고침 하는것이 아님
    - routes 에 등록된 컴포넌트와 매핑됨
  - 목표 경로는 'to' 속성으로 지정됨 
  - 기능에 맞게 html 

- router-html
  - 주어진 url에 대해 일치하는 컴포넌트를 렌더링 하는 컴포넌트
  - 실제component가 DOM에 부착되어 보이는 자리를 의미
  - 장고에서 block tag와 비슷 

- router-view

  - url 변경, 새로고침은 없지만 
  - 컴포넌트가 바뀐다. 
  - django에서 block tag와 비슷하다. 

- components /views
  - 경로만 다르다
  - 하지만 **views에 들어있는 뷰들은 라우터랑 연결** 
  - **components : 라우터랑 연결 안되어있는 뷰** 

- 주소를 이동하는 2가지 방법
  - 선언적 방식 네비게이션
  - ==프로그래밍 방식 네비게이션 (중요)==

- 선언적 방식 네비게이션

  - router-link 'to' 속성으로 주소 전달
    - routes에 등록된 주소와 매핑된 컴포넌트 방식

- **프로그래밍 방식 네비게이션**

  - $router

  - 이름으로 바인딩을 통해서 매핑하는 것 {name: '이름'}

  - ==다만 HTML에서 직접 사용하기 보다는 data에 넣어서 사용하는 것을 권장!== 

  - 보낼때는 특정한 곳으로 이동하고 싶을때 

    - `this.$router.push`

  - 히스토리 스텍에 이동할 url을 넣는 push 방식

  - 이름 동일하게 작성하자! 

  - 사용할때는

    - `$route.params `

    ```js
    router 안 index.js 
    {
        path:'/hello/:userName',
        name: 'hello',
        component:HelloView,
      }
    ```

    ```vue
    views 안에 컴포넌트
    
    data() {
            return {
                userName: this.$route.params.userName
            }
        }
    
    tethods :{
    	toHome(){
    	this.$rounter.push({name:'hello',params:{userName: this.inputData}})
    }
    }
    
    
    
    
    vue templeate
     <router-link :to="{ name: 'hello', params: {userName: 'ssafy'} }">Hello</router-link> 
    ```
    
    

- lazy-loading
  - 모든 파일을 하번에 로드하려고 하면 모든 걸 다 읽는 시간이 매우 오래 걸린다.
  - 미리 로드를 하지 않고 특정 라우터에 방문할 때 매핑된 컴포넌트의 코드를 로드하는 방식을 활용할 수 있음 
    - 모든 파일을 한번에 로드하지 않아도 되기 때문에 최초에 로드하는 시간이 빨라짐
    - **당장 사용하지 않을 컴포넌트는 먼저 로드하지 않는 것이 핵심!** 

```javascript
{
    // lazy-loading 방식 첫 로딩에 랜더링 하지 않고 해당 라우터가 동작할 때 컴포넌트를 렌더링 한다. 
    path: '/about',
    name: 'about',
    component: () => import('../views/AboutView.vue')
  },
```

#### global before guard

- **전역가드**

  - 전국적으로 건뭄소를 세울때

  - router.beforeEach()

  - ==콜백함수==

    - to : **이동할** url 정보가 담긴 라우터 객체

    - from: **현재 url 정보**가 담긴 라우터 객체 

    - next: **지정한 url 이동**하기 위해 호출하는 함수
      - 콜백 함수 내부에서 ==반드시 한번만 호출==되어야함 
      - 기본적으로 to에 해당하는 url로 이동 


  - url이 변경되어 **화면이 전환되기전** **router.beforeEach()** 가 호출됨

  - 변경된 url 로 라우팅 하기 위해서는 next()를 호출해야함


- **라우터 가드**

  - 특정 지역 검문소

  - 특정 URL에서만 동작

  - 로그인 여부에 따른 라우팅 처리

  - **beforeEnter()**

- **컴포넌트 가드**

  - 특정 지역의 공간 검문소

  - 라우터 컴포넌트 안에서 정의 

  - 이친구는 매개변수가 변화하면 바뀐다. 

  - **beforeRouteUpdate()**

    - 해당 컴포넌트 렌더링하는 url이 변경될때 실행되는 가드 

      ```
      befroreRouteUpdate(to, from ,next){
      	this.userName = to.parmas.userName
      }
      ```


- 전역가드만 콜백이고 나머지는 직접 호출된다!

- **404 Not Foud**

  - routes에 최 하단부에 작성해야한다

    ```
    const routes = [
    {
    	path:'*',
    	redirect: '/404'
    }
    ]
    ```

    

- axios

  - `npm i axios`

  - `import axios from 'axios'`

    

- **optinal chaining (?.)**
  - 에러 발생시키지 않고 undefined 를 반환

