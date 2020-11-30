# 09. 추상 클래스(abstract class) 구현하기

## 추상 클래스란?

- 구현 코드 없이 메서드의 선언만 있는 추상 메서드(abstract method)를 포함한 클래스

- 메서드 선언(declaration) : 반환타입, 메서드 이름, 매개변수 로 구성

- 메서드 정의(definition) : 메서드 구현(implementation)과 동일한 의미 구현부(body) 를 가짐 ({ })

- 예) int add(int x, int y); // 선언 <br>
&nbsp;&nbsp;int add(int x, int y){ } // 구현부가 있음, 추상 메서드 아님

- abstract 예약어를 사용

- 추상 클래스는 new 할 수 없음 ( 인스턴스화 할 수 없음 )