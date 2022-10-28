- DOM

  - document.createElement 
  - setAttribute 

  - addEventListener( 이벤트 이름, 콜백함수 )

  - appendchild() - 자식 추가

  - removeChild() - 노드삭제

  - 속성 조회
    - getAttribute(속성 이름)
    - setAttribute(name, value)

- Event

  - 프로그래밍하고있는 시스템에서 일어나는 사건 혹은 발생
  - 키보드 키 입력, 마우스, 버튼 클릭, 결과를 받거나 조작, 데이터 제출(submit)
  - ~하면 ~ 한다.
  - Event 핸들러
    - 타겟 요소를 대상으로 이벤트리스터 부착 
    - EventTarget.addEventListener(type, listener)
    - document > 페이지 전체 
    - type
      - 대표 이벤트
      - input, click, submit
    - listener
      - 콜백함수
      - **event 객체**를 유일한 매개변수로 받는다.  

- Event 취소(중요)
  - event.preventDefault()
    - 기본 동작을 중단

- lodash
  - 자바스크립트 유틸리티 라이브러리
  - array, object 등에서 자료구조 다룰때 
  - reverse, sortBy, range
- This
  - 함수의 호출방식에 따라서 달라짐
  - 언제 object인지만 알아두면됨
  - 전역변수 - window
  - 함수 
    - 단순 호출 - window
    - 매서드, 즉 object 내부의 매서드로 정의되어서 호출되면 - object 가르킴 
    - 화살표 함수 ->object 자동으로 한단계 상위scope를 바인딩 한다. 