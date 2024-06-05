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

# 앱 개발의 숙련 과정: 고급 UI 및 기능 - 3주차

**[수업 목표]**

- Fragment의 기본 개념과 다양한 화면 구현을 위한 사용법을 이해할 수 있다.
- ViewPager를 사용하여 Fragment 간의 페이징을 구현한다.
- RecyclerView를 사용하여 효율적인 데이터 리스트 표시 방법을 알 수 있다.
- 동적 문자열 처리, HTML 태그 활용 등을 통해 다양한 UI 요구사항을 구현할 수 있다.
- Fragment와 RecyclerView를 활용하여 실제 날씨 앱을 구현할 수 있다.

![image](https://github.com/chihyeonwon/Sparta_Coding_1/assets/58906858/df8830a9-c73f-4d29-a368-d118b34a9847)

- 단어 의미
    - ‘조각’, ‘부분’, 작은 조각이나 부분적인 요소를 나타내는 말,
    - 전체에서 일부를 이루는 작은 부분
    - 안드로이드에서도 동일한 의미로 사용됨.
- 사용자 인터페이스(UI)의 일부를 나타내는 재 사용 가능한 클래스
- **목적**
    - 복잡한 UI의 모듈화를 통한 유연한 관리
    - Activity 하나에 많은 기능을 넣으면 너무 거대해질 수 있어요. 이를 기능별 Fragment로 모듈화하여 유연하게 관리할 수 있어요
- **비유**
    - Activity : **액자 vs** Fragment : **그림들**
- **필요한 이유**
    - **재사용성** : 다양한 Activity에서 재사용 가능
    - **모듈성** : 복잡한 UI를 여러 개의 작은 단위로 나누어 효율적으로 관리
    - **유연한 사용자 인터페이스**: 하나의 Activity 내에서 여러 Fragment를 교체하거나 함께 표시함으로써 다양한 화면 크기와 방향에 맞는 유연한 사용자 인터페이스를 제공
 
![image](https://github.com/chihyeonwon/Sparta_Coding_1/assets/58906858/5314d936-02b9-42a0-abcb-b76f4102ce50)

- **독립적인 라이프 사이클**: Fragment는 자체 라이프 사이클을 가지고 있어서, Activity의 라이프 사이클과 독립적으로 관리. 앱의 안정성을 높여줌
- **성능 향상**: Fragment는 필요할 때만 로드되고 제거될 수 있어, 메모리 사용과 앱의 전반적인 성능을 향상시킴
- **라이프 사이클 :** Activity와는 다른 Fragment 자체적인 Lifecycle을 가지고 있음

![image](https://github.com/chihyeonwon/Sparta_Coding_1/assets/58906858/6dfa14f6-1e56-492c-b5e7-c3ed5d4a3bc6)

1. **Fragment의 생성**
    1. **`Fragment`**를 상속받으며, **`onCreateView`** 메서드를 오버라이드하여 Fragment의 레이아웃을 연결함.
  
```kotlin
class FirstFragment : Fragment() {
    private var _binding: FragmentFirstBinding? = null
    private val binding get() = _binding!!

    override fun onCreateView(
        inflater: LayoutInflater, container: ViewGroup?,
        savedInstanceState: Bundle?
    ): View? {
        _binding = FragmentFirstBinding.inflate(inflater, container, false)
        return binding.root
    }

    override fun onViewCreated(view: View, savedInstanceState: Bundle?) {
        super.onViewCreated(view, savedInstanceState)
        binding.textviewFirst.text = "Sparta First Fragment"
        binding.buttonFirst.setOnClickListener {
        }
    }

    override fun onDestroyView() {
        super.onDestroyView()
        _binding = null
    }
}
```

2. **레이아웃 XML 파일 생성**
    1. Fragment의 UI를 정의하는 XML 레이아웃 파일을 생성. **`res/layout`** 폴더에 위치함
  
```kotlin
<!-- fragment_first.xml -->
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="16dp"
    tools:context=".FirstFragment">

    <Button
        android:id="@+id/button_first"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="@string/next"
        app:layout_constraintBottom_toTopOf="@id/textview_first"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <TextView
        android:id="@+id/textview_first"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:text="@string/lorem_ipsum"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@id/button_first" />
</androidx.constraintlayout.widget.ConstraintLayout>
```

3. **Activity 레이아웃에 FragmentContainerView 추가**
    1. **`FragmentContainerView`**는 Activity의 레이아웃 XML 파일에 추가
    2. **`android:name`** 속성에는 Fragment의 전체 클래스 이름을 지정
  
```kotlin
<!-- activity_main.xml -->
<androidx.fragment.app.FragmentContainerView
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/fragment_container"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:name="com.yourpackage.FirstFragment" />
```

4. **Activity에서 동적으로 추가도 가능**
    1. xml에서 **`android:name`**를 사용하지 않을 경우엔 코드에서 동적으로 추가 또는 교체
  
```kotlin
class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        // Fragment를 동적으로 추가하는 코드
        if (savedInstanceState == null) {
            supportFragmentManager.beginTransaction()
                .replace(R.id.fragment_container, FirstFragment())
                .commit()
        }
    }
}
```




