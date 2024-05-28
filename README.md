# Sparta_Coding_1
[국비교육] 스파르타코딩클럽 안드로이드 앱 개발자 과정 1회차 학습 정리
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
​```
