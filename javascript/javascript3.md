#함수방식으로 클래스 만들기

함수 방식 클래스의 경우는 하나의함수 내부에 프로퍼티와 메서드를 정의하는 구조입니다. 프로퍼티와 메서드는 반드시자기자신을나타내는 this에 정의해야 합니다.

```javascript

//클래스 정의
function User(){
	this.name="leetaesu";
	this.age = 10;
	this.showInfo=function(){
		document.write("name ="+this.name+", age ="+this.age);
	}
}

// 인스턴스 생성
var user=new User();

// 메서드 호출
user.showInfo();


```

자바스크립트에서는 클래스를 만들기 위한 키워드가 따로 존재하진 않습니다. 클래스를 만드는 방법은 함수 만드는 방법과 동일하기 때문에 둘다 function 이라는 키워드를 사용합니다. 그래서 일반적으로 구분짓기위해 함수이름은 소문자로 시작하며 클래스는 대문자로 시작합니다

```javascript 

// 함수 예
function user(){
}

// 클래스 예
function User(){
}

```

함수방식에서 생성자는 클래스 이름 자체가 생성자이기 때문에 인스턴스가 생성될대 자동으로 호출됩니다.

```javascript

function 클래스이름(){
	this.프로퍼티 = 초깃값;
	this.메서드 = function(){}
}

var user = new 클래스이름();

```