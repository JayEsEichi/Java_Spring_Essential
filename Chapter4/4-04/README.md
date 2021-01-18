# 04. Class 클래스 사용하기

## Class 클래스

- 자바의 모든 클래스와 인터페이스는 컴파일 후 class 파일이 생성됨

- Class 클래스는 컴파일 된 class 파일을 로드하여 객체를 동적 로드하고, 정보를 가져오는 메서드가 제공됨

- Class.forName("클래스 이름") 메서드로 클래스를 동적으로 로드 함

```
Class c = Class.forName("java.lang.String");
```

- 클래스 이름으로 직접 Class 클래스 가져오기
```
Class c = String.class;
```

- 생성된 인스턴스에서 Class 클래스 가져오기
```
String s = new String();
Class c = s.getClass();  //Object 메서드
```
