# 아에팀 68: 일반적으로 통용되는 명명 규칙을 따르라.  
![java_code_convention](https://ifh.cc/g/ls580.png)  

자바의 명명 규칙은 크게 `철자`와 `문법`, 두 범주로 나눈다.  
* 철자 규칙은 패키지, 클래스, 인터페이스, 메서드, 필드, 타입 변수의 이름을 다룬다.  
    * 이 규칙을 어긴 API는 사용하기 어렵고, 유지보수하기 어렵다.  
    * 패키지와 모듈 이름은 각 요소를 점(.)으로 구분 하여 계층적으로 짓는다.   
    패키지라면 조직의 인터넷 도메인 이름을 역순으로 사용한다. edu.cmu, com.google식이다.  
    패키지 이름의 나머지는 해당 패키지를 설명하는 하나 이상의 요소로 이뤄진다.  
    요소의 이름은 보통 한 단어 혹은 약어로 이뤄진다.  
    * 클래스와 인터페이스의 이름은 하나 이상의 단어로 이뤄지며, 각 단어는 대문자로 시작한다.  
    > 널리 통용되는 줄일말을 제외하고는 단어를 줄여 쓰지 않도록 한다.  
    
    * 약자의 경우 첫 글자만 대문자로 하는 쪽이 훨씬 많다. 약자가 혼합되는 경우라도 각 약자의 시작과 끝을 명확히 할 수 있기 때문이다.  
    * 상수 필드를 구성하는 단어는 모두 대문자로 쓰며 단어 사이는 밑줄로 구분한다.  
    (VALUES, NEGATIVE_IDENTITY 등)  
        * static ifnal 필드
        * 불변 참조 타입  
    * 타입 매개변수 이름은 보통 한 문자로 표현한다. 대부분 다섯 가지 중 하나다.
        * 임외의 타입엔 T
        * 컬렉션 원소의 타입은 E
        * 맵의 키와 값에는 K와 V를
        * 예외에는 X를
        * 메서드의 반환 타입에는 R을 사용한다.

| 식별자 타입           |           예 |
|:------:|:-----------:| 
| 패키지와 모듈 | rog.junit.jupiter.api, com.google.common.collect|
| 클래스와 인터페이스 |Stream,  FutureTask,  LinkedHashMap,  HttpClient|  
| 메서드와 필드 | remove, groupingBy, getCrc|
| 상수 필드 | MIN_VALUE, NEGATIVE_IDENTITY|
| 지역변수 | i, denom, houseNum|
| 타입 매개변수 | T, E, K, V, X, R, U, V, T1, T2|  

* 문법 규칙
    * 객체를 생성할 수 있는 클래스(열거 타입 포함)의 이름은 보통 단수 명사나 명사구를 사용한다. (Thread, PriorityQueue, ChessPiece등)  
    객체를 생성할 수 없는 클래스의 이름은 보통 복수형 명사로 짓는다. (Collectors, Collections 등)  
    * 인터페이스 이름은 클래스와 똑같이 짓거나 able 혹은 ible로 끝나는 형용사로 짓는다. (Runnable, Iteralbe, Accessible)  
    * 애너테이션은 워낙 다양하게 활용되어 지배적인 규칙 없이 명사, 동사, 전치사 형용사가 두루 쓰인다. (BindingAnnotation, Inject, ImplementedBy, Singleton 등)  
    * 메서드의 이름은 동사나 (목적어를 포함한) 동사구로 짓는다. (append, drawImage).  
    boolean값을 반환하는 메서드라면 보통 is나 has로 시작하고 명사구, 형용사로 짓는다 (isDigit, isProbablePrime, isEmpty, isEnabled, hasSiblings 등)  
    반환 타입이 boolean이 아니거나 인스턴스의 속성을 반환하는 메서드의 이름은 get으로 시작하는 동사구로 짓는다.  
    * 객체의 타입을 바꿔서, 다른 타입의 또 다른 객체를 반환하는 인스턴스 메서드의 이름은 보통 toType 형태로 짓는다.(toString, toArray 등)  
    객체의 내용을 다르뷰로 보여주는 메서드의 이름은 asType 형태로 짓는다. (asList 등)  
    객체의 값을 기본 타입 값으로 반환하는 메서드의 이름은 보통 typeValue 형태로 짓는다. (intValue 등)
    * 정적 팩터리의 이름을 다양하지만, from, of, valueOf, instance, getInstance, newInstance,  getType, newType을 흔히 사용한다.  

    > 표준 명명 규칙을 체화하여 자연스럽게 몸에 베도록 하자.  
    자바 언어 명세의 말을 인용하자면 "오랫동안 따라온 규칙과 충돌한다면 그 규칙을 맹종해서는 안된다." 상식이 이끄는 대로 따르자.
    



