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
