# 아이템 58: 전통적인 for문 보다는 for-each 문을 사용하라.  
```java
for (int i = 0; i < a.length; i++) { 
    ...  // a[i]로 무언가를 한다.
}
```  
* 반복자와 인덱스 변수로 코드가 지저분 하다.
* 오류가 생길 가능성이 높아진다.
    * 잘못된 변수를 사용 했을 때 컴파일러가 잡아주리라는 보장이 없다.  

이상의 문제는 for-each 문 (= 향상된 for문) 으로 해결 가능하다.  
```java
for (Element e : elements) {
    ... // e로 무언가를 한다.
}
``` 

for-each 문의 가독성을 확인해 보자.  
먼저 전통적인 for문 먼저 살펴보자.
```java
for (Iterator<Suit> i = suits.iterator ; i.hasNext(); ) {
    Suit suit = i.next();
    for (Iterator<Rank> j = ranks.iterator(); j.hasNext; ) {
        deck.add(new Card(suit, j.next()));
    }
}
```
for-each 문
```java
for(Suit suit : suits) {
    for (Rank rank : ranks) {
        deck.add(new Card(suit, rank));
    }
}
```

for-each 문을 사용할 수 없는 상황 3가지.  
1. 파괴적인 필터링  
    * 예를들어 컬렉션을 순회하면서 선택된 원소를 제거해야 한다면 반복자의 remove 메서드를 호출해야 한다.
        * 자바 8부터는 Collection의 removeIf 메서드를 사용해 컬렉션을 명시적으로 순회하는 일을 피할 수 있다.  
2. 변형
    * 리스트의 반복자나 배열의 인덱스를 사용하여 원소의 값 혹은 일부를 교체 할때  
3. 병렬 반복
    * 여러 컬렉션을 병렬로 순회해야 한다면 각각의 반복자와 인덱스 변수를 사용해 엄격하고 명시적으로 제어해야 한다. 





> 정리
for-each 문은 전통적인 for문과 비교했을 때 명료하고, 유연하고, 버그를 예방해준다. 성능 저하도 없다. 가능한 모든 곳에서 for 문이 아닌 for-each문을 사용하자.

    