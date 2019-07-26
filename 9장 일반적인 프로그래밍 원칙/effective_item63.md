# 아이템 63: 문자열 연결은 느리니 주의하라.  
* 문자열은 불변이라서 두 문자열을 연결할 경우 양쪽의 내용을 모두 복사해야 하므로 성능 저하는 피할 수 없는 결과다.  
```java
public String statement() {
    String result = "";
    for (int i = 0; i < numItems(); i++) {
        result += lineForItem();    // 문자열 연결
    }
    return result;
}
```  
**성능을 포기하고 싶지 않다면 String 대신 StringBuilder를 사용하자.**  

> 정리
많은 문자열을 연결할 때는 문자열 연결 연산자(+)를 피하자. 대신 StringBuilder의 append 메서드를 사용하라.  