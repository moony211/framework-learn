# Week 1: Web Fundamentals (Semantic HTML & CSS Box Model)

## 📅 일정
- **시작일**: 2026-03-18
- **종료일**: 2026-03-24
- **총 시간**: 20-25시간

## 🎯 학습 목표

### 필수 이해사항
- ✅ Semantic HTML 요소의 의미와 사용법
- ✅ CSS Box Model (margin, border, padding, content)
- ✅ `box-sizing: border-box`의 중요성
- ✅ 웹 표준과 접근성 기본 개념

### 성공 지표
- 포트폴리오 사이트 static HTML/CSS 완성
- HTML validator (https://validator.w3.org/) 통과
- GitHub에 첫 커밋 완료

## 📚 학습 자료

### 필수 읽기
1. [MDN: HTML 기초](https://developer.mozilla.org/ko/docs/Learn/HTML/Introduction_to_HTML)
2. [MDN: CSS Box Model](https://developer.mozilla.org/ko/docs/Learn/CSS/Building_blocks/The_box_model)
3. [Semantic HTML 가이드](https://html.com/wp-content/uploads/html5-semantic-elements.jpg)

### 추천 시각 자료
- YouTube: "HTML and CSS for Beginners" (traversy media)
- HTML 시맨틱 요소 설명 (한국어)

### 인터랙티브 연습
- [Flexbox Froggy](https://flexboxfroggy.com/) - Week 2 예습
- [CSS Grid Garden](https://cssgridgarden.com/) - Week 2 예습

## 📖 학습 내용 상세

### Day 1: Semantic HTML 이해

####什么是 시맨틱 HTML?
의미(semantic)를 전달하는 HTML 요소들. 스크린 리더, 검색 엔진이 콘텐츠 구조를 이해하는 데 도움.

#### 주요 시맨틱 태그
```html
<header>    <!-- 페이지나 섹션의 헤더 -->
<nav>       <!-- 내비게이션 링크 -->
<main>      <!-- 페이지의 주요 콘텐츠 (하나만) -->
<article>   <!-- 독립적인 콘텐츠 (블로그 글, 뉴스) -->
<section>   <!-- 문서의 구획 (주제별 그룹) -->
<aside>     <!-- 부가 정보 (사이드바) -->
<footer>    <!-- 페이지나 섹션의 푸터 -->
<figure>    <!-- 이미지/다이어그램과 캡션 -->
<figcaption><!-- figure의 캡션 -->
<time>      <!-- 날짜/시간 -->
<details>   <!-- 추가 정보 (확장/축소) -->
<summary>   <!-- details의 요약 -->
<mark>      <!-- 하이라이트 -->
<progress>  <!-- 작업 진행률 -->
```

#### 비시맨틱 태그 vs 시맨틱 태그
```html
<!-- 비추천 (의미 없음) -->
<div class="header">...</div>
<div class="nav">...</div>
<div class="main">...</div>

<!-- 추천 (의미 명확) -->
<header>...</header>
<nav>...</nav>
<main>...</main>
```

#### 실습: 기본 HTML 구조
```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>나의 포트폴리오</title>
    <meta name="description" content="풀스택 개발자를 꿈꾸는 [이름]의 포트폴리오 사이트">
</head>
<body>
    <!-- header 영역 -->
    <header>
        <nav>
            <ul>
                <li><a href="#about">소개</a></li>
                <li><a href="#skills">기술스택</a></li>
                <li><a href="#projects">프로젝트</a></li>
                <li><a href="#contact">연락처</a></li>
            </ul>
        </nav>
    </header>

    <!-- 주요 콘텐츠 -->
    <main>
        <!-- 소개 섹션 -->
        <section id="about">
            <article>
                <h1>안녕하세요, 김개발입니다</h1>
                <p>풀스택 개발자를 꿈꾸고 있습니다.</p>
            </article>
        </section>

        <!-- 기술스택 섹션 -->
        <section id="skills" class="section">
            <div class="container">
                <h2>기술스택</h2>
                <div class="skills-grid">
                    <div class="skill-card">
                        <h3>Frontend</h3>
                        <ul>
                            <li>HTML5, CSS3</li>
                            <li>JavaScript (ES6+)</li>
                            <li>React</li>
                        </ul>
                    </div>
                    <div class="skill-card">
                        <h3>Backend</h3>
                        <ul>
                            <li>Node.js</li>
                            <li>Express</li>
                            <li>PostgreSQL</li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <!-- 프로젝트 섹션 -->
        <section id="projects" class="section">
            <div class="container">
                <h2>프로젝트</h2>
                <div class="projects-grid">
                    <article class="project-card">
                        <h3>Todo 앱</h3>
                        <p>React로 만든 Todo 리스트 앱</p>
                    </article>
                    <article class="project-card">
                        <h3>Weather 앱</h3>
                        <p>OpenWeather API 활용 날씨 앱</p>
                    </article>
                </div>
            </div>
        </section>
    </main>

    <!-- 푸터 (연락처) -->
    <footer class="footer" id="contact">
        <div class="container">
            <p>&copy; 2026 김개발. All rights reserved.</p>
            <div class="social-links">
                <a href="https://github.com/yourusername">GitHub</a>
                <a href="https://linkedin.com/in/yourusername">LinkedIn</a>
            </div>
        </div>
    </footer>
</body>
</html>
```

#### 중요 규칙
1. `<main>`은 페이지당 하나만
2. heading level은 순차적으로 (`<h1>` → `<h2>` → `<h3>`)
3. `id`는 고유하게, `class`는 재사용용
4. `<a>`의 `href` 필수, `<button>`은 `<a>` 대신 사용

---

### Day 2: CSS Box Model

#### Box Model 개념
모든 HTML 요소는 네 개의 레이어로 구성:

```
┌─────────────────────────────┐
│         margin (투명)        │ ← 외부 여백 (요간 간격)
├─────────────────────────────┤
│   border (선/테두리)         │
│  ┌─────────────────────┐   │
│  │   padding (내부 여백) │   │ ← 콘텐츠와 테두리 사이
│  │  ┌───────────────┐   │   │
│  │  │   content     │   │   │ ← 실제 내용 (텍스트/이미지)
│  │  │               │   │   │
│  │  └───────────────┘   │   │
│  └─────────────────────┘   │
└─────────────────────────────┘
```

#### CSS 속성 예시
```css
.box {
  /* Content 크기 */
  width: 300px;
  height: 200px;

  /* Padding (내부 여백) */
  padding: 20px;                    /* 상하좌우 20px */
  padding: 10px 20px;               /* 상하 10px, 좌우 20px */
  padding: 5px 10px 15px 20px;      /* 상 우 하 좌 (시계방향) */
  padding-top: 10px;
  padding-right: 15px;
  padding-bottom: 10px;
  padding-left: 5px;

  /* Border (테두리) */
  border: 2px solid #333;           /* 두께 스타일 색상 */
  border: 1px dashed #ccc;
  border-radius: 8px;               /* 모서리 둥글게 */
  border-top: 2px solid #333;
  border-bottom: none;

  /* Margin (외부 여백) */
  margin: 10px;                     /* 상하좌우 10px */
  margin: 0 auto;                   /* 가운데 정렬 (블록 요소) */
  margin-top: 20px;
  margin-bottom: 30px;
}
```

#### box-sizing 속성 (매우 중요!)

**기본값: `content-box`**
```css
.box {
  box-sizing: content-box;  /* 기본값 */
  width: 300px;             /* content 영역만 300px */
  padding: 20px;            /* padding 추가 */
  border: 2px solid #333;   /* border 추가 */
  /* 실제 너비 = 300 + 20*2 + 2*2 = 344px */
}
```

** 추천: `border-box`**
```css
.box {
  box-sizing: border-box;   /* padding + border 포함 */
  width: 300px;             /* 전체 너비 = 300px */
  padding: 20px;
  border: 2px solid #333;
  /* content 너비 = 300 - 40 - 4 = 256px */
}
```

**전역 적용 (Best Practice):**
```css
* {
  box-sizing: border-box;
}

*는 모든 요소 선택자 (universal selector)
```

---

### Day 3: 포트폴리오 사이트 구조 만들기

#### 프로젝트 구조
```
my-portfolio/
├── index.html
├── styles.css
└── README.md
```

#### HTML 구조 예시
```html
<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>김개발 - 풀스택 개발자</title>
    <meta name="description" content="풀스택 개발자 김개발의 포트폴리오">
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header class="header">
        <nav class="nav">
            <div class="logo">KD</div>
            <ul class="nav-menu">
                <li><a href="#about">소개</a></li>
                <li><a href="#skills">기술스택</a></li>
                <li><a href="#projects">프로젝트</a></li>
                <li><a href="#contact">연락처</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <!-- Hero Section -->
        <section id="about" class="section hero">
            <div class="container">
                <h1>안녕하세요,</h1>
                <h2>풀스택 개발자 김개발입니다</h2>
                <p>사용자 경험을 중시하는 웹 애플리케이션을 만듭니다.</p>
            </div>
        </section>

        <!-- Skills Section -->
        <section id="skills" class="section">
            <div class="container">
                <h2>기술스택</h2>
                <div class="skills-grid">
                    <div class="skill-card">
                        <h3>Frontend</h3>
                        <ul>
                            <li>HTML5, CSS3</li>
                            <li>JavaScript (ES6+)</li>
                            <li>React</li>
                        </ul>
                    </div>
                    <div class="skill-card">
                        <h3>Backend</h3>
                        <ul>
                            <li>Node.js</li>
                            <li>Express</li>
                            <li>PostgreSQL</li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <!-- Projects Section -->
        <section id="projects" class="section">
            <div class="container">
                <h2>프로젝트</h2>
                <div class="projects-grid">
                    <article class="project-card">
                        <h3>Todo 앱</h3>
                        <p>React로 만든 Todo 리스트 앱</p>
                    </article>
                    <article class="project-card">
                        <h3>Weather 앱</h3>
                        <p>OpenWeather API 활용 날씨 앱</p>
                    </article>
                </div>
            </div>
        </section>
    </main>

    <footer class="footer">
        <div class="container">
            <p>&copy; 2026 김개발. All rights reserved.</p>
            <div class="social-links">
                <a href="https://github.com/yourusername">GitHub</a>
                <a href="https://linkedin.com/in/yourusername">LinkedIn</a>
            </div>
        </div>
    </footer>
</body>
</html>
```

---

### Day 4: CSS 스타일링

#### CSS 파일 구조
```css
/* 전역 스타일 */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, sans-serif;
    line-height: 1.6;
    color: #333;
}

.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
}

/* Header & Navigation */
.header {
    background: #fff;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    position: sticky;
    top: 0;
    z-index: 100;
}

.nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 0;
}

.logo {
    font-size: 1.5rem;
    font-weight: bold;
}

.nav-menu {
    display: flex;
    list-style: none;
    gap: 2rem;
}

.nav-menu a {
    text-decoration: none;
    color: #333;
    transition: color 0.3s;
}

.nav-menu a:hover {
    color: #0070f3;
}

/* Sections */
.section {
    padding: 4rem 0;
}

.hero {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    text-align: center;
}

.hero h1 {
    font-size: 3rem;
    margin-bottom: 1rem;
}

.hero h2 {
    font-size: 2rem;
    margin-bottom: 1rem;
    opacity: 0.9;
}

/* Skills Grid */
.skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 2rem;
    margin-top: 2rem;
}

.skill-card {
    background: #f9fafb;
    border: 1px solid #e5e7eb;
    border-radius: 8px;
    padding: 2rem;
}

/* Projects Grid */
.projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
    margin-top: 2rem;
}

.project-card {
    background: #fff;
    border: 1px solid #e5e7eb;
    border-radius: 8px;
    padding: 1.5rem;
    transition: box-shadow 0.3s;
}

.project-card:hover {
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

/* Footer */
.footer {
    background: #1f2937;
    color: white;
    padding: 2rem 0;
    text-align: center;
}

.social-links {
    margin-top: 1rem;
    display: flex;
    gap: 1rem;
    justify-content: center;
}

.social-links a {
    color: white;
    text-decoration: none;
}
```

---

### Day 5: Box Model 실습

#### Card 컴포넌트 스타일링
```css
.card {
    background: white;
    border: 1px solid #e5e7eb;
    border-radius: 12px;
    padding: 24px;
    margin: 16px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
}

/* Card anatomy */
.card {
    /* content 영역 */
    width: 300px;

    /* padding: content와 border 사이 */
    padding: 20px;

    /* border: 테두리 */
    border: 1px solid #ccc;
    border-radius: 8px;

    /* margin: 다른 요소와의 간격 */
    margin: 10px;
}

/* 실제 너비 계산 (content-box 기준)
Total width = 300 + 20*2 + 1*2 + 10*2 = 362px

border-box를 적용하면?
Total width = 300px (고정)
Content width = 300 - 40 - 2 = 258px
*/
```

---

### Day 6-7: 프로젝트 통합 및 GitHub에 업로드

#### GitHub 저장소 생성 과정

```bash
# 1. 프로젝트 폴더 생성
mkdir my-portfolio-2026
cd my-portfolio-2026

# 2. 파일 생성
touch index.html styles.css README.md

# 3. Git 초기화
git init

# 4. 파일 추가
git add index.html styles.css README.md

# 5. 첫 커밋
git commit -m "feat: initial portfolio structure with semantic HTML"

# 6. GitHub에 repository 생성 후 연결
git branch -M main
git remote add origin https://github.com/yourusername/my-portfolio-2026.git
git push -u origin main
```

####.gitignore (필요시)
```
# Node.js
node_modules/
npm-debug.log

# OS
.DS_Store
Thumbs.db

# VS Code
.vscode/
```

#### README.md 템플릿
```markdown
# 나의 포트폴리오

## 프로젝트 소개
풀스택 개발자 과정 첫 번째 프로젝트입니다.
Semantic HTML과 CSS Box Model을 적용한 정적 포트폴리오 사이트입니다.

## 기술 스택
- HTML5 (Semantic Elements)
- CSS3 (Box Model, Flexbox, Grid)

## 실행 방법
그냥 브라우저에서 `index.html`을 열면 됩니다.

```bash
# 또는 Python으로 간단한 서버
python -m http.server 8000
# http://localhost:8000
```

## 배포
- GitHub Pages: https://yourusername.github.io/my-portfolio-2026/
- Vercel:coming soon

## 배운 점
- Semantic HTML의 중요성
- CSS Box Model 이해
- 웹 표준 준수의 의미

## TODO
- [ ] 반응형 디자인 추가
- [ ] JavaScript 동적 기능 추가
- [ ] Next.js로 리팩토링
```

---

## ✅ 주간 체크리스트 (금요일까지)

### 완료 확인사항
- [ ] `index.html`에 시맨틱 HTML 구조 작성 완료
- [ ] `styles.css`에 Box Model 개념 적용
- [ ] `* { box-sizing: border-box; }` 전역 적용
- [ ] 포트폴리오 사이트 브라우저에서 정상 표시
- [ ] GitHub repository 생성 완료
- [ ] 첫 커밋 완료 (`feat:` prefix 사용)
- [ ] (선택) GitHub Pages 또는 Vercel에 배포 시도

### HTML 검증
1. https://validator.w3.org/ 접속
2. "Validate by File Upload" 선택
3. `index.html` 업로드
4. 에러 0개, 경고 최소화 확인

### 코드 품질 셀프리뷰
- [ ] 커밋 메시지가 Conventional Commits 형식인가?
  - 예: `feat: add semantic header and navigation`
  - `fix:`, `chore:`, `docs:` 등
- [ ] 불필요한 `console.log` 없는가?
- [ ] `.env` 파일이나 민감정보 커밋 안 했나?
- [ ] 코드 포맷팅 (들여쓰기 2 or 4 spaces) 일관되었나?

---

## 🆘 트러블슈팅

### 문제 1: CSS 적용이 안 돼요
**원인**: `styles.css` 파일 링크가 없거나 경로가 틀림
**해결**:
```html
<!-- head 안에 이 줄이 있는지 확인 -->
<link rel="stylesheet" href="styles.css">
```

### 문제 2: margin이 예상과 다르게 적용돼요
**원인**: margin collapsing (부모-자식 margin 합쳐짐)
**해결**: padding이나 border 추가, 또는 overflow: auto

### 문제 3: 요소 크기가 예상보다 커요
**원인**: box-sizing: content-box 기본값
**해결**: `* { box-sizing: border-box; }` 추가

### 문제 4: GitHub Pages 배포가 안 돼요
**원인**: repository 설정에서 Pages 기능 활성화 안 함
**해결**:
1. GitHub repo Settings → Pages
2. Source: Deploy from a branch
3. Branch: main, / (root)
4. Save

---

## 📊自我 평가

### 기술 이해도 (1-10점)
- Semantic HTML: ____ 점
- CSS Box Model: ____ 점
- Git/GitHub: ____ 점

### 코드 품질
- HTML validity: 통과 / 실패
- CSS 정리 상태: 깔끔함 / 개선필요
- 커밋 메시지 규칙: 준수 / 비준수

### 시간 투자
- 총 코딩 시간: ____ 시간
- 학습 시간 (문서 읽기): ____ 시간
- 금일 목표 달성: ✅ / ❌

### 질문/고민
1.
2.

---

## 🚀 다음 주차 (Week 2) 미리보기

**Week 2 주제**: Flexbox, Grid, Responsive Design

주요 학습 내용:
- CSS Flexbox (1D layout)
- CSS Grid (2D layout)
- 반응형 웹 디자인 (Media Queries)
- 모바일/태블릿/데스크탑 레이아웃

과제: 현재 포트폴리오 사이트를 반응형으로 개선

---

**Week 1 완료 후**:
1. GitHub repository URL을 커뮤니티에 공유 (코드 리뷰)
2. "Week 1 완료했습니다!"라고 알려주세요
3. 궁금한 점이나 피드백 요청하기
