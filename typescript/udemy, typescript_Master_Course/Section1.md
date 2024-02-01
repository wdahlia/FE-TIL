
# Section1 TypeScript 개요
<br>

```javascript

console.log(null * 213); // null에 숫자 곱해도 error 발생 ❌ 0 출력
console.log(undefined * 8976); // undefined에 숫자 곱해도 error 발생 ❌ NaN(Not A Number) 출력]

const obj = { width: 832, height: 900 };
console.log(obj.heighth); 
// 객체 프로퍼티 접근 시에도 존재하지 않는 프로퍼티에 접근해도 error 발생 ❌ undefined 출력

```

- 자바스크립트 코드의 특징은 Error가 발생해야 할 상황에도 에러가 발생하는 것이 아닌, 값을 반환
- 이는 프로젝트의 규모가 커지면 커질 수록 디버깅에 어려움을 유발하게 됨

<br>

`Why? 왜 자바스크립트는 이러한 문제가 존재할까` 

- 애초에 자바스크립트 자체는 브라우저 스크립팅 기능 추가를 위한 몇 주안에 만들어진 프로젝트
- 널리 사용 할 것을 예상하고 만든 프로젝트가 아님
- 오류를 방지 할 수 있는 도구의 필요성이 확대됨 => 그래서 등장한 것이 **`TypeScript`**
- **TypeScript**는 JavaScript에 *타입 시스템*이 붙은 것

<br>


### Type 시스템

정적 타입 검사기로서, 코드를 실행하기 전에 프로그램 데이터의 종류나 타입 검사를 실행하여 오류를 알려주는 것

- 실행 전 개발 단계에서 오류를 잡아주기 때문에 수정 후, 자바스크립트로 컴파일 진행하면 됨