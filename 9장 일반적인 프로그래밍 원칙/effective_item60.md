# 아이템 60: 정확한 답이 필요하다면 float와 double은 피하라.  
float와 double 타입은 과학과 공학 계산용으로 설계 되었다. 넓은 범위의 수를 빠르게 정밀한 '근사치'로 계산하도록 설계 되었다.  
따라서, 정확한 결과가 필요할 때는 사용하면 안된다.  
**float와 double 타입은 특히 금융 관련 계산과는 맞지 않다.**  

```java
public class BigDecimalTest {
    public static void main(String[] args) {
        double funds = 1.00;
        int itemBought = 0;
        for (double price = 0.10;  funds >= price; price += 0.10) {
            funds -= price;
            itemBought++;
        }
        System.out.println(itemBought + "ea buy");
        System.out.println("change(dollar) : " + funds);

    }
}
```  
프로그램을 실행해 보면 사탕 3개를 구입후 잔돈은 0.3999999999999999달러가 남았음을 확인 할 수 있다.  
이 문제를 올바르게 해결 하기 위해서는  
> 금융 계산에는 BigDecimal, int 혹은 long을 사용해야 한다.  

  


BigDecimal의 단점 2가지.  
1. 기본 타입보다 쓰기가 훨씬 불편하다.  
2. 느리다.  

>정리  
정확한 답이 필요한 계산에는 float나 double을 피하라.  
소수점 추적은 시스템에 맡기고, 코딩 시의 불편함이나 성능 저하를 신경 쓰지 않겠다면 BigDecimal을 사용하라.  
반면, 성능이 중요하고 소수점을 직접 추적할 수 있고 숫자가 너무 크지 않다면 int나 long을 사용하라.  

* 숫자를 아홉 자리 십진수로 표현할 수 있다면 int를 사용하고, 열여덟 자리 십진수로 표현할 수 있다면 long을 사용하라. 열여덟 자리를 넘어가면 BigDecimal을 사용해야 한다.