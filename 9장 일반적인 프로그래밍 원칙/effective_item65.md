# 아이템 65: 리플렉션보다는 인터페이스를 사용하라.  
* 컴파일타임 타입 검사가 주는 이점을 하나도 누릴 수 없다. 
* 리플렉션을 이용하면 코드가 지저분하고 장황해진다.  
* 성능이 떨어진다.  

리플렉션은 아주 제한된 형태로만 사용해야 그 단점을 피하고 이점만 취할 수 있다.  

리플렉션의 단점 2가지.  
1. 런타임에 총 여섯 가지나 되는 예외를 던질 수 있다.  
2. 클래스 이름만으로 인스턴스를 생성해내기 위해 많은 량의 코드를 작성하도록 한다.  

