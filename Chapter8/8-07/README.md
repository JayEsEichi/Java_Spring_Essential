# 07. 피보나치 수열 문제 여러 방식으로 해결하기


![fibo1](./img/fibanacci.png)


![fibo2](./img/fibo.png)



## 재귀 함수로 풀이하기

```
public int fibonacciRecur(int n) {
		

		if (n == 0) return 0;
		if (n == 1) return 1;

		return fibonacciRecur(n - 1) + fibonacciRecur(n - 2);
}
```	

## 반복문으로 풀이하기

```
public int fibonacciIter(int n) {
		
		int ppre = 0;
		int pre = 1;
		int current = 0;

		if (n == 0) return 0;
		if (n == 1) return 1;

		for (int i = 2; i <= n; i++) {
			
			current = ppre + pre;
			ppre = pre;
			pre = current;	
		}

		return current;
}
```

## 메모이제이션 

```
public int fibonacciMem(int n) {
		
		value[0] = 0;
		value[1] = 1;
		int result = 0;
		
		if (n == 0) {
			return value[0];
		}
			
		if (n == 1) {
			return value[1];
		}
		
		for(int i = 2; i<=n; i++) {
			
			result = value[i-1] + value[i-2];
			
			if(value[i] == 0) {
				value[i] = result;
			}

		}
		
		return result;
}
```


