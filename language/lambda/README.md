# Lambda
목표 : 
 * 람다 문법에 익숙해 지기 
 * 유용한 경우 찾기
## 정의
람다는 : 
 * 다른 함수로 전달할 수 있는 작은 코드 덩어리

장점 : 
 * 공통 코드 구조를 라이브러리 함수로 추출하기 쉽다
 * Kotlin에서 자주 사용

사용 예제 : 
 * collection에서 특히 많이 사용
 * 일반적인 collection 접근 패턴 -> 람다를 표준 라이브러리 함수로 전달

## 함수 인자로 사용되는 코드 블럭
 * 어떤 이벤트가 일어날 때 이 부분을 실행해 주세요!
 * 자료구조에 있는 모든 아이템에 이 연산을 적용해 주세요!
 * -> 함수 인자로 직접 코드 블럭을 전달하면 된다!

ex)
```kotlin
data class Book(val title: String, val isdn: Int)

fun findLongestTitleBook(books: List<Book>){
    var lTitlebook = Book("", 0)
    for (book in books) {
        if (book.title.length > lTitlebook.title.length) {
            lTitlebook = book
        }
    }
}
```

### 문법
작은 코드 블록으로 값처럼 전달이 가능합니다. 따라서 독립적으로 선언하고 변수에 저장할 수 있습니다. 

val sum = {x: Int, y: Int -> x + y }


{
	x: Int, y: Int -> x + y
}
원칙 :
 * 대괄호 내부에 있어야 한다
 * 인자에 괄호를 붙이지 않는다.
 * 화살표는 람다의 인자와 바디를 구분자이다.
