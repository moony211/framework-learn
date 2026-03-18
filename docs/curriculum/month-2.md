# Month 2: Modern Frontend (React) (Week 5-8)

## 📅 기간: Week 5-8 (2026-04-15 ~ 2026-05-12)

## 🎯 월간 목표
- React 18 기본 개념 숙달
- Hooks (useState, useEffect, useReducer) 활용
- TypeScript 기본 타이핑
- **최종 산출물**: React Todo 앱 (TypeScript + 상태관리 라이브러리)

## 📊 주별 상세

### Week 5: React Components & JSX
**학습 목표**: React 컴포넌트, JSX, props/state 기본
**과제**: Button, Input, Modal, Card 등 컴포넌트 10개 제작
**시간**: 25-30시간

#### 핵심 내용
- 함수형 컴포넌트 vs 클래스 컴포넌트 (함수형이 표준)
- JSX 문법 (JavaScript inside HTML)
- Props (부모→자식 데이터 전달)
- Component composition (컴포넌트 합성)

#### 과제
1. 기본 컴포넌트 10개 만들기 (Button, Input, Card, Modal, Alert 등)
2. 각 컴포넌트에 props 받아 동적으로 렌더링
3. Storybook 또는 간단한 showcase 페이지 만들기 (선택)

---

### Week 6: React Hooks (useState, useEffect)
**학습 목표**: 상태 관리, 사이드 이펙트
**과제**: Counter, Form, API fetching 컴포넌트
**시간**: 25-30시간

#### 핵심 내용
- `useState`: 로컬 상태 관리
- `useEffect`: 생명주기, API 호출, 구독/해제
- Effect cleanup (메모리 누수 방지)
- Dependency array 이해

#### 과제
1. Counter 컴포넌트 (증가/감소/리셋 버튼)
2. Form 컴포넌트 (입력 유효성 검사)
3. API fetching 컴포넌트 (Fetch API + loading/error 상태)

---

### Week 7: Advanced Hooks (useReducer, Context API)
**학습 목표**: 복잡한 상태 관리, 전역 상태
**과제**: Shopping Cart 시스템
**시간**: 25-30시간

#### 핵심 내용
- `useReducer`: Reducer 패턴, 복잡한 state 로직
- `Context API`: 전역 상태 공유 (Props drilling 방지)
- `useContext`: Context 소비
- Custom Hooks: 재사용 가능한 로직 추출

#### 과제
**Shopping Cart 시스템**
- 상품 목록 (Product list)
- 장바구니 (Add/Remove/Update quantity)
- 총액 계산
- Context API로 장바구니 상태 전역 관리
- Custom Hook: `useCart()` 만들기

---

### Week 8: React Router & TypeScript
**학습 목표**: 라우팅, 타입 안전성
**과제**: 라우팅 가능한 Todo 앱 (3+ 페이지)
**시간**: 25-30시간

#### 핵심 내용
- React Router v6 (`<BrowserRouter>`, `<Routes>`, `<Route>`)
- 동적 라우팅 (`:id` params)
- Nested routes
- TypeScript 기본 (interface, type, generic)
- Props 타입 정의

#### 과제
1. React Router 설정 (Home, About, Projects 페이지)
2. Todo 앱에 라우팅 추가 (Todo 목록, 상세, 작성)
3. TypeScript 전환 (`.tsx` 확장자)
4. Props에 interface 정의

---

## 📦 월간 프로젝트 (Month 2 Final)

### 프로젝트: React Todo 앱 (TypeScript)

**요구사항**:
1. Todo CRUD 기능 (생성, 읽기, 수정, 삭제)
2. 상태관리: Zustand 또는 Pinia (선택)
3. 완전한 TypeScript 타이핑
4. (선택) 테스트 1-2개 작성
5. (선택) localStorage 연동 (持久성)

**기술 스택**:
- React 18
- TypeScript
- Zustand (또는 Pinia)

**폴더 구조**:
```
react-todo-app/
├── src/
│   ├── components/
│   │   ├── TodoList.tsx
│   │   ├── TodoItem.tsx
│   │   ├── TodoInput.tsx
│   │   └── TodoFilter.tsx
│   ├── store/
│   │   └── todoStore.ts (Zustand)
│   ├── types/
│   │   └── todo.ts (interface Todo)
│   ├── hooks/
│   │   └── useTodos.ts (custom hook)
│   ├── App.tsx
│   └── main.tsx
├── package.json
├── tsconfig.json
└── README.md
```

**핵심 구현**:
```typescript
// types/todo.ts
interface Todo {
  id: string;
  title: string;
  completed: boolean;
  createdAt: Date;
}

// store/todoStore.ts (Zustand)
interface TodoStore {
  todos: Todo[];
  addTodo: (title: string) => void;
  toggleTodo: (id: string) => void;
  deleteTodo: (id: string) => void;
  updateTodo: (id: string, title: string) => void;
}
```

---

## 📚 추가 학습 자료 (Month 2)

### React
- [React 공식 문서 (beta.react.dev)](https://beta.react.dev/)
- [React God 상태관리 가이드](https://react.dev/learn/scaling-up-with-reducer-and-context)

### TypeScript
- [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html)
- [TypeScript Playground](https://www.typescriptlang.org/play)

### Zustand
- [Zustand 공식 문서](https://zustand-demo.pmnd.rs/)

---

## ✅ Month 2 완료 체크리스트

- [ ] React 컴포넌트 작성 가능
- [ ] useState, useEffect, useReducer 이해
- [ ] Context API로 전역 상태 관리
- [ ] Custom Hooks 작성 경험
- [ ] React Router로 다중 페이지 라우팅
- [ ] TypeScript 기본 타이핑 적용
- [ ] React Todo 앱 완성 및 GitHub 업로드
- [ ] (선택) Jest/RTL 테스트 1-2개 작성

---

## 🎯 다음 월 (Month 3) 미리보기

**주제**: Node.js, Express, RESTful API
**프로젝트**: 블로그 백엔드 API (회원, 글, 댓글)

주요 학습:
- Express.js 라우팅 및 미들웨어
- JWT 인증
- Zod validation
- API 문서화 (OpenAPI)
