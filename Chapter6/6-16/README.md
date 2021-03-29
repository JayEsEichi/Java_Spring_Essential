# 16. 여러가지 보조 스트림 클래스들

## 보조 스트림 

- 실제 읽고 쓰는 스트림이 아닌 보조 기능을 추가하는 스트림

- FilterInputStream과 FilterOutputStream 이 보조 스트림의 상위 클래스들

- 생성자의 매개변수로 또 다른 스트림(기반 스트림이나 다른 보조 스트림)을 가짐

- 상위 클래스 생성자

| 생성자 | 설명 |
| ------ | ------ |
| protected FilterInputStream과(InputStream in) | 생성자의 매개변수로 InputStream을 받습니다. |
| public FilterOutputStream(OutputStream out) | 생성자의 매개변수로 OutputStream을 받습니다. |

![deco](./img/decostream.png)

