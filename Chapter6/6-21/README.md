# 21. Thread 클래스의 여러 메서드들

## Thread 우선순위

- Thread.MIN_PRIORITY(=1) ~ Thread.MAX_PRIORITY(=10)

- 디폴트 우선순위 : Thread.NORMAL_PRIORITY(=5)

- 우선 순위가 높은 Thread가 CPU의 배분을 받을 확률이 높다

- setPriority()/getPriority()

- Thread 우선순위 예제

```



```

## join()

- 동시에 두 개 이상의 Thread가 실행 될 때 다른 Thread의 결과를 참조 하여 실행해야 하는 경우 join() 함수를 사용

- join() 함수를 호출한 Thread가 not-runnable 상태가 감

- 다른 Thread의 수행이 끝나면 runnable 상태로 돌아옴

![join](./img/join.png)
