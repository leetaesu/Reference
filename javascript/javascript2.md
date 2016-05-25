#오브젝트 리터럴 방식으로 클래스 만들기

리터럴 방식을 이용한 간단한 클래스만들기

```javascript 

var user = {
	name : "taesu",
	age : 31,
	showInfo : function(){
		document.write("name ="+this.name+", age ="+this.age);
	}
}
user.showInfo();

```

아래 함수단위 코딩으로 만들어진 탭메뉴를 

#### 기존 함수단위 코드
```javascript

// 탭메뉴 관련 변수
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

오브젝트 리터럴 방식 위한 클래스 작성 6단계

1. 클래스 생성하기
2. 변수를 프로퍼티로 만들기
3. 함수를 메서드로 만들기
4. 객체 내부에서 프로퍼티와 메서드 사용하기
5. 첫 번째 탭메뉴 인스턴스 생성하기
6. 객체 외부에서 프로퍼티와 메서드 사용하기

를 이용하여 클래스를 작성해보자

#### 프로토타입 방식 코드 변경
```javascript

$(document).ready(function(){
	tabMenu1.init();
	tabMenu1.initEvent();
});

var tabMenu1 = {
	$tabMenu:null,
	$menuItems:null,
	$selectMenuItem:null,

	// 요소 초기화
	init:function(){
		this.$tabMenu = $("#tabMenu1");
		this.$menuItems = this.$tabMenu.find("li");
	},

	// 이벤트 등록
	initEvent:function(){
		var objThis = this;
		this.$menuItems.on("click",function(){
			objThis.setSelectItem($(this));
		});
	},

	// $menuItem에 해당하는 메뉴 아이템 선택하기
	setSelectItem:function($menuItem){
		// 기존 선택메뉴 아이템을 비활성화 처리 하기
		if(this.$selectMenuItem){
			this.$selectMenuItem.removeClass("select");
		}

		// 신규 아이템 활성화 처리 하기
		this.$selectMenuItem = $menuItem;
		this.$selectMenuItem.addClass("select");
	}
}

```

오브젝트 리터럴 방식의 클래스 특징

1. 인스턴스를 여러 개 만들 수 없습니다.
2. 주 용도는 여러 개의 데이터 포장용

리터럴은 여러 개의 데이터를 묶을 때 주로 사용합니다.