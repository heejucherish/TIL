# 1011 django-db-시험범위

image= models.ImageField(blank=True)

- 빈문자열 blank : 기본값은 false인데 true 하면 유효성 검사를 통과 하기 위해서. is_valid 통과하기 위해서 이미지는 꼭 게시물에 안적어도 되기 때문이다. 
- null > 기본값 false true로 바꾸면 빈값을  null  로 저장 
  - NULL 로 바꿔서 저장한다. 
- 왜 이미지는 blank true 냐? 이미지 필드에는 문자열 저장되기때문에 . 문자열에서 빈값 특징은 '' 빈 문자열이 되어야하기때문에 
  - 하지만 다른 필드 > 빈값 > null

- **데이터 없음을 표현하는 방법때문에 blank 사용!**

- Pillow 설치해야 이미지 업로드 가능함ㅋ. 
- static : 서비스 제공자가 소유
- media : 사용자 유저가 올리는 파일
- static_root : 장고 서버가 배포 될때 모을때 
- 서버 실행 되는 동안 > static 폴더를 생성하게되고 이미지를 배포하면 > 그림이 안보인다. 
  - 변경되더라도 로드가 되지않는다.
  - 서버를 껏다가 다시 키면 정상적으로 보인다.  
- first_name__endswith= '준' > LIKE '%준' 
- Q object > OR statement : 중요! 
- **aggregate() /annotate() > 중요 ! 시험 ! 특징 기억**
  - aggregate 언제 사용 어떤 결과 > 결과가 바로 딕셔너리로 나온다. 딕셔너리 반환, 전체에 대한 정보 를 계산할때 주로 aggregate를 사용한다. 어그리게이트는 딕셔너리 
  - annotate는 언제 사용 어떤 결과 > 요약값을 계산한다. 전체 보다는 일부항목. 각 컬럼 별로 요약값 계산 할때 주로 사용한다. 가상 필드를 붙여준다. group by에 해당 

- N:1예시 관계를 가지고 있을때 Aggregation > 관통에 잇을 확률 ! 
-  





















