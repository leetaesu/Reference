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