## 209p. 이 코드는 보일러가 비어있을 때만 돌아간다. 라는 주석이 잘 이해되지 않습니다.
-> 이 책에서 계속 public class 안에 private으로 만들고 있음, 하나만 만들어야하니까 null 체크처럼 해준다는 의미에서 보일러가 비어있을 때만 돌아간다고 표현한 것 아닐까 하는 추론

## 214p. uniqueInstance 변수를 static으로 선언한 이유가 잘 와닿지 않습니다.
-> 인스턴스를 생성하고 바꾸지 않기 때문에, 정적 변수랑 같은 개념으로 이해했음

## 216p. 동기화 블록 안에서도 다시 한 번 조건문으로 null 체크를 한 이유에 대해서도 얘기해보고 싶습니다.
-> null 체크를 하고 들어갔는데 다른 스레드가 그 사이에 그 사이에 들어갈 수 있어서 다시한 번 null 체킹을 해주는거임
처음엔 동기화를 들어가기 전에 하는 널체크이거 두 번째 널체크는 인스턴스를 만들기 전에 하는 널체크임

## 싱글턴 활용사례
스프링 컨테이너에서는 싱글턴이 자동으로 됨
리액트 개발할 때 url줄 때 하나의 인스턴스만 생성되게 하는 경험이 있음!
코틀린은 객체 선언 기능을 통해 object로 싱글턴 객체를 제공함, 오직 하나의 인스턴스인데 전역에서 접근할 수 있도록 동반 객체 (companion object)를 생성한 경험
