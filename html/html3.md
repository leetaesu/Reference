#Meta Tag 의 신세계

Meta Tag 는 html에서 문서 자체를 설명을 해주거나 문서시작시 동작도 가능하게 해주는 태그죠, 흔히 이 문서의 핵심언어는 어떤것인가, 작성자는 누구인가, 사용자의 화면에서 출력은 어떤 형태로 할 것인가 등등 여러가지 기능을 지정해 줄 수 있어요.

설명이야 이렇게 간단히 될 수 있지만 meta tag 의 상세 내용을 알게 되면 이런 기능까지 있었는지 놀라실거에요!!

우선 메타태그는 종류는

```html
	<META name="Subject" content="홈페이지주제 입력">
	<META name="Title" content="홈페이지이름 입력">
	<META name="Descript-xion" content="설명문 입력">
	<META name="Keywords" content="키워드 입력">
	<META name="Author" content="만든사람 이름">
	<META name="Publisher" content="만든단체나회사 이름">
	<META name="Other Agent" content="웹책임자 이름">
	<META name="Classification" content="카테고리위치(분류)">
	<META name="Generator" content="생성프로그램(에디터)">
	<META name="Reply-To(Email)" content="메일주소 입력">
	<META name="Filename" content="파일이름 입력">
	<META name="Author-Date(Date)" content="제작일">
	<META name="Location" content="위치">
	<META name="Distribution" content="배포자">
	<META name="Copyright" content="저작권">
	<META name="Robots" content="ALL">
	<META name="robots" content="index,follow" /> 
	   : 이 문서도 긁어가고 링크된 문서도 긁어감.
	<META name="robots" content="noindex,follow" />
	   : 이 문서는 긁어가지 말고 링크된 문서만 긁어감.
	<META name="robots" content="index,nofollow" />
	   : 이 문서는 긁어가되, 링크는 무시함.
	<META name="robots" content="noindex,nofollow" />
 	  : 이 문서도 긁지 않고, 링크도 무시함.
	<META HTTP-EQUIV="Expire" ConTENT="-1">
  	 :캐쉬 완료(파기)시간 정의.
	<META HTTP-EQUIV="Last-Modified" ConTENT="Mon,20 Jul 2007 19:30:30">
	   :최종수정일을 정의.	
	<META HTTP-EQUIV='Cache-Control' ConTENT='no-cache'>
	<META HTTP-EQUIV='Pragma' ConTENT='no-cache'>
	   :캐쉬가 되지 않게 하는 태그	
	<META HTTP-EQUIV="Content-type" content="text/html; charset=euc-kr">
	   :웹문서의 언어 설정.	
	<META HTTP-EQUIV="Imagetoolbar" content="no">
	   :그림위에 마우스 오버시 이미지 관련 툴바가 생기지 않음.	
	<META HTTP-EQUIV="Refresh" content="15;URL=http://galaxy.channeli.net/jakalky/sitemap.htm">
	   :페이지이동
	
	<META HTTP-EQUIV="Page-Enter" content="RevealTrans(Duration=5/시간 초단위, Transition=21) ">
	  :페이지 로딩시 트랜지션 효과(장면 전환 효과)

```



