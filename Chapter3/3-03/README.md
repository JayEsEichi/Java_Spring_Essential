# 03. 상속에서 클래스 생성 과정과 형 변환

## 하위 클래스가 생성 되는 과정

- 하위 클래스를 생성하면 상위 클래스가 먼저 생성 됨 

Customer.java
```
public Customer() {
		customerGrade = "SILVER";
		bonusRatio = 0.01;
		
		System.out.println("Customer() 생성자 호출");
}
```

VIPCustomer.java
```
public VIPCustomer() {
		customerGrade = "VIP";
		bonusRatio = 0.05;
		salesRatio = 0.1;
		
		System.out.println("VIPCustomer() 생성자 호출");
}
```