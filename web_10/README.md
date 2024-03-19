# web_10

1. 
What is BOM ?
BOM = (browser object model)
: HTML 페이지의 각 HTML 태그들을 객체화한 것으로 
자바스크립트 코드로 화면에 출력된 HTML 태그의 
콘텐츠나 모양을 변경하기 위해서 설계되었따.

2.
window 객체의 생성
window 객체는 열려 있는 브라우저 윈도우나 탭 윈도우를 나타내는 객체
윈도우마다 하나의 윈도우 객체가 생성된다.

1) 브라우저가 새로운 웹 페이지를 로드할 때 윈도우 객체 자동 생성
2) <iframe> 태그 당 하나의 window객체 자동 생성
3) 개발자가 다음 자바스크립트 코드로 임의의 window 객체 생성
window.open("웹페이지 URL", "윈도우이름", "윈도우속성")

window.open()
윈도우 기능 중 가장 많이 사용하는 것으로 새 윈도우를 여는 것이다.
window.open("http://www.naver.com","","");
윈도우를 새로 열고 네이버 페이지를 출력

형식
window.open(sURL, sWindowName, sFeature)
- sURL : 윈도우에 출력할 웹 페이지 주소 문자열
- sWindowName : 새로 여는 윈도우 이름 문자열로서 생략 가능
- sFeature : 윈도우 모양, 크기 등의 속성들을 표현하는 문자열

-sWindowName : _blank(새탭), _parent(부모 윈도우에 출력)

