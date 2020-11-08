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
