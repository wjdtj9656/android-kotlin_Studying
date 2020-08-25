<h1>chapter5 내용 정리</h1>

<h4>Intent</h4>
<p>Intent란 안드로이드에서 앱 구성 요소 간의 작업을 요청할 수 있는 메시지 객체</p>

<h4>Click 이벤트 리스너 등록방법 2가지 비교</h4>
<img width="418" alt="Listener" src="https://user-images.githubusercontent.com/24909625/90487722-d2116500-e175-11ea-992f-8f31912aa0b2.PNG">
<p>출처: 안드로이드 with Kotlin 앱 프로그래밍</p>
<pre>
<code>
package com.example.lotto

import android.content.Intent
import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.view.View
import kotlinx.android.synthetic.main.activity_test.*

class TestActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_test)

        button.setOnClickListener{
            val intent = Intent(this@TestActivity, MainActivity::class.java)
            startActivity(intent)
        }
        button2.setOnClickListener{
            val intent = Intent(this@TestActivity,ConstellationActivity::class.java)
            startActivity(intent)
        }
        button3.setOnClickListener{
            val intent = Intent(this@TestActivity,NameActivity::class.java)
            startActivity(intent)
        }
        button4.setOnClickListener {
            val intent = Intent(this@TestActivity,ResultActivity::class.java)
            startActivity(intent)
        }
    }

    //xml에서 참조할 수 있게 메소드를 정의하는 방법
/*
    fun goConstellation(view: View){
        val intent = Intent(this@TestActivity, ConstellationActivity::class.java)
        startActivity(intent)
    }
    */
</code>
</pre>

<h4>Toast 메시지 설정코드</h4>
<pre>
<code>
Toast.makeText(applicationContext,"띄우고 싶은 메시지", Toast.LENGTH_LONG).show()
</code>
</pre>

<h4>Activity 시작위해 Intent사용 2가지방법</h4>
<ul>
<li>명시적 호출(activity,service 이름알때)</li>
<li>암시적 호출(activity,service 이름 명확히 적지않고, 작업유형을 선언)</li>
</ul>

<h4>안드로이드 View</h4>
<p>UI의 구성 요소 중 가장 추상화된 개념으로서, 화면에 표시되는 가장 기본적인 요소</p>

<h4>View, Viewgroup</h4>
<p>레이아웃은 뷰그룹을 상속받은 실제 구현 클래스임, 버튼, 텍스트뷰, 에딧텍스트는 View를 상속받은 UI요소임</p>

<h4>AbsoluteLayout</h4>
<p>초창기 안드로이드에는 종종 쓰였지만, 이제는 거의 사용되지 않는 레이아웃
<br>
AbsoluteLayout은 포함된 모든 자식 뷰를 절대적인 좌표로 위치시킵니다.
<br>
화면의 해상도에 따라 view의 위치가 바뀌는 것이 문제.(멀티 해상도 지원에 부적합)</p>

<h4>LinearLayout</h4>
<p>위쪽부터 선형대로 view 배치, 복잡한 뷰도 구현 가능,가운데 배치 위해선 gravity속성 사용가능</p>

<h4>margin Vs padding</h4>
<p>margin 부모 뷰와의 거리로, 객체가 움직임<br>
padding은 뷰와 뷰안의 객체사이의 거리</p>

<h4>RelativeLayout</h4>
<p>view를 부모뷰, 또는 다른 view와의 상대적인 위치관계를 기반으로 배치함</p>
