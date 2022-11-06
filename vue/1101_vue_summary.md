#### vue

#### SSR CSR 

- 면접

#### MVVM Pattern

- vie - 우리 눈에 보이는 부분
- model - 실제 데이터 
- view model 

#### data

- 뷰 인스턴스의 데이터 객체 혹은 인스턴스 속성 
- {} 오브젝트 여야 함 

#### methods - s 주의! 

- 뷰 인스턴스에 사용하는 함수를 정의해서 모아두는 곳 
- 메서드를 정의할때는 arrow 함수 사용 X 

#### v-show & v-if

- 시험 자주 출제
- v-show
  - dom을 css를 통해서 보여줄건지 말건지 결정 
  - 랜더링 비용은 들지만, toggle 비용은 싸다
  - css의 display 속성을 가지고 보여줄건지 말건지 block/ none 값만 변경해주면 됨 
- v-if 
  - v-show 와 사용 방법은 동일하지만
  - 값이 false인 경우  DOM에서 사라진다. 

#### v-for

- key 속성을 무조건 넣기!



#### v-on

- 약어 @ 

- 이벤트 리스너

#### v-bind

- 속성에 데이터를 연결할때 사용한다. 
- 많이 사용

#### methods & computed

- 시험 자주 출제 

- computed
  - 사용하는 변수가 변하면 계산을 새로한다. 계산 > 메모리에 저장
  - 종속 대상이 변하지 않으면 항상 캐싱된 값을 반환한다. 
- methods
  -  동작을 담당한다.
  - 호출 될때마다 함수를 실행 
  - 같은 결과여도 매번 새롭게 계산 

#### watch

- computed랑 헷갈림 
- 차이점
  - computed는 계산, watch는 동작
  - 특정 데이터 변화를 감지해서 그때 동작 
- array, object의 내부 요서 변경 감지를 위해서는 depp 속성 추가 필요

#### filters - s 주의!



#### vue2 style guide

- **v-for 는 항상 key 를 사용**하기 
- 데이터의 예측 가능한 행동을 유지시키기

- **v-for 랑 v-if** 
  - v-if가 먼저 계산이 됨 , 우선 순위가 높음
  - 그래서 동시에 사용하지말고 따로따로 계산 
  - 아니면 computed 속성을 사용해서 해결, filter로 사용 
  - v-for = 'user in users' : key="user.id"
  - <li> 자식 요소로 v-if 작성
  - **동일한 태그에 사용하지 않으면 됨!** 

#### Todo

1. 뷰 기본 모형 만들기 div app , 뷰 cdn 

2. input 이랑 버튼 만들기

3. ul 과 li태그

4. 버튼을 클릭 했을때 li 추가

5. methods 하나 만들기 appTodo 

6. csl appTodo 하고 - 확인

7. appTodo 에 todo 추가 시키기 

8. 입력받은 데이터 가져오기 content  v-model로 양방향

9. todolist 배열 data에 추가 

10. this.todoList.push(this.content)

11. this.content = " " 빈문자열 넣어주기

12. input check 박스 만들기  리스트 내부로 넣어주기

13. 체크박스에 v-model(양방향)로 isCompleted 로 해서 완료됐는지 안됐는지 확인 

14. isCompleted 도 개별로 가져가야 한꺼번에 체크가 되지않음

15.   그래서 오브젝트 형태로 관리하기 const todo = { content: this.content, isCompleted:false}

16. 그러고 todo를 push

17. 개발적으로 가지고잇는 isCompleted 로 바인딩 시키기

18. v-model = todo.isCompleted

19. todo.content 만 보이게 만들기

20. 그다음 가로줄 / 회색 

21. style 태그 만들기 

22. .completed { text-decoration: line-thoriugh, color: gray }

23. span tag추가  class 구분 

24. v-bind:class= "{completed: todo.isCompleted }" 뒤에 있는 값이 트루일때는 completed가 붙음

25. status 양방향 select에 추가

26. 데이터 추가 status  기본값은 all >value로

27. 상태 값에 따라 다르게 보이게 

28.  상태에 따라 반복문의 array의 값이 계속 변경되어야 한다. 

29. computed 로 상태값 구분 

30. todoListByStatus 라는 배열을 계산 

31. this.todoList 에 있는걸 filter로 걸러내기

32. return 문으로 구분하기

33. if문 사용해서 구분하기 

34. ! > false>isProgress

35. else if > true > complete

36. else > return true : 이경우는 all 을 의미 

37. v-for 키설정

38. this 어디잇는지 꼭 확인! 

    



