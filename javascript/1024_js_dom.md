### 1024

- 웹페이지에서 할 수 있는 자바스크립트
- 웹 페이지 > 동적으로 

#### Browser APIs

- 데이터를 제공, 오디오를 재생

#### DOM

- 문서의 구조화 된 표현을 제공
- 자바스크랩트가 DOM 구조에 접근할 수있는 방법을 제공한다. 
- 스타일/내용을 변경 할수있게 도움
- HTML 콘텐츠를 추가, 제거, 변경, 동적으로 페이지 스타일을 추가 
- HTML 문서를 구조화 하여 각 요소를 객체로 취급
  - 프로그래밍 언어로 접근할수있다 JS로 접근할 예정 

- JS는 DOM API를 통해서 웹페이지를 동적으로 만든다. 

- DOM은 웹페이지의 객체 지향 표현이다.  
- DOM의 주요 객체
  - window
    - 가장 최상위 객체 
    - 탭 기능이 있는 브라우저에서는 각각의 탭을 각각의 window 객체로 나타낸다. 
    - 최상위 클래스라서 생략도 가능하다. 
  - document 
    - 브라우저가 불러온 웹 페이지 
    - <body> 태그 같은... 
- 파싱 parsing
  - 구문 분석, 해석 이라는 뜻 

####  DOM 조작

- 선택 후 조작 (순서 중요)

  1. 선택

     - querySelector (selector) 
       - 만족하는 첫번째 element 객체를 반환 (여러개 선택하고 싶으면 x)- 객체 하나 찾는거 
     - querySelectorAll(seletor)
       - 여러 element 선택 
       - NodeList를 반환 

  2. 조작

     - createElement(tagName)
     - innerText 
       - 속성값 
     - 부모.appendChild()
       - 한 node를 특정 부모 자식 nodelist중 마지막 자식으로 삽입 
       - 한번에 오직 하나의 node만 추가할 수있음 
       - 추가된 Node 객체를 반환

     - removeChild()
       - 삭제
     - getAttribute
       - 해당 요소의 지정된 값을 반환
     - setAttribute
       - 속성이 이미 존재한다면 값을 갱신

- 모든 웹페이지는 사건이 발생한다. 

#### Event

- addEventListener()
  - 이벤트 처리기, 핸들러 
  - 의 콜백함수는 fuction() 으로 사용하기 화살표함수 사용하지 않기

- lodash 라이브러리

- 폼이벤트

| 이벤트 | 설명                                                    |
| ------ | ------------------------------------------------------- |
| input  | input, textarea 요소 값이 변경 되었을 때                |
| change | 선택버튼, 체크박스, 라디오 버튼 등 상태가 변경 되었을때 |
| submit | 버튼키를 이용해서 폼을 제출 할때                        |
| reset  | 리셋 버튼을 클릭할때                                    |
| copy   | 폼 필드의 콘텐츠를 잘라내기 했을 때                     |
| paste  | 폼 필드의 큰텐츠를 붙여넣기 할때                        |
| select | 텍스트를 선택했을 때                                    |

- 마우스 이벤트	

시험문제: 밑줄친 this가 가르키는 것은 무엇인가?

#### this

- This 는 화살표 함수를 쓰는것이 좋다. 

- 호출되는 순간에 결정되는것 (런타임)
  - 장점 
    - 함수(메서드)를 하나만 만들어서 여러 객체에서 재사용할 수 있다. 
  - 단점
    - 이런 유연함이 실수로 이어질 수 있다. 단점 

