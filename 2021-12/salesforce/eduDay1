Appbuild Edu D+1
======================
오늘 첫 교육 과정 
일단 전체적 플랫폼 살펴보았음
백의 APPEX는 java언어랑 굉장이 흡사하다곤 하시나 테이블 조인이 안 일어난다  
join리마인드 시간을 다시 가져본다..  
조인은 두개 이상의 테이블이나 데이터베이스를 연결하여 데이터를 검색하는 방법이다.  
자신이 검색하고 싶은 컬럼이 다른 테이블에 있을 경우 주로 사용하며 여러 개의 테이블을 마치 하나의 테이블인 것처럼 활용 하는 방법이다.  
보통 pk 또는 FK로 두 테이블을 연결하고, 테이블을 연결하려면 적어도 하나의 컬럼은 서로 공유되어야 한다 
 
 이거 TIL에 정리 했었는데 기억 왜 안남 ;-;?
 
#### innter join
교집함임. 기존 테이블과 join한 테이블이의 중복된 값임

`
SELECT
A.NAME,
B,AGE
FROM EX_TABLE A
INNER JOIN JOIN_TABLE B 
ON A.NO_EMP = B.NO_EMP AND B.DEPT = B.DEPT

`

아 근데 나 진짜 sql문법 진짜 제로에 가깝기에.. 문법 다시 집고 간다;;;  

-------문법 ------

SQL : Structured Query Language 디비 제어 언어  
1) DML : Data manipulation Language  
- INSERT 정보저장 (Create)
- SELECT 정보 조회 (Read)  
- UPDATE 정보 수정 (Update)  
- DELETE 정보 삭제 (Delete)  

2) DDL : Data Definition Language  
- CREATE 테이블 생성
- DROP 테이블 삭제  
- ALTER 테이블 구조 수정  


3) DCL : Data Control Language  
- COMMIT : 정보를 실제 디비에 저장  
- ROLLBACK : 작업을 취소  





SELECT*
FROM 첫번째 테이블 이름
INNER JOIN 두번째 테이블 이름
ON 조건  


SELECT*
FROM 첫번째 테이블 이름
JOIN 두번째 테이블 이름
ON 조건


SELECT*
FROM 첫번째 테이블 이름 AS별칭
     두번째 테이블 이름 AS 별칭
WHERE 조건



EX. RESERVE테이블의 NAME필드와 CUSTOMER 테이블의 NAME필드가 서로 일치하는 레코드만 INNERJOIN으로 가져와방  
1.SELECT*
FROM Reservation
INNER JOIN Customer
On Reservation.Name = Customer.Name;

2.SELECT*
FROM Reservation
JOIN Customer
On Reservation.Name = Customer.Name;


3.SELECT*
FROM Reservation AS r, Customer AS c
WHERE r.Name=C.Name;


#### left  outer join
#### right outer join
### full outer join 
일단 오늘은 이너조인까지만 ㅇㅅㅇ ㅎㅎ;;  

그다음 테이블의 개념을 가진것이 object인데 테이블 보다 더 기능이 많다고 하신다.  
object를 하나의 업무라고 보면 된다
엄청나게 많은 스탠다드 object들이 있다.  
모두들의 특징을 알아야 설계가 가능하다

Case - 제품의 문의사항 요구사항들이 들어간다.
Opportunity 영업관리 
Delievery
Contract
Account 고객관리 ...

그다음 object Permission도 배움 
profile 을 통해 오브젝트에서 CRUD 권한 주는것도 배웠고, profile 전부 하나하나 객체마다 설정하는거 넘 빡시니까
뭐 똑같은 예를들어서 mimi access권한을 가지는 porfile을 주되 permission Set을 통해 어떤 유저는 특별히 Edit Access를 준다던가 가능함ㅎ
