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

1. 함수 방식에서 프로퍼티와 메서드는 this에 만들어 줍니다.
2. 인스턴스 생성 방법은 "클래스이름" 함수를 호출할 때 new 키워드를 추가해 호출해 준다.


만약 new 를 붙이지 않으면 인스턴스 생성이 아닌 함수 호출이 되어 정상적으로 작동하지 않게 됩니다.

```javascript

//인스턴스 생성 방법

function 클래스이름(){
	this.프로퍼티1 = 초깃값;
	this.메서드1 = function(){}
}

var 인스턴스 = new 클래스이름();

```

객체 외부에서 프로퍼티와 메서드 접근 방법은 전 단계에서 배운 오브젝트 리터럴 방식처럼 함수 방식도 접근하려면 접근 연산자를 사용하여 접근 할수 있습니다.

```javascript

// 객체 외부에서 프로퍼티 메서드 접근방법

function 클래스이름(){
	this.프로퍼티1 = 초깃값;
	this.메서드1 = function(){}
}

var 인스턴스 = new 클래스이름();
인스턴스.프로퍼티1;
인스턴스.메서드1();

```

```javascript

// 객체 내부에서 프로퍼티 메서드 접근방법

function 클래스이름(){
	this.프로퍼티1 = 초깃값;
	this.메서드1 = function(){
		this.프로퍼티1;
		this.메서드2();
	}
	this.메서드2 = function(){
	}
}

var 인스턴스 = new 클래스이름();

```

---

기존에 함수 단위 방식의 코드를 함수 방식 클래스 코드로 변경해보자 

```javascript 

// 함수 단위 코드

var $tabMenu =null;
var $menuItems=null;
var $selectMenuItem=null;

$(document).ready(function(){
	// 탭메뉴 요소 초기화
	init();
	// 탭메뉴 요소에 이벤트 등록
	initEvent();
});

// 요소 초기화
function init(){
	$tabMenu = $("#tabMenu1");
	$menuItems = $tabMenu.find("li");
}

// 이벤트 등록
function initEvent(){
	$menuItems.on("click",function(){
		setSelectItem($(this));
	});
}

// $menuItem에 해당하는 메뉴 아이템 선택하기
function setSelectItem($menuItem){
	// 기존 선택메뉴 아이템을 비활성화 처리 하기
	if($selectMenuItem){
		$selectMenuItem.removeClass("select");
	}

	// 신규 아이템 활성화 처리 하기
	$selectMenuItem = $menuItem;
	$selectMenuItem.addClass("select");
}

```

이전 오브젝트 리터럴 방식과 동일하게

1. 클래스 생성하기
2. 변수를 프로퍼티로 만들기
3. 함수를 메서드로 만들기
4. 객체 내부에서 프로퍼티와 메서드 사용하기
5. 인스턴스 사용하기
6. 객체 외부에서 프로퍼티와 메서드 사용하기

```javascript 

$(document).ready(function(){
	// 인스턴스 생성
	var tabMenu1 = new TabMenu();
	tabMenu1.init();
	tabMenu1.initEvent();
});

function TabMenu(){
	this.$tabMenu =null;
	this.$menuItems=null;
	this.$selectMenuItem=null;
	// 요소 초기화
	this.init = function() {
		this.$tabMenu = $("#tabMenu1");
		this.$menuItems = this.$tabMenu.find("li");
	}

	// 이벤트 등록
	this.initEvent = function() {
		var objThis = this;
		this.$menuItems.on("click", function() {
			objThis.setSelectItem($(this));
		});
	}

	// $menuItem에 해당하는 메뉴 아이템 선택하기
	this.setSelectItem = function($menuItem) {
		// 기존 선택메뉴 아이템을 비활성화 처리 하기
		if (this.$selectMenuItem) {
			this.$selectMenuItem.removeClass("select");
		}

		// 신규 아이템 활성화 처리 하기
		this.$selectMenuItem = $menuItem;
		this.$selectMenuItem.addClass("select");
	}
}

```

이렇게 변경된 함수방식 클래스는 기존 오브젝트 리터럴과 달리 여러개의 탭이 생성되어도 인스턴스만 추가되면 쉽게 추가가 가능합니다

```javascript

// 상단 기존코드
$(document).ready(function(){
	// 인스턴스 생성
	var tabMenu1 = new TabMenu();
	tabMenu1.init();
	tabMenu1.initEvent();
});

// --> 변경 (init 함수와 initEvent 함수를 내부로 바꾸고 새롭게 인스턴스만 추가해준다
$(document).ready(function(){
	// 인스턴스 생성
    var tabMenu1 = new TabMenu("#tabMenu1");
	var tabMenu2 = new TabMenu("#tabMenu2");
});


// 상단 기존코드
function TabMenu(){
	this.$tabMenu =null;
	this.$menuItems=null;
	this.$selectMenuItem=null;
	// 요소 초기화
	this.init = function() {
		this.$tabMenu = $("#tabMenu1");
		this.$menuItems = this.$tabMenu.find("li");
	}


// --> 변경 (init 함수에 매개변수를 받아서 지정해주면 인스턴스만 실행해주면 쉽게 탭메뉴를 추가 시킬수 있다.
function TabMenu(selector){
    this.$tabMenu =null;
    this.$menuItems=null;
    this.$selectMenuItem=null;
    // 요소 초기화
    this.init = function(selector) {
        this.$tabMenu = $(selector);
        this.$menuItems = this.$tabMenu.find("li");
    }

...

	// 해당 인스턴스 생성자로 호출된부분의 init함수와 initEvent를 실행한다.
    this.init(selector);
    this.initEvent();

```




