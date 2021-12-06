Each algorithm, java ->commit everyday!




반복문 
- for :반복 횟수를 알고 있을때 사용
- while : 그렇지 않을때 사용

```java
for(초기화;조건식;증감식;){
    }
```

## 중첩 for문
```java

  public static void main(String[] args) {

	//5행 10열의 별찍기
	for (int j = 0; j < 5; j++) {
	  for (int i = 0; i < 10; i++) {
		System.out.print("*");
	  }
	  System.out.println();
	}
  }

```

```java

  public static void main(String[] args) {

	//삼각형 별찍기

	System.out.println("*");
	System.out.println("**");
	System.out.println("***");
	System.out.println("****");
	System.out.println("*****");

	System.out.println("=======deli=========");

	for (int i = 0;i<1; i++){
	  System.out.print("+");
	}
	System.out.println();

	for (int i = 0;i<2; i++) {
	  System.out.print("+");
	}
	System.out.println();

	for (int i = 0;i<3; i++) {
	  System.out.print("+");
	}
	System.out.println();

	for (int i = 0;i<4; i++) {
	  System.out.print("+");
	}
	System.out.println();

	for (int i = 0;i<5; i++) {
	  System.out.print("+");
	}

	System.out.println();
	System.out.println("=======deli=========");

	for(int j = 0; j<6; j++) {
	  for (int i = 0; i < j; i++) {
		System.out.print("+");
	  }
	  System.out.println();
	}
  }
}

```