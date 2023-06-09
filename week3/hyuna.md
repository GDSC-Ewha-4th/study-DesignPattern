## 주문 시스템에서 모든 주문에 대한 서브 클래스를 만들면 어떤 디자인 원칙에 위배될까?
- 바뀌는 부분은 캡슐화한다.
- 상속보다는 구성을 활용한다.
- 구현보다는 인터페이스에 맞춰서 프로그래밍한다는 만족하고 있는가? </br>
-> 상속을 하고 있기 때문에 이건 만족하고 있다.
- 상호작용하는 객체 사이에서 최대한 느슨한 결합을 사용하고 있는가? </br>
-> 휘핑이나 모카처럼 다양한 옵션이 배버레지 클래스와 상관없이 자유자재로 추가 수정 삭제 가능하다.

## OCP를 준수하는 실제 프로젝트 사례에는 어떤 것이 있을까?
OCP 원칙의 가장 잘 따르는 예시가 바로 자바의 데이터베이스 인터페이스인 JDBC이다. 
만일 자바 애플리케이션에서 사용하고 있는 데이터베이스를 MySQL에서 Oracle로 바꾸고 싶다면, 복잡한 하드 코딩 없이 그냥 connection 객체 부분만 교체해주면 된다.

## 데코레이터 패턴과 인터페이스 사용은 같은 의미일까?
인터페이스 구현 중 데코레이터 패턴이 될 수 있는 경우도 있고 그렇지 않은 경우도 있다.

## 인스턴스 변수를 감싸고자 하는 객체로 설정하는 생성자란 무엇일까?
```java
// Mocha 인스턴스에는 Beverage의 레퍼런스가 들어있으며, 아래 2가지가 필요하다.
// 1. 감싸고자 하는 음료를 저장하는 인스턴스 변수
// 2. 인스턴스 변수를 감싸고자 하는 객체로 설정하는 생성자
public Mocha(Beverage beverage) 
this.beverage = beverage;
```
위 코드를 보면 인스턴수 변수 `this.beverage` 를 감싸고자하는 객체인 `Beverage beverage` 로 초기화해주는 생성자가 필요하다.

## 특정 형식에 의존하는 클라이언트 코드란 무엇일까?
클라이언트가 데코레이터 패턴으로 인해 내부를 볼 수 없으면 안되는 경우를 말한다.
예를 들어 HouseBlend를 데코레이터로 감싸고 나면 그 커피가 하우스블렌드인지 다크로스트인지 알 수 없어서 구상 구성 요소로 할인과 같은 추가 작업을 할 수 없게 된다. 
