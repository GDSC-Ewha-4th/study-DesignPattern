## 제품 클래스는 모두 똑같은 인터페이스를 구현해야 한다는 말은 어떤 의미일까?
이번 주에 배운 디자인 원칙에서 추상화된 것에 의존하게 만들고 구상 클래스에 의존하지 않게 만들어야 한다고 했는데, 그것과 같은 맥락이다.
제품을 사용할 클래스에서는 구상 클래스가 아닌 인터페이스의 레퍼런스로 객체를 참조해야 하므로, 제품 클래스가 모두 똑같은 인터페이스를 구현하도록 해야한다.
제품이 다르다고 각자 다른 구상 클래스의 레퍼런스로 객체를 참조하면 제품의 변경이나 추가, 삭제등이 자유롭지 못하다.

</br>

## 팩토리 메소드 패턴을 제외하고, 의존성 뒤집기 원칙을 준수하는 다른 방법에는 무엇이 있을까?
전략 패턴이 의존성 뒤집기 원칙을 준수하는 다른 사례가 될 수 있다.
고수준 구성 요소를 바탕으로 만들어진 각각의 전략들은 일종의 저수준 구성 요소가 된다. 구성된 이 전략들은 고수준 구성 요소에 의존하지만, 전략의 추상들은 각각의 전략에 의존하지 않는다.

</br>

## 왜 저수준 구성 요소 뿐만 아니라 고수준 구성 요소와 저수준 구성 요소 모두가 의존하는가?
최상위 요소가 되는 피자 가게도 피자라는 추상에 의존하고 있다. 최하위 요소가 되는 치즈 피자 역시 피자라는 추상에 의존하여 구성된 개념이다.
따라서 두 구성 요소 모두 하나의 추상 클래스에 의존하여 돌아가는 형태이다.

</br>

## 간단한 팩토리 vs 팩토리 메소드 vs 추상 팩토리 메소드
### 간단한 팩토리
단순히 인스턴스 생성기능만 따로 빼준 것을 말한다.

</br>

### 팩토리 메소드
팩토리 메소드는 단순한 추상-구상 패턴이다.
객체를 생성하는 방법을 수정하거나 새로운 객체를 수정하기 좋다.

</br>

### 추상 팩토리 메소드
추상-구상-구성 패턴이다.
추상 팩토리를 구상하고 그 구상 팩토리를 구성해서 쓴다.
이때 이 구상 팩토리는 내가 구현하고자 하는 객체 안에 있다.
팩토리 메소드를 더 캡슐화한 방식이라고 할 수 있다.