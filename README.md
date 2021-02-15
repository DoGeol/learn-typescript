# Typescript

1. 타입 스크립트란?

   - 자바스크립트에 타입을 부여한 수퍼셋(super set) 언어

   - 사용하는 이유

     1. 에러의 사전 방지

     2. 코드 가이드 및 자동 완성(개발 생산성 향상)

        - apps.js

          ```javascript
          // JSDoc을 이용하여 프로퍼티를 사전 정의하여 노출
          
          /**
           * @typedef {object} Address
           * @property {string} city
           * @property {string} street
           */
          
          /**
           * @typedef {object} User
           * @property {string} name
           * @property {string} email
           * @property {Address} address
           */
          
          /**
           * @returns {Promise<User>}
           */
          
          function fetchUser() {
            return axios.get(url);
          }
          
          fetchUser().then(function(response) {
            response.address.street
          })
          ```

        - sample.ts

          ```typescript
          function add(a: number, b: number): number {
              return a + b;
          }
          
          var result = add(10, 20);
          
          // Type 지정으로 자동완성 기능에서 Number 타입에서 사용 가능한 메소드들이 노출됌.
          result.toLocaleString();
          ```

        - sample.js

          ```javascript
          //@ts-check
          /**
           * 
           * @param {number} a 첫번째 숫자
           * @param {number} b 두번째 숫자
           */
          function sum (a, b) {
              return a + b;
          }
          
          sum(10, '20');
          ```

2. 타입스크립트 사용 방법

   - npm install -g typescript

     - npm 12 버전 이상
     - tsc [파일 이름]

   - 설정

     - tsconfig.json

       ```json
       {
           // 컴파일러 옵션
           "compilerOptions": {
               // javascript 사용
               "allowJs": true,
               // @ts-check 옵션
               "checkJs": true,
               // 값이 없을 경우 any를 넣어주는 설정
               "noImplicitAny": true
           }
       }
       ```