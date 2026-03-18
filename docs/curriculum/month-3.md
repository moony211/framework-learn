# Month 3: Backend Fundamentals (Week 9-12)

## 📅 기간: Week 9-12 (2026-05-14 ~ 2026-06-09)

## 🎯 월간 목표
- Node.js와 Express.js로 RESTful API 구축
- JWT 인증 구현
- 입력값 검증 (Zod)
- 파일 업로드 처리
- **최종 산출물**: 블로그 백엔드 API (회원, 글, 댓글 CRUD)

---

## 📊 주별 상세

### Week 9: Node.js & Express Basics
**학습 목표**: Node.js 모듈, npm, Express 라우팅
**과제**: 간단한 미들웨어 logger 작성
**시간**: 25-30시간

#### 핵심 내용
- CommonJS vs ES Modules
- npm 패키지 관리
- Express 기본 (app, request, response)
- 미들웨어 개념 및 작성
- 라우팅 (라우트 파라미터, 쿼리 파라미터)

#### 과제
1. 간단한 서버 (`app.listen(3000)`)启动
2.logger 미들웨어 작성 (request method, URL, response time 로깅)
3. CRUD API 기초: Post (메모) 생성/조회/수정/삭제

---

### Week 10: RESTful API Design
**학습 목표**: RESTful API 설계 원칙, HTTP 상태코드
**과제**: CRUD API (메모장) 완성
**시간**: 25-30시간

#### 핵심 내용
- RESTful API 원칙 (Resource, HTTP Method semantics)
- HTTP 상태 코드 (200, 201, 400, 401, 403, 404, 500)
- 요청/응답 구조 (JSON)
- 컬렉션/단일 리소스 라우팅

#### 과제
메모장 API (`/api/memos`):
```
GET    /api/memos          # 목록
POST   /api/memos          # 생성
GET    /api/memos/:id      # 상세
PUT    /api/memos/:id      # 수정
DELETE /api/memos/:id      # 삭제
```

#### 필수 요구사항
- 각 엔드포인트 올바른 HTTP method 사용
- 성공: 200/201, 실패: 4xx/5xx
- 응답 JSON 형식 일관성
- (선택) Pagination 구현

---

### Week 11: Error Handling & Validation
**학습 목표**: 에러 처리, 입력값 검증
**과제**: Zod/Joi를 활용한 검증 구현
**시간**: 20-25시간

#### 핵심 내용
- try-catch, error 다루기
- 커스텀 에러 클래스
- Zod schema 정의 및 validation
- HTTP 요청 파라미터, body 검증
- sanitization (XSS 방지)

#### 과제
1. `zod` 설치 및 schema 정의
2. 모든 POST/PUT 요청에 validation middleware 추가
3. 유효성 검사 실패 시 400 Bad Request 반환
4. 에러 응답 형식 일관성 유지

```typescript
// Zod schema 예시
const memoSchema = z.object({
  title: z.string().min(1).max(100),
  content: z.string().min(1),
});

// validation middleware
function validate(schema: z.Schema) {
  return (req: Request, res: Response, next: NextFunction) => {
    const result = schema.safeParse(req.body);
    if (!result.success) {
      return res.status(400).json({ errors: result.error.errors });
    }
    req.body = result.data;
    next();
  };
}
```

---

### Week 12: Authentication & File Upload
**학습 목표**: JWT 인증, 파일 업로드
**과제**: 회원가입/로그인 API + 이미지 업로드
**시간**: 25-30시간

#### 핵심 내용
- JWT (JSON Web Token) 개념
- Password hashing (bcrypt)
- 회원가입/로그인 flow
- Multer (파일 업로드 미들웨어)
-Protected routes (인증 필요 라우트)

#### 과제
1. **회원가입 API** (`POST /api/auth/register`)
   - 이메일, 비밀번호 입력
   - bcrypt로 비밀번호 해싱
   - DB에 사용자 저장
   - JWT 토큰 발급 (선택)

2. **로그인 API** (`POST /api/auth/login`)
   - 이메일/비밀번호 확인
   - JWT 토큰 발급
   - HTTP-only cookie or Authorization header

3. **파일 업로드 API** (`POST /api/upload`)
   - Multer 설정 (single file)
   - 파일 저장 (로컬 또는 S3)
   - 파일 URL 반환

4. **Protected Route**
   - JWT verification middleware
   - 인증 없이 접근 시 401 반환

---

## 📦 월간 프로젝트 (Month 3 Final)

### 프로젝트: 블로그 백엔드 API

**요구사항**:
- 회원 CRUD (회원가입, 로그인, 프로필 조회/수정)
- 글 CRUD (생성, 목록, 상세, 수정, 삭제)
- 댓글 CRUD
- JWT 인증 (로그인 필요 API)
- 파일 업로드 (프로필 이미지)
- API 문서화 (OpenAPI/Swagger)

**기술 스택**:
- Node.js + Express
- PostgreSQL + Prisma (Month 4에 추가)
- JWT (jsonwebtoken)
- bcrypt
- Zod (validation)
- Multer (file upload)

**API 명세 예시**:
```yaml
# 인증
POST   /api/auth/register    # 회원가입
POST   /api/auth/login       # 로그인
POST   /api/auth/logout      # 로그아웃

# 사용자
GET    /api/users/:id        # 프로필 조회
PUT    /api/users/:id        # 프로필 수정 (인증 필요)
POST   /api/users/:id/avatar # 프로필 이미지 업로드 (인증 필요)

# 글
GET    /api/posts            # 목록 (paginated)
POST   /api/posts            # 작성 (인증 필요)
GET    /api/posts/:id        # 상세
PUT    /api/posts/:id        # 수정 (작성자만)
DELETE /api/posts/:id        # 삭제 (작성자만)
GET    /api/posts?tag=react  # 태그 필터링 (선택)

# 댓글
GET    /api/posts/:id/comments
POST   /api/posts/:id/comments (인증 필요)
DELETE /api/comments/:id (작성자만)

# (선택) 좋아요
POST   /api/posts/:id/like (인증 필요)
DELETE /api/posts/:id/like (인증 필요)
```

**폴더 구조**:
```
blog-api/
├── src/
│   ├── routes/           # 라우트 정의
│   │   ├── auth.routes.ts
│   │   ├── user.routes.ts
│   │   ├── post.routes.ts
│   │   └── comment.routes.ts
│   ├── middleware/       # 미들웨어
│   │   ├── auth.ts       # JWT verification
│   │   ├── validation.ts # Zod validation
│   │   └── errorHandler.ts
│   ├── controllers/      # 요청 처리 로직 (선택)
│   ├── services/         # 비즈니스 로직 (선택)
│   ├── models/           # 데이터 모델 (Prisma之后)
│   ├── schemas/          # Zod schema
│   ├── utils/            # 헬퍼 함수
│   ├── types/            # TypeScript types
│   └── app.ts            # Express app 설정
├── .env
├── package.json
├── tsconfig.json
├── openapi.yaml (Swagger)
└── README.md
```

**API 문서화 (Swagger/OpenAPI)**:
- `swagger-jsdoc` + `swagger-ui-express` 설치
- `swagger.ts`에서 주석으로 API 문서 작성
- `/api-docs` 경로에서 문서 확인

```typescript
// swagger 설정
const swaggerJsdoc = require('swagger-jsdoc');
const swaggerUi = require('swagger-ui-express');

const swaggerDefinition = {
  openapi: '3.0.0',
  info: {
    title: 'Blog API',
    version: '1.0.0',
  },
};

const options = {
  swaggerDefinition,
  apis: ['./src/routes/*.ts'],
};

const swaggerSpec = swaggerJsdoc(options);
app.use('/api-docs', swaggerUi.serve, swaggerUi.setup(swaggerSpec));
```

---

## 📚 추가 학습 자료 (Month 3)

### Express.js
- [Express 공식 문서](https://expressjs.com/)
- [Express Generator (스캐폴딩)](https://expressjs.com/en/starter/generator.html)

### JWT
- [JWT 공식 사이트](https://jwt.io/)
- [Auth0: JWT 이해하기](https://auth0.com/learn/json-web-tokens/)

### Bcrypt
- [bcrypt npm](https://www.npmjs.com/package/bcrypt)
- [bcrypt Node.js 예제](https://www.npmjs.com/package/bcrypt#usage)

### Multer
- [Multer GitHub](https://github.com/expressjs/multer)

### API Design
- [REST API Tutorial](https://restfulapi.net/)
- [Microsoft REST API Guidelines](https://github.com/microsoft/api-guidelines)

---

## ✅ Month 3 완료 체크리스트

- [ ] Node.js + Express 서버 작성 가능
- [ ] RESTful API 설계 원칙 이해
- [ ] 미들웨어 작성 및 사용
- [ ] Zod/Joi validation 적용
- [ ] JWT 인증 구현 (회원가입/로그인)
- [ ] bcrypt로 비밀번호 해싱
- [ ] Multer 파일 업로드 구현
- [ ] 블로그 백엔드 API 완성
- [ ] API 문서 (Swagger) 작성
- [ ] 에러 처리 및 HTTP 상태 코드 올바른 사용

---

## 🎯 다음 월 (Month 4) 미리보기

**주제**: Database & ORM (PostgreSQL + Prisma)
**프로젝트**: Todo Fullstack (React 프론트 + Express 백엔드 + PostgreSQL DB)

주요 학습:
- SQL 기본 (SELECT, JOIN)
- PostgreSQL 설치 및 설정
- Prisma Schema 설계
- Prisma CRUD 연산
- N+1 문제 해결
