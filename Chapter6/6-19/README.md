# 19. 데코레이터 패턴을 활용한 커피 머신 프로그램

## Decorator Pattern

- 자바의 입출력 스트림은 decorator pattern 임

- 여러 decorator들을 활용하여 다양한 기능을 제공

- 상속 보다 유연한 구현 방식

- 지속적인 기능의 추가와 제거가 용이함

- decorator와 component는 동일한 것이 아님 ( FileInputStream 만이 파일에서 읽는 기능이 제공 됨)

![decorator](./img/decorator.png)

## 커피를 만들어보아요~

    Decorator Pattern을 활용하여 커피를 만들어 봅시다.

    아메리카노
    카페 라떼 = 아메리카노 + 우유
    모카 커피 = 아메리카노 + 우유 + 모카시럽
    크림 올라간 모카커피 = 아메리카노 + 우유 + 모카시럽 + whipping cream



