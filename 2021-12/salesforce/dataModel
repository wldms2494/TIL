look up relationship 과 master-detail relationship 알자
=======================
salesforce developer 사이트에 마치 내 심정과 같은 분이 글을 올려주셨다  
Difference between Lookup Relationship and Master-Detail RelationShip

Hello Everybody,


   I am new in SalesForce. I don't understand what is the difference between the lookup and master-details relationships. Both are one to many relation ship.... and I can't imagine while developing when I should use each.. So, please advice
 

Thank you,

    Sally
    
    샐리가 아니라 지은이 아냐?
   
 원투매니 첨조같은데 모가 다른걸까 수업을 들어도 무슨 말인지 알아듣기 좀 힘들었다
 
 enth가 답해주었다
 
 there's fundamental differences in behavior and record sharing that you need to read up on..
 fudamental differences ㅜㅜ fundamental !!!ㅋㅋㅋㅋㅋ
 the following is purely a summary from memory and may not be 100% accuate, please to the salesforce help for explanation
 
 (모야 fundamental difference라고 내 기를 죽여놨으면 장황하게 설명해주셔야죠 !!! )
 
 the key difference is master-detail has direct dependancy between objects
 - you cannot have a detail record without master
 - the detail record inherits sharing rules from master
 detail record가 모냥 ?
 레코드라 하면 세일즈포스에서 테이블로 치면 raw에 해당하고 송지은 머리속에서는 하나의 instance라고 이해하고 있다.
 여기서 구냥 인스턴스가 아니라 디테일 인스턴스라는 말인가?
 필드의 실제 값이라고 생각하면 되나
 property가 필드라고 생각한다면 (column이 되는것이징)그러면 하나의 인스턴스의 컬럼에 해당하는 값이라고 생각해볼까?
 그러면 you cannot have a detail record without master라하면
 상위없이는 하위에서 컬럼에 해당하는 값을 가질 수 없다는 말일까? 
 지금 내가 이야기하고자 하는 이야기는 data value를 뜻하는것 같군ㅇ
  <img src="https://user-images.githubusercontent.com/80088918/150979241-2d757988-3e49-4587-8344-4ccc602e6611.png">
 
 여기는 잠시 놔두겠당. 
 
 
 # master-detail relationship
 - access to a detail record is inherited from the mastser record.
 디테일 레코드로의 접근은 마스터 레코드로 부터 상속된다. 
 
 - the detail record is automatically deleted when the parent is deleted
 디테일 레코드는 부모가 삭제될때 자동으로 삭제된다
 
 -  the parent reference is always required on the child record
 부모의 참조는 자식 레코드에서 항상 되야 한다. 
 
 - you can choose whether or tho the detail record can be reparented.
 디테일레코드가 부모가 또 부모가 될지 안될지는 결정할 수 있다. 
 
 detail record 왜케 많이 나옴 ;0;ㅋㅋㅋ
 아ㅏ 플러스 note
 the detail side of master-detail relationship must be custom object
 마스터 디테일 관계에서 디테일한 부분은 무조건 커스텀 오브젝트여야 한다. 
 
 아 쓰다보니 detail record 는 마스터 디테일 관계에서 걍 디테일의 레코드를 말하는 고 아님:;;? 마치 자식의 인스턴스들 레코드!!
 
 그럼 다시 
 
 acces to detail record is inherited from the master record
 자식 레코드의 접근은 부모 레코드로 부터 상속받는다 구래!! 뭔말인지 알겠오!!
 위에꺼 다시
 you cannot have a detail record without master
 부모가 없으면 자식은 레코드를 가질 수 없다 응!!
 the detail record is automatically deleted when the parent is deleted
 부모가 사라지면 자식의 레코드도 자동으로 사라진다.
 아~! 
 master-detail은 말 그대로 굉장히 real master처럼 굉장히 master slavetic한 종속적인 관계가 느껴진다.
 나는 부모자식이란 느낌이 많이 와닿아서 원투매니 문제가 나올때는 계속 master-detail을 골랐는데
 신중하게 생각해야겠군
 
 이제 룩업!!
 최근에 넷플릭스에서 본 don't look up 영화 생각나네
 # lookup relationship 
 - the child record and parent record have independent sharing
 이제 차일드라는 자식이란 말을 드뎌 쓰는구나! 힝
 두개의 오브젝트는 서로 독립된 관계를 가진다. 
 차일드는 부모를 바라보지만 그냥 바라만 보는거구나?
 - the lookup field on the child record can be optional or required
 자식의 룩업필드는 (룩업필드라하면 부모에서 참조한 필드를 말하는걸까?) 선택적이 될 수 있고, required가 될 수도 있다.
 설정할때 이런 칸도 있다.
 what to do if the lookup record is deleted? 
 always require a value in the field in order to save a record
 clear the value of this field. you can't choose this option if you make this field required.
 dont allow deletion of the look up record that's part of a lookup relationship
 delete this record also.
 
 룩업관계에서 부모가 삭제된다면?
 항상 레코드를 저장하기 위해 필드 data value값을 요구해라
 필드의 벨류를 없애버려라. 하지만 필드가 required라고 되있다면 넌 이거 선택 못함ㅋ
 룩업관계라면 룩업 래코드는 삭제 못한다
 뭐 자식것도 삭제해라
 
 이런말인듯 4이 말이 삭제해라 아니라 이정도인줄만 알았는데 해석해보니 굉장히 상세했구만?
 
 
#### look up relationship
- parent is not required field by default (부모는 디폴트로는 required가 아니다) 
- no impact on security and access
- deletion removes value in lookup field; can specify alternative behaviors .삭제는 룩업필드의 벨류도 없앤다?;; 하지만 대체 행동들을 명시함 위에 부분을 보면 4가지로 삭제방식 상세하게 말해놓은거 이찌?
- child can have up to 40 parents 자식은 부모 40명까지 있을 수 있다...? 역시 룩업은 프리하네 .. 하늘에 40명의 부모를 올려다 보는것을 상상해보아야지..
- can be multiple layers deep.. 깁숙히 여러 계층이 될 수 있다? 몬말이야? 근데 마스터 디헤일이랑 대조하는 말은 "can be up to 3layers deep. a standard object cannot be a child"
- lookup field on page layout depends on required/optional choice. 글치 룩업은 올려만 보는것이지 페이지에 무조건 넣어야 하는것은 아니야ㅎㅎ

### master-detail relationship
- parent field on child is required.(자식에서 부모필드는 required이다)
- __access to parent determines access to children__ 이거 좀 중요한듯. 오브젝트에는 늘 접근 권한? 같은것이있다.user들은 object에 대하여 각각 다른 access를 가지는 것이지. master-detail관계의 옵젝트라면 이 접근을 그대로 물려받게 되는것임
- deleting parent automatically deletes children. 부모의 삭제는 자동으로 자식까지 삭제한다.
- child can have 2 parents. 역시 마슽허....
- can be up to 3layers deep. a standard object cannot be a child 3계층 이상까지만 딥해질 수 이싸..? 스탠다드 옵젝트는 차일드가 될 수 없어!
- lookup field on page layout is required . 마치 마스터가 말하는고지 야이자식아 너는 내가 가진 필드 무족권 넣어야 해!!!!

아 정리하니까 이제 좀 이해가 되는 옵젝트들의 관계 ㅜ^ㅜ




 
 
