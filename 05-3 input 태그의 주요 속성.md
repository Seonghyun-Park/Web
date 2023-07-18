### 자동으로 입력 커서를 갖다 놓는 autofocus 속성

 - 페이지를 불러오자마자 폼에서 원하는 요소에 마우스 포인터를 표시할 수 있다.

 ```html
 <input type=텍스트-입력-필드 autofocus required>
 ```

### 힌트를 표시해 주는 placeholder 속성

 - 사용자가 텍스트를 입력할 때 입력란에 적당한 힌트 내용을 표시해서 그 필드를 클릭하면 내용이 사라지도록 만든다. 
 - 이렇게 하면 텍스트 필드 앞에 제목을 사용하지 않고도 사용자에게 해당 필드에 어떤 내용을 입력해야 할지 알려 줄 수 있어서 편리하다.

 ---
 - autofocus 속성을 사용해 웹 문서를 불러오자마자 '이름'옆의 텍스트 필드에 입력 커서가 표시되도록 한다.
 - placeholder 속성을 사용해 '연락처' 필드에 힌트를 표시한다.

 ```html
 <label for="user-name">이름</label>
 <input type="text" id="user-name" autofocus required>
 ...
 <label for="phone">연락처</label>
 <input type="tel" id="phone" placeholder="하이픈 빼고 입력해 주세요.(01012345678)">
 ```
 ![image](https://github.com/Seonghyun-Park/Web/assets/121333241/9e37d335-5017-4b7a-839d-b68b3bd0dc46)

### 읽기 전용 필드를 만들어 주는 readonly 속성

 - 사용자가 입력하지는 못하고 읽게만 하는 읽기 전용 필드를 만들 수도 있다.
 - readonly 속성은 해당 필드를 읽기 전용으로 바꾼다.
 - 텍스트 필드나 텍스트 영역에 내용이 표시되어 있어도 사용자는 그 내용을 볼 수만 있고 입력은 할 수 없다.

 ```html
 <input type=텍스트-입력-필드 readonly>
 ```

### 필수 입력 필드를 지정하는 required 속성

 - 반드시 입력해야 하는 내용에는 required 속성을 지정해 필수 필드로 만들 수 있다.

 ---
 - 주문 상품을 readonly 속성을 사용해 읽기 전용으로 만든다.
 - '이름', '배송주소', '연락처'를 필수 필드로 지정
 
 ```html
 <form>
  <fieldset>
    <legend>배송정보</legend>
    <ul id="shipping">
      <li>
        <label for="prod">주문상품</label>
        <input type="text" id="prod" value="상품용 3KG" readonly>
      </li>
      <li>
        <label for="user-name">이름</label>
        <input type="text" id="user-name" autofocus required>
      </li>
      <li>
        <label for="addr">배송주소</label>
        <input type="text" id="addr" required>
      </li>
      <li>
        <label for="mail">이메일</label>
        <input type="email" id="mail">
      </li>
      <li>
        <label for="phone">연락처</label>
        <input type="tel" id="phone" placeholder="하이픈 빼고 입력해 주세요.(01012345678)" required>
      </li>
      <li>
        <label for="d-day">배송 지정</label>
        <input type="date" id="d-day"> <small>(주문일로부터 최소 3일 이후)</small>
      </li>
    </ul>
  </fieldset>
  <div>
    <input type="submit" value="주문하기">
    <input type="reset" value="취소하기">
  </div>
 </form>
 ```
 ![image](https://github.com/Seonghyun-Park/Web/assets/121333241/a9b4c3b4-0872-456c-9c03-38bd28a9bb4b)

### 실습

```html
<body> 
    <div id="container">
      <h1>회원 가입을 환영합니다</h1>
      <form>
        <fieldset>
          <legend>사용자 정보</legend>    
          <ul>
            <li>
              <label for="uid">아이디</label>
              <input type="text" id="uid" autofocus placeholder="4자~10자 사이, 공백없이" required> 
            </li>
            <li>
              <label for="umail">이메일</label>
              <input type="email" id="umail" required> 
            </li>
            <li>
              <label for="pwd1">비밀번호</label>
              <input type="password" id="pwd1" placeholder="문자와 숫자, 특수 기호 포함" required> 
            </li>        
            <li>
              <label for="pw2">비밀번호 확인</label>
              <input type="password" id="pwd2" required> 
            </li>
          </ul>      
        </fieldset>
        <fieldset>
          <legend>이벤트와 새로운 소식</legend>
          <input type="radio" name="mailing" id="mailing_y" value="mailing_yes">
          <label for="mailing_y">메일 수신</label>
          <input type="radio" name="mailing" id="mailing_n" value="mailing_no" checked>
          <label for="mailing_n">메일 수신 안 함</label>     
        </fieldset>
        <div id="buttons">
          <input type="submit" value="가입하기">
          <input type="reset" value="취소">
        </div>
      </form>
    </div>           
  </body>
```
![image](https://github.com/Seonghyun-Park/Web/assets/121333241/3344bc1f-8474-48db-86a6-693131088dfe)
![image](https://github.com/Seonghyun-Park/Web/assets/121333241/4d255fa9-a094-46b2-99d0-a2af59da00f7)