# 아이템 20 : 추상 클래스보다는 인터페이스를 우선하라.  
자바 8부터 인터페이스도 디폴트 메서드를 제공할 수 있게 되었다.  
추상 클래스와의 차이점은 추상클래스가 정의한 타입을 구현하는 클래스는 반드시 추상 클래스의 하위 클래스가 되어야 한다.  
반면 인터페이스가 선언한 메서드를 모두 정의하고 그 일반 규약을 잘 지킨 클래스라면 다르 어떤 클래스를 상속했든 같은 타입으로 취급된다.  
> 인터페이스는 믹스인(mixin) 정의에 안성 맞춤이다.  

믹스인 : 클래스가 구현할 수 있는 타입으로, 원래의 '주된 타입' 외에도 특정 선택적 행위를 제공한다고 선언하는 효과를 준다. 예컨대 Comparable은 자신을 구현한 클래스의 인스턴스들끼리 순서를 정할 수 있다고 선언하는 믹스인 인터페이스다.  

>정리  
일반적으로 다중 구현용 타입으로는 인터페이스가 가장 적절하다.
