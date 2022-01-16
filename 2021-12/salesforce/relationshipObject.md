Relationship between Objects
==========================

데이터 설계하는 과정이다 반갑다  
디자인적인거랑 세일즈 포스 뭔지만 배우다가   
백앤드적인 요소가 처음으로 등장했다  
Object가 객체라는 개념에서 스프레트시트 즉 테이블 개념으로 바뀌었다. 모 salesforce에 익숙해져야 하니 모  
그래도 각 object간 pk개념과 fk로 연결되는것은 같은 개념인 듯 하다.  
<img src = "https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f77955bc-8e87-4adf-9590-48c8349e6e87/Untitled.png">
data model은 Account 랑 Contact 두가지 objects가 있다.
pk로 각 row마다 식별자가 있으며, 포랭키로 연결된다   
fk - points to primarykey : relates child to parent  

   ### object relationships

you can create a one to many relationship between wo objects

Contact and Customerstory

**one to many 가 어떤거였죠 호호**

하나의 주체가 여러 상태 값을 가질 수 있는 형태임.

예를 들어서, 

아이디 하나에는 여러가지 주문이 들어간다.

내가 오징어, 새우, 소고기 등을 주문을 한다고하면

나라는 아이디 주체가, 여러 주문의 상태 값을 가지게 되는 것이다.

그리고 서로 참조하는 ERD를 설계할때, 화살표는 fk에서 나온다;!

참조 되는 테이블은 화살표를 받는다.

참조 되는 테이블을 부모 테이블이라 하고, fk가 정의된 테이블이 자식 테이블이다. 

진지하게 나 SQL공부 필요함;;......

다시 본론으로 들어와서

you can create a one-to mamy relationship between two objects.

the relationship is defined on the child object using a custom field.’

 자식 테이블에서 정의된다규?

**These are the types of relationship fields :** 

Master datail

Lookup

Hierarchy(계층 , 이 단어 왜케 안외워지는지.. user object only)  

Self realtionship(Lookup)

**with external objects we use :** 

indirect( opposite direct, 간접)

external

그럼 types of realationship fields 중, Master-Detail Relationship부터 보자

access to a detail record is inherited from the master record.

데이터를 상속받아서 본다는 말인듯.

<img src = "https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8622f377-db5b-405b-84cf-d60700c6283c/Untitled.png">
delivery가 course에 참조 되는 것이겠지? 왜냐하몬 화살표 받는 쪽이 참조 되는 것이니깐

이라고 말을 했지만

참조 되는 것은 즉 부모 테이블이라는 말이다 그래서

Course가 Delivery를 참조 하는 것이고, Delivery는 참조되는 테이블이라고 보면 된다.

the detail record is automatically deleted when the parent is deleted

부모꺼 지워지면 자동으로 자식 테이블에 있던 데이터도 지워짐

the parent reference is always required on the child record 

약간 몬소린지 모르겟네ㅇㅇ

<img src = "https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9052c47e-d480-4085-8e63-1a6c6f095099/Untitled.png">
보면 자식 인스턴스에는 부모 참조가 항상 요구된다는 말인고 같은데..

자식이 포렝키 가진거는 항상 부모테이블에 잇어야 한다는 말인걸까?ㅋㅋ

you can choose whether or not the detail record can be reparented

다음은 lookup 타입 보쟝
