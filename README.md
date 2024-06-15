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
- **Fragment에 Paging 효과 적용하기**
    - Fragment Paging을 위해 **ViewPager2**와 **FragmentStateAdapter**를 활용하여 구현
    - 인기 있는 Fragment 관리 기법 중 하나
    - ☑️ **ViewPager2와 FragmentStateAdapter 사용 가이드**


1. ViewPager2 레이아웃 XML 파일에 추가   
```kotlin
<!-- activity_main.xml -->
<androidx.viewpager2.widget.ViewPager2
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/viewPager"
    android:layout_width="match_parent"
    android:layout_height="match_parent" />
```
2. FragmentStateAdapter 사용
    1. **`FragmentStateAdapter`**를 상속받는 어댑터를 생성하여 ViewPager2에 연결
```kotlin
class WeatherFragmentStateAdapter(activity: AppCompatActivity) : FragmentStateAdapter(activity) {
    override fun getItemCount() = 2 //추가 하고 싶은 Fragment 갯수

    override fun createFragment(position: Int): Fragment {
        return when (position) {
            0 -> FirstFragment() // 각 Position 별 Fragment 연결
            else -> SecondFragment()
        }
    }
}
```
3. ViewPager2에 adapter 연결
```kotlin
class MainActivity : AppCompatActivity() {
    private lateinit var binding: ActivityMainBinding

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        binding = ActivityMainBinding.inflate(layoutInflater)
        with(binding) {
            setContentView(root)
            // viewPager에 FragmentStateAdapter를 상속해서 만든 Adapter 연결
            viewPager.adapter = WeatherFragmentStateAdapter(this@MainActivity)
        }
    }
}
```
4. [선택] @paging시 Indicator 달기
```kotlin
// build.gradle
dependencies {
    implementation("me.relex:circleindicator:2.1.6")
```
```kotlin
<!-- activity_main.xml -->
<me.relex.circleindicator.CircleIndicator3
        android:id="@+id/indicator"
        android:layout_width="0dp"
        android:layout_height="20dp"
        android:layout_marginBottom="23dp"
        app:ci_drawable="@drawable/indicator_black_circle"
        app:ci_drawable_unselected="@drawable/indicator_gray_circle"
        app:ci_height="8dp"
        app:ci_margin="10dp"
        app:ci_width="8dp"
        app:layout_constraintBottom_toBottomOf="@+id/view_pager"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent" />
```
```kotlin
class MainActivity : AppCompatActivity() {
    private lateinit var binding: ActivityMainBinding

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        binding = ActivityMainBinding.inflate(layoutInflater)
        with(binding) {
            setContentView(root)
            val adapter = WeatherFragmentStateAdapter(this@MainActivity)
            viewPager.adapter = adapter
            indicator.setViewPager(viewPager)
            adapter.registerAdapterDataObserver(indicator.adapterDataObserver)
        }
```
03. Data 연동 : RecyclerView 활용하기

![image](https://github.com/chihyeonwon/Sparta_Coding_1/assets/58906858/36b97b23-9a05-4253-946b-df9867e54fb8)

- 리스트 형태의 Data를 표시하는 데 사용되는 위젯 중 가장 **신제품**
- 많은 아이템을 효율적으로 관리하고 보여주는 역할
- 리스트를 스크롤 할 때, 위에 있던 아이템은 **재활용** 돼서 아래로 이동하여 **재사용** 함.

- ☑️ **RecyclerView 준비물**
    - **LayoutManager**
        - **`LayoutManager`**는 **`RecyclerView`** 내부의 아이템들이 어떻게 배치될지를 결정
        - 기본 제공되는 **`LayoutManager`**로는 **`LinearLayoutManager`**, **`GridLayoutManager`**, **`StaggeredGridLayoutManager`** 등

![image](https://github.com/chihyeonwon/Sparta_Coding_1/assets/58906858/a3e4bd3d-47de-45da-a7c5-fb1406c21802)
```kotlin
recyclerView.layoutManager = LinearLayoutManager(this) // 수직 리스트를 위한 LinearLayoutManager
// 또는
recyclerView.layoutManager = GridLayoutManager(this, 2) // 2열 그리드를 위한 GridLayoutManager
```

- **RecyclerView.Adapter**
    - **`RecyclerView`**에 표시될 데이터와 해당 데이터를 보여줄 **`ViewHolder`**를 연결
    - **`Adapter`**는 데이터 셋의 변경 사항을 **`RecyclerView`**에 알리고, 데이터를 기반으로 뷰를 생성
    - 각 리스트 Item 내부 layout도 만들어 주세요. **item_layout.xml**
 
```kotlin
class WeatherItemListAdapter :
    ListAdapter<WeatherData, WeatherItemListAdapter.ItemViewHolder>(object :
        DiffUtil.ItemCallback<WeatherData>() {
        override fun areItemsTheSame(oldItem: WeatherData, newItem: WeatherData): Boolean {
            return oldItem.time == newItem.time
        }

        override fun areContentsTheSame(oldItem: WeatherData, newItem: WeatherData): Boolean {
            return oldItem == newItem
        }
    }) {

    override fun onCreateViewHolder(parent: ViewGroup, viewType: Int): ItemViewHolder {
        val inflater = LayoutInflater.from(parent.context)
        val binding = ItemLayoutBinding.inflate(inflater, parent, false)
        return ItemViewHolder(binding)
    }

    override fun onBindViewHolder(holder: ItemViewHolder, position: Int) {
        holder.bind(getItem(position))
    }
}
```
- **ViewHolder**
    - **`RecyclerView`**의 **개별 아이템 뷰**를 위한 객체입니다.
    - 아이템 뷰의 모든 서브 뷰를 담고 있어 재사용과 성능 최적화에 도움을 줍니다.

```kotlin
inner class ItemViewHolder(binding: ItemLayoutBinding) :
        RecyclerView.ViewHolder(binding.root) {
        val timeView = binding.timeTv
        private val temperatureView = binding.tempTv
        private val weatherStatusView = binding.weatherIv
        private val rainStatusView = binding.rainIv
        fun bind(item: WeatherData?) {
            val res = timeView.context.resources
            timeView.text = item?.time?.toTimeFormat()
            temperatureView.text = res.getString(R.string.temp_text, item?.temperature)
            weatherStatusView.setImageResource(item?.skyStatus?.icon ?: R.drawable.ic_sunny)
            rainStatusView.setImageResource(item?.rainState?.icon ?: R.drawable.ic_sunny)
        }

        private fun String.toTimeFormat(): String {
            return if (this.length == 4) "${this.substring(0, 2)}:${this.substring(2)}" else this
        }
    }
```

## **04. 다양한 UI 요구 사항의 처리**
✔️  다양한 UI 요구 사항을 구현해야 할 경우 어떤 방법들이 있을지 알아보아요.

- 다양한 날씨 상태 별로 날씨 상태 문구와 이미지를 어떻게 표현할 수 있을까요?
    - **Enum class**란?
        - 열거형을 나타내는 특별한 클래스 유형
        - Kotlin에서는 **`enum class`** 키워드를 사용하여 정의
        - 고정된 상수들의 집합
    - Enum class의 활용
        - **`SkyStatus`**는 하늘 상태를 나타내며, **`value`**, **`text`**, **`icon`**, **`colorIcon`** 네 개의 속성을 가짐
        - 상태는 **`GOOD`**, **`CLOUDY`**, **`BAD`**로 구분
        - 날씨의 상태 값이 왔을 때 UI 요구 사항 별로 날씨 문구나, 흑백 아이콘, 컬러 아이콘 들을 자유롭게 활용 가능

```kotlin
enum class SkyStatus(val value: Int, val text: String, val icon: Int, val colorIcon: Int) {
    GOOD(1, "맑음", R.drawable.ic_sunny, R.drawable.ic_color_sunny),
    CLOUDY(3, "구름 많음", R.drawable.ic_sun_clouny, R.drawable.ic_color_sunny_cloudy),
    BAD(4, "흐림", R.drawable.ic_cloudy_2, R.drawable.ic_color_cloudy)
}

mainWeatherText.text = data.skyStatus.text
weatherStatusIv.setImageResource(data.skyStatus.colorIcon)
```

- **문자열 서식 지정**
    - 문자열의 서식을 지정해야 할 경우, 문자열 리소스에 서식 인수를 추가하여 지정할 수 있음
    - `%1$s`는 문자열이고 `%2$d`는 정수
 
```kotlin
<string name="welcome_messages">Hello, %1$s! You have %2$d new messages.</string>

var text = getString(R.string.welcome_messages, username, mailCount)

<string name="rain_percent">강수 확률 %1$s%%</string>

mainRainPercentTv.text = getString(R.string.rain_percent, data.rainPercent)
```

- **HTML 마크업을 사용하여 스타일 지정**
    - HTML 마크업을 사용하여 문자열에 스타일을 추가할 수 있음
    - 지원되는 HTML 요소
        - 굵게: <b>
        - 기울임 꼴: <i>, <cite>, <dfn>, <em>
        - 텍스트 25% 확대: <big>
        - 텍스트 20% 축소: <small>

```kotlin
<string name="welcome_messages">Hello, %1$s! You have &lt;b>%2$d new messages&lt;/b>.</string>

val text: String = getString(R.string.welcome_messages, username, mailCount)
val styledText: Spanned = Html.fromHtml(text, FROM_HTML_MODE_LEGACY)
```

## 이젠 나도 전문가 : 비동기 처리와  아키텍처 - 4주차
**[수업 목표]**

- 기상청 Open API 연결을 통해 실시간 날씨 데이터를 받아오는 방식을 알 수 있다.
- 네트워크 요청 및 데이터 처리 과정에서 발생하는 다양한 예외 상황을 이해하고 처리할 수 있다.
- 코루틴을 사용한 비동기 프로그래밍 기법을 이해하고, 날씨 앱에서 비동기적으로 데이터를 처리할 수 있다.
- MVVM 아키텍처 패턴과 LiveData를 활용하여 UI와 데이터 간의 반응형 연결을 구현할 수 있다.

## **01. 4주차 오늘 배울 것**

<aside>
✔️ **실제 날씨 Data를 코루틴과 MVVM 패턴을 적용하여 연결해 보기!**

</aside>
- 이번 4차시 목표는요?
    
☑️ 이번엔 WeatherApp에 **영혼**을 불어 넣어보아요.
    
- 3주 차에서 배운 WeatherApp은 가짜 날씨 정보로 이루어져 있어요.
- 실제 기상청 서버를 이용해 날씨를 지역 별로 보여줄 수 있을까요?

### ⁉️  기상청 정보에서 날씨 정보를 가지고 오려면 어떻게 해야 하나요?

- 공공 데이터 포탈이라고 들어보셨나요?
- 정부 및 공공 기관이 보유한 다양한 데이터를 일반인, 개발자, 기업 등에게 공개하는 곳으로, 날씨, 교통, 보건, 교육 등 다양한 분야의 데이터를 제공하고 있답니다!
- 기존에 배웠던 Retrofit 코드를 활용하면서 MVVM 아키텍처를 적용하여 안정적인 WeatherApp을 만들어 보아요!

## **02.** Open API 연결과 예외 처리: 안정성 확보

<aside>
✔️ 기상청 API 문서를 참고하여 Retrofit을 이용해 서버에 연결하고, 예외 상황에 대한 처리를 추가해 보아요.
</aside>

## 다양한 서비스 구현 및 앱 출시 - 5주차
     
- 공공 데이터 포탈의 기능과 사용 방법을 이해한다.
- 다양한 서비스 중에서 적합한 서비스를 선택하고, 효과적인 화면 구성 방법을 이해한다.
- 구글 플레이 콘솔의 기능을 이해하고, 플레이 스토어에 앱을 출시하는 절차를 알 수 있다.
- 공공 서비스 포탈을 활용해 '약방' 앱을 구현하고 플레이 스토어에 배포하는 과정을 알 수 있다.

## 사업을 해도 전혀 데미지없는 사업. 
행정안전부가 지난 7월, 올해 국가중점데이터 개방사업 통합 착수보고회를 개최하고     
‘2023년 국가중점데이터 개방사업’을 본격 추진한다고 밝혔습니다.    
정부가 가치가 높은 국가중점데이터를 일부 개방함으로써 이를 활용한 서비스 강화로 국민 편의가 높아질 것이라고 하는데요.    

![image](https://github.com/chihyeonwon/Sparta_Coding/assets/58906858/bd354084-957d-4441-9318-3901ccb76698)
![image](https://github.com/chihyeonwon/Sparta_Coding/assets/58906858/f03060f8-9972-4b31-858e-f926179eb2cd)

앞으로도 가능성이 무궁무진한 무료 데이터 포탈 서비스죠?      
24년엔 법과, 일자리, 과학, 부동산, 먹거리, 여가 등 다양한 분야에서   
다양한 데이터가 새롭게 제공될 예정이니 한발 빠르게 도전해 보아요!   

![image](https://github.com/chihyeonwon/Sparta_Coding/assets/58906858/be648354-f5d1-4b40-bb4a-79a12089763f)
![image](https://github.com/chihyeonwon/Sparta_Coding/assets/58906858/9597a7ec-34ca-416a-8b52-e028f67008bc)
![image](https://github.com/chihyeonwon/Sparta_Coding/assets/58906858/6a864b7b-e699-4788-a498-19b2e9b1972e)
![image](https://github.com/chihyeonwon/Sparta_Coding/assets/58906858/d6bc9cdb-6620-4d4b-ae9d-90ea610db5b5)

- **서비스에 따른 효과적인 화면 구성을 고민해 보기**
    - 앱이 많은 Data를 제공할 경우 효과적으로 보여줄 수 있는 UI 구성도 무척 중요해요.
    - 많은 앱 중에  내 앱을 빛나게 해줄 디자인이 추가되면 더 좋겠죠?
    
    1. **서비스 목적과 타겟 사용자 정의**: 앱의 목적 및, 대상을 명확히 이해하는 것이 중요해요.  앱이 제공해야 할 핵심 기능과 사용자의 편의성에 맞게 화면이 구성되어야 해요
    2. **사용자 경험(UX) 설계 원칙 적용**: 쉽고 직관적으로 사용할 수 있도록 하는 것이 중요해요. 이를 위해 간결성, 일관성, 접근성과 같은 기본적인 UX 설계 원칙을 적용해야 해요.
    3. **정보 구조 설계**: 사용자가 앱 내에서 필요한 정보를 쉽게 찾을 수 있도록, 효과적인 정보 구조를 설계하는 것이 중요해요. 명확한 메뉴 구조와 직관적인 탐색 경로를 제공해야 해요.
    4. **프로토타이핑과 테스트**: 실제 사용자의 반응과 피드백을 얻기 위해 초기 디자인을 프로토타입으로 구현하고 테스트하는 것이 중요해요. 이 과정을 통해 문제점을 발견하고 개선할 수 있어요





