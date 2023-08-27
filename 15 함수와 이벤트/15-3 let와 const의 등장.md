### let을 사용한 변수의 특징

- ES6에서는 변수를 선언하기 위한 예약어로 let와 const가 추가되었고, 되도록이면 var 예약어는 사용하지 않을 것을 권장한다.
- var는 함수 영역(레벨)의 스코프를 가지지만
- let와 const는 블록 영역의 스코프를 가진다.

#### 블록 안에서만 쓸 수 있는 변수

- let 예약어로 선언한 변수는 변수를 선언한 블록({ }로 묶은 부분)에서만 유효하고 블록을 벗어나면 사용할 수 없다.

```html
<body>
  <script>
    function calcSum(n) {
      let sum = 0; // sum은 calcSum()의 블록({}) 안에서만 사용할 수 있다.
      for(let i = 1; i < n + 1; i++) {	// 변수 i는 for문을 벗어나면 사용할 수 없다.
        sum += i;	
      }      
      console.log(sum);
    }    
    calcSum(10);    
  </script>
</body>
```

![image](https://github.com/Seonghyun-Park/Web/assets/121333241/344d58bd-c042-4ae6-8d16-b7fce9035633)

- 전역 변수를 선언하고 싶다면 let 예약어를 쓰지 않고 변수 이름과 초깃값만 할당하면 된다.

```html
<body>
  <script>
    function calcSum(n) {
      sum = 0; // 전역 변수 선언
      for(let i = 1; i < n + 1; i++) {						
        sum += i;	
      }            
    }    
    calcSum(10);    
    console.log(sum);
  </script>
</body>
```
![image](https://github.com/Seonghyun-Park/Web/assets/121333241/344d58bd-c042-4ae6-8d16-b7fce9035633)

#### 재할당은 가능하지만 재선언은 할 수 없는 변수

- let 예약어를 사용하여 선언한 변수는 값을 재할당할 수는 있지만 변수를 재선언할 수는 없다.

```html
<body>
  <script>
    function calcSum(n) {
      let sum = 0;
      for(let i = 1; i < n + 1; i++) {						
        sum += i;	
      }      
      sum = 100; // sum 변수에 값 100을 재할당한다.
      console.log(sum);
    }    
    calcSum(10);    
  </script>
</body>
```
![image](https://github.com/Seonghyun-Park/Web/assets/121333241/32b6c2e0-cb52-403a-b70e-33de85871d6f)

- 블록 변수 sum 재선언

```html
<body>
  <script>
    function calcSum(n) {
      let sum = 0;
      for(let i = 1; i< n + 1; i++) {						
        sum += i;	
      }      
      let sum; // sum 변수 재선언 (sum이 중복으로 선언되었다는 메시지가 나타난다.)
      console.log(sum);
    }    
    calcSum(10);    
  </script>
</body>
```
![image](https://github.com/Seonghyun-Park/Web/assets/121333241/83c797c3-75a6-4cad-95a9-a03b0a91d38e)

#### 호이스팅이 없는 변수

- let 에약어를 사용한 변수는 선언하기 전에 사용할 경우 오류 메시지를 나타낸다.

```html
<body>
  <script>		 
    var x = 10;

		function displayNumber() { 								
      console.log("x is " + x); // 변수 y를 초기화하기 전에 사용할 수 없다.
      console.log("y is " + y); 
      let y = 20;
		}
    displayNumber();
  </script>
</body>
```
![image](https://github.com/Seonghyun-Park/Web/assets/121333241/57d4f6d5-a450-407d-9f3f-775410701ab4)

### const를 사용한 변수의 특징

- const로 선언한 변수는 상수 변수이다.
- 변하지 않는 값을 변수로 선언할 때 에약어 const를 사용한다.
- 프로그램 안에서 특정한 상숫값을 자주 사용한다면 변수에 담아서 사용하는 것이 편하다.
- const로 할당한 변수는 재선언하거나 재할당할 수 없으며, let 예약어를 사용한 변수처럼 블록 레벨의 스코프를 가진다.

```html
<body>
  <script>
    const currentYear = 2020;
    console.log(currentYear);
    const currentYear; // currentYear 변수 재선언
    console.log(currentYear);
  </script>
</body>
```
![image](https://github.com/Seonghyun-Park/Web/assets/121333241/93cc21fb-5b30-493c-850b-e25ac8c42173)

- const를 사용해 이미 값을 지정한 변수에 새로운 값을 할당할 수도 없다.

```html
<body>
  <script>
    const currentYear = 2020;
    console.log(currentYear);
    currentYear = 2100; // currentYear 변수 재할당
    console.log(currentYear);
  </script>
</body>
```
![image](https://github.com/Seonghyun-Park/Web/assets/121333241/425aa10f-9591-4008-a160-9e01e5c2d66c)

- 변수 때문에 생기는 오류를 줄이려면 let과 const를 사용하는 것이 좋다.
- 값이 자주 바뀌는 변수라면 **let 예약어**를 사용하고
- 재할당이 없는 변수라면 **const 예약어**를 사용한다.

### 자바스크립트 변수, 이렇게 사용하세요

#### 전역 변수는 최소한으로 사용합니다

- 전역 변수는 프로그램 어디서든 접근할 수 있으므로 편리하게 사용할 수 있다.
- 하지만 예상하지 못한 곳에서 값이 달라질 수 있다.
- 그만큰 오류가 발생할 확률이 높아지므로 전역 변수는 되도록이면 적게 사용하는 것이 좋다.

#### var 변수는 함수의 시작 부분에서 선언합니다

- var를 사용한 변수는 어디에서 선언하든 상관없지만 내부에서 호이스팅이 생기므로 오류가 발생할 수 있다.
- var 변수는 함수 시작 부분에 선언하는 것이 변수를 확인하기도 쉽고 오류를 줄이는 방법이다.

#### for 문에서 카운터 변수를 사용할 때는 var 예약어를 사용하지 않습니다

- for문의 카운터 변수는 for문 밖에서 선언하거나 아예 let를 사용해서 블록 변수로 선언하는 것이 좋다.

```js
// for문 밖에서 선언
var i;
for (i = 1; i <= n; i++) {
  ...
}

// let을 사용해서 블록 변수로 선언
for (let i = 1; i <= n; i++) {
  ...
}
```

#### ES6를 사용한다면 예약어 var보다 let를 사용하는 것이 좋다.

- 간혹 여러 사람이 작성한 프로그램을 합치다 보면 변수가 중복될 수도 있는데 이럴 경우 문제가 발생한다.
- 이럴 때 재선언할 수 없는 let를 사용하는 것이 좀 더 안전하다.