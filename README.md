# Sparta_Coding_1
[국비교육] 스파르타코딩클럽 안드로이드 앱 개발자 과정 1회차 학습 정리
## 튜터
![image](https://github.com/chihyeonwon/Sparta_Coding_1/assets/58906858/c8e96a92-09cd-4262-9ac8-64b777cd6546)

## 24.05.28 
![image](https://github.com/chihyeonwon/Sparta_Coding_1/assets/58906858/06817e66-de44-4f5f-9e28-c41538743f1d)
![image](https://github.com/chihyeonwon/Sparta_Coding_1/assets/58906858/9fea1a5b-6dc3-4c61-83d6-2e56dff70602)
![image](https://github.com/chihyeonwon/Sparta_Coding_1/assets/58906858/001b9ca5-b11a-416e-aeb5-7ba9b4f537ae)
```
AVD Pixel 7 API 34
```
[코틀린 플레이 그라운드](https://developer.android.com/training/kotlinplayground?hl=ko)
- **데이터 형 (Data Types)**
    - **정의**: 여러 데이터를 구조화하는 데 사용되는 자료형
    - **종류**:
        - **`List`**: 목록 형태의 컬렉션을 제공
        - **`Map`**: 키와 값의 쌍으로 데이터를 저장
        - **`Set`**: 중복 없는 유일한 요소들의 모음
```kotlin
val todoList: List<String> = listOf("Study Kotlin", "Develop App", "Test Features")
for (todo in todoList) {
    println(todo)
}

val userProfiles: Map<String, String> = mapOf("username" to "Sparta", "email" to "sparta@example.com")
println("Email of the user: ${userProfiles["email"]}")

val uniqueNumbers: Set<Int> = setOf(1, 2, 3, 4, 3, 2)
for (number in uniqueNumbers) {
    println(number)
}
```

Collection : 데이터의 그룹을 저장하고 관리하는 자료 구조 (List, Set, Map)      
map : 컬렉션의 각 요소에 대해 지정된 변환을 수행하고, 결과를 새로운 리스트로 반환        
   
```kotlin   
val numbers = listOf(1, 2, 3, 4, 5)
val squaredNumbers = numbers.map { it * it }
println(squaredNumbers) // [1, 4, 9, 16, 25]
```
filter : 주어진 조건에 맞는 요소들만 선택하여 새로운 컬렉션을 만듦
```kotlin
val numbers = listOf(1, 2, 3, 4, 5)
val evenNumbers = numbers.filter { it % 2 == 0 }
println(evenNumbers) // [2, 4]
```
☑️ 함수  
특정 작업을 수행하는 코드 블록    
동일한 코드를 반복하는 대신 함수에 반복되는 코드를 함수로 묶어 호출할 수 있음    
함수의 선언 : fun 키워드 뒤에 함수 이름이 오도록 사용    
입력 파라미터와 반환 타입(Return)을 가질 수 있음       
```
fun greet(name: String): String {
    return "Hello, $name!"
}

val message = greet("Android Developer")
println(message) // "Hello, Android Developer!"
```
람다 함수 : 이름 없이 사용되는 함수로, 간단한 연산이나 콜 백에 유용
```kotlin
button.setOnClickListener { 
    println("Button clicked!") 
}
```
클래스   
객체 지향 프로그래밍의 핵심 요소로, 데이터와 그 데이터를 처리하는 메서드를 하나로 묶은 것    
class 키워드로 정의되며, 프로퍼티와 메서드 함수를 가짐     
```kotlin
class User(val name: String, val age: Int) {
    fun greet() {
        println("Hello, my name is $name.")
    }
}
val user = User("Sparta", 25)
user.greet() // "Hello, my name is Sparta."
```​
데이터 클래스 : data 키워드를 사용하여 data에 초점을 맞춘 클래스를 만들 수 있음
```kotlin
data class Book(val title: String, val author: String)

val book = Book("Kotlin for Android", "John Doe")
println(book) // Book(title=Kotlin for Android, author=John Doe)
```
☑️ 상속
하나의 클래스가 다른 클래스의 속성과 메서드를 확장하거나 재정의
```kotlin
open class Mom(val name: String) {
    fun momCard() {
        println("$name buy car")
    }
}

class Son(name: String, val age: String) : Mom(name) {
    fun myCard() {
        println("$name buy book")
    }
}

val me = Son("Isup", "18")
me.momCard() // "Sedan buy car"
me.myCard() // "Sedan buy book"
​```
자식 클래스와 부모 클래스 사이에 : 연산자를 사용하여 상속을 표시

class MainActivity : Activity()
```

```
부모 클래스에서 함수를 참조하려면 다음 예와 같이 super 키워드를 사용    

override fun onViewCreated(view: View, savedInstanceState: Bundle?) {
    super.onViewCreated(view, savedInstanceState)
}
```
## 1주차 새로이 알게된 것
```
constraint 레이아웃에서 width는 0을 자주 쓴다.
constraint 레이아웃을 자주 쓰는 추세, bias 비율을 써서 비율 정할 수 있음
텍스트는 sp, 이미지는 dp를 자주 씀
constraintVertical_bias Attribute
constraintHorizontal_bias = "0.2" // 0 ~ 1 사이의 값으로 조율
```
