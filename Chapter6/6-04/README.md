# 04. 객체지향 프로그래밍 vs. 람다식 구현

## 객체 지향 프로그래밍과 람다식 비교

- 문자열 두 개를 연결하여 출력하는 예제를 두 가지 방식으로 구현해 보자

- 인터페이스 선언

```
public interface StringConcat {
	
	public void makeString(String s1, String s2);

}
```

- 객체 지향 프로그래밍으로 구현하기

 인터페이스를 구현한 클래스 만들기

```
public class StringConCatImpl implements StringConcat{

	@Override
	public void makeString(String s1, String s2) {
		System.out.println( s1 + "," + s2 );
	}
}
```
 클래스를 생성하고 메서드 호출하기

```
public class TestStringConcat {

	public static void main(String[] args) {

		String s1 = "Hello";
		String s2 = "World";
		StringConCatImpl concat1 = new StringConCatImpl();
		concat1.makeString(s1, s2);
    }
}
```
