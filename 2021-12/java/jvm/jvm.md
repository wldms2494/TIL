JVM
======
자바가 다른 프로그래밍 언어와 확연히 구별되는 특징은 "Write once, run everywhere"(한번 작성하면 어디에든 실행된다)라고 할 수 있다.  

다른 언어의 경우 OS에서  제공하는 라이브러리를 가져와서 써야하고 각 OS의 특성에 맞게 다시 개발하여야 하는 문제점이 있다.  
이러한 문제점을 해결하기 위해서 자바 프로그램은 JVM이라는 일종의 가상 서버에서  동작하도록 설계되었다.  

개발자는 더이상 OS를 신경쓰지 않아도 되고, 공통된 라이블리를 이용해서 개발에만 집중하는것이 가능해졌다!!  
즉 자바 언어는 JVM과 소통하고 JVM은 여러 OS들과 소통한다. 맥에서 개발한다면 맥용 JVM을 설치하면 되고 윈도우에서 사용한다면 윈도우용 JVM을 설치하면 된다.  
    

그래서!  
JVM이란,자바 가상 머신(소프트 웨어로 구현된 하드웨어, 컴퓨터속의 컴퓨타..)
일반 애플리케이션 코드는 OS만 거치고 하드웨어로 전달되는게 맞는데 비해 자바애플리케이션은 JVM을 한번 더 거치기 때문에,  
그리고 하드웨어에 맞게 완전히 컴파일된 상태가 아니고 실행시에 해석 되기 때문에 속도가 느리다는 단점이 있음
Java Byte Code(JVM이 이해할 수 있는 기계어)를 운영체제에 맞게 해석해주는 역할을 한다.  
시스템 메모리를 관리하면서 자바 기반 애플리케이션을 위해 이식 가능한 실행 환경을 제공한다.  


<img src = "https://user-images.githubusercontent.com/80088918/148188224-e47d35db-e96e-4d72-bbfb-f048ea688f7e.png">
javac.exe -> 컴파일러. 자바 코드를 바이트코드로 컴파일  
java.exe -> 인터프리터. 컴파일러가 생성한 바이트 코드를 해석하고 실행  
javadoc.exe -> 자동 문서 생성기, (???) 소스파일에 있는 주석을 이용하여 JAVA API문서와 같은 형식의 문서를 자동으로 생성  
jar.exe -> 압축 프로그램 . 클래스 파일과 프로그램의 실행에 관련된 파일을 하나의 자르 파일로 (.jar) 압축하거나 압축해제함.  


#### JDK와 JRE의 차이???  
JDK를 설치했다면.. JRE도 같이 설치 된다.  
JDK만 설치하면 모두 설치되는것..  
JRE는 컴파일된 자바를 실행시킬수 있는 자바환경이다.  
만약 JRE만 설치 되어 있다면.. 읽기 전용이 되는것임  
JDK가 설치되야 쓰고 읽는게 가눙!

OR
자바 프로그래밍을 하기 위해 필요한 기능을 제공해주는 JDK
그리고 자바 프로그램 실행 환경을 제공해주는JRE

JDK = JRE + 개발에 필요한 실행파일(dev tools)  
JRE = JVM + 클래스 라이브러리(JAVA API)

# Java language - JVM - OS
<img src = "https://user-images.githubusercontent.com/80088918/147938970-3122dcd6-f690-43d1-b866-fccab600719b.png">
<img src  ="https://user-images.githubusercontent.com/80088918/148313703-a11ae7e0-b74a-4784-8247-96747e435b7f.png">
내부 구조를 큰 형태로 분리해보면  
클래스 로더 서브 시스템(Class loader SubSystem)  
실행 데이터영역(Runtime Data area)  
실행 엔진(Execution Engine)으로 나눌 수 있다  

### 클래스 파일  

클래스 파일은 개발자가 만들거나 이미 만들어진 프로그램을 의미한다.  
개발자가 개발하는 자바 프로그램은 .java 이며 이파일이 자바ㅋ 컴파일러에서 컴파일러 과정을 거치면 .class파일이 생성된다.  
이렇게 컴파일 과정을 거쳐 생성된 클래스 파일은 JVM에서 실행이 가능하다.   
JAVA프로그램은 하나 혹은 그 이상의 클래스 파일들로 구성이 되고 이 클래스파일이 서로 유기적으로 동작하면서 프로그램은 자기의 기능을 수행하게 된다.  


### 클래스 로더 서브 시스템
- 클래스 파일(컴파일된넘)을 JVM 메모리에 올려놓게함   
- 클래스 로더란 '.class' 바이트 코드를 읽어 들여 class 객체를 생성하는 역할을 담당

자바 클래스 파일은 OS에서 직접 동작하지 않고 JVM 위에서 동작한다.  
JVM은 실행할 클래스 파일을 읽고 , JVM 메모리이에 올려놓는 과정이 필요한데 이 과정을 클래스 로딩이라고 한다.  
이 작업은 JVM의 클래스 로더 서브 시스템이 담당한다.  
클래스 로더 서브 시스템을 줄여서 클래스 로더라고 부르며   
다음과 같은 과정으로 JVM 메모리에 클래스 파일을 로딩한다.  
1. JVM에서 실행할 클래스 파일의 내부 구조를 분석한다.  
어떤 메소드가 있는지 어떤 변수가 선언되어 있는지 각각의 성격을 분석함  
2. 분석된 내용을 바탕으로 성격에 따라 구분하고 각각 JVM의 적합한 메모리 영역에 데이터를 올려놓는다.!  
3. 분류된 데이터는 JVM의 특별한 메모리 영역에 저장되어 있다가 클래스가 실행되면 JVM의 실행 영역의 힙 메모리로 복사된다. 그리고 시스템 리소스를 활용해서 클래스를 실행 시킨다.  

클래스를  분석하는 과정에서 클래스 로더는 자바 언어의 기능 중 하나인 리플렉션 기법을 사용하여 컴파일 된 클래스의 내부를  분석함  
(리플렉션 기법 - 객체를 통해 클래스의 정보를 분석해내는 기법. 투영 이라는 의미)
<img src = "https://user-images.githubusercontent.com/80088918/147940102-08182ca2-5136-469d-b246-a3511d68d1b6.png">  
자바는 클래스를 동적으로 로딩할 수 있는 구조를 가지고 있고 이를 동적 로딩(Dynamic loading)이라고 한다  
런타임시 JVM이 동적으로 참조할 클래스 로딩. 클래스에 대한 정보를 가지고 있지 않음.!!  
프로그램을 실행하는 도중 새로운 클래스를 로딩할 수 있음을 의미함. 클래스 파일을 로딩하는 시점에 따라 다음처럼 나뉜다.  
#### Class Loader 유형
- Bootstrap Class loader : Jvm 런타임 실행을 위해 기반이 되는 파일을 로드하며, rt.jar와 연관이 있다.  
- Extension Class Loader : Extension Class Loader가 자바 최상위 객체 Object를 포함한 자바 API를 로드한다  
- System Class Loader : System Class Loader가 클래스패스에 포함된 클래스들을 로드한다.  
BootStrap class loaer, extension class Loader를 보통 JVM을 위한 class loader이고, System Class Loader하위에 Userdefined class loader를 만들어 WAS나 Framwork 내에서 사용된다  



#### Class Loader Work  
"파일로 존재하는 Class를 RUntime Memory에 타입으로 만드는 작업을 Class Loader Work라고 한다"  
__Loading__ : binary 형태의 Type을 JVM 메모리에 올리는 과정  
__Linking__ : Loading 된 클래스를 Runtime 상태의 Binary type data로 구성하는 과정. verification(jvm에서 사용 가능한지), Preparation(type이 필요로 하는 memory를 할당해 주는 작업), resolution(실제 메모리 주소값으로 변경)

__initialization__ : 자 이제 초기화!

#### Class Loading 방법
Dynamic Loading : 모든 Class는 참조되는 순간 동적으로 Load 및 Link를 한다.  
1. 로드타임 동적 로딩 : 프로그램 실행 초깅 클래스를 로딩하는 것.   
하나의 Class를 Loading하는 과정에서 이와 관련된 클래스들을 한꺼번에 로딩한다.  

```java
public class Hello{
  public static void main(String[]args) {
	System.out.println("Hello world");
  }
    }
```
Hello라는 클래스에서 String객체를 파라미터로 이용하고 있고, System 객체를 호출하고 있다.  
이 경 우 ~!  
Hello Class가 Class loader에 의해 JVM내로 Loading될 때,  
java.lang.String Class와 java.lang.System Class가 동시에 Loading이 이루어 진다.  

Hello 클래스 실행 시  
부트스트랩 클래스 로더 생성 > Object 클래스 읽음 > Hello.class파일 읽음 > Hello 클래스 로딩시 java.lang.String Class와 java.lang.System 클래스 필요  
즉, 하나의 클래스(Hello)를 로딩하는 과정에서 동적으로 클래스들이 로딩하는것을 말함ㅋ


ㅏ



2. 런타임 동적 로딩 : 프로그램 실행 중간에도 클래스를 로딩하는 것. (보충 필요)

## 실행 데이터 영역
클래스 로더로부터 분석된 데잍를 저장하고 실행 도중 필요한 데이터를 저장하는 영역.  
메모리에 올라간 클래스, 객체, 변수들이 저장되는 곳으로 크게  
다섯개 영역(메소드, 스택, 힙 레지스터, 네이티브 메소드)로 구분된다.  

<img src = "https://user-images.githubusercontent.com/80088918/147941195-41261221-779b-432b-ab74-2ed00e7e30f4.png">  

#### 메소드 영역
클래스 로더에 의해서 로딩된 클래스가 저장되는 곳  
클래스는 메소드와 클래스 변수로 구성 되어 있잖아유? 이를 클래스의 메타 정보라고 함.  
JVM에서 클래스를 실행하면! 메소드 영역에서 클래스 정보를 복사하고 `heap` 영역에서 메모리를 할당하여 실행한다. 
JVM 메모리 영역 중 가장 먼저 데이터가 저장되는 영역

#### 스택 영역
클래스 실행은 곧 메소드 호출을 의미, 또한 메소드는 다른 메소드를 호출할 수 있다.  
호출된 (실행된) 메소드 정보가 저장되는 곳, 실행이 끝나면 저장된 정보는 삭제된다  
메소드가 실행될 때마다 저장되는 메소드 정보에는 매개변수, 지역변수, 복귀주소 등이 있다. 이 영역에서는 스택을 데이터 관리 기법으로 사용한다(LIFO 젤 먼저들어온게 젤 늦게 나감) 때문에 메소드의 호출 정보나 호출 순서를 추적하기 편함  

#### 힙 영역
JVM중 가장 중요한 역할!  
객체는 클래스가 실행 될 때 생성해서 힙 영역에 저장 됨. (객체가 생성되면 힙 메모리에 할당이 됨) 그러므로 힙 영역은 JVMㅇ서 가장 중요한 데이터를 저장함과 동시에 매우 새밀새밀한 관리가 이뤄짐  
힙 영역은 여러개의 영역으로 또 나눠짐.. (Young, Permanent, Old) 로 나눠지고 클래스 파일이 실행 되면 메소드 영역에서 클래스 정보를 복사해서 힙 영역에 실행할 클래스를 위한 메모리를 할당함.  
즉 힙 영역은 동적으로 데이터가 생성되고 소멸(GC)되는 영역이다. 그래서 JVM 성능 향상을 위해 튜닝이 가능한 영역이기도 함!  
young (Eden, Servivor1, Servivor2) permanent old에 대해서도 다음에 적어보겠고..
<img src = "https://user-images.githubusercontent.com/80088918/147942640-93a252ad-9867-4370-b27b-882789e4ef10.png">  
#### 레지스터 영역
현재 JVM이 수행할 명령어의 주소를 저장하는 메모리 공간(개발자가 특별히 여기서 하는 일은 없는 영역)  

#### 네이티브 메소드 스택 영역
OS의 시스템 정보, 리소스를 사용하거나 접근하기 위한 코드로 보통 C, C++ 로 작성한다.~
자바 이외의 언어(C, C++ , 어셈블리 등)로 작성된 코드를 실행할 때, Native Method Stack 이 할당되며, 일반적인 C스택을 사용한다