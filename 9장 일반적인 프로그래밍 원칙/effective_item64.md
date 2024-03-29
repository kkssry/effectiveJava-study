# 아이템 64: 객체는 인터페이스를 사용해 참조하라.  
* 적합한 인터페이스만 있다면 매개변수뿐 아니라 반환값, 변수, 필드를 전부 인터페이스 타입으로 선언하라.  
객체의 실제 클래스를 사용해야 할 상황은 '오직' 생성자로 생성할 뿐이다.  
```java
// 좋은 예. 인터페이스를 타입으로 사용했다.
Set<Son> sonSet = new LinkedHashSet<>();
```  
```java
// 나쁜 예. 클래스를 타입으로 사용했다.
LinkedHashSet<Son> sonSet = new LinkedHashSet<>();
```  
**인터페이스를 타입으로 사용하는 습관을 길러두면 프로그램이 훨씬 유연해 질 것이다.**  

인터페이스 대신 클래스 타입을 사용해야 하는 경우
1. 적합한 인터페이스가 없는 경우
    * String과 BigInteger 같은 값 클래스.  
2. 클래스 기반으로 작성된 프레임 워크가 제공하는 객체
    * OutputStream 등 java.io 패키지의 여러 클래스가 이 부류에 속한다.
3. 인터페이스에는 없는 특별한 메서드를 제공하는 클래스
    * 예를 들어, PriorityQueue 클래스는 Queue 인터페이스에는 없는 comparator 메서드를 제공한다.


>정리  
적합한 인터페이스가 없다면 클래스의 계층구조 중 필요한 기능을 만족하는 가장 덜 구체적인(상위의) 클래스를 타입으로 사용하라.
