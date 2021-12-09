



Array and LinkedList
====================


# LinkedList 

크기가 정해저 있지 않은 데이터의 공간,
연결고리로 이어주기만 하면 자유 자재로 늘어날 수 있습니다. 

좋아 보이지만, 리스트는 특정 원소에 접근하려면 연결고리를 따라 탐색해야 한다.  

ex) 연결고리고 칸이 이뤄진 화물 열차 (연결고리가 포인터, 화물칸이 노드)

`LinkedList list = new LinkedList();` 타입 미설정 Object  
`LinkedList <Integer> num = new LinkedList<Integer>();` //int로 타입 설정

- linkedList는 선언시 크기를 미리 생성할 수 없습니다(자유자재로 늘어나는고 알쥐?)  


# Array 
배열의 크기가 정해진 데이터의 공간, 한번 정해지면 바꿀수 없음
배열은 원소에 즉시 접근이 가능함. room[0], 여기서 0은 원소의 순서이며, 인덱스라고 부른다.
ex) 캡슐 호텔.

<img src = "https://user-images.githubusercontent.com/80088918/145353081-0639aba4-a562-4f19-a87c-11d320c297fc.png">



# StringBuilder
String과 String을 합칠때 사용  
문자열을 더할 때 새로운 객체를 생성하는 것이 아니라 기존의 데이터에 더하는 방식을 사용하기 때문에
상대적으로 속도도 빠르며 부하가 적다.  
```
public class Stringbuilder {

public static void main(String[] args) {


	StringBuilder sb = new StringBuilder();
	sb.append("hello");
	sb.append("world");
	System.out.println(sb);
}
}z
```
