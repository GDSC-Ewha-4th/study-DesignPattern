# 객체지향 디자인패턴 스터디 - 1주차


## 질문
### 41p) 상속의 단점이 될 수 있는 요소 중 'A. 서브클래스에서 코드가 중복된다'는 답이 잘 이해가 가지 않습니다.
: 상속의 장점을 보통 재사용이라고 하는데, 답안이 이와 약간 상충되는 느낌이어서 헷갈렸다.
<br/><br/>
A. 같은 방식으로 오버라이딩하는 클래스가 중복될 수 있으니까 단점이다. 
<br/><br/>
-> **상속이 코드를 재사용한다는 점에선 좋지만, 오버라이딩 코드(내용)가 중복될 수 있으므로 주의해야 한다.**

<br/>

### 46p) fly()와 quack() 은 분리하고 display()는 분리하지 않은 이유는?
A. 바뀌는 부분과 그렇지 않은 부분 분리하기인데, display()는 모든 오리가 가지고 있으므로 바뀌지 않은 부분이라고 생각했다. 
   display()도 바뀌는 내용이라고 하면, 서브 클래스 하나하나 다 새로 정의해야 한다. 꽥꽥 같은 경우는 아예 안 우는 오리도 있을 수 있다.
   
<br/>

### 47p) 디자인 원칙 '구현보다는 인터페이스에 맞춰서 프로그래밍한다.'가 이해가 잘 안 된다.
A. '구현'은 일단 돌아가게만 짜는 코드다. 그렇게 하지말고 인터페이스를 활용해서 효율적으로 코드를 짜는 게 좋다!
<br/><br/>
Q. 그럼 앞에 나온, 인터페이스를 활용한 게 비효율적이라는 말은 왜 나온 건가.
<br/><br/>
A. 그건 인터페이스만 선언해놓고 클래스 안에서 구현해서 사용하는 거고, 디자인 원칙에 나온 말은 인터페이스를 구현해놓은 클래스들을 사용하는 것이므로 효율성의 측면에서 차이가 있는 거 같다.

<br/>

### 48p & 57p) 57p에 나와있는 코드를 48p에서처럼 구현된 객체를 대입하는 식으로 바꾸면 더 효율적인 코드일까?
A. getter 함수가 없어서 코드를 이렇게 표현한 거 같다.
<br/><br/>
Q. 모든 상황에 getter를 미리 선언해놓고 나중에 대입하는 게 좋은 건지, 아니면 한 번은 생성자를 사용하는 게 맞는 건지?
<br/><br/>
A. 57p는 테스트 코드라서 굳이 getter 함수를 만들지 않았고, 실제로 반복적으로 사용하는 코드에서는 getter를 활용하는 게 더 효율적일 거 같다.

<br/>

### 51p) 다른 클래스에 '위임'한다는 말이 정확히 무슨 말일까?
A. 한 클래스 안에 모든 메소드를 구현하면 다형성이 지켜지지 않으므로 다른 클래스에 위임해서, 맡겨서 쓰는 게 좋다.
<br/><br/>
Q. 모든 오리가 꽉꽉 거리는 게 아닌데 만약 삑삑이면 코드가 어떻게 되는 건지?
<br/><br/>
A. QuackBehavior 인터페이스에 꽉 클래스도 구현되어 있고, 삑 클래스도 구현되어 있다.
   그래서 quackBehavior = new Bbeak(); 선언하고, quackBehavior가 참조되는 객체에 그 행동을 위임하기 때문에 삑 소리가 나올 수 있다.

<br/>

## 헷갈리는 내용 정리
### 52p 의 MallardDuck 정리
Duck 슈퍼클래스에 quackBehavior 변수와 performQuack() 메소드가 선언 및 정의되어 있다. 그러므로 Duck 을 상속받은 MallardDuck은 quackBehavior와 performQuack을 사용할 수 있다.
<br/>
그리고 한편, MallardDuck은 생성자를 통해 quackBehavior에 Quack 클래스를 선언한다. Quack 클래스이기 때문에 performQuack()이 호출되면 "꽥꽥" 소리를 낸다. 
<br/>
이 때 "꽥꽥" 소리를 내는 행동은 MallardDuck에게 책임이 있는 게 아니라 Quack 객체에게 위임된다.
