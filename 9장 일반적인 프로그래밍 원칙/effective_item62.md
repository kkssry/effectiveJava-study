# 아이템 62: 다른 타입이 적절하다면 문자열 사용을 피하라.  
* 문자열은 다른 값 타입을 대신하기에 적합하지 않다.  
* 문자열은 열거 타입을 대신하기에 적합하지 않다.  
* 문자열은 혼합 타입을 대신하기에 적합하지 않다.  
* 문자열은 권한을 표현하기에 적합하지 않다.  

> 정리
문자열은 잘못 사용하면 번거롭고, 덜 유연하고, 느리고, 오류 가능성도 크다. 문자열을 잘못 사용하는 흔한 예는 기본 타입, 열거 타입, 혼합 타입이 있다.