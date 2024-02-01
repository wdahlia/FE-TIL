# Type Annotation
<br>

- 변수 뒤에 `:` 콜론을 적고 타입을 적는 방법
- 명시적으로 표현할 수 있는 방법


```typescript

// string

let movieTitle : string = "Monster";
movieTitle = "Mommy";
movieTitle = 9; // 🔧 string이 입력 되어야하는데 number가 들어왔다고 오류가 발생했음을 알려줌

movieTitle.upper();

// 🔧 문자열 타입에 쓸수 없는 메서드나 프로퍼티를 쓰면 오류 표시
// python에 있는 메서드의 값이기 때문에 쓸수 없음

movieTitle.toUpperCase(); // 오류 없이 사용 가능



// number

let numCar : number = 9;
numCar += 1; // 오류 없이 증감 연산 가능
numCar = "carNumber"; // 컴파일은 정상 작동 하나, number가 입력 되어야 하는데 string이 입력 되었다고 오류 발생


// boolean

let gameOver : boolean = false;
gameOver = true; // 오류 없이 가능
gameOver = "true" // 🔧 boolean이 입력 되어야 하는데 string이 입력 되었다고 오류 발생


// bigInt, Symbol도 사용 가능하나, 주로 string, number, boolean 사용

```


- 해당 코드들에서 오류가 발생 하더라도 js 컴파일 오류가 나지는 않음 
- 컴파일은 정상 작동 하나, 터미널을 통해 어디에 어떤 문제가 있는지를 명확하게 설명해준다.

<br>

### Type Inference

<br>

- Type Annotation은 타입을 처음 배우고 파악 할 시에 좋은 도구이지만, 실제로 변수 작성 시에는 타입 추론을 사용하면 된다.
- TypeScript는 변수 선언을 통해 어떤 값이 할당 되었는지를 파악 가능
- Type Annotation이 필요한 경우도 분명 존재하지만(문자열 배열 타입 등.), 대부분은 추론 가능

<br>

```typescript
let tvShow = "Selling Sunset";
// 이때 tvShow에 마우스 호버 시 자동으로 string으로 타입 추론 된 것을 확인 할 수 있다.

tvShow = false; // 🔧 string인데 boolean 입력 되었다고 오류 발생
```
<br>

### Any
<br>

- JavaScript에 없고 **TypeScript에만** 있는 타입
- `any`는 말 그대로 어떤 타입도 받을 수 있음
<br>


```typescript

let thing: any = "hello";
thing = 1;
thing = false;
thing();
thing.toUpperCase();

// 모두 타입 체크를 하지 않음

```

<br>

`참고`
- 타입 스크립트에서 타입 추론을 해주는데 왜 **Type Annotation**이 필요한가? `암묵적 any` 때문

```typescript
const movieArray = ["Monster", "Star Is Born", "NottingHill", "Harry Potter"];
let favoriteMovie; // 이 때, favoriteMovie에 마우스를 호버 하면 any로 할당 되어 있는 것을 확인할 수 있음

for (movie of movieArray) { 
  if (movie === "Harry Potter") {
    favoriteMovie = "Harry Potter";
  }
}

// 이 경우 favoriteMovie가 any이기 때문에

favoriteMovie();
favoriteMovie.ddafasdfasf();

// 사용해도 타입 에러가 나지 않음
// favoriteMovie에 명시적으로 Type Annotation을 해주어야 하는 이유
// let favoriteMovie : string;

```

- 값을 할당하지 않고 선언만 하게 되면, 암묵적으로 type은 any가 되게 되고, 이 때문에 함수가 아님에도 함수 선언, 메서드 사용에 오류가 발생하지 아니함
- 다만, string이 할당이 되어 있기 때문에, 원래는 되지 않아야 하는게 맞는것 따라서, 이 경우에는 string으로 타입 명시를 해주어야함