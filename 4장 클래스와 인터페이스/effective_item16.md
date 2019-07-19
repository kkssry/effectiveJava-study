# 아이템 16 : public 클래스에서는 public 필드가 아닌 접근자 메서드를 사용하라.  


```java
clas Point {
    public double x;
    public double y;
}
```  
이런 클래스는 데이터 필드에 직접 접근할 수 있어 캡슐화의 이점을 제공하지 못한다.(아이템 15)  
1. public 클래스는 절대 가변 필드를 직접 노출해서는 안된다.  
2. 불변 필드라면 노출해도 덜 위험하지만 완전히 안심 할 수는 없다.  
3. package-private 클래스나 private 중첩 클래스에서는 종종 (불변이든 가변이든) 필드를 노출하는 편이 나을 때도 있다.  
