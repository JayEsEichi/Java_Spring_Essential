# 08. 다운 캐스팅과 instanceof 

## 다운 캐스팅(downcasting)

- 업캐스팅된 클래스를 다시 원래의 타입으로 형 변환

- 하위 클래스로의 형 변환은 명시적으로 해야 함

```
Customer vc = new VIPCustomer();              //묵시적
VIPCustomer vCustomer = (VIPCustomer)vc;      //명시적
```