# static메서드의 구현과 활용

## static 메서드 만들기

- serialNum 변수를 private으로 선언하고 getter/setter 구현

Employee.java
```
private static int serialNum = 1000;

 ...
public static int getSerialNum() {
	return serialNum;
}

public static void setSerialNum(int serialNum) {
	Employee.serialNum = serialNum;
}
```

- 클래스 이름으로 호출 가능 ( 클래스 메서드, 정적 메서드 )
```
System.out.println(Employee.getSerialNum());
```

## static 메서드(클래스 메서드)에서는 인스턴스 변수를 사용할 수 없다

- static 메서드는 인스턴스 생성과 무관하게 클래스 이름으로 호출 될 수 있음

- 인스턴스 생성 전에 호출 될 수 있으므로 static 메서드 내부에서는 인스턴스 변수를 사용할 수 없음

Employee.java
```
public static void setSerialNum(int serialNum) {
		int i = 0;
		
		employeeName = "Lee";  //오류발생
		Employee.serialNum = serialNum;
	}
```

EmployeeTest2.java
```
public class EmployeeTest2 {

	public static void main(String[] args) {

		System.out.println(Employee.getSerialNum());
		Employee.setSerialNum(1003);
		System.out.println(Employee.getSerialNum());
	}
}
```


