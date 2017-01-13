#less 분기 전 (분류 필요)


css 프레임워크는 sass , less , stylus 가 있습니다.

기본적으로 사용하던 css 문법이랑 비슷한 sass 와 less 가 가장 많이 쓰이고 있습니다.

sass 나 less 나 한개의 문법만 배워도 두가지는 서로 비슷한 면이 많아서 쉽게 사용할 수 있습니다.

저희는 라이브에 배포할때 코드압축을 따로 하지 않는걸로 알고있는데, 그럼 로컬환경 작업 방식으로 진행 하겠습니다.

less를 less.js로 변환을 해주면 서버자원을 많이 소모하기 때문에 css변환해서 올리면 서버자원을 

줄일 수 있습니다.

왜 우선 css 보다 less 를 사용해야하는 점 아래 3가지가 가장 대표적이죠!

1. 변수 

2. 믹스인

3. 중첩

초보자는 우선 이 3가지만 중점적으로 공부를 한다음 적용을 해보면 엄청 좋으실 거에요

그외에 더욱 효과적으로 사용할수 있게 도와주는 네임스페이스 기법 , 믹스인 추가활용법 등등 있고,

javascript 처럼 연산자나 기본 색상관련함수 ,수학관련 함수등 기본제공 함수도 있지만, 이건 3가지를 공부한다음에 진행하면 될 것 같아요

우선 가장 쉽게 이해하기 쉬운 부분부터 보자면 **중첩 관련 규칙**이 있어요

이게 무엇이냐면 간단하게 말해서 우리는 css 점수라는걸 다들 알고 계시죠? ( 아래 설명 있어요 )

important 10000점 ,인라인 스타일 1000점 , id는 100점 , 클래스는 10점 , 태그는 1점 이죠 ,

그래서 우리는 css 작성할때 순서대로 표기를 하고 있죠? 예시를 보여드릴게요


### 기존 css 방식

``` css
.wrap .content .inBox{border:1px solid red}  
.wrap .content .inBox .pen_group{width:20px; height:30px}  
.wrap .content .inBox .pen_group .red_pen{color:red}  
```
기존 css방식에서는 중첩의 개념을 다 선언해줌으로써 css 점수를 적용해서 코드자체가 보기도 불편할뿐더러 유지보수 측면에서 좋지 않았습니다. 

아래 소스는 기존 css를 less 방식으로 변경 해보았습니다.

```css
.wrap{
	.content{
		.inBox{
			border:1px solid red;
			.pen_group{
				width:20px;
				height:30px;
				.red_pen{
					color:red;
				}
				.green_pen{
					color:green;
				}
			}
		}
	}
}

```

위에 방식처럼 불필요한 중복되는 코드를 없애면서 코드가 한결 보기 쉽게 변했어요.
