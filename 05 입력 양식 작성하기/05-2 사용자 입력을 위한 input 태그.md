### < input >태그의 type속성 한눈에 살펴보기

|종류|설명|
|---|---|
|text|한 줄짜리 텍스트를 입력할 수 있는 텍스트 박스를 삽입|
|password|비밀번호를 입력할 수 있는 필드를 삽입|
|search|검색할 때 입력하는 필드를 삽입|
|url|URL 주소를 입력할 수 있는 필드를 삽입|
|email|이메일 주소를 입력하 수 있는 필드를 삽입|
|tel|전화번호를 입력할 수 있는 필드를 삽입|
|checkbox|주어진 여러 항목에서 2개 이상 선택할 수 있는 체크 박스를 삽입|
|radio|주어진 여러 항목에서 1개만 선택할 수 있는 라디오 버튼을 삽입|
|number|숫자를 조절할 수 있는 스핀 박스 삽입|
|range|숫자를 조절할 수 있는 슬라이드 막대 삽입|
|date|사용자 지역을 기준으로 날짜(연, 월, 일)를 삽입|
|month|사용자 지역을 기준으로 날짜(월, 일)를 삽입|
|week|사용자 지역을 기준으로 날짜(연, 주)를 삽입|
|time|사용자 지역을 기준으로 시간(시, 분, 초, 분할 초)을 삽입|
|datetime|국제 표준시(UTC)로 설정된 날짜와 시간(연, 월, 일, 시, 분, 초, 분할 초)을 삽입|
|datetime-local|사용자가 있는 지역을 기준으로 날짜와 시간(연, 월, 일, 시, 분, 초, 분할 초)을 삽입|
|submit|전송 버튼 삽입|
|reset|리셋 버튼 삽입|
|image|submit 버튼 대신 사용할 이미지 삽입|
|button|일반 버튼 삽입|
|file|파일을 첨부할 수 있는 버튼 삽입|
|hidden|사용자에세는 보이지 않지만 서버로 넘겨주는 값이 있는 필드 생성|

### 텍스트와 비밀번호를 나타내는 type="text"와 type="password"

 - 텍스트 필드
   - 폼에서 가장 많이 사용하는 요소
   - 아이디, 이름, 주소 등 한 줄짜리 일반 텍스트를 입력할 때 사용
 - 비밀번호 필드
   - 입력하는 내용을 화면에 보여주지 않아야 한다. '*'나 '큰 점'으로 표시
   - 다른 동작은 텍스트 필드와 같은 속성

 ```html
 <input type="text">
 <input type="password">
 ``` 

 - 텍스트 필드와 비밀번호 필드에서 사용하는 주요 속성
 1. size: 텍스트와 비밀번호 필드의 길이를 지정
   - 화면에 몇 글자가 보이도록 할 것인지를 지정
   - (ex) 최대로 입력할 수 있는 글자 수가 10개인데 size 속성값을 5로 지정하면 필드 크기는 5개 글자 크기에 맞추고 나머지 5개 글자는 화면에 보이지 않는다.
 
 2. value: 텍스트 필드 요소가 화면에 표시될 때 텍스트 필드 부분에 보여주는 내용
   - 이 속성을 사용하지 않으면 빈 텍스트 필드가 표시
   - 비밀번호 필드에서는 사용하지 않는 속성

 3. maxlength: 텍스트 필드와 비밀번호 필드에 입력할 수 있는 최대 문자 수를 지정

 ```html
 <form>
  <fieldset>
    <label>아이디: <input type="text" id="user-id" size="10"></label>
    <label>비밀번호: <input type="password" id="user-pw" size="10"></label>
    <input type="submit" value="로그인">
  </fieldset>
 </form>
 ``` 
 ![image](https://github.com/Seonghyun-Park/Web/assets/121333241/ce85103f-a2fd-4807-9ddd-bc07c8dac86a)

### 다양한 용도에 맞게 입력하는 "type=search", type="url", type="email", type="tel"

 - type="search"
   - 웹 브라우저에서 검색을 위한 텍스트 필드로 인식(화면으로 볼 때는 텍스트 필드와 동일)
   - 이 필드에 검색어를 입력하면 오른쪽에 X 가 표시되어 입력한 검색어를 지울 수 있다.
 - type="url"
   - 웹 주소를 입력하는 필드
 - type="email"
   - 이메일 주소를 입력하는 필드
   - 만약 입력값이 지정한 형식에 맞지 않는다면 웹 브라우저에서 오류 메시지를 보여 준다.
 - type="tel"
   - 전화번호를 나타내는 필드
   - 전화번호는 지역마다 형식이 다르므로 사용자가 입력한 값이 전화번호인지 아닌지 체크할 수 없다.
   - 모바일 기기의 웹 브라우저에서 확인하면 이메일 주소를 입력하거나 전화번호를 입력할 때 가상 키보드 배열이 바뀐다.

 ```html
 <ul>
  <li>
    <label for="user-name">이름</label>
    <input type="text" id="user-name">
  </li>
  <li>
    <label for="addr">배송 주소</label>
    <input type="text" id="addr">
  </li>
  <li>
    <label for="mail">이메일</label>
    <input type="email" id="mail">
  </li>
  <li>
    <label for="phone">연락처</label>
    <input type="tel" id="phone">
  </li>
 </ul>
 ```
 ![image](https://github.com/Seonghyun-Park/Web/assets/121333241/f3f4c1b9-6077-4429-80a1-e11bcd828163)

### 체크 박스와 라디오 버튼을 나타내는 type="checkbox", type="radio"

 - 체크 박스(checkbox): 여러 항목 중 2개 이상을 선택
 - 라디오 버튼(radio): 여러 항목 중 1개만 선택
   - 항목을 1개만 선택할 수 있으므로 이미 선택한 항목이 있을 경우 다른 항목을 선택하면 기존 항목은 취소된다.
   - 라디오 버튼에서 하나의 버튼만 선택할 수 있게 하려면 아래와 같이 모든 라디오 버튼의 name을 똑같이 지정해야 한다.
 
 ```html
 <input type="checkbox">
 <input type="radio">
 ```

 - 체크 박스, 라디오 버튼에서 사용하는 속성
 1. value: 선택한 체크 박스나 라디오 버튼을 서버에게 넘겨줄 값을 지정
   - 이 값은 영문이거나 숫자여야 하며 필수 속성이다.
 2. checked: 체크 박스나 라디오 버튼의 항목은 처음에 아무것도 선택되지 않은 상태로 화면에 표시되는데, 여러 항목 중에서 기본으로 선택해 놓고 싶은 항목에 사용

 ```html
  <fieldset>
      <legend>상품 선택</legend>
      <p><b>주문할 상품을 선택해 주세요.</b></p>
      <ul>
        <li>
          <label><input type="checkbox" value="s_3">선물용 3kg</label>
          <input type="number">개 <!--number: 숫자를 조절할 수 있는 스핀 박스 삽입 -->
        </li>
        <li>
          <label><input type="checkbox" value="s_5">선물용 5kg</label>
          <input type="number">개
        </li>
        <li>
          <label><input type="checkbox" value="f_3">가정용 3kg</label>
          <input type="number">개
        </li>
        <li>
          <label><input type="checkbox" value="f_5">가정용 5kg</label>
          <input type="number">개
        </li>
      </ul>   
      <p><b>포장 선택</b></p>
      <ul>
        <li><label><input type="radio" name="gift" value="yes" >선물 포장</label></li>
        <li><label><input type="radio" name="gift" value="no">선물 포장 안 함</label></li>
      </ul>     
    </fieldset>
 ```
 ![image](https://github.com/Seonghyun-Park/Web/assets/121333241/1c436090-d73b-4815-b55d-762ac11a0a71)
   
### 실습

```html
<fieldset>
        <legend>사용자 정보</legend>
        <ul>
          <li>
            <label for="uid">아이디</label>
            <input type="text" id="uid">
          </li>
          <li>
            <label for="umail">이메일</label>
            <input type="email" id="umail">
          </li>
          <li>
            <label for="pwd1">비밀번호</label>
            <input type="password" id="pwd1">
          </li>
          <li>
            <label for="pwd2">비밀번호 확인</label>
            <input type="password" id="pwd2">
          </li>
        </ul>
      </fieldset>
      <fieldset>
        <legend>이벤트와 새로운 소식</legend>
        <input type="radio" name="mailing" id="mailing_y">
        <label for="mailing_y">메일 수신</label>
        <input type="radio" name="mailing" id="mailing_n" checked>
        <label for="mailing_n">메일 수신 안 함</label>
      </fieldset>
      <div id="buttons">
        <input type="submit" value="가입하기">
        <input type="reset" value="취소">
      </div>
```
![image](https://github.com/Seonghyun-Park/Web/assets/121333241/ff898cf7-bf99-482f-a9c1-d19482cf63eb)

### 숫자 입력 필드를 나타내는 type="number", type="range"

 - number: 스핀 박스가 나타나면서 숫자를 선택할 수 있다.
 - range: 슬라이드 막대를 움직여 숫자를 입력할 수 있다.

 ```html
 <input type="number">
 <input type="range">
 ```

 - 숫자 필드에서 사용하는 속성
 
 1. min: 필드에 입력할 수 있는 최솟값을 지정, 기본 최솟값은 0
 2. max: 필드에 입력할 수 있는 최댓값을 지정, 기본 최댓값은 100
 3. step: 숫자 간격을 지정, 기본값은 1
 4. value: 필드에 표시할 초깃값

 - 스핀 박스 사용(type="number")
 ```html
 <ul>
  <li>
    <label><input type="checkbox" value="s_3">선물용 3kg</label>
    <input type="number" min="0" max="5">개 (최대 5개)
  </li>
  <li>
    <label><input type="checkbox" value="s_5">선물용 5kg</label>
    <input type="number" min="0" max="3" value="1">개 (최대 3개)
  </li>
 </ul>
 ```
 ![image](https://github.com/Seonghyun-Park/Web/assets/121333241/b98c700a-7436-4891-9c33-57e5efc74194)


 - 슬라이드 막대 사용(type="range")

 ```html
  <ul>
  <li>
    <label><input type="checkbox" value="f_3">가정용 3kg</label>
    <input type="range" min="0" max="5">개 (최대 5개)
  </li>
  <li>
    <label><input type="checkbox" value="f_5">가정용 5kg</label>
    <input type="range" min="0" max="3" value="1">개 (최대 3개)
  </li>
 </ul>
 ```
 ![image](https://github.com/Seonghyun-Park/Web/assets/121333241/fb45cec4-7822-4345-bb2d-ebb0c9fa1b11)

### 날짜 입력을 나타내는 type="date, type="month", type="week"

 ```html
 <input type="date | month | week">
 <!--- '|' 기호는 나열한 옵션 중 하나가 속성값이 되어야 한다는 의미--->
 ```
 1. type="date"로 지정하면 달력에서 날짜를 선택해서 입력할 수 있다. 
   - 날짜를 선택하면 필드에 "yyyy-mm-dd" 형식으로 연도, 월, 일이 표시된다.
 2. type="month"로 지정하면 달력에서 월을 선택해서 입력할 수 있다. 
   - 월을 선택하면 "yyyy-mm" 형식으로 연도, 월까지만 입력된다.
 3. type="week"로 지정하면 달력에서 주를 선택해서 입력할 수 있다. 
   - 주를 선택하면 1월 첫째 주를 기준으로 몇 번째 주인지 표시된다.

 ```html
 <h1>날짜 지정하기</h1>
 <input type="date">
 <input type="month">
 <input type="week">
 ```
 ![image](https://github.com/Seonghyun-Park/Web/assets/121333241/0644ee75-f61e-453b-b3af-8cc7beb37c27)
 ![image](https://github.com/Seonghyun-Park/Web/assets/121333241/2338404f-bbd0-412e-a561-8120e8dd943d)
 ![image](https://github.com/Seonghyun-Park/Web/assets/121333241/1bdee40f-d3b1-4536-9446-1328f33b7874)

### 시간 입력을 나타내는 type="time", type="datetime", type="datetime-local"

 ```html
 <input type="time | datetime | datetime-local">
 ```

 1. type="time"은 폼에서 시간을 입력하게 한다. 
   - 첫 번째 항목부터 '오전'과 '오후'를 의미하고 나머지는 '시'와 '분'을 의미한다.
 2. type="datetime" 또는 type="datetime-local" 유형을 사용하면 사용자가 웹 문서를 보고 있는 지역에 맞는 날짜와 시간을 함께 입력할 수 있다.

 ```html
 <h1>시간 지정하기</h1>
 <input type="time">
 <input type="datetime-local">
 ```
 ![image](https://github.com/Seonghyun-Park/Web/assets/121333241/82a6ee03-f07c-4074-bf66-77d4c2cdf54e)
![image](https://github.com/Seonghyun-Park/Web/assets/121333241/2d38f16e-2dd4-4b17-b326-58aad5274dee)

### 날짜나 시간의 범위

 - min: 범위의 시작 날짜나 시간을 지정
 - max: 범위의 마지막 날짜나 시간을 지정
 - step: 스핀 박스의 화살표를 클릭했을 때 증감시킬 크기를 지정
 - value: 기본적으로 표시할 날짜나 시간 지정

 ```html
 <input type="date" min="2020-02-01" max="2020-02-15">
 ```
 ![image](https://github.com/Seonghyun-Park/Web/assets/121333241/c03060bd-af54-4968-afab-c2e9ec6c16c5)

### 전송, 리셋 버튼을 나타내는 type="submit", type="reset"

 - submit: 폼에 입력한 정보를 서버로 전송
   - submit 버튼으로 전송된 정보는 < form >태그의 action 속성에서 지정한 폼 처리 프로그램에 넘겨진다.
   - value 속성을 사용해서 버튼에 표시할 내용을 지정한다.
 - reset: < input >요소에 입력된 모든 정보를 재설정해서 사용자가 입력한 내용을 모두 지우는 역할
   - value 속성을 사용해서 버튼에 표시할 내용을 지정한다.

 ```html
 <input type="submit | reset" value="버튼에 표시할 내용">
 ```

 ```html
 <div>
  <input type="submit" value="주문하기">
  <input type="reset" value="취소하기">
 </div>
 ```
 ![image](https://github.com/Seonghyun-Park/Web/assets/121333241/523635d2-0366-450e-9a10-6b8cc8fcc27e)

### 이미지 버튼을 나타내는 type="image"

 - type="image"는 submit 버튼과 같은 기능을 하는 이미지 버튼을 나타낸다.

 ```html
 <input type="image" src="이미지 경로" alt="대체 텍스트">
 ``` 

 ```html
 <label>아이디: <input type="text" id="user_id" size="10"></label>
 <label>비밀번호: <input type="password" id="user_pw" size="10"></label>
 <input type="image" src="images/login.png" alt="로그인">
 ```
 ![image](https://github.com/Seonghyun-Park/Web/assets/121333241/8b4a2724-d2b9-494b-8a0b-5a591a52ad84)

### 기본 버튼을 나타내는 type="button"

 - type="button"은 submit이나 reset 버튼과 같은 기능이 없고 오직 버튼 형태만 삽입
 - 주로 버튼을 클릭해서 자바스크립트를 실행할 때 사용

 ```html
 <input type="button" value="버튼에 표시할 내용">
 ```

 - 버튼을 만들고, 버튼을 클릭하면 연결한 문서가 새 탭에서 보인다.
 ```html
 <form>
  <input type="button" value="공지 창 열기" onclick="window.open('notice.html')">
 </form>
 ```
 ![image](https://github.com/Seonghyun-Park/Web/assets/121333241/16c134f6-e911-4d4b-8d0c-c36d27d93e93)
 ![image](https://github.com/Seonghyun-Park/Web/assets/121333241/15734459-cdba-4a51-a844-d73b4d20aef6)

### 파일을 첨부할 때 사용하는 type="file"

 - 폼에서 사진이나 문서를 첨부해야 하는 경우
 
 ```html
 <input type="file">
 ```
 ![image](https://github.com/Seonghyun-Park/Web/assets/121333241/0f897d2c-226a-4105-9f97-8d0d30fa47c0)

### 히든 필드 만들 때 사용하는 type="hidden"

 - 화면의 폼에는 보이지 않지만 사용자가 입력을 마치면 폼과 함께 서버로 전송되는 요소
 - 사용자에게 굳이 보여 줄 필요는 없지만 관리자가 알아야 하는 정보는 히든 필드로 입력
 ---
 - 히든 필드를 사용해 사용자가 사이트에서 로그인하는 정보를 서버로 넘겨준다.
 - 웹 브라우저에는 히든 필드가 보이지 않으므로 사용자는 그 정보를 알 수 없다.
 - 하지만 [로그인] 버튼을 클릭하면 입력한 정보와 함께 히든 필드의 내용이 서버로 함께 전송된다.
 
 ```html
 <fieldset>
      <input type="hidden" name="url" id="url" value="사이트를 통한 직접 로그인">
    	<label>아이디: <input type="text" id="user_id" size="10"></label>
      <label>비밀번호: <input type="password" id="user_pw" size="10"></label>
      <input type="submit" value="로그인">
 </fieldset>
 ```
 ![image](https://github.com/Seonghyun-Park/Web/assets/121333241/b50e0e37-5aca-4a48-8214-5afcdbeb73db)
