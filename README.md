# JS AMAZONA CLONE PROJECT

# 설명 

## Vanilla JS & MongoDB & express를 이용한 ECommerce Site 프로젝트 (아마존 참고)

# 프로젝트 구조 


# 스크린샷









# history

1. record
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
    17. localStorage.js
        - 브라우저 localStorage에 카트에 담을 정보 set & get 기능, 사용자 정보 set & get 삭제 기능 작성 
        - 배송정보(Shipping), 구매정보(Payment) 추가
    18. Token 인증 타입 Bearer 사용
        - access token 서버에 제출해서 인증을 해야한다 -> 이때 인증 방법이 Bearer Authentication이다.
        - Bearer - JWT 혹은 OAuth에 대한 토큰을 사용한다.(토큰요청헤더 Authorization필드의 타입)
        - 사용시 header과 아닌 headers를 사용해야 오류가 안 난다.
    19. Checkout-wizard -> 결제 기능 구현
        - 1단계 : (signin)로그인 완료 
        - 2단계 : (shipping) 배송정보 입력
        - 3단계 : (payment) 결제 paypal
        - 4단계 : (place order) 주문화면
        - Checkoutsteps component 생성
        - redirectUser() -> cart에 상품이 있을경우 shipping화면으로 , 상품이 없을 경우 메인화면으로 이동
    20. HTTP - respomse code
        - 200 => "OK"
        - 201 => "Created"
        - backend > routers > orderRouter.js -> res.status를 201로 보냈기 때문에 
        - frontend > src > api.js > createOrder에서 
        ```js
        if (response.statusText !== 'Created') {
            throw new Error(response.data.message);
        }
        ```
        statusText code를 Created로 체크한다.
    21. data의 id 형식은 24자리의 16진수여야 합니다.
        - MongoDB 에서는 데이터가 쌓일 경우, 그 데이터 하나하나를 document라고 하며 document는 ObjectId를 가진다.
        - ObjectId는 16진수 24자리로 이루어져 있다.
