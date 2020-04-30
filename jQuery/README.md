# jQuery

>  과거에. 생활 코딩 오픈 튜토리얼의 내용을 정리한 파일입니다.



jQuery는 자바스크립트의 생산성을 향상시켜주는 자바스크립트 라이브러리 입니다. 

## 1. jQuery

* library: 자주 사용하는 코드를 재사용할 수 있는 형태로 가공해서 프로그래밍 효율을 높여주는 코드들
* 특징
  1. 엘리멘트 선택에 강력한 방법
  2. 선택한 엘리먼트들을 효율적으로 제공하는 다양한 수단을 제공
  3. 자바스크립트 라이버러리
* 사용방법
  * `$(".클래스이름").html('콘텐츠').css('background-color', 'yellow');` 
  * `.`을 통해서 method를 붙여 줄 수 있다. 이를 **chain**이라 부른다.
  * `$(제어대상).method1().method2();`  => 주어에 서술어를 붙인 형태와 비슷. 인간의 문법과 비슷해 생산성을 높여준다.



## 2. JavaScript VS jQuery

> 코드의 간결성



## 3. Wrapper

* Wrapper(래퍼)란? 둘러싼다는 뜻

* `jQuery(`엘리먼트 오브젝트 | 'css스타일 선택자'`)`

  * `해당 부분`이 래퍼, 인자로 전달된 요쇼들에 jQuery의 기능을 부가해서 반환

* 안전한 사용 -> $(엘리먼트)와 jQuery(엘리먼트는 같은 의미지만 $를 사용하는 다른 라이브러리와 충돌이 가능)

* 두가지의 해결 방법이 있음

  1. **$대신 jQuery를 사용**

     ```html
     <script type="text/javascript">
         jQuery('body').html('hello world');
     </script>
     ```

     

  2. **$를 함수의 지역변수로 선언해서 외부에 있을지도 모르는 타 라이브러리 $와의 충돌 에방**

     ```html
     <script type="text/javascript">
         (function($)){
          	$('body').html('hello world');
         })(jQuery)
     </script>
     ```

* jQuery의 사용 형태는 다음과 같다

  * `jQuery(selector, [context])`
  * `jQuery(element)`



## 4. 선택자

jQuery wrapper에서는 css선택자가 위치할 수 있는데, 이를 통해서 제어하려는 엘리먼트를 빠르고 정확하게 지정할 수 있다.

* `"#이름"` : id 선택자
* `".이름"` : class 선택자
* `"li" `: element 선택자
* `"#이름1, #이름2"` :다중 선택자



## 5. Chain

jQuery의 메소드들은 반환값으로 자기자신을 반환한다는 규칙.

**이를 통해서 한번 선택대상에 연속적인 제어가 가능하다.**

* 장점
  1. 코드가 간결해짐
  2. 인간의 언어와 유사해, 자연스러운 과정

**탐색(traversing)** : chain의 대상을 바꿔서 체인을 계속 연장시킬 수 있는 방법



## 6. event(이벤트)

* **이벤트란?**
  1. 시스템에서 일어나는 사건
  2. javascript나 jQuery에게 이벤트란 브라우저에서 일어나는 사건
     * 클릭, 마우스 이동, 타이핑, 페이지 로딩 등
  3. 이벤트 발생시 작동할 로직을 시스템에게 알려주는 이벤트가 발생했을 때 그시스템이 로직을 호출
* **jQuery의 이벤트**
  1. 크로스 브라우징의 문제를 해결
     * Cross Browsing(크로스 브라우징) : 적어도 표준 웹기술을 채용하여 다른 기종 혹은 플랫폼에 따라 달리 구현되는 기술을 비슷하게 만듦과 동시에 어느 한쪽에 최적화되어 치우지지 않도록 공통 요소를 사용하여 웹 페이지를 제작하는 기법을 말하는 것이다
  2. bind로 이벤트 핸들러를 설치하고, unbind로 제거
  3. trigger로 이벤트 핸들러를 강제로 실행
  4. click, ready와 같이 다양한 이벤트 헬퍼(helper)를 제공함
  5. live를 이용하면 현재 존재 하지 않는 엘리먼트에 이벤트 핸들러를 설치할 수 있음



## 7. 엘리멘트 제어

jQuery는 엘리먼트를 제어하는 일관되고 풍부한 기능들을 제공합니다.

http://api.jquery.com/category/manipulation/

**종류**

* 자식으로 삽입
  * .append(), .appendTo(), .html(), .prepend(), .prependTo(), .text()
* 형제로 삽입
  * .after(), .before(), .insertAfter(), .insertBefore()
* 부모로 감싸기
  * .unwrap(), .wrap(), .wrapAll(), .wrapInner()
* 삭제
  * .detach(), .empty(), .remove(), .unwrap()
* 치환
  * .replaceAll(), .replaceWith()
* 클래스
  * .addClass(), .hasClass(), .removeClass(), .toggleClass()
* 속성제어
  * .attr(), .prop(), .removeAttr(), .removeProp(), .val()



## 8. 폼

- 서버로 데이터를 전송하기 위한 수단
- [생활코딩 HTML 튜토리얼 폼 편 참고](http://opentutorials.org/course/11/14)
- Query는 폼을 제어하는데 필요한 이벤트와 메소드를 제공한다.
- jQuery 폼 API 문서 : http://api.jquery.com/category/forms/

* ex) .focus(), .blur(), .change(), .select(), .submit(), .val()



## 9. 탐색

- 체인 컨텍스트를 유지하면서 제어의 대상이 되는 엘리먼트를 변경하는 기법
- [chain 챕터참고 ](http://opentutorials.org/jquery_tutorial/?id=77)
- http://api.jquery.com/category/traversing/



## 10. 애니메이션

- 자바스크립트와 CSS를 이용해서 HTML엘리먼트에 동적인 효과를 줄 수 있다.
- jQuery의 효과 메소드를 호출하는 것만으로 간단히 효과를 줄 수 있다.



## 11. Ajax

### ajax란?

- **A**synchronous **J**avaScript **a**nd **X**ML 의 약자
- 자바스크립트를 이용해서 비동기식으로 서버와 통신하는 방식. 이 때 XML을 이용한다.
- 꼭 XML을 이용할 필요는 없고, 최근에는 json을 더 많이 이용한다.
- **비동기식**이란 **여러가지 일이 동시적으로 발생**한다는 뜻으로, 서버와 통신하는 동안 다른 작업을 할 수 있다는 의미.

### $.ajax(settings)

- jQuery를 이용한 ajax통신의 가장 기본적인 API
- **주요속성**
  - data : 서버에 전송할 데이터, key/value 형식의 객체
  - dataType : 서버가 리턴하는 데이터 타입 (xml, json, script, html)
  - type : 서버로 전송하는 데이터의 타입 (POST, GET)
  - url : 데이터를 전송할 URL
  - success : ajax통신에 성공했을 때 호출될 이벤트 핸들러