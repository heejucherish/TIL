# Operating System  운영체제(기본)

#### process&Thread

---

##### :ballot_box_with_check: 운영체제란 무엇인가?

- 일반적으로 하드웨어를 관리하고, `응용 프로그램과 하드웨어 사이에서 인터페이스` 역할을 하며, 시스템의 동작을 제어하는 시스템 소프트웨어를 운영체제라고 합니다.

##### :ballot_box_with_check: 프로세스와 스레드에 대해 설명해주세요.

- 프로세스는 현재 실행 중인 프로그램을 의미하며 스레드는 프로세스 내부에서 실행되는 작업 흐름의 단위를 의미합니다.

##### :ballot_box_with_check: 멀티 스레드의 장점 및 단점은 무엇인가?

- 스레드는 자원을 공유하기 때문에 `Context Switch가 적고 오버헤드가 작습니다.`
- 단점은 프로세스 내부의 자원을 공유하기 때문에 `동시에 자원에 접근했을 때 문제`가 될 수 있습니다. 또한, 하나의 스레드가 자신의 데이터 공간을 망가뜨린다면 해당 데이터를 공유하고 있는 모든 스레드에 치명적인 문제를 발생시킵니다.

##### :ballot_box_with_check: Thread-safe가 뭐에요?

- 멀티 스레드 환경에서 공유 자원에 **여러 스레드 접근이 있어도 프로그램 실행에 문제 없음**을 의미합니다.

##### :ballot_box_with_check: 세마포어와 뮤텍스를 설명해주세요.

- 여러 프로세스나 쓰레드가 `공유 자원에 접근`하는 것을 제어하기 위한 방법입니다.
- 세마포어는 `count`를 주어 count 값만큼 프로세스/스레드가 접근 가능하도록 하는 기법이며 뮤텍스는 `lock/unlock`으로 권한을 가진 프로세스/스레드만 접근할 수 있도록하는 기법입니다.





#### Scheduling

---

##### :ballot_box_with_check: 스케줄러란?

- 어떤 프로세스에게 자원을 할당할지 결정하는 운영체제의 커널 모듈입니다.

##### :ballot_box_with_check: 스케줄링이 무엇인지와 목적을 설명해주세요

- 스케줄링은 프로세서에게 필요한 자원을 어떻게 할당할 것인지 선택하는 알고리즘 입니다.
- 단위 시간당 처리량을 최대화하고 효율적으로 자원을 할당하기 위한 목적을 가지고 있습니다.

##### :ballot_box_with_check: 비선점방식과 선점방식을 설명해주세요.

- 비선점 방식은 프로세스가 CPU를 점유하고 있는 경우 다른 프로세스가 CPU를 `빼앗지 못하는 방식`입니다. 비선점방식은 CPU를 중간에 가로채지 않기 때문에 응답시간 예측이 용이하다는 장점이 있지만 중요한 작업이 오래 기다리는 경우가 발생할 수 있다는 단점이 있습니다.
- 선점 방식은 프로세스가 CPU를 점유하고 있어도 우선 순위가 높은 프로세스가 오면 CPU를 `빼앗을 수 있는 방식`입니다. 선점방식은 우선 순위가 높은 프로세스가 빠르게 처리할 수 있다는 장점이 있지만 잦은 Context Switching으로 오버헤드가 증가한다는 단점이 있습니다

##### :ballot_box_with_check: Context Switching이란?

- Context Switching이란 하나의 프로세스가 CPU를 사용 중인 상태에서 다른 프로세스가 CPU를 사용하도록 하기 위해, 이전의 프로세스의 상태(문맥)를 보관하고 새로운 프로세스의 상태를 적재하는 작업을 말한다.



#### 메모리 관리 전략

---

:ballot_box_with_check: 교착상태(DeadLock)가 무엇이며, 4가지 조건은?

:ballot_box_with_check: 외부 단편화와 내부 단편화란?

:ballot_box_with_check: 메모리 단편화 해결 기법에 대해 설명하시오.

:ballot_box_with_check: 페이징의 장점과 단점은?



#### 가상메모리

---

##### :ballot_box_with_check: 가상메모리의 역할은 무엇인가요?

##### :ballot_box_with_check: Demand Paging(요구 페이징)에 대해 설명하시오.

##### :ballot_box_with_check: Cache 메모리를 사용하는 이유에 대해 설명하시오.

##### :ballot_box_with_check: 페이징의 장점과 단점은?



#### 커널

---

##### :ballot_box_with_check: Kernel(커널)이란?

##### :ballot_box_with_check: 커널 수준 스레드와 사용자 수준 스레드의 각각 장단점?

##### :ballot_box_with_check: 인터럽트가 필요한 이유 및 언제 발생되는지 말해주세요.

##### :ballot_box_with_check: 시스템콜이란 무엇이며 시스템 콜을 사용하는 예시를 말해주세요.

##### :ballot_box_with_check: 서브루틴과 시스템 콜의 차이는?



##### 이외의 질문

---

:ballot_box_with_check: 부팅이란

:ballot_box_with_check: 파일 시스템이란

:ballot_box_with_check: 캐시와 레지스터의 차이점은 무엇인가요?

:ballot_box_with_check: 페이징과 세그먼테이션이란?



