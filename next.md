Next.js

```
project-root/
├── app/                           # App Router 기본 디렉토리
│   ├── api/                       # API 라우트
│   │   └── route.ts
│   ├── favicon.ico                # 파비콘
│   ├── globals.css                # 전역 스타일 (Tailwind 포함)
│   ├── layout.tsx                 # 루트 레이아웃
│   └── page.tsx                   # 홈페이지
│
├── components/                    # 재사용 가능한 컴포넌트
│   ├── ui/                        # UI 컴포넌트
│   └── common/                    # 공통 컴포넌트
│
├── lib/                           # 유틸리티 및 헬퍼 함수
│   ├── db.ts                      # 데이터베이스 연결
│   └── utils.ts                   # 일반 유틸리티 함수
│
├── types/                         # TypeScript 타입 정의
│   └── index.ts                   # 공통 타입 내보내기
│
├── prisma/                        # Prisma ORM 관련 파일
│   ├── schema.prisma              # 데이터베이스 스키마
│   └── migrations/                # 마이그레이션 파일
│
├── public/                        # 정적 파일
│
├── middleware.ts                  # Next.js 미들웨어
├── next.config.js                 # Next.js 설정
├── package.json                   # 의존성 및 스크립트
├── postcss.config.js              # PostCSS 설정 (Tailwind용)
├── tailwind.config.ts             # Tailwind CSS 설정
└── tsconfig.json                  # TypeScript 설정
```

next 프로젝트 시작

- npx create-next-app@latest 폴더명
- cd 폴더명
- npm run dev => 시작
- ctrl + c => 종료

디렉터리 구조
.next => 서버라인
app : 최상위 디렉터리 애플리케이션의 모든 경로, 라우트를 관리한다.
app/api : API의 엔드포인트를 정의하는데 사용(DB 연결)
app/api/[경로폴더]/route.ts : 연결 파일
ex) app/api/user/route.ts => /user 로 데이터를 보낼 때

app/page.tsx : APP.js와 같은 메인페이지 ( / 경로 )
app/layout.tsx : 최상위 레이아웃 결정 (모든 페이지에 적용)
app/type/type.ts : 타입스크립트에서 사용할 타입 정의
app/lib 폴더 : DB연결 설정, 서버 설정 전반적인 설정값을 저장

- 정적라우팅 : 경로의 폴더명으로 연결
  app/[경로폴더]/page.tsx : 연결 페이지 컴포넌트
  ex) app/user/login/page.tsx => /user/login 로 연결

- 동적라우팅 : [id] 대괄호 표기법을 통한 동적 세그먼트를 정의
  app/board/[id]/page.tsx => /board/1, /board/6

app > layout.tsx => body > {children}

- JavaScript => ajax(Asynchronous Javascript And Xml) => fetch
- React => axios라이브러리 설치 => node.js와 브라우저를 위한 Promise API를 활용하는 HTTP 통신 라이브러리이다.
  외부 api를 가져올 때 사용하는 라이브러리
- Next.js => ajax 내장 => fetch 가능(내부서버연결용 DB). axios 추가 설치도 가능(외부 API 연결용)

설치
npm i axios

---

useState(), useReducer() : 상태 관리, 상태 업데이트 훅
useReducer() : 주로 복잡한 상태관리 로직을 다루거나 여러 컴포넌트 간의 상태를 공유할 때 사용
const [state, dispatch] = useReducer(reducer, initialState)

- state : 상태를 관리할 변수 명
- dispatch : state 변경시 필요한 정보를 전달하는 함수
- reducer : dispatch를 확인해서 state를 변경해주는 함수
- initialState : state의 초기값

---

next.js 서버 <-> mysql DB

- npx create-next-app@latest next-board
- cd next-board
- npm i mysql2




