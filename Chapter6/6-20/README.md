# 20. 자바에서 Thread 만들기

## Thread 란?

- process 
  실행 중인 프로그램
  프로그램이 실행되면 OS로 부터 메모리를 할당받아 프로세스 상태가 됨

- thread
  하나의 프로세스는 하나 이상의 thread를 가지게 되고, 실제 작업을 수행하는 단위는 thread임
  
![thread](./img/thread.png)


## multi-threading 

- 여러 thread가 동시에 수행되는 프로그래밍, 여러 작업이 동시에 실행되는 효과

- thread는 각각 자신만의 작업 공간을 가짐 ( context )

- 각 thread 사이에서 공유하는 자원이 있을 수 있음 (자바에서는 static instance)

- 

