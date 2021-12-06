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