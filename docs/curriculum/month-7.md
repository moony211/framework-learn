# Month 7: [PLACEHOLDER] (Week 13-16)

## 📅 기간: Week 13-16 (2026-06-11 ~ 2026-07-07)

## 🎯 월간 목표
- PostgreSQL 기초 SQL 마스터
- Prisma ORM을 이용한 DB 접근
- ERD 설계 및 관계형 데이터베이스 이해
- N+1 문제 해결 및 쿼리 최적화
- **최종 산출물**: Todo Fullstack (React + Express + PostgreSQL + Prisma)

---

## 📊 주별 상세

### Week 13: SQL Basics
**학습 목표**: SELECT, JOIN, GROUP BY, WHERE
**과제**: 10개 이상의 JOIN 쿼리 작성, EXPLAIN 분석
**시간**: 20-25시간

#### 핵심 내용
- SELECT, WHERE, ORDER BY, LIMIT
- JOIN (INNER, LEFT, RIGHT, FULL OUTER)
- GROUP BY, HAVING, 집계 함수 (COUNT, SUM, AVG, MAX, MIN)
- Subquery, CTE (Common Table Expressions)
- EXPLAIN으로 쿼리 실행 계획 분석

#### 과제
1. **기본 CRUD**:
   ```sql
   SELECT * FROM users;
   SELECT name, email FROM users WHERE age > 20;
   SELECT * FROM posts ORDER BY created_at DESC LIMIT 10;
   ```

2. **JOIN 연습** (최소 10개):
   ```sql
   -- users + posts (1:N 관계)
   SELECT u.name, p.title FROM users u
   JOIN posts p ON u.id = p.user_id;

   -- posts + comments (1:N)
   -- posts + likes (M:N, junction table)
   -- categories + posts (N:N)
   -- LEFT JOIN으로 모든 사용자 + 해당 글 (글 없어도 포함)
   ```

3. **집계**:
   ```sql
   -- 사용자별 글 수
   SELECT u.name, COUNT(p.id) as postCount
   FROM users u LEFT JOIN posts p ON u.id = p.user_id
   GROUP BY u.id;

   -- 월별 글 작성 수
   SELECT DATE_TRUNC('month', created_at), COUNT(*)
   FROM posts
   GROUP BY DATE_TRUNC('month', created_at);
   ```

4. **EXPLAIN ANALYZE**로 쿼리 성능 분석

#### 학습 자료
- [SQLBolt](https://sqlbolt.com/)
- [PostgreSQL Tutorial](https://www.postgresqltutorial.com/)
- [Mode SQL Tutorial](https://mode.com/sql-tutorial/)

---

### Week 14: PostgreSQL Installation & Prisma Setup
**학습 목표**: 로컬 DB 설치, Prisma 초기 설정
**과제**: PostgreSQL 설치, Prisma CLI 사용법
**시간**: 20-25시간

#### 핵심 내용
- PostgreSQL 설치 (Windows/Mac/Linux)
- `psql` CLI 또는 pgAdmin 사용
- Database 생성, 사용자 생성
- Prisma init, schema.prisma 파일 구조
- Prisma Client 사용법

#### 설치 가이드

**Mac (Homebrew)**:
```bash
brew install postgresql
brew services start postgresql
createdb mydb
psql mydb
```

**Windows**:
```powershell
# Download PostgreSQL installer from https://www.postgresql.org/download/windows/
# 또는 Docker 사용:
docker run --name my-postgres -e POSTGRES_PASSWORD=secret -p 5432:5432 -d postgres
```

**Ubuntu/Debian**:
```
sudo apt update
sudo apt install postgresql postgresql-contrib
sudo -u postgres psql
CREATE DATABASE mydb;
```

#### Prisma 설치 및 설정
```bash
npm install prisma --save-dev
npx prisma init

# .env 파일 자동 생성
DATABASE_URL="postgresql://username:password@localhost:5432/mydb?schema=public"

# schema.prisma 수정
datasource db {
  provider = "postgresql"
  url      = env("DATABASE_URL")
}

generator client {
  provider = "prisma-client-js"
}

# Prisma Client 설치
npm install @prisma/client

# 첫 마이그레이션
npx prisma migrate dev --name init

# Prisma Studio (데이터 베이UI)
npx prisma studio
```

---

### Week 15: Prisma Schema Design & Relations
**학습 목표**: Schema 설계, 관계 설정
**과제**: ERD 작성 → Schema 변환
**시간**: 20-25시간

#### 핵심 내용
- Prisma data model 문법
- 관계 (Relation): 1:1, 1:N, N:M
- Attribute (field, @id, @default, @unique)
- Enumerations (enum)
- Indexes, @@map, @@unique

#### 과제
**Todo 앱 ERD → Prisma Schema**

```
users (사용자)
├── id (UUID, primary key)
├── email (unique)
├── name
├── password (hashed)
├── createdAt
└── todos (1:N relation)

todos (할 일)
├── id (UUID, primary key)
├── title
├── description
├── completed (boolean, default false)
├── userId (ForeignKey → users.id)
└── user (User, relation)
```

```prisma
// schema.prisma
generator client {
  provider = "prisma-client-js"
}

datasource db {
  provider = "postgresql"
  url      = env("DATABASE_URL")
}

model User {
  id        String   @id @default(uuid())
  email     String   @unique
  name      String?
  password  String
  createdAt DateTime @default(now())
  todos     Todo[]

  @@map("users")
}

model Todo {
  id          String   @id @default(uuid())
  title       String
  description String?
  completed   Boolean  @default(false)
  userId      String
  user        User     @relation(fields: [userId], references: [id], onDelete: Cascade)
  createdAt   DateTime @default(now())
  updatedAt   DateTime @updatedAt

  @@map("todos")
}
```

**마이그레이션 실행**:
```bash
npx prisma migrate dev --name create_user_todo_tables
# SQL 파일 생성 migrations/xxxx_create_user_todo_tables.sql
```

---

### Week 16: Prisma CRUD & Query Optimization
**학습 목표**: Prisma CRUD, N+1 문제 해결
**과제**: include, select, executecount 활용
**시간**: 25-30시간

#### 핵심 내용
- Prisma Client 인스턴스 생성
- CRUD operations (create, findUnique, findMany, update, delete)
- Relations: include, select
- Query optimization: N+1 문제 이해 및 해결
- Raw queries (필요시)

#### 과제
```typescript
// src/lib/prisma.ts
import { PrismaClient } from '@prisma/client';
export const prisma = new PrismaClient();

// CRUD 예제

// CREATE
const user = await prisma.user.create({
  data: {
    email: 'test@example.com',
    name: 'Test',
    password: 'hashed_password',
    todos: {
      create: [
        { title: 'Todo 1' },
        { title: 'Todo 2' },
      ],
    },
  },
});

// READ with relations (N+1 문제 주의!)
// ❌ 잘못된 방법 (N+1 문제):
const users = await prisma.user.findMany();
for (const user of users) {
  // 각 사용자마다 추가 쿼리 실행 (N번)
  user.todos = await prisma.todo.findMany({ where: { userId: user.id } });
}

// ✅ 올바른 방법 (단일 쿼리 with include):
const users = await prisma.user.findMany({
  include: {
    todos: true, // 모든 todo 포함
    // 또는 선택적 필드:
    // todos: { select: { id: true, title: true } }
    // todos: { where: { completed: false } }
  },
});
```

**N+1 문제 이해**:
- 사용자 10명 + 각 사용자의 todos 조회
- N+1 방식: 1 (users) + 10 (todos) = 11회 쿼리
- Prisma `include`: JOIN으로 1회 쿼리

**과제**:
1. 사용자별 todo 목록 조회 (N+1 문제 해결)
2. 특정 사용자의 완료된 todo만 조회
3. todo count 포함된 사용자 목록 조회
4. pagination 구현 (`skip`, `take`)

---

## 📦 월간 프로젝트 (Month 4 Final)

### 프로젝트: Todo Fullstack

**요구사항**:
- 프론트엔드: React (Month 2의 Todo 앱 개선)
- 백엔드: Express + Prisma + PostgreSQL (Month 3 API 확장)
- 풀스택 연동: 프론트에서 백엔드 API 호출
- Docker Compose로 로컬 개발 환경 구성

**기술 스택**:
- Frontend: React + TypeScript + Zustand
- Backend: Node.js + Express + TypeScript + Prisma
- Database: PostgreSQL (Docker)
- Dev: Docker Compose

**폴더 구조** (Monorepo 권장):
```
todo-fullstack/
├── docker-compose.yml
├── package.json (root, workspaces)
├── apps/
│   ├── frontend/         # React app (Month 2 Todo 앱)
│   │   ├── src/
│   │   ├── package.json
│   │   └── ...
│   └── backend/          # Express API (Month 3 확장)
│       ├── src/
│       │   ├── routes/
│       │   ├── middleware/
│       │   ├── lib/prisma.ts
│       │   └── app.ts
│       ├── prisma/
│       │   └── schema.prisma
│       ├── package.json
│       └── ...
└── README.md
```

**API 연동 예시**:

```typescript
// frontend/src/api/todoApi.ts
const API_BASE = 'http://localhost:3001/api';

export const todoApi = {
  getTodos: async (): Promise<Todo[]> => {
    const res = await fetch(`${API_BASE}/todos`);
    return res.json();
  },

  getTodo: async (id: string): Promise<Todo> => {
    const res = await fetch(`${API_BASE}/todos/${id}`);
    return res.json();
  },

  createTodo: async (title: string): Promise<Todo> => {
    const res = await fetch(`${API_BASE}/todos`, {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify({ title }),
    });
    return res.json();
  },

  updateTodo: async (id: string, data: Partial<Todo>): Promise<Todo> => {
    const res = await fetch(`${API_BASE}/todos/${id}`, {
      method: 'PATCH',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify(data),
    });
    return res.json();
  },

  deleteTodo: async (id: string): Promise<void> => {
    await fetch(`${API_BASE}/todos/${id}`, { method: 'DELETE' });
  },
};
```

---

## 📚 추가 학습 자료 (Month 4)

### PostgreSQL
- [PostgreSQL 공식 문서](https://www.postgresql.org/docs/)
- [PostgreSQL Exercises](https://pgexercises.com/)
- [Awesome PostgreSQL](https://github.com/dhamaniasad/awesome-postgres)

### Prisma
- [Prisma 공식 문서](https://www.prisma.io/docs/)
- [Prisma YouTube 채널](https://www.youtube.com/c/Prisma)
- [Awesome Prisma](https://github.com/catalinmiron/react-awesome-prisma)

### ORM 비교
- [Prisma vs Sequelize vs TypeORM](https://dev.to/estebanm Arroyo/comparing-prisma-sequelize-and-typeorm-1jcm)

---

## ✅ Month 4 완료 체크리스트

- [ ] PostgreSQL 로컬 설치 및 기본 명령어 숙지
- [ ] SQL 기본 문법 (SELECT, JOIN, GROUP BY) 숙달
- [ ] Prisma 초기 설정 및 Schema 설계
- [ ] 1:1, 1:N, N:M 관계 설정
- [ ] Prisma CRUD 연산 구현
- [ ] N+1 문제 이해 및 해결 (include 활용)
- [ ] Docker Compose로 프론트+백엔드+DB 환경 구성
- [ ] React 프론트엔드 + Express 백엔드 연동
- [ ] API 문서 작성 (OpenAPI/Swagger)

---

## 🎯 다음 월 (Month 5) 미리보기

**주제**: Next.js Mastery (App Router)
**프로젝트**: 기술 블로그 (Markdown → SSR)

주요 학습:
- Next.js 14 App Router
- Server Components vs Client Components
- NextAuth.js 인증
- Markdown 처리 (remark, gray-matter)
