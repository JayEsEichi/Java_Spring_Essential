# 13. 표준 입출력 스트림

## System 클래스의 표준 입출력 멤버

```
public class System{ 
	public static PrintStream out; 
	public static InputStream in; 
	public static PrintStream err; 
}
```

- System.out

표준 출력(모니터) 스트림

System.out.println("출력 메세지");

- System.in

표준 입력(키보드) 스트림

int d = System.in.read() // 한 바이트 읽기

- System.err

표준 에러 출력(모니터) 스트림

System.err.println("에러 메세지");



