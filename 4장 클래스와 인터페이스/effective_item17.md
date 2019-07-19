# 아이템 17 : 변경 가능성을 최소화하라  
불변 클래스란 쉽게 말해 그 인스턴스의 내부 값을 수정할 수 없는 클래스다.  
* 예를들어, 자바 플랫폼 라이브러리에서 불변 클래스
    * String, 기본 타입의 박싱된 클래스, BigInteger, BigDecimal등  

불변 클래스의 장점
* 설계 하기 쉽다.
* 구현하기 쉽다.
* 사용하기 쉽다.
* 오류가 생길 여지가 없어 안전하다.  

불변 클래스로 만드는 5가지 규칙  
1. 객체의 상태를 변경하는 메서드(변경자)를 제공하지 않는다.  
2. 클래스를 확장할 수 없도록 한다.  
    * 하위 클래스에서 객체의 상태를 변하게 만드는 상태를 막아준다.
3. 모든 필드를 final로 선언한다.  
4. 모든 필드를 private으로 선언한다.  
5. 자신 외에는 내부의 가변 컴포넌트에 접근할 수 없도록 한다.   

```java
public class Complex {            // 복소수
    private final double re;      // realPart (실수부)   
    private final double im;      // imaginaryPart (허수부)

    private Complex(double re, double im) {
        this.re = re;
        this.im = im;
    }

    public Complex plus(Complex c) {
        return new Complex(re + c.re, im + c.im);
    }

    public Complex minus(Complex c) {
        return new Complex(re - c.re, im - c.im);
    }

    public Complex times (Complex c) {
        return new Complex (re * c.re - im * c.im,
                            re *c.im + im * c.re);


    ... 코드 생략


    } 
}

```


불변 객체는 단순하여 생성된 시점의 상태를 파괴될 때까지 그대로 간직한다.  
**불변 클래스는 값이 다르면 반드시 독립된 객체로 만들어야 된다.**  
클래스가 불변임을 보장하려면 자신을 상속하지 못하게 해야 한다.
* final 클래스로 선언
* 모든 생성자를 private 혹은 package-private으로 만들고 public 정적 팩터리 제공  


```java
public class Complex {            // 복소수
    private final double re;      // realPart (실수부)   
    private final double im;      // imaginaryPart (허수부)

    private Complex(double re, double im) {
        this.re = re;
        this.im = im;
    }

    public static Complex valueOf(double re, double im) {
        return new Complex(re, im);
    }

    ... 코드 생략


    } 
}

```
