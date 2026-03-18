# 풀스택 개발자 마스터 프로그램 (12개월)

## 프로그램 개요

- **시작일**: 2026-03-18
- **총 기간**: 48주 (12개월)
- **목표**: 실제 서비스 배포 가능한 풀스택 개발자 양성
- **방법론**: 프로젝트 기반 학습(PBL) + 스프린트 주기 + 코드 리뷰

## 빠른 시작

### 1주차 (Week 1) - Web Fundamentals
- **학습 목표**: Semantic HTML, CSS Box Model
- **과제**: 개인 포트폴리오 사이트 (static)
- **시작하기**: [Week 1 상세 보기](./curriculum/week-1.md)

```bash
# 첫 걸음
npx create-next-app@latest my-app --typescript --tailwind --app
# 아직 Next.js는 나중에, 지금은 HTML/CSS 기초부터!
```

## 커리큘럼 구조

```
Quarter 1: 기초 다지기 (개월 1-3)
├── Month 1: Web Fundamentals (HTML/CSS/JS)
├── Month 2: Modern Frontend (React)
└── Month 3: Backend Fundamentals (Node.js/Express)

Quarter 2: 풀스택 통합 (개월 4-6)
├── Month 4: Database & ORM (PostgreSQL/Prisma)
├── Month 5: Next.js Mastery (App Router)
└── Month 6: Fullstack Integration (E-commerce MVP)

Quarter 3: 실전 심화 (개월 7-9)
├── Month 7: Payment Integration (Stripe/PG)
├── Month 8: Real-time & Performance (Socket.IO/Redis)
└── Month 9: Testing & Quality (Jest/Playwright)

Quarter 4: 전문가 및 취업 준비 (개월 10-12)
├── Month 10: DevOps & Scalability (Docker/Cloud)
├── Month 11: Microservices & Advanced Patterns
└── Month 12: Portfolio & Career Prep
```

## 핵심 기술 스택 (2026년)

### 프론트엔드
- HTML5, CSS3 (Flexbox, Grid)
- React 18+ (Hooks, Server Components)
- TypeScript
- Next.js 14+ (App Router)
- Tailwind CSS

### 백엔드
- Node.js (Express/NestJS)
- RESTful API / GraphQL
- JWT, OAuth2 (NextAuth.js)
- Socket.IO (실시간)

### 데이터베이스
- PostgreSQL (SQL)
- Redis (캐시, Pub/Sub)
- Prisma (ORM)

### DevOps & 클라우드
- Docker, Docker Compose
- GitHub Actions (CI/CD)
- Vercel, AWS, GCP
- Sentry, Lighthouse

### 결제 시스템
- Stripe (글로벌)
- Toss Payments, KG엔파이 (국내)

## 학습 방법

### 주간 사이클
```
월요일: 이번 주 목표 설정
화-목: 집중 코딩 (Pomodoro: 25min × 4)
금요일: 코드 리뷰 + 리팩토링
토요일: 프로젝트 집중 (6시간)
일요일: 회고 + 다음 주 계획
```

###自我평가 (매주 금요일)
- [ ] 학습 목표 달성
- [ ] 과제 완수
- [ ] 코드 품질 (커밋 메시지, 정리)
- [ ] 시간 투자 (최소 20시간)
- [ ] 질문/고민 정리

## 주요 산출물

### 프로젝트 (5개 이상)
1. 포트폴리오 웹사이트 (静态)
2. React Todo 앱
3. 블로그 백엔드 API
4. Todo Fullstack (React + Express + DB)
5. 기술 블로그 (Next.js)
6. 이커머스 MVP
7. 결제 플랫폼
8. 실시간 협업 툴
9. 테스트 커버리지 프로젝트
10. 클라우드 배포 프로젝트

### 포트폴리오 패키지 (12개월 후)
```
github.com/yourname/
├── e-commerce-fullstack
├── realtime-collab-tool
├── saas-subscription
├── microservices-demo
└── portfolio-website

velog.io/yourname/
├── Next.js App Router 완전 정복
├── Stripe 결제 연동 실전 가이드
├── PostgreSQL 쿼리 최적화 10가지
└── ... (총 12개 글)
```

## 시작하기

### 사전 준비
1. Git 설치 및 GitHub 계정 생성
2. VS Code 설치 (추천 확장 프로그램)
3. Node.js 18+ 설치
4. PostgreSQL 설치 (또는 Docker)

### 첫 주 행동 계획
1. [ ] Week 1 과제 확인 ([상세](./curriculum/week-1.md))
2. [ ] `index.html`, `styles.css` 생성
3. [ ] GitHub repository 생성
4. [ ] 첫 커밋 만들기
5. [ ] 주간 체크리스트 작성

## 참고 자료

### 공식 문서
- [MDN Web Docs](https://developer.mozilla.org/)
- [React 공식 문서](https://react.dev/)
- [Next.js 공식 문서](https://nextjs.org/docs)
- [Node.js 공식 문서](https://nodejs.org/en/docs/)
- [PostgreSQL Tutorial](https://www.postgresqltutorial.com/)

### recommended courses
- **한국어**: 인프런, 코데고, 코드스테이츠
- **영어**: Frontend Masters, Udemy (React/Next.js)
- **무료**: freeCodeCamp, The Odin Project

### 커뮤니티
- **한국**: OKKY, 기름 (Geer.io), 개발자 커뮤니티 Meetup
- **글로벌**: Reddit (r/reactjs, r/golang), HackerNews
- **Discord**: Reactiflux, The Odin Project

## 성공을 위한 핵심 원칙

1. **꾸준함 > 완벽함**: 매일 2시간이라도 코딩하기
2. **실습 > 이론**: "만들면서 배우기" 원칙
3. **공유 > 독백**: GitHub, 블로그에 지속 공유
4. **질문 > 막힘**: 2시간 막히면 질문하기 (커뮤니티)
5. **복습 > 새로운 것**: 주 1회 복습 시간 필수

---

**질문이나 피드백이 있으시면 언제든 알려주세요!**

**다음 단계**: [Week 1 상세 커리큘럼](./curriculum/week-1.md)로 이동
