## 주석의 의미
```java
public class ChocolateBoiler {
	private boolean empty;
	private boolean boiled;
	private static ChocolateBoiler uniqueInstance;
  
  	// 보일러가 비어 있을 때만 돌아감
	private ChocolateBoiler() {
		empty = true;
		boiled = false;
	}
  
```

인스턴스가 null 일 때만 이 메소드가 실행된다는 의미이다.

</br>

## uniqueInstance 변수를 static으로 선언한 이유
이 변수는 동기화와는 관련없이 항상 정적변수이다. </br>
그렇다면 uniqueInstance에 하나뿐인 인스턴스는 왜 정적 변수로 선언할까? 싱글턴 패턴에서는 하나의 인스턴스만 생성하도록 하기 때문이다.

</br>

## 동기화 블록 안에서 또 null 체크를 한 이유
```java
public static Singleton getInstance) {
		if (uniqueInstance == null) { //인스턴스가 있는지 확인하고, 없으면 동기화된 블록으로 들어감
        
        	// 이러면 처음에만 동기화됨
            // 블록에서도 다시 한 번 변수가 null인지 확인한 다음 인스턴스를 생성함
			synchronized (Singleton.class) {
				if (uniqueInstance = null) { 
					uniqueInstance = new Singleton(); 
                }
			}
        }
		return uniqueInstance;
    }
```
처음 널체크는 동기화를 들어가기 위한 조건이고, 두번째 널체크는 인스턴스 생성을 위한 조건이다.

</br>

## 싱글톤 패턴 사용 경험
서버 설계에서는 다른 여러 서비스에서 유저 서비스를 호출해도 단 하나의 호출로 처리된다. 스프링에서 @Bean 으로 관리되는 것들이 모두 싱글톤 컨테이너이다. </br>
안드로이드 개발에서는 Companion Object가 쓰인다. 자바와 달리 코틀린은 객체 선언 기능을 통해 싱글턴을 언어에서 기본 지원한다. 객체 선언은 클래스 선언과 그 클래스에 속한 단일 인스턴스의 선언을 합친 선언이다. </br> 
Companion Object는 private 생성자를 호출하기 좋은 위치다. Companion Object는 자신을 둘러싼 클래스의 모든 private 멤버에 접근할 수 있다. 화면 간에 공유해야 하는 객체를 한 화면에서 딱 하나만 만들어 쓸 때 이 Companion Object를 이용한다.
