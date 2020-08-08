<h1>chapter 3</h3>
<table borer="1">
 <tr>
<td>코드</td>
<td>코드는 프로그램이 어떻게 동작하는지를 기술해 놓은 파일임. 언어에 따라 kt,java,cpp,c 등등이 있음.</td>
</tr>
<tr> 
 <td>리소스</td>
<td>리소스는 프로그램 실행과 관계된 정적 데이터임. 실행 환경이나 조건과 같은 변수에 의해 결과가 변화지 않고 고정되어 있는 데이터 <br>ex)이미지 </td>
</tr>
<tr> 
<td>설정 및 환경정보</td>
<td> 프로젝트가 가져야 하는 환경 정보의 모음. 프로젝트의 소스크드는 어느 경로에 있는지 </td>
</tr>
</table>
<h4>레이아웃 편집</h4>
<ul>
<li>위지윅(WYSIWYG)(What You See Is What You Get)방식인 design텝
<li>XML 코드 수정을 할 수 있는 Text텝
</ul>

<hr>
<h4>Gradle scripts</h4>
<p>어플리케이션이 어떻게 구성되는지 빌드 정보, 환경설정 정보를 가지고있음</p>
<p>Gradle은 빌드 시스템임. Gradle은 크게 android, dependencies</p>
<p>dependencies는 어플리케이션이 작동하기 위한 라이브러리

<h4>안드로이드의 진입점(entry point)</h4>
<p>보통 언어는 main이 entry point지만, 안드로이드에선 단일 진입점 대신 4대 컴포넌트를
가지고있음. activity, service, broadcastReceiver, content Provider</p>
<img width="424" alt="진입점" src="https://user-images.githubusercontent.com/24909625/89642320-91e8f180-d8ee-11ea-93cf-fecdc01367af.PNG">
<p>출처: 안드로이드 with Kotlin 앱 프로그래밍 가이드</p>

<h4>런처란</h4>
<p>런처는 안드로이드 홈화면을 담당하는 특수한 어플리케이션.</p>
<p>안드로이드의 모든 어플은 홈키를 누르면 홈화면으로 돌아갑니다. 반대로 런처는
홈 화면에서 다른 어플을 실행하는 역할을 함.</p>

<h4>캡슐화의 주된 목적</h4>
<ol>
<li>내부의 복잡한 로직을 숨겨 외부에서 쉽게 사용하기 위해
<li>내부의 주요 속성을 보호
</ol>

<h4>오버로딩 vs 오버라이딩</h4>
<p>오버로딩: 같은기능을 하지만 입력 받는 자료형이 다를때</p>
<p>오버라이딩: 상속에서 부모가 제공한 기능을 바꿔서 쓰는 것</p>

<h4>프레임워크 vs 라이브러리</h4>
<p>라이브러리: 내가 메소드를 불러서 사용</p>
<p>프레임워크: 나의 메소드가 불려서 사용됨</p>