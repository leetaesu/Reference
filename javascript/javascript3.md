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