# 전체 커리큘럼 개요 (48주)

## 프로그램 정보
- **시작일**: 2026-03-18
- **총 기간**: 48주 (12개월)
- **현재 진행**: Week 1 (Month 1 시작)
- **방법론**: 프로젝트 기반 학습 (PBL) + 스프린트 주기 + 코드 리뷰

## 분기별 구조 (Quarterly Structure)

### Quarter 1: 기초 다지기 (개월 1-3, Week 1-12)
목표: 프론트엔드 + 백엔드 기초 완성

**Month 1: Web Fundamentals** (Week 1-4)
- Semantic HTML, CSS Box Model
- Flexbox, Grid, Responsive Design
- JavaScript ES6+, DOM 조작
- Async/await, Fetch API
- **최종 산출물**: 정적 포트폴리오 사이트

**Month 2: Modern Frontend** (Week 5-8)
- React 18, Hooks (useState, useEffect, useReducer)
- React Context, Custom Hooks
- React Router v6
- TypeScript 기본
- **최종 산출물**: React Todo 앱 (TypeScript)

**Month 3: Backend Fundamentals** (Week 9-12)
- Node.js, Express.js
- RESTful API 설계
- Error handling, Validation (Zod)
- JWT Authentication, 파일 업로드
- **최종 산출물**: 블로그 백엔드 API (회원, 글, 댓글)

---

### Quarter 2: 풀스택 통합 (개월 4-6, Week 13-24)
목표: Next.js + DB + 인증 통합 풀스택

**Month 4: Database & ORM** (Week 13-16)
- SQL 기본 (SELECT, JOIN, GROUP BY)
- PostgreSQL 설치 및 설정
- Prisma Schema 설계, 관계 설정
- Prisma CRUD, N+1 문제 해결
- **최종 산출물**: Todo Fullstack (React + Express + PostgreSQL)

**Month 5: Next.js Mastery** (Week 17-20)
- Next.js 14 App Router
- Server Components, 데이터 fetching
- Client Components, hydration
- Route Handlers (API Routes)
- NextAuth.js 인증
- **최종 산출물**: 기술 블로그 (Markdown → SSR)

**Month 6: Fullstack Integration** (Week 21-24)
- Next.js + API Routes 통합
- 환경변수 관리, Vercel 배포
- Docker Compose로 로컬 환경
- GitHub Actions CI/CD 파이프라인
- **최종 산출물**: 이커머스 MVP (상품, 장바구니, 주문)

---

### Quarter 3: 실전 심화 (개월 7-9, Week 25-36)
목표: 결제, 실시간, 테스트 전문성

**Month 7: Payment Integration** (Week 25-28)
- Stripe 기본 개념, 테스트 계정
- Payment Element 구현
- Webhook 처리 (서명 검증)
- Stripe Subscription (구독)
- 국내 PG (Toss Payments) 연동
- **최종 산출물**: 유료 콘텐츠 플랫폼 (Stripe + 국내 PG)

**Month 8: Real-time & Performance** (Week 29-32)
- WebSocket 기본
- Socket.IO 실시간 채팅
- Redis Pub/Sub
- 이미지 최적화, CDN (Cloudflare)
- **최종 산출물**: 실시간 협업 툴 (채팅 + 코드 에디터)

**Month 9: Testing & Quality** (Week 33-36)
- Jest/Vitest 단위 테스트
- React Testing Library
- API 테스트 (Supertest)
- Playwright E2E 테스트
- ESLint, Prettier, Husky (코드 품질 자동화)
- **최종 산출물**: 테스트 커버리지 90%+ 프로젝트

---

### Quarter 4: 전문가 및 취업 준비 (개월 10-12, Week 37-48)
목표: DevOps 전문성 + 포트폴리오 완성 + 취업 준비

**Month 10: DevOps & Scalability** (Week 37-40)
- Dockerfile 최적화 (multi-stage build)
- Docker Compose 프로덕션
- AWS/GCP 클라우드 배포
- 모니터링 (Sentry, LogRocket)
- 성능 최적화 (Lighthouse 90+)
- **최종 산출물**: 클라우드 배포 완료 (CI/CD + 모니터링)

**Month 11: Microservices & Advanced Patterns** (Week 41-44)
- 모노리스 vs 마이크로서비스 설계
- API Gateway 패턴 (Kong/Express Gateway)
- RabbitMQ/Kafka basics
- 캐싱 전략 (Redis), OpenTelemetry 분산 추적
- **최종 산출물**: 마이크로서비스 기반 플랫폼 (3+ 서비스)

**Month 12: Portfolio & Career Prep** (Week 45-48)
- GitHub 프로필 최적화
- Next.js 포트폴리오 사이트 제작
- 기술 블로그 12개 글 완성
- 한국어/영어 이력서 작성
- 기술 면접 준비 (코딩 테스트, 시스템 설계)
- **최종 산출물**: Fullstack Portfolio Pack

---

## 기술 스택 (2026년 기준)

```
📱 프론트엔드
├── HTML5, CSS3 (Flexbox, Grid)
├── JavaScript ES6+
├── React 18+ (Hooks, Server Components)
├── TypeScript
├── Next.js 14+ (App Router)
├── Tailwind CSS
└── Zustand / Redux Toolkit

🖥️ 백엔드
├── Node.js (v18+)
├── Express.js / NestJS
├── RESTful API / GraphQL
├── NextAuth.js (Auth.js)
├── Socket.IO
└── JWT, OAuth2

💾 데이터베이스
├── PostgreSQL (SQL)
├── Redis (Cache, Pub/Sub)
└── Prisma (ORM)

⚙️ DevOps & 클라우드
├── Docker, Docker Compose
├── GitHub Actions (CI/CD)
├── Vercel / AWS / GCP
├── Nginx
├── Sentry (에러 추적)
└── Lighthouse (성능)

💳 결제 시스템
├── Stripe (글로벌)
└── Toss Payments, KG엔파이 (국내)

🔍 테스트
├── Jest / Vitest
├── React Testing Library
├── Supertest
├── Playwright (E2E)
└── ESLint, Prettier, Husky
```

---

## 주별 학습 사이클

```
주 1 (월-일):
├─ 월요일: 이번 주 목표 설정 + 학습 내용 확인
├─ 화-목: 집중 코딩 (Pomodoro: 25min × 4 = 2시간 × 3 = 6시간/일)
├─ 금요일: 코드 리뷰 + 리팩토링 + 주간自我평가
├─ 토요일: 프로젝트 집중 (6-8시간)
└─ 일요일: 회고 + 다음 주 계획 (2시간)

총 주당 목표 시간: 25-30시간
```

## 성공을 위한 핵심 원칙

1. **꾸준함 > 완벽함**: 매일 2시간이라도 코딩
2. **실습 > 이론**: "만들면서 배우기"
3. **공유 > 독백**: GitHub, 블로그에 공유
4. **질문 > 막힘**: 2시간 막히면 질문
5. **복습 > 새로운 것**: 주 1회 복습 필수

---

## 월간 진행 현황 추적

| 월 | 주차 | 상태 | 시작일 | 완료일 | 총시간 | 점수(1-10) | 비고 |
|---|------|------|--------|--------|--------|-------------|------|
| 1 | 1-4 | 진행 중 | 3/18 | - | - | - | Week 1 시작 |
| 1 | 1 | 완료 | 3/18 | 3/24 | - | - | Semantic HTML |
| ... | ... | ... | ... | ... | ... | ... | ... |

---

## 참고 및 연락

- **GitHub**: [링크]
- **기술 블로그**: [링크]
- **커뮤니티**: [OKKY, Reddit, Discord]

---

**다음 단계**: [Week 1 상세](./week-1.md)로 이동
