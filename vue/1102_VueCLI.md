 #### Vue CLI

---

##### Node.js

- 자바스크립트를 브라우저가 아닌 환경에서도 구동할 수 있게 됨
- NPM
  - 자바스크립트 패키지 관리자
  - Node.js 에서는 npm

---

##### Vue CLI

-  Vue 개발을 위한 표준도구
- 프로젝트의 구성을 도와주는 역할
- 확장 플러그인 GUI, Babel 등 다양한 tool 제공
- ==설치 git bash (글로벌 진행)==
  -  npm install -g @vue/cli

- ==프로젝트 생성**( vscode terminal )**==
  - vue create vue-cli(프로젝트명)
  - 다음 vue2 선택
  - 장고랑 다른점! 를 해줘야함 바로 서버를 못키기때문에. 
    - cd vue-cli :이동후에
    - npm run serve :서버키기

###### Vue CLI 프로젝트 구조

- node_modules- Babel
  - 자바스크립트의 컴파일러
    - 컴파일러: 자바스크립트의 ES6+ 코드를 구버전으로 번역/변환해주는 도구
  - 자바스크립트의 파편화 표준화의 영향으로 작성된 코드의 스펙트럼이 매우 다양하기때문에
  - 호환성 때문에. 
  - 원시코드 -> 목적코드로 옮기는 과정

- node_modules -Webpack
  - 모듈간의 의존성 문제를 해결하기 위한 도구
  - static modeule bundler
  - 프로젝트에 필요한 모든 모듈을 매핑하고 내부적으로 종속성 그래프를 빌드함 

- Module
  - 모듈간의 의존성 문제
    - 모듈간의 의존성이 깊어지면서 모듈간의 문제인지 파악하기 어려움
      - 해결: webpack 
- Bundelr
  - 모듈 의존성 문제를 해결해주는 작업이 bundling
  - webpack은 다양한 번들러 중 하나
  - 모듈들을 하나로 묶어주고 묶인 파일은 하나 혹은 여러개로 만들어짐
  - Bundling된 결과물은 개별 모듈의 실행 순서에 영향을 받지 않고 동작하게 됨 
  - vue cli는 이런 바벨 웹팩에 대한 초기설정이 자동으로 되어있다. 
- package-lock.json
  - 노드 모듈 에 설정되는 모듈과 관련된 모든 의존성을 설정 및 관리
  - 협업 및 배포 환경에서 정확히 동일한 종속성을 설치하도록 보장하는 표현
  - 사용할 패키지의 버전을 고정
  - 개발 과정간의 의존성 패키지 충돌 방지
- public
  - favicon
    - 서버 켰을때 아이콘 
  - index.html
    - vue 앱의 뼈대가 되는 html v파일
    - vue 앱과 연결될 요소가 있음 

- Component
  - UI를 독립적이고 재사용 가능한 조각들로 나눈것
    - 즉 , 기능별로 분화한 코드 조각
  - CS에서는 다시 사용할 수 있는 범용성을 위해 개발된 소프트웨어 구성 요소를 의미
  - 하나의 app을 구성할 때 중첩된 컴포넌트들의 tree로 구성하는 것이 보편적임
    - web 시간에 배운 HTML 요소들의 중첩을 떠올려 보자!
      - Body tag를 root node로 하는 tree의 구조이다. 
      - vue에서는 src/app.vue를 root node로 하는 tree구조를 만들어준다
  - 컴포넌트는 유지보수 쉽게
  - 재사용 용이
  - 우리가 사용하는 웹 서비스는 여러개의 컴포넌트로 이루어져 있음
  - 하나의 컴포넌트를 만들어보면 반복되는 UI를 쉽게 처리할 수 있음
- 뷰에서 말하는 컴포넌트란?
  - 이름이 있는 재사용 가능한 뷰 인스턴스
- 그러면 뷰 인스턴스는?
  - 앞서 수업에서 사용한 new Vue()로 만든 인스턴스 
- SFC
  - 하나의 .vue 파일이 하나의 vue instance이고, 하나의 컴포넌트이다. 
    - 즉 싱글파일 컴포넌트
  - 뷰 인스턴스를 기능단위로 작성하는것이 핵심이다. 
  - 뷰 인스턴스에서는 html, css, javascript 코드를 한번에 관리
  - 컴포넌트 기반 개발의 핵심 기능 
- ==vue cli가 뷰를 컴포넌트 로 based 하게 사용하도록 도와줌==

###### vue component 구조정리

- App.vue
- 이 App.vue 를 index.html과 연결
- 결국 index.html 파일 하나만 랜더링
  - 이게 바로 SPA

- MyComponent.vue 이름 주의! 

  - 카멜케이스 

- ==컴포넌트 만드는 과정==

  - components 폴더 안에

    1. 파일만들기

    2. name 등록

    3. 최상위 태그 추가

- ==컴포넌트 등록 3단계==

  1. 불러오기

     1. app.vue 에서

     2. script 밑에서 불러오기 import

        ```javascript
        <script>
        import HelloWorld from './components/HelloWorld.vue'
        //1. 불러오기
        //import MyComponent from './components/MyComponent.vue'
        import MyComponent from '@/components/MyComponent'
        ```

        

  2. 등록하기

     1. app.vue에서

     2. 등록하기

        ```javascript
        export default {
          name: 'App',
          components: {
            HelloWorld,
            MyComponent, (등록하기)
          }
        }
        </script>
        ```

        

  3. 보여주기

     1. app.vue에서

     2. template에서 보여주기

        ```js
        	// 보여주기
        	<MyComponent/>
            <HelloWorld msg="Welcome to Your Vue.js App"/>
          </div>
        </template>
        ```

        

- node_modules  생성법
  - 프로젝트가 있는 위치에서 
  - ==npm instal==l 

##### Data in components

- 데이터 교환 
- 상위에서 데이터 정의된걸 하위에서 어떻게 사용할수 있는가?
  - 필요한 컴포넌트들끼리 데이터를 주고 받으면 될까? 
    - 단점 많음 
  - 컴포넌트는 부모-자식 관계를 가지고 있으므로, 부모-자식 관계만 데이터를 주고받게 하자! 
    - 데이터 흐름을 파악하기 용이하다
    - 유지 보수하기 쉬워짐 
- ==pass props & emit event==
  - 부모 > 자식 으로의 데이터 흐름
    - pass props 의 방식
  - 자식 > 부모로의 데이터 흐름
    - emit event의 방식 

###### pass props

- **요소의 속성**을 사용하여 데이터 전달
- props는 부모(상위) 컴포넌트의 정보를 전달하기 위한 사용자 지정 특성

```javascript
app.vue(부모)
// 정적인 props 
<HelloWorld msg-title="Welcome to Your Vue.js App"/>


helloworld.vue(자식)

<h1>{{ msgTitle }}</h1>

props: {
    msgTitle: String
  }

```

- props 이름

  - prop-data-name="value"의 형태로 데이터를 전달 

    - 속성의 키 값은 kebab-case

    - 부모 : html: msg-title

    - 자식 : props 선언 msgTitle : type 

      

- dynamic props
  - v-bind directive 를 사용해 데이터를 동적으로 바인딩
  - 부모 컴포넌트의 데이터가 업데이트 되면 자식 컴포넌트로 전달되는 데이터 또한 업데이트 



- ==vue-cli 에서는 컴포넌트의 data는 return {}==

  ```javascript
  data: function () {
      return {
        dynamicProps:'이건 동적인 데이터!',
      }
    }
  ```

  - :my-props(부모) > myProps (자식)

  - :num-props="1" >숫자 1 

- ==단방향 데이터 흐름==<u>(시험 자주 출제)</u>

  - 모든 props는 부모에서 자식으로 즉 아래로 단방향 바인딩 형성
  - 아래> 위는 불가능!
  - 위 > 아래만 가능 
  - 하위 컴포넌트에서 prop를 변경하려고 시도해서는 안되며, 그렇게 하면 vue는 경고 출력
  - prop 자식에서는 READ ONLY 
  - ==목적==
    - ==하위 컴포넌트가 실수로 상위 컴포넌트 상태를 변경하여 앱의 데이터 흐름을 이해하기 힘들게 만드는 것을 방지 !==
    - 결론: 유지보수 

###### Emit Event

- 부모 컴포넌트에서 자식 컴포넌트로 데이터를 전달할때는 <u>이벤트를 발생 시킴</u>)
- 이벤트를 발생시키는게 어떻게 데이터를 전달하는 것인가?
  - 데이터를 이벤트 리스너의 **콜백함수의 인자**로 전달
  - 상위 컴포넌트는 해당 이벤트를 통해 데이터를 받음

- 순서

  1. 자식 컴포넌트에 있는 버튼 클릭 이벤트를 청취하여 연결된 핸들러 함수(childToParent) 호출

  2. 호출된 함수에서 $emit을 통해 상위 컴포넌트에 이벤트 (child-to-parent) 발생
  3. 상위 컴포넌트는 자식 컴포넌트가 발생시킨 이벤트를 청취하여  연결된 핸들러 함수 호출(parentGetEvent), 함수의 인자로 전달된 데이터(childData) 가 포함되어있음
  4. 그다음 호출된 함수에서 console.log(`~child data`)

##### ==passprops / emit event 컨벤션==

- html 요소 케밥
- 자스 카멜케이스
- props
  - 상위 > 하위 흐름에서 html 요소로 내려줌 : 케밥
  - 하위에서 받을때는 자스가 받음 : camelCase
- emit
  - emit **이벤트** 발생(@케밥-케이스)시키면 html 요소 : kebab-case
  - 메서드 변수명 등은 자스에서 사용함: camelCase

###### summary

- props(케밥 -> 카멜케이스)

  - 부모는 html에서 속성으로 data를 전달하고 (케밥) 
    - :속성 = "데이터변수명"

  - 자식은 props에 전달받는 data 선언 >이름: type  (카멜케이스)
    - @click = 
  - 단방향 데이터 흐름

- emit

  - 전달하는 값의 개수가 여러개이면 매개변수 선언도 여러개 들어가면됨. 

- component 요소 에서 @click 은 .native
