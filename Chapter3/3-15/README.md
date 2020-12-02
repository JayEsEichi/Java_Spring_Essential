# 15. 여러 인터페이스 구현하기, 인터페이스의 상속

## 여러 인터페이스 구현

- 자바의 인터페이스는 구현 코드가 없으므로 하나의 클래스가 여러 인터페이스는 구현 할 수 있음 

- 디폴트 메서드가 중복 되는 경우는 구현 하는 클래스에서 재정의 하여야 함

![multi](./img/multi.png)


Sell.java
```
public interface Sell {

	void sell();
	
}
```

Buy.java
```
public interface Buy {

	void buy();
}
```

Customer.java
```
public class Customer implements Buy, Sell{

	@Override
	public void sell() {
		System.out.println("customer sell");
	}

	@Override
	public void buy() {
		System.out.println("customer buy");		
	}

	public void sayHello() {
		System.out.println("Hello");
	}

}
```
CustomerTest.java
```
public class CustomerTest {

	public static void main(String[] args) {

		Customer customer = new Customer();
		customer.buy();
		customer.sell();
		customer.sayHello();
		
		Buy buyer = customer;
		buyer.buy();
		
		Sell seller = customer;
		seller.sell();
	}
}
```

## 디폴트 메서드가 중복 되는 경우




## 인터페이스의 상속




## 클래스 상속과 인터페이스 구현 함께 쓰기



