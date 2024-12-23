### 문자열 리스트 개행 시간복잡도
- List에 대해 println() 함수로 개행을 할 때마다 시간복잡도가 O(n)
- List의 크기가 n일 때, 총 시간 복잡도는 O(n^2)
<br><br>
- List를 joinToString("\n") 함수로 문자열로 변환할 때 시간복잡도가 O(n)
- List의 크기가 n일 때, 이를 출력까지 하는 총 시간 복잡도는 O(n)
<br><br>
- StringBuilder를 사용하여 append("\n") 함수로 문자열을 개행할 때 시간복잡도가 O(n)
- List의 크기가 n일 때, 이를 출력까지 하는 총 시간 복잡도는 O(n)
<br><br>
- StringBuffer를 사용하여 append("\n") 함수로 문자열을 개행할 때 시간복잡도가 O(n)
- List의 크기가 n일 때, 이를 출력까지 하는 총 시간 복잡도는 O(n)

### StringBuffer vs StringBuilder
- 공통점 : 문자열을 추가할 때 사용
- 함수 : append(), insert(), delete(), replace(), reverse()
- 차이점 : StringBuffer는 동기 지원, StringBuilder는 비동기 지원
- 코틀린에서 StringBuilder를 사용하는 것이 더 효율적, 왜냐하면 동기화를 고려할 필요가 없기 때문

### 문자열의 특정 문자 제거
- 문자열이 전부 숫자로 이루어져 있을 때 특정 숫자만 제거하고 싶을 때
- replaceAll() 함수를 사용하여 특정 문자를 제거할 수 있음
  ```kotlin
    val str = "1234567890"
    val result = str.replace("3", "")
    println(result) // 124567890
    ```
- toCharArray().map{ it.toString().toInt() } 함수를 사용하여 문자열을 숫자로 변환할 수 있음
  ```kotlin
    val str = "1234567890"
    val result = str.toCharArray().map{ it.toString().toInt() }
    println(result) // [1, 2, 3, 4, 5, 6, 7, 8, 9, 0]
    ```
- replaceAll(), toCharArray().map{ it.toString().toInt() } 둘의 시간복잡도는 O(n)
