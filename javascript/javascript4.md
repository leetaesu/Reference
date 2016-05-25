#프로토타입으로 방식으로 클래스 만들기

프로토타입으로 만드는 클래스는 3가지 클래스 만들기 방법중에 가장 좋은 방법입니다. 여러분이 사용하시는 jquery역시 프로토타입 방식으로 만들어진 클래스입니다.

```javascript 

// prototype 문법
function 클래스이름(){
	this.프로퍼티1=초깃값;
	this.프로퍼티2=초깃값;	
}

클래스이름.prototype.메서드=function(){
}

```

프로퍼티의 정의는 함수 방식처럼 this를 이용해서 정의하며 메서드는 prototype이라는 프로퍼티에 정의하는 구조입니다.

```javascript

//클래스 생성자

function User(){
	//프로퍼티 정의
	this.name="taesu.lee";
	this.age=31;
}

//메서드 정의
User.prototype.showInfo=function(){
	document.write("name ="+this.name+", age="+this.age);
}

//인스턴스 생성
var user = new User();

//메서드 호출
user.showInfo();

```

1. 프로토 타입 방식에서 생성자는 함수 방식과 마찬가지로 클래스이름 자체가 생성자이며 인스턴스를 생성할때 자동 호출 됩니다.






