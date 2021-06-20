## 타입
- 튜플
배열에서 타입의 순서를 정의할 수 있다.
  ```typescript
  const array: [string, number] = ["hi", 1];
  ```
- 객체
  ```typescript
  const obj: object = {};
  const person: {name: string; age: number} = {
    name: "minseok",
    age: 28
  }
  ```

- Boolean값
  ```typescript
  const show: boolean = false;
  ```

- 함수
  
  아래와 같은 경우에 ts lang server가 type 추론을 통해 함수의 반환값 타입을 number로 해줌
  ```typescript
  function sum(a: number, b: number){
    return a+b;
  }
  ```
  아래와 같이 반환 type도 정의해줄 수 있음
  ```typescript
  function sum(a: number, b: number): number{
    return a+b;
  }
  ```
  함수의 옵셔널 파라미터를 이용하기 위해 parameter 뒤에 ?를 붙여주면 꼭 전달하지 않아도 되는 파라미터가 된다.
  ```typescript
  function log(a: number, b?: number): number{
    console.log()
  }
  ```

## 인터페이스

- 변수 인터페이스
  ```typescript
  interface User {
    name: string;
    age: number;
  }
  ```

- 함수 구조를 정의하는 인터페이스

  아래와 같은 방식은 라이브러리를 만들 때 함수 형식을 잡을 때 유용하다.
  ```typescript
  interface sumFunction {
    (a: number, b: number): number;
  }

  var func: sumFunction;
  func = function(a: number, b: number): number {
    return a+b;
  }
  ```
- 인덱싱 
  ```typescript
  interface stringArray {
    [index: number]: string
  }

  var arr: stringArray = [1, 2, 3];
  ```
- 인터페이스 확장
  ```typescript
  interface Person {
    name: string;
    age: number;
  }

  interface Developer {
    name: string;
    age: number;
    skills: string[];
  }
  //위와 동일
  interface Developer extends {
    skills: string[];
  }
  ```