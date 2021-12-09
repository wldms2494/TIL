Stack & Queue
==============
스택은 마지막에 저장한 데이터를 가장 먼저 꺼내게 되는

LIFO(Last In First Out)

큐는 처음에 저장한 데이터를 가장 먼저 꺼내게 되는

FIFO(First In First Out)




스택은 0,1,2 순서로 데이터를 넣었다면 2,1,0 순서로 꺼내게 된다

넣은 순서와 꺼낸 순서가 뒤집어지게 되는 것이다.

큐는 0,1, 2 순서로 데이터를 넣었다면 꺼낼 때 역시 0,1, 2 순서로 꺼내게 되는 것이다

스택과 큐를 구현하기 위해서는 어떤 컬렉션 클래스를 사용하는 것이 좋을까?

순차적으로 데이터를 추가하고 삭제하는 스택에는 ArrayList와 같은 배열 기반의 컬렉션 클래스가 적합하지만,

큐는 데이터를 꺼낼 때 항상 첫 번째 저장된 데이터를 삭제하므로 ArrayList와 같은 배열 기반의 컬렉션 클래스를 사용한다면 데이터를 꺼낼 때마다 빈 공간을 채우기 위해 데이터의 복사가 발생하므로 비 효율 적이다. 그래서 큐는 LinkedList로 구현하는 것이 더 적합하다.

```java

import java.util.*;

public class Main  {
  public static void main(String[] args) {

   Stack st = new Stack();
   Queue q = new LinkedList(); //Que's interface

    st.push("0");
    st.push("1");
    st.push("2");

    q.offer("0");
    q.offer("1");
    q.offer("2");

    System.out.println("===stack===");
    while(!st.empty()){
      System.out.println(st.pop());
    }

    System.out.println("===Queue===");
    while(!q.isEmpty()) {
      System.out.println(q.poll());
    }
  }
}
```


자바에서는 스택을 클래스로 구현하여 제공하고 있지만 큐는 인터페이스로만 정의해 놓았을 뿐 별도의 클래스를 제공하고 있지 않다. 대신 큐 인터페이스를 구현한 클래스들이 있어서 이 들 중 하나의 선택해서 사용하면 된다.

스택의 활용 예 - 수식계산, 수식괄호 검사 , 웹 브라우저의 뒤로/ 앞으로

큐의 활용 예 - 최근 사용 문서 ( ? )