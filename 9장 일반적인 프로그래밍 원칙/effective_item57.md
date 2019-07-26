# 아이템 57: 지역변수의 범위를 최소화 하라  
지역변수의 유효 범위를 최소로 줄이면 코드 가독성과 유지보수성이 높아지고 오류 가능성은 낮아진다.  
> 지역변수의 범위를 줄이는 가장 강력한 기법은 역시 '가장 처음 쓰일 때 선언 하기'다.  

* 사용하려면 멀었는데, 미리 선언부터 해두면 코드가 어수선해져 가독 성이 떨어 진다.  
* 메서드를 작게 유지하고 한 가지 기능에 집중하는 것이다.
* 실수로 의도한 범위 앞 혹은 뒤에서 그 변수를 사용하면 끔찍한 결과로 초래할 수 있다.  
> 반복 변수의 값을 반복문이 종료된 뒤에도 써야 하는 상황이 아니라면 while 문보다 for문을 쓰는 편이 낫다.  

**예시 )**  

*1. while 문을 쓰는 경우*
```java
Iterator<Element> i = c.iterator();
while(i.hasNext()) {
    doSomething(i.next());
}

...

Iterator<Element> i2 = c2.iterator();
while(i.hasNext()) {                // 버그!
    doSomething(i2.next());
}
```  
두번째 while문에서 실수로 i2를 초기화 했지만 이전 while문에서 쓴 i를 다시 쓰고 있다. 불행히도 i의 유효범위는 아직 끝나지 않았으므로, 이 코드는 컴파일도 잘 되고 실행 시 예외도 던지지 않는다.  
프로그램 오류가 겉으로 드러나지 않으니 오랜 기간 발견되지 않을 수도 있다.

*2. for문을 쓰는 경우*
```java
for (Iterator<Element> i = c.iterator(); i.hasNext(); ) {
    Element e = i.next();
    ... //e로 무언가를 한다.
}

...

for (Iterator<Element> i2 = c2.iterator(); i.hasNext(); ) {
    Element e2 = i2.next();
    ... //e2와 i2로 무언가를 한다.
}
```  
변수 유효 범위가 for 문 범위와 일치하여 똑같은 이름의 변수를 여러 반복문에서 써도 서로 아무런 영향을 주지 않는다.  

for 문의 장점을 하나 더 얘기하자면 while문 보다 짧아서 가독성이 좋다.  
  
