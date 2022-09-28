### @DisplayName

테스트 코드 작성 시, 함수명으로 결과를 받으면 무슨 테스트인지 헷갈릴 수 있으니, @DisplayName 어노테이션을 사용하여 결과로 표시할 이름(혹은 내용) 정의

```java
public class Test {
    
    @Test
    @DisplayName("~~테스트")
    public void MyTest() {/**/}
}
```

그냥 메서드 이름을 한글로 작성할 수도 있는데, 왜 굳이 DisplayName을 사용할까?

-> 한글로 작성해도 이름이 길어질 경우 띄어쓰기를 위해 언더바를 사용해야 해서 가독성 떨어짐

<br/>

### @Nested

관심사가 비슷한 메서드들을 하나로 묶어주는 역할. 예를 들어, 같은 기능을 테스트하는데, 성공 / 실패 두가지 케이스를 모두 테스트.

```java
public class Test {
    
    @Nested
    @DisplayName("A 테스트")
    class testA {
        
        @Test
        @DisplayName("성공")
        public void success() {/**/}
        
        @Test
        @DisplayName("실패")
        public void fail() {/**/}
    }
    
    @Nested
    @DisplayName("B 테스트")
    class testB {
        
        @Test
        @DisplayName("성공")
        public void success() {/**/}

        @Test
        @DisplayName("실패")
        public void fail() {/**/}
    }
}
```