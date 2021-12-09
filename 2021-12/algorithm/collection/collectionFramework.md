 Java Collection Framework
============


자료 구조와 알고리즘은 서로 뗄수 없는 의존적인 관계이다.
알고리즘을 풀기위해 문제를 해석한 다음 보통 자료 구조를 선택한다.  
자료 구조를 선택하면 해당 자료구조에 맞는 알고리즘을 선택하는데 보다 더 효율적인 알고리즘을 선택할 수 있다.  


ex )  순서가 있는 데이터들이 있을때 inser/add, remove/delete가 빈번하게 발생한다면 LinkedList,  
아닐 경우에는 ArrayList를 쓴다.  


자바의 대표적인 자료구조인 Collection을 이해하는것은 필수!!!

### `일정 타입의 데이터들이 모여 쉽게 가공할 수 있도록 지원하는 자료구조의 뼈대`

**컬렉션이란**?  데이터를 모아 놓은 그룹,

**프레임 웍**?  표준화된 프로그래밍 방식 ( 뼈대)

collection Framework의 등장 이후 부터 다양한 종류의 (데이터 그룹)  collection 클래스가 추가되고, 각 모든 컬렉션 클래스 들을 표준화된 방식으로 다룰 수 있도록 체계화 되었다.


- **List**

  순서가 있는 데이터의 집합, 데이터의 중복을 허용한다.

  ArrayList,  LinkedList,  Stack, Vector..etc



- **Set**

  순서를 유지하지 않는 데이터의 집합, 데이터의 중복을 허용하지 않는다.

  Hashset, TreeSet

- **Map**

  key와 value로 이루어진 데이터 집합.
  key는 중복을 허용하지 않고, 값은 중복을 허용한다.

  HashMap, treeMap, Hashtable etc..
