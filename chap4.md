<h1>chapter4</h1>

<h4>java Vs kotlin(차이점 일부)</h4>
<img width="467" alt="일부" src="https://user-images.githubusercontent.com/24909625/89729032-d39fa680-da6c-11ea-9bc1-d156a759046a.PNG">
<p>출처 : 안드로이드 with kotlin 앱 프로그래밍</p>

<h4>Intent</h4>
<p>Activity 간 화면 전환을 위해서 Intent라는 클래스 사용함</p>
<p>ex)startActivity(Intent(this@MainActivity, BmiJavaActivity::class.java))</p>

<h4>bmi 계산 어플 (java.ver)</h4>
<pre>
<code>
package com.example.kotlinsample;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

public class BmiJavaActivity extends AppCompatActivity {
    EditText tallField;
    EditText weightField;
    TextView resultLabel;
    Button bmiButton;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.layout_view_binding);

        tallField = findViewById(R.id.tallField);
        weightField = findViewById(R.id.weightField);
        resultLabel =findViewById(R.id.resultLabel);
        bmiButton = findViewById(R.id.bmiButton);
        findViewById(R.id.bmiButton).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view){
                String tall = tallField.getText().toString();

                String weight = weightField.getText().toString();


                double bmi = Double.parseDouble(weight)/Math.pow(Double.parseDouble(tall)/100.0,2);

                resultLabel.setText(" 키:"+ tall + " 체중:" + weight+ " bmi 지수:"+bmi);
            }
        });
    }
}
</code>
</pre>
<p>layout_view_binding.xml레이아웃을 만든후, 그 레이아웃에 연결하였음.</p>
<p>안드로이드 에디트텍스트(EditText)는 TextView로부터 파생된 클래스로 TextView는 단순히 Text를 보여주는 역할을 한다면 EditText는 Text를 입력 및 수정까지 가능한 뷰(View) 위젯입니다.</p>
 

<h4>bmi 계산 어플 (kotlin.ver)</h4>
<pre>
<code>
package com.example.kotlinsample

import android.os.Bundle
import androidx.appcompat.app.AppCompatActivity
import kotlinx.android.synthetic.main.layout_view_binding.*

class BmiKotlinActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        setContentView(R.layout.layout_view_binding)

        bmiButton.setOnClickListener{

            val tall = tallField.text.toString().toDouble()

            val weight = weightField.text.toString().toDouble()

            val bmi = weight / Math.pow(tall / 100, 2.0)

            resultLabel.text = "키: ${tallField.text}, 체중 : ${weightField.text}, BMI: $bmi"
        }
    }
}
</code>
</pre>
<p>코틀린과 자바의 차이점 중 하나는 view바인딩 작업이 없어져 코드가 간결 해 졌습니다.</p>

<h4>코틀린의 변수</h4>
<p>var clickCount = 0 은 var clickCount:Int = 0 과 같음.</p>
<p>코틀린은 컴파일 시점에 타입을 결정하는 정적타입 언어임. (타입추론)</p>

<h4>코틀린 반복문 예시</h4>
<pre>
<code>
for(item in collection){
	println(item)
}
////////////////////////
for(i in 0..100){
	println(i)
}
</code>
</pre>

<h4>java Vs Kotlin 함수</h4>
<pre>
<code>
fun function(age:int): int {
   return 0
}
</code>
</pre>
<p>코틀린에서는 변수이름:타입 으로 인자를 쓰고, 반환값이 없을때는 자바와는 다르게(void)
아무것도 쓰지 않아도 된다.(Unit) 반환값이 있을때는 :타입으로 명시</p>

<h4>최상위 함수</h4>
<p>자바는 무조건 함수가 클래스 내부에 위치해야 하지만 코틀린은 아니다. 클래스 외부에 있는 함수를 최상위 함수라 함.</p>

<h4>같은이름의 패키지 3개</h4>
<p>test인것은 안드로이트 기능과 상관없는 java, kotlin 코드를 테스트, 
andoridTest는 안드로이드 환경과 연관된 코드를 테스트 합니다.</p>

<h4>kotlin vs java (getter, setter)</h4>
<pre>
<code>
package com.example.kotlinsample;

public class PersonJava {
    private int age;

    private final String name;

    public PersonJava(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }
    public void setAge(int age){
        this.age=age;
    }
    public String getName() {
        return name;
    }
}
</code>
</pre>
<p>Person.java의 파일내용</p>

<pre>
<code>
package com.example.kotlinsample

class PersonKotlin {
    var age:Int = 0
    val name:String

    constructor(name:String){
        this.name = name
    }

}
</code>
</pre>
<p>PersonKotlin.kt의 파일내용</p>
<p>코틀린의 경우 var로 선언할경우 getter와 setter를, val로 선언할경우 getter를
자동 생성하여 따로 만들어줄 필요가 없어서 간결하다</p>


<h4>프로퍼티 vs 필드</h4>
<p>프로퍼티(property)는 필드(field)와 getter or setter의 조합을 의미함 
따라서 코틀린은 getter와 setter을 자동 생성하니 자동으로 프로퍼티가됨.</p>