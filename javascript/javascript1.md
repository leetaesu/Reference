#javscript class ??

우선 시작하기 앞서... 책을 한권 샀는데 보는 도중 책의 내용이 좋아서 공부도 할겸 까먹지 않게 정리를 하면서 작성 하려고 합니다. 
출처는 교재 : 자바스크립트+jquery 완정정복 스터디3 입니다. 저자는 김춘경(딴동네)분이 만드셨습니다. 그리고 보충 설명이나 내용들은 구글에서 검색하여 기재 할 려고 합니다. 저는 제가 다시보기위해 정리하는 것이기 때문에 책을 구매하시는걸 추천합니다.

---

함수가 특정 알고리즘을 포장하는 기술이라면 클래스는 이렇게 만들어진 수 많은 변수와 함수 중 연관 있는 변수와 함수만을 선별해 포장하는 기술입니다. 이렇게 클래스로 포장하는 이유는 객체 단위로 코드를 그룹화하고 코드를 재사용하기 위해서입니다. 

쉽게 설명하여 아래에 함수랑 클래스랑 비교를 해드리겠습니다.

**함수 :** 특정 기능을 하는 변수와 구문으로 이루어져 있다.

**클래스 :** 연관 있는 변수와 함수로 이루어져 있다.

함수나 클래스나 둘다 코드그룹화 및 중복코드 제거 및 코드 재사용을 하는걸 맞지만, 클래스는 객체 단위로 구분지으며, 함수는 기능 단위로 그분 짓는다.

---

자바스크립트에서는 객체지향 프로그래밍 언어에서 기본적으로 제공하는 클래스라는 개념을 제공하지 않지만, 자바스크립트에서 클래스처럼 사용할 수 있는 방법이 세 가지 지원합니다. 

**[리터럴 방식]**

```javascript

var 인스턴스 = {
	프로퍼티1:초깃값,
	프로퍼티2:초깃값2,

	메서드1:function(){

	},
	메서드2:fucntion(){

	}
}

```

**[함수 방식]**

```javascript

function 클래스이름(){
	this.프로퍼티1 = 초깃값;
	this.프로퍼티2 = 초깃값;

	this.메서드1=function(){

	}
	this.메서드2=function(){

	}	
}

```

**[프로토타입 방식]**

```javascript

function 클래스이름(){
	this.프로퍼티1 = 초깃값;
	this.프로퍼티2 = 초깃값;
}
클래스이름.prototype.메서드1=function(){

}
클래스이름.prototype.메서드2=function(){

}
```

---

######인스턴스

함수를 사용하려면 함수 호출을 해줘야 하듯 클래스를 사용하려면 일반적으로 인스턴스를 생성해줘야 합니다. 인스턴스를 생성하지 않고 사용하는 클래스도 있습니다. 실무의 예로 설명 하자면 한페이지에 두개의 탭 패널이 있는 경우 두개의 클래스를 만드는 것이 아니라 하나의 탭패널 클래스를 만든 후 두 개의 탭패널 인스턴스를 만들어 사용하는 것이죠, 

```javascript

var 인스턴스 = new TabPanel();

```

######객체

객체라는 용어는 인스턴스의 다른 말일 뿐 두용어 모두 클래스의 실체를 나타내는 용어입니다. 앞서 인스턴스 예제에서 보여준 부분을 예로 들면 

인스턴스 예 : 탭패널을 사용하기 위해서는 탭패널의 인스턴스를 먼저 만들어주세요

객체 예 : 특정 탭패널을 동적으로 선택하고 싶다면 탭패널 객체의 A() 메서드를 호출 하면 됩니다.

위의 예처럼 인스턴스와 객체는 동일한 의미를 가질때도 있고, 명확히 구분해서 사용할 때도 있으니 상황에 맞게 선택해서 사용하면 됩니다.


######프로퍼티

클래스 내부에 만드는 변수를 프로퍼티라고 부르며 멤버변수라고도 부릅니다.

프로퍼티에는 주로 객체 내부에서 사용하는 일반적인 정보와 객체 내부 함수(메서드)에서 처리한 결과값이 저장됩니다. 


######메서드

클래스에 만드는 함수를 메서드라고 부르며 멤버함수라고도 부릅니다.

메서드는 주로 객체의 프로퍼티 값을 변경하거나 알아내는 기능과 클래스를 대표하는 기능이 담기게 됩니다.



