###### 여기서 잠깐!
###### 모든 예제는  jsfiddle 로 구성 되었습니다.
###### 직접 강좌를 들으시고 자신만의 방식대로 소스를 직접 수정해보고 추가해보는 열정적인 당신이 되어주세요! 아래에 jsfiddle 간단한 사용 방법을 알려 드리겠습니다.

[jsfiddle 바로가기](https://jsfiddle.net) 을 접속해보면 아래 이미지로 접속이 되실거에요
![](image/img_html1_3.png)

HTML 이라고 써있는 부분에 HTML 태그를 입력하고 CSS도 입혀보실것이 있다면 넣으시고 마찬가지로 javascript 도 가능하답니다.

상단 메뉴에서 Run 을 누르면 아래 이미지처럼  Result 부분에 작성하신 결과물을 확인해 보실수 있어요.

![](image/img_html1_4.png)

강좌는 jsfiddle로 연동되게 예제를 보여드릴 예정이오니 직접 이것저것 만져보면서 강좌를 들으시면 빠른 성장을 하실것이라 생각되어요. 

---

#필수 Tag 16선

[*1*] **a**   

a 태그는 인라인 태그로서 텍스트나 이미지에 링크를 연결해 줄때 필요해요!

기본속성은 href , target 으로 구성됩니다.

``` html
<a href="http://www.naver.com" target="_blank">네이버 Go! Go!</a>
```

target="_blank" 속성을 넣어주면 링크를 눌렀을 경우 링크가 새창으로 이동되요.

``` html
<a href="http://www.naver.com" target="_self">네이버 Go! Go!</a>
```

``` html
<a href="http://www.naver.com">네이버 Go! Go!</a>
```

target="_self" 속성은 현재페이지에서 링크로 이동되요. 하지만 _self 속성은 기본속성이니 적지 않으셔도 됩니다.

[예제 확인하기](https://jsfiddle.net/leetaesu/ynpa6jgj/1/)

######그외에도 2개의 부분이 더있는데 이부분은 특별한 경우말고는 사용되지 않아요. 그래도 호기심 가득한 분이시라면 테스트 해보시는 것 을 추천합니다.
######_parent : 부모창에 해당 링크를 열어요
######_top : 화면이 여러 프레임으로 이루어져있는 경우 모든 프레임을 지우고 전체 화면에 열어요

---

[*2*] **br**   

br 태그는 영역을 줄바꿈 하는 역할을 담당합니다.

br 태그는 단일 태그이기 때문에 <br /> 슬러시로 마무리를 지어줍니다.
```ex)삼치와 마요는 투닥투닥 대지만, 아플때는 서로를 아끼는 귀여운 고양이들이랍니다.``` 흔히 이런 텍스트가 있는경우 강제 개행이 필요할 때가 있겠죠? 이럴때는 
```ex)삼치와 마요는 투닥투닥 대지만,<br /> 아플때는 서로를 아끼는 귀여운 고양이들이랍니다.``` 해주면 투닥투닥 대지만, 에서 강제개행이 이루어 집니다. 텍스트뿐만 아니라 ```<br /><br /><br />``` 이런식으로 여러번을 작성햇을 경우 한줄 개행이아니라 3줄 개행이라 단락의 공간이 생깁니다. 여백을 주고 싶을때는 나중에 배울 css속성의 padding , margin 속성을 이용하도록 해요

[예제 확인하기](https://jsfiddle.net/leetaesu/ynpa6jgj/2/)

---

[*3*] **link**

우리는 html과 css와 javascript로 작업을 진행하죠 그럼 html 파일에다가 css와 js를 적으면 index.html 파일의 크기가 너무많아지고 관리하기도 힘들어 지겠죠? 그런경우에는 css와 js 파일만을 작성할 파일을 작성한후 link 태그를 이용하도록 하죠

```html
 <link rel="stylesheet" href="test.css" />
 <script type="text/javascript" src="test.js"></script>
```

위에 보듯이 type 과 src 경로를 맞추어 주어서 link태그로 파일을 관리해 봅시다.

---

[*4*] **input**

input 태그는 폼안에 기본적인 컨트롤을 생성하죠, 
input 태그안에 여러가지 속성을 제어할 수 있는데,
type,name,value,size,width,height,max,maxlength,min 속성을 제어할 수 있습니다.

**type** 속성은 필수 속성으로써

* text : 텍스트 입력을 받기위한 필드로써 그대로 출력된다.
* password : 비밀번호를 받기위한 필드로써 ●●● 식으로 출력된다.
* checkbox : 복수 선택이 가능한 체크박스 생성 
* radio : 체크박스와는 달리 단일 선택만 가능한 박스 생성  
* submit : 송신버튼 생성  
* reset : 리셋버튼 생성  
* button : 범용버튼 생성.  
* image : 이미지버튼 생성.  
* file : 송신파일 선택필드 생성  
* hidden : 필드를 html상에는 있지만 눈으로는 보여지지 않는다.

**name** 속성   
name="이름"(필수 속성) : 컨트롤의 이름 지정. type의 속성이 checkbox나 radio일 경우 name속성이 같은 값으로 지정되면 하나의 그룹으로 취급한다.

**value** 속성  
value="값" : 초기값을 미리 정할 수 있다.

**size** 속성   
size="폭" : 컨트롤의 폭을 지정. type속성이 text이거나 password일 경우 문자수를 지정하고 그외의 경우에는 가로폭의 픽셀값을 지정한다.

**width , height** 속성  
요소의 가로와 세로 사이즈를 조정할 수 있지만, css로 처리하기 때문에 자주 사용되지 않는다.

**max , min** 속성 
max , min는 input 요소에 허용하는 값의 최소 최대값을 지정하지만 자주 사용되지 않는다. 
max,  : input요소에 허용하는 값의 최대값을 지정하지만 마찬가지로 사용되지 않는다.

**maxlength** 속성  
maxlength : type속성이 text이거나 password 일때 최대 글자수를 제한할 수 있게 해준다.

###### 아래 이미지를 보시면 자주보이는 naver의 로그인 하는 창입니다. 

![](image/img_html1_5.png)

###### 아이디라고 표시된 곳이 type 속성이 text로 표시되어있는 상태이고 비밀번호라고 되있는곳은 type속성이 password 라고 기재가 되어있습니다. 이부분에 아이디와 비밀번호를 입력하게되면 아래 이미지처럼 적용됩니다.

![](image/img_html1_6.png)  

예제에서는 input의 기본적인 예제를 담아 보았습니다.

[예제 확인하기](https://jsfiddle.net/leetaesu/ynpa6jgj/3/)

---

[*5*] **textarea**

textarea는 사용자의 내용을 입력받을 수 있는 필드에요. 댓글입력,문의내용 같은 곳에서 볼 수 있죠, textarea는 input과 마찬가지로 많은 속성들을 가지고 있어요.

속성의 종류에는 

* autofocus : 페이지가 새로고침이 되면 포커스가 자동으로 가게 해줍니다.
* cols,rows : 표시될 폭을 문자수로 지정하는데 css 처리하는것이 좋습니다.
* disabled : 모든 조작을 불가능 하게 합니다.
* dirname : 요소의 방향성을 결정합니다.
* form : 다른 폼 소유자와 명시적으로 연관시키기위해 사용됩니다.
* maxlengh : type속성이 text이거나 password일 경우 최대 입력 문자수를 지정할수 있습니다.
* name : textarea의 이름을 지정합니다
* placeholder : 임의적으로 힌트를 보여줍니다. IE8 브라우저 이상만 지원합니다.
* readonly : 컨트롤의 조작을 불가능하게 하지만 데이터는 서버에 전송한다. true ,false 로 지정해줘요
* required : 필수요소인지를 지정합니다. true ,false 로 지정해줘요

textarea 의 간단한 예제를 아래에서 확인해보세요, 그리고 저속성들이 무엇을 뜻하는지 한번쯤 적어서 확인해보시면 좋을 듯 싶어요

[예제 확인하기](https://jsfiddle.net/leetaesu/ynpa6jgj/4/)

---

[*6*] **button**

버튼 요소를 생성합니다. textarea처럼 속성은 autofocus,disabled, name, type, value 5가지가 있어요.  
**type** 속성에서는  

* submit : 폼을 제출합니다. 기본값입니다.
* reset : 폼을 리셋합니다.
* button : 아무것도 하지 않습니다.

[예제 확인하기](https://jsfiddle.net/leetaesu/ynpa6jgj/5/)

---

[*7*] **table**

[*8*] **ol,ul,dl**

[*9*] **div**

[*10*] **form**

[*11*] **h1~h6**

h태그는 1번부터 6번까지 지정 할 수 있어요. 숫자는 등급을 나타내며 h1 이 가장 높은 등급이며 h6이 가장 낮은등급이죠. 예를들어 홈페이지를 만들때 로고부분은 h1이 되겟죠? 아래 콘텐츠 영역에서 기사영역처럼 한영역이 있는부분은 h3이 되겠죠

![](image/img_html1_7.png)  

한문서의 h1 요소는 한개만 사용하도록 해요. 그래서 로고부분이 가장 적당하겠죠?

[예제 확인하기](https://jsfiddle.net/leetaesu/ynpa6jgj/6/)

[*12*] **iframe**

[*13*] **img**

[*14*] **map**

[*15*] **select**

[*16*] **strong - span**

