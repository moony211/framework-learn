# Month 1: Web Fundamentals (Week 1-4)

## 📅 기간: Week 1-4 (2026-03-18 ~ 2026-04-13)

## 🎯 월간 목표
- Semantic HTML 구조 이해 및 적용
- CSS Box Model, Flexbox, Grid 완벽 마스터
- JavaScript ES6+ 기본 문법 숙달
- DOM 조작 및 비동기 처리 (Fetch API)
- **최종 산출물**: 정적 포트폴리오 웹사이트 (GitHub Pages 배포)

## 📊 주별 상세

### Week 1: Semantic HTML & CSS Box Model
**기간**: 2026-03-18 ~ 2026-03-24
**시간**: 20-25시간
**성공 지표**: 포트폴리오 사이트 static HTML/CSS 완성

#### 학습 목표
- ✅ Semantic HTML 요소 (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`)
- ✅ CSS Box Model (margin, border, padding, content)
- ✅ `box-sizing: border-box` 전역 적용
- ✅ 웹 표준 검사 통과

#### 주 차별 태스크
- [ ] Day 1-2: Semantic HTML 구조 학습 및 예제 작성
- [ ] Day 3-4: CSS Box Model 개념 이해 및 스타일 적용
- [ ] Day 5-7: 포트폴리오 사이트 통합 및 GitHub 업로드

#### 과제
1. **포트폴리오 사이트 구조**: `index.html` 작성 (시맨틱 요소만 사용)
2. **CSS Box Model**: `styles.css` 작성 (padding, border, margin 적용)
3. **GitHub**: 저장소 생성 및 첫 커밋 (`feat:` prefix)

#### 학습 자료
- [MDN: HTML 기초](https://developer.mozilla.org/ko/docs/Learn/HTML/Introduction_to_HTML)
- [MDN: CSS Box Model](https://developer.mozilla.org/ko/docs/Learn/CSS/Building_blocks/The_box_model)
- [HTML Validator](https://validator.w3.org/)

#### 체크리스트
- [ ] `<div>` 대신 시맨틱 요소 사용했는가?
- [ ] `* { box-sizing: border-box; }` 적용했는가?
- [ ] heading level 순차적 (`h1` → `h2`)인가?
- [ ] Git 커밋 메시지가 Conventional Commits인가?
- [ ] HTML validator 에러 0개인가?

---

### Week 2: Flexbox & Grid & Responsive Design
**기간**: 2026-03-25 ~ 2026-03-31
**시간**: 20-25시간
**성공 지표**: 모바일/태블릿/데스크탑 모두 정상 표시

#### 학습 목표
- ✅ CSS Flexbox (1D layout)
- ✅ CSS Grid (2D layout)
- ✅ Media Queries (반응형)
- ✅ 반응형 포트폴리오 사이트 완성

#### 주 차별 태스크
- [ ] Day 1-2: Flexbox 기본 (justify-content, align-items, flex-direction)
- [ ] Day 3-4: CSS Grid 기본 (grid-template-columns, gap)
- [ ] Day 5-7: Media Queries 및 기존 포트폴리오 반응형 개선

#### 과제
1. **Flexbox 연습**: Flexbox Froggy 완료
2. **CSS Grid 연습**: CSS Grid Garden 완료
3. **기존 포트폴리오 반응형 개선**: 모바일/태블릿/데스크탑 레이아웃 최적화

#### 학습 자료
- [Flexbox Froggy](https://flexboxfroggy.com/)
- [CSS Grid Garden](https://cssgridgarden.com/)
- [CSS Tricks: A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [CSS Tricks: A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)

#### 체크리스트
- [ ] Flexbox와 Grid 중 어떤 상황에 어떤 걸 쓰는지 이해했는가?
- [ ] Mobile-first 접근법 사용했는가? (`min-width` media queries)
- [ ] 반응형 이미지 (`max-width: 100%`) 적용했는가?
- [ ] 모바일(375px), 태블릿(768px), 데스크탑(1200px) 테스트 완료?

---

### Week 3: JavaScript Basics & DOM Manipulation
**기간**: 2026-04-01 ~ 2026-04-07
**시간**: 25-30시간
**성공 지표**: Todo 리스트 앱 (로컬 저장) 완성

#### 학습 목표
- ✅ JavaScript 변수, 함수, 조건문, 반복문
- ✅ DOM 선택 및 조작 (`querySelector`, `classList`, `innerHTML`)
- ✅ 이벤트 처리 (`addEventListener`)
- ✅ LocalStorage를 활용한 데이터 저장
- ✅ CRUD 기능 구현

#### 주 차별 태스크
- [ ] Day 1-2: JavaScript 변수, 함수, 화살표 함수, template literals
- [ ] Day 3-4: DOM API 학습 (`querySelector`, `createElement`, `appendChild`)
- [ ] Day 5-7: Todo 리스트 앱 제작 (추가, 삭제, 토글, LocalStorage)

#### 과제
**Todo 리스트 앱** (`index.html` 단일 파일)
```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <title>Todo List</title>
</head>
<body>
    <h1>Todo List</h1>
    <input type="text" id="todoInput" placeholder="할 일 입력">
    <button id="addBtn">추가</button>
    <ul id="todoList"></ul>

    <script>
        // JavaScript 코드
        // 1. 할 일 추가
        // 2. 할 일 삭제
        // 3. 할 일 토글 (완료/미완료)
        // 4. LocalStorage 저장/불러오기
    </script>
</body>
</html>
```

#### 학습 자료
- [JavaScript.info](https://javascript.info/)
- [MDN: JavaScript](https://developer.mozilla.org/ko/docs/Web/JavaScript)
- [DOM Enlightenment](http://domenlightenment.com/) (선택)

#### 체크리스트
- [ ] 변수 스코프 (var/let/const) 이해했는가?
- [ ] 화살표 함수 (`=>`) 사용 가능한가?
- [ ] DOM 조작시 `innerHTML` XSS 취약점 인지하고 있는가?
- [ ] LocalStorage 동작 방식 이해했는가?
- [ ] 이벤트 위임 (event delegation) 적용했는가?

---

### Week 4: Async JavaScript & Fetch API
**기간**: 2026-04-08 ~ 2026-04-14
**시간**: 25-30시간
**성공 지표**: OpenWeather API 성공 연동

#### 학습 목표
- ✅ Promise, async/await 이해
- ✅ Fetch API 사용법
- ✅ 외부 API 호출 및 데이터 표시
- ✅ 에러 처리 (try-catch)

#### 주 차별 태스크
- [ ] Day 1-2: Promise, async/await 문법
- [ ] Day 3-4: Fetch API 학습 (GET, POST, headers, body)
- [ ] Day 5-7: Weather App 제작 (OpenWeather API)

#### 과제
**Weather App** (`index.html` 단일 파일)
```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <title>Weather App</title>
</head>
<body>
    <h1>날씨 앱</h1>
    <input type="text" id="cityInput" placeholder="도시 이름">
    <button id="searchBtn">검색</button>
    <div id="weatherResult"></div>

    <script>
        // 1. OpenWeather API 키 발급 (무료)
        // https://openweathermap.org/api

        // 2. 사용자 입력받아 API 호출
        // 3. 응답 데이터 파싱
        // 4. 날씨 정보 화면에 표시
        // 5. 에러 처리 (도시 없음, 네트워크 오류)
        // 6. (선택) LocalStorage에 최근 검색 도시 저장
    </script>
</body>
</html>
```

#### 학습 자료
- [MDN: Fetch API](https://developer.mozilla.org/ko/docs/Web/API/Fetch_API)
- [JavaScript.info: Promise](https://javascript.info/promise)
- [OpenWeather API](https://openweathermap.org/api)

#### 체크리스트
- [ ] async/await와 `.then()` 차이 이해했는가?
- [ ] Fetch error handling (try-catch) 적용했는가?
- [ ] API 응답 JSON 파싱했는가?
- [ ] API 키를 코드에 하드코딩하지 않고 `.env`나 변수로 관리했는가?
- [ ] 로딩 상태 표시했는가?

---

## 📦 월간 프로젝트 (Month 1 Final)

### 프로젝트: 포트폴리오 웹사이트 (정적)

**요구사항**:
1. Semantic HTML 기반 구조
2. CSS Box Model, Flexbox, Grid 활용
3. 반응형 디자인 (모바일/태블릿/데스크탑)
4. JavaScript 최소 1개 이상 동적 기능 (예: 모달, 탭, Todo)
5. GitHub Pages 또는 Vercel 배포

**폴더 구조**:
```
my-portfolio-2026/
├── index.html
├── styles.css
├── script.js (선택)
├── README.md
└── assets/
    ├── profile.jpg
    └── project1.png
```

**README.md 필수 내용**:
```markdown
# 나의 포트폴리오

## 프로젝트 소개
풀스택 개발자를 꿈꾸는 김개발의 포트폴리오 사이트입니다.

## 기술 스택
- HTML5 (Semantic Elements)
- CSS3 (Flexbox, Grid, Responsive)
- JavaScript (ES6+)

## 실행 방법
index.html 파일을 브라우저에서 열거나,
```bash
python -m http.server 8000
```
로 로컬 서버 실행.

## 배포
- GitHub Pages: https://yourusername.github.io/my-portfolio-2026/

## 배운 점
1. Semantic HTML의 중요성
2. CSS Grid로 복잡한 레이아웃 구현
3. 반응형 디자인 Mobile-first 접근법

## TODO
- [ ] Next.js로 리팩토링
- [ ] 더 많은 프로젝트 추가
- [ ] 애니메이션 효과 추가
```

**배포 방법 (GitHub Pages)**:
1. GitHub repository 생성
2. 코드 푸시
3. Settings → Pages
4. Source: Deploy from a branch, Branch: main, / (root)
5. Save → URLCopied

**배포 방법 (Vercel)**:
1. https://vercel.com/new
2. GitHub repository 연결
3. Framework Preset: Other
4. Root Directory: . (루트)
5. Deploy

---

## 📊 Self Evaluation Checklist (금요일)

### 완료 확인
- [ ] Week 1-4 모든 과제 완료
- [ ] 포트폴리오 웹사이트 배포 완료
- [ ] GitHub repository 생성 및 10+ 커밋
- [ ] HTML validation 통과
- [ ] 반응형 테스트 (모바일/태블릿/데스크탑)
- [ ] 기술 블로그 1주차 회고 글 작성 (선택)

### 기술 수준 평가 (1-10점)
- Semantic HTML: ____ 점
- CSS (Flexbox/Grid): ____ 점
- JavaScript (ES6+): ____ 점
- Git/GitHub: ____ 점

### 시간 투자
- 총 코딩 시간: ____ 시간
- 문서 학습 시간: ____ 시간
- 일평균: ____ 시간

### 질문/고민 정리
1.
2.

### 다음 월 (Month 2) 준비
- [ ] React 설치 및 기본 문법 학습 시작
- [ ] Next.js 공식 문서 책갈피
- [ ] React DevTools 설치

---

## 🔄 다음 월 (Month 2) 미리보기

**주요 학습 내용**:
- React 18 컴포넌트, JSX
- Hooks (useState, useEffect)
- TypeScript 기본
- React Router

**월간 프로젝트**: React Todo 앱 (TypeScript)

---

**Month 1 완료 후**:
1. 포트폴리오 사이트 URL 공유 (코드 리뷰)
2. Self Evaluation 작성
3. Month 2 Week 5 시작

**질문 있으면 언제든 물어보세요!**
