
What is Redis?
===============
#### Fast, open sourced in-memory data store for use as a database, cache, message broker, and queue
Redis는 빠른 오픈 소스 inMemory 키 값 데이터 구조 스토어입니다.  
Redis는 다양한 인메모리 데이터 구조 집합을 제공하므로 다양한 사용자 정의 애플리케이션을 손쉽게 생성할 수 있습니다.  
주요 Redis 사용 사례로는 캐싱, 세션 관리, pub/sub 및 순위로들 수 있습니다.

__Cache__ : 나중에 요청올 결과를 미리 저장해두었다가 빠르게 서비스를 해주는것을 의미  
Look aside Cache->디비를 가기전에 캐시에서 데이터가 있는지 확인하고, 없으면 디비로간다.(가장 일반적인 방법)

Factorial 계산: 20880!를 계산해 두고 어딘가에 저장해 뒀다면 20881! 계산은 금방 나온다 ~!  
-> 접근 속도가 다름  
디스크 메모리 L3cache L2 cache l1cache core  
<-capicity                       -> latency

Acronym : Remote Dicationly Server


- In-memory Database (Cache)
  : Database 보다 더 빠른 Memory에 더 자주 접근하고 덜 자주 바뀌는 데이터를 저장하자.

- (In-memory 특성상 메모리 파편화, 가상 메모리 등의 이해가 필요함ㅋ)
  Data Structure
  : redis 는 *Collection 자료 구조* 를 제공한다.

- persistence 를 지원하여 서버가 꺼지더라도 다시 데이터를 불러들일 수 있다. 명시적으로 삭제, Expire를 설정하지 않으면 데이터가 삭제되지 않는다. 스냅샷(기억장치)기능을 제공하여 메모리의 내용을 .*rdb파일로 저장해서 해당 시점으로 복구도 가능 !
  자바의 자료구조와 어떤 차이가 있는가?



AWS는 Redis용 Amazon ElasticCache라는 최적화된 완전 관리형 데이터베이스 서비스를 통해 Redis를 지원하며,  
고객은 원하는 경우 AWS EC2에서 자체 관리형 Redis를 실행할 수도 있습니다.

Benefits of Redis
========

1) 놀러울정도로 빠른 성능
   : 데이터를 디스크(HDD-HardDiskDrive) 또는 SSD(Solid State Drive -메모리 반도체에 데이터 저장)에 저장하는 대부분의 데이터 베이스 관리 시스템과는 달리 모든 Redis 데이터는 서버의 주 메모리에 상주합니다.  
   Redis와 같은 인 메모리 데이터 베이스는 디스크에 access해야 할 필요를 없앰으로써 검색 시간으로 인한 지연을 방지하고   
   CPu 명령을 적게 사용하는 좀 더 간단한 알고리즘으로 데이터에 access할 수 있습니다.  
   일반적으로 작업을 실행하는 데 1초 미만이 소요됩니다.


2) 인메모리 데이터 구조  
   : Redis를 사용하면 사용자가 다양한 데이터 유형에 매핑되는 키를 저장할 수 있습니다.

단점
===============
1.인메모리 저장 스토어이기 때문에 만약 내 놋북 용량이 8GB 라면? 메인 데이터베이스로 사용하기엔 부족하고.. 그러면 큰용량의 렘을 구매해야하나? 그러려니 비용이 발생한다  

2.인메모리 데이터 스토어이기 때문에, physical Memory이상을 사용하면 당연히 문제가 발생하게 된다. 죽으면 swap이 발생했을때 디스크에 접근하게 되는데 그러면 레이턴시가 발생하게되고 결국 레디스의 가장 큰 장점을 잃게 된다.. 그래서 메모리관리가 엄청엄청 중요하다~  





Redis Use Cases
===============
#### Caching

Redis is a great choice for implementing a highly available in-memory cache to decrease data accesss latency,  
increase throughput, and ease the load off your relational or NoSQL db and application.
Redis can serve frequently requested items at sub-milliseconds response times,  
and enables you to easily scale for higher loads without growing the costlier backend.  
DB query results caching, persistent session caching, web page caching, and caching of frequently used objects such as  
images, files, and metadata are all popular examples of caching with Redis !


#### Chat, messaging, and queues
#### Gaming leaderboards
#### Session Store
#### Rich media streaming
#### Geospatial
#### Machine Learning
#### Real-time analytics