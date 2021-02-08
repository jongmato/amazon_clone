# JS AMAZONA CLONE PROJECT

## Vanilla JS & MongoDB & express를 이용한 ECommerce Site (아마존)

1. 폴더 구조
    1. jsamazona root 폴더 생성
    2. frontend & backend 폴더 생성 (프론트 백 구분)
    3. frontend 폴더에 src 폴더 생성
    4. src폴더 > 프론트단 구성 파일 
    5. frontend 폴더 > screen폴더 > view 파일
    6. frontend 폴더 > images폴더 > 프로젝트에서 사용하는 이미지 
    7. frontend 폴더 -> axios(HTTP 비동기 통신 라이브러리)사용
    8. frontend 폴더 -> package.json ->webpack 사용
        - app.js -> index.js로 이름 변경 (webpack에서 index.js를 main.js로 변환)
    9. utils.js ->  parseRequestURL(), Indicator(로딩바) 구성
    10. index.js -> router, routes 
    11. root jsamazona folder > backend 폴더 생성
    12. root jsamazona folder -> package.json -> express, babel, nodemon 사용
        - babel(자바스크립트 컴파일러) : 최신문법(es6 이상)을 브라우저에서 사용가능한 하위 버전으로 바꿔준다(es5이하)
        - 따라서 backend 폴더 > server.js에서 require()대신 import from 구문 사용
    13. eslint airbnb-base사용
    14. mongoDB 설치 (DB->mongodb사용)
    15. npm install mongoose dotenv
        - mongoose : MongoDB ODM(Object Document Mapping -> 객체(Javascript)와 문서(MongoDB)를 1대1 매칭)
        - dotenv : DB관련 정보 등 보안이 필요한 정보를 외부 파일로(환경변수 파일 -> .env)만들어 관리하는 페키지 
    16. npm install body-parser express-async-handler jsonwebtoken  
        - body-parser : API 요청(POST, PUT)에서 받은 body(req.body) 값을 파싱하는 역할을 수행하는 미들웨어
        - express-async-handler : express router에서 async 함수를 호출할 때 오류가 발생함 -> router에서 async/await 사용하기위한 wrapper 라이브러리
        - jsonwebtoken : 정보를 JSON객체 형태로 주고 받기 위한 표준규약에 따라 생성한 암호화된 문자열(토큰) 회원인증에서 사용