제네릭스
========
### 제네릭이란 ?
클래스 내부에서 사용할 데이터 타입을 외부에서 지정하는 기법을 의미한다.  
->데이터 타입을 일반화(generalize)하는것을 의미.

```java

class Person<T> {
    public T info;    
}

public class GenericDemo {

    public static void main(String[] args) {
        Person<String> p1 = new Person<String>();
        Person<StringBuilder> p2 = new Person<StringBuilder>();
    }
}
```
`public T info` 에서 T는 info라는 필드의 데이터 타입이다. 명시적으로 지정된 데이터 타입이 아님.  
GenericDemo class에서  new Person 새로운 인스턴스가 생성 될때 인스턴스안의 info라는 필드의 데이터 타입은,   
<String> 타입이 젤 위의Person<T>로 들어가게 되고   
그 T가 다시 T info로 내려가서 결국 String info가 된다.

그리고 자연스럽게 생성된 인스턴스를 받아내는 변수값 p1의 데이터 타입 역시,
인스턴스의 데이터 타입과 일치되어야한다.p1의 데이터 타입 역시 Person**<String>**이여야 한다.
`Person <String> p1 = new Person<String>();` p1의 클래스 와 새로운 객체를 생성하는 클래스와 서로 클래스들이 쌍을 이뤄야 한다

p2가 생성될때, 새로 생성되는 인스턴스 안의 info라는 필드의 데이터 타입은 Person<StringBuilder> 가<T>로 들어가서 StringBuilder info; 가 됨
마찬가지로, 이런 생성된 인스턴스를 받는 p2라는 변수 역시 똑같은 클래스인 Person<StringBuilder>로 지정되어야 한다.
형변환이 자유롭게 가능하게 됨

### 제네릭은 제일 최근에 도입된 자바 기술 중 하나이고, 이 제네릭이 도입되기전에 발생되었던 어려움은 무엇일까?


```java
class StudentInfo{
    public int grade;
    StudentInfo(int grade){ this.grade = grade; }
}
class StudentPerson{
    public StudentInfo info;
    StudentPerson(StudentInfo info){ this.info = info; } 
    //StudentPerson의 생성자는 StudentInfo라는 데이터 타입의 info를 매개변수로 받고 있다.
}


//studendt와 똑같은 메커니즘을 가지는 Employee class

class EmployeeInfo{
    public int rank;
    EmployeeInfo(int rank){ this.rank = rank; }
}
class EmployeePerson{
    public EmployeeInfo info;
    EmployeePerson(EmployeeInfo info){ this.info = info; }
}
public class GenericDemo {
    public static void main(String[] args) {
        StudentInfo si = new StudentInfo(2);
        StudentPerson sp = new StudentPerson(si);//생성된si 라는 info는 newPerson의 인자로 들어가게 된다.
        System.out.println(sp.info.grade); // 2
        EmployeeInfo ei = new EmployeeInfo(1);
        EmployeePerson ep = new EmployeePerson(ei);
        System.out.println(ep.info.rank); // 1
    }
}


```

#### 코드의 중복을 제거 해보자 !
```java
class StudentInfo{
    public int grade;
    StudentInfo(int grade){ this.grade = grade; }
}
class EmployeeInfo{
    public int rank;
    EmployeeInfo(int rank){ this.rank = rank; }
}
class Person{
    //StudenPerson과 employee person 의 중복을 제거하고 Person이라는 클래스를 생성
    public Object info; 
    //studentInfo데이터타입과 EmployeeInfo의 공통 데이터 조상인, 즉 모든 클래스의 조상인 Object를 가져온다.
    // 어떠한 클래스의 instance도 올수있다
    Person(Object info){ this.info = info; }
}
public class GenericDemo {
    public static void main(String[] args) {
     Person p1 = new Person("부장님?");
     //우리가 기대하는 info는 grade 나 rank가 오는 것임
     //하지만 여기에다가 만약에 String 값을 집어 넣는다면?
    
     
     
     //그럼 일단 , Person의 info값을 가져와보자   
   EmployeInfo ei = p1.info;
    //오류가 발생하게됨 왜냐, p1의 info는 Object타입이며, ei의 데이터타입은 EmployeeInfo라는 아주 구체적인 데이터타입임.
   
    //EmployeeInfo 로 형변환이 필요하다.
        
        
    EmployeeInfo ei = (EmployeeInfo)p1.info; //오류 발생 X
    //p1.info는 Object타입이지만 (EmployeeInfo를 넣어서 형 변환을 해줌
    //하지만 EmployeeInfo는 int라는 자료형을 가지고 있으며,        
    //우리가 p1값에 넣은 자료형은 String 임. 형변환을 시도했지만 하지만 컴파일시 오류가 검출되지 않는다.
    //다행히 런타임 오류 발생.(ClassCastException) .타입이 안전하지 않음.
                 
    }
}

```

처음으로 돌아가서 우리가 StudentPerson 과 EmployeePerson을 나눴을때는,  
데이터 타입이 안전하다는 장점을 가지고 있었지만 코드의 중복을 발생 시켰고,  
우리가 그 중복을 해결을 위해 두개를 합치는 과정 중    
데이터타입을 Object로 설정해버려서 데이터가 불안정해지는 결과를 초래했고  컴파일시 오류를 확인할 수 없게 되어버렸다.  
-> JDK1.5이전에는 여러 타입을 사용해야 하는 대부분의 클래스나 메소드에서 인수나 반환값으로  Object 타입을 사용했다.  
하지만 이 경우에눈 반환된 Object 객체를 다시 원하는 타입으로 변환해야 하며 , 이때 오류가 발생할 가능성도 존재한다.  

### 제네릭화

```
class StudentInfo{
    public int grade;
    StudentInfo(int grade){ this.grade = grade; }
}
class EmployeeInfo{
    public int rank;
    EmployeeInfo(int rank){ this.rank = rank; }
}
class Person<T>{
    public T info;
    Person(T info){ this.info = info; }
}
public class GenericDemo {
    public static void main(String[] args) {
        Person<EmployeeInfo> p1 = new Person<EmployeeInfo>(new EmployeeInfo(1));
        EmployeeInfo ei1 = p1.info;
        System.out.println(ei1.rank); // 성공
         
        Person<String> p2 = new Person<String>("부장");
        String ei2 = p2.info;
        System.out.println(ei2.rank); // 컴파일 실패
        //p2.info는 String이고 , rank필드는 String 을 가지지 않기에 호출하면 실패가 된다.

```

제네릭의 선언 및 생성 정리
======================
```java

class MyArray<T>{
  T element;
  void setElement(T element) {
	this.element = element;
  }
  T getElement(){
	return element;
  }
}
```
'T'는 타입변수라고 하며, 임의의 참조형 타입을 의미한다.  
여러개의 타입 변수는 쉼표로 구분한다.  
타입변수는 클래스에서 뿐만아니라 메소드의 매개변수나 반환값으로도 사용할 수 있다.  
위와 같이 선언된 제네릭 클래스를 생성할때에는 타입 변수자리에 실제 타입을 명시해야한다.
`MyArray<Integer> myArr = new MyArray<Integer>();`

다시 한번 제네릭이란?
- 다양한 타입의 객체들을 다루는 메서드나 컬렉션 클래스에 컴파일 시의 타입 체크를 해주는 기능이다.

- 제네릭의 장점
1) 제네릭을 사용하면 잘못된 타입이 들어올 수 있는 것을 컴파일 단계에서 방지할 수 있다.(타입의 안정성을 높임)
2) 클래스 외부에서 타입을 지정해주기 때문에 따로 타입을 체크하고 변환해줄 필요가 없다. 관리가 편한다.
3) 비슷한 기능을 지원하는 경우 코드의 재사용성이 높아진다.


