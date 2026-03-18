# 나의 포트폴리오 웹사이트

> 풀스택 개발자의 첫걸음

![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)

## 📋 프로젝트 소개

풀스택 개발자를 목표로 하는 제 첫 번째 포트폴리오 웹사이트입니다.

Semantic HTML과 CSS Box Model을 활용하여 웹 표준을 준수하며,
접근성과 SEO를 고려한 구조로 제작되었습니다.

**주요 특징**:
- ✅ Semantic HTML 요소만 사용 (div/span 최소화)
- ✅ CSS Box Model 완벽 적용 (`box-sizing: border-box`)
- ✅ 반응형 웹 디자인 (Mobile-first)
- ✅ 웹 표준 검사 통과

---

## 🎯 학습 목표

이 프로젝트는 "풀스택 개발자 마스터 프로그램"의 **Week 1** 과제로 제작되었습니다.

- **Semantic HTML**: `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>` 등
- **CSS Box Model**: margin, border, padding, content 관계 이해
- **Responsive Design**: Flexbox, Grid, Media Queries
- **Git & GitHub**: 버전 관리 및 코드 공유

---

## 🛠️ 기술 스택

| 기술 | 설명 | 버전 |
|------|------|------|
| HTML5 | Semantic Elements, 웹 표준 | - |
| CSS3 | Flexbox, Grid, Box Model, Responsive | - |
| JavaScript ES6+ | DOM 조작, 이벤트 처리 | ES2020 |
| Git | 버전 관리 | 2.x |

---

## 📁 프로젝트 구조

```
my-portfolio-2026/
├── index.html          # 메인 HTML 파일 (Semantic HTML)
├── styles.css          # 스타일시트 (CSS Box Model 적용)
├── assets/             # 이미지, 폰트 등 (추가 예정)
│   ├── profile.jpg
│   └── project1.png
├── README.md           # 프로젝트 문서 (이 파일)
└── .gitignore         # Git 제외 파일 (필요시)
```

---

## 🚀 실행 방법

### 로컬에서 실행

1. 프로젝트 클론 또는 다운로드
```bash
git clone https://github.com/moony211/framework-learn.git
cd my-portfolio-2026
```

2. 브라우저에서 index.html 파일 열기
   - 방법 1: 파일 더블클릭
   - 방법 2: VS Code Live Server (권장)
   - 방법 3: Python/http.server (옵션)

```bash
# Python 3으로 간단한 HTTP 서버
python -m http.server 8000
# http://localhost:8000 접속
```

3. 브라우저에서 http://localhost:8000 열기

### GitHub Pages 배포 (완료 시)

1. GitHub 저장소 Settings → Pages
2. Source: Deploy from a branch
3. Branch: main, / (root) 폴더 선택
4. Save 후 1-2분 대기
5. URL: https://yourusername.github.io/my-portfolio-2026/

---

## 🎨 주요 기능 및 섹션

### 1. 헤더 & 내비게이션

- Sticky header (스크롤 시 상단 고정)
- 반응형 메뉴 (모바일에서도 접근 가능)
- Smooth scroll 링크 (`html { scroll-behavior: smooth; }`)

### 2. Hero 섹션 (소개)

```html
<section id="about" class="hero">
    <h1>안녕하세요,</h1>
    <h2>풀스택 개발자 이개발입니다</h2>
    <p>사용자 경험을 중시하는 웹 애플리케이션을 만듭니다.</p>
</section>
```

### 3. 기술스택 섹션

- CSS Grid로 반응형 카드 레이아웃
- Hover effect (transform, box-shadow)

### 4. 프로젝트 섹션

- 프로젝트 카드 그리드
- 각 카드: 제목, 설명, 링크

### 5. 푸터 (연락처)

- Social links (GitHub, LinkedIn, Email)
- Copyright 정보

---

## ✅ 검증 및 테스트

### HTML Validation

- https://validator.w3.org/에서 검증 완료
- 에러 0개, 경고 최소화

### 접근성 검사

- https://wave.webaim.org/
- Screen reader 테스트 (옵션)

### 반응형 테스트

- 모바일 (375px, 390px)
- 태블릿 (768px, 1024px)
- 데스크탑 (1200px, 1440px, 1920px)

---

## 📊 코드 품질

### Conventional Commits

```bash
feat: initial portfolio structure with semantic HTML
fix: correct navigation anchor links
docs: update README with project description
```

### CSS Best Practices

- `* { box-sizing: border-box; }` 전역 적용
- Mobile-first media queries
- CSS Custom Properties (예정)
- BEM-like naming convention (block__element--modifier)

---

## 🎓 배운 점 (Learning Log)

### 1. Semantic HTML의 중요성

- **이전에 몰랐던 것**: `<div>`만 사용해도 되지만 의미 없는 태그
- **깨달음**: 스크린 리더, SEO, 유지보수성 모두 향상
- **적용**: 모든 요소를 의미 있는 태그로 대체

### 2. CSS Box Model 이해

- **문제**: padding과 border를 추가하면 요소 크기가 예상보다 커짐
- **해결**: `box-sizing: border-box`로 width/height에 padding+border 포함
- **확신**: 이제 레이아웃 계산이 정확해짐

### 3. 반응형 디자인 Mobile-first

- **시도**: Desktop-first → mobile에서 깨짐
- **개선**: `min-width` media queries로 Mobile-first
- **결과**: 모든 화면에서 자연스러운 레이아웃

---

## 🐛 알려진 이슈 (Known Issues)

### 1. 모바일 메뉴 토글 버튼 없음
- **현재**: 데스크탑만 고려한 내비게이션
- **해결**: Week 2에서 JavaScript로 토글 버튼 추가 예정

### 2. 이미지 최적화 미흡
- **현재**: 이미지 파일 없음 (text-only)
- **해결**: 실제 이미지 추가 시 Next.js Image 컴포넌트로 리팩토링

### 3. JavaScript 동적 기능 부재
- **현재**: 정적 HTML/CSS
- **해결**: Week 3에서 Todo 앱 기능 추가 예정

---

## 📈 진도 현황

| 주차 | 완료 여부 | 주요 내용 | 커밋 수 |
|------|-----------|-----------|---------|
| Week 1 | ✅ 진행 중 | Semantic HTML, CSS Box Model | 5 |
| Week 2 | ⏳ 예정 | Flexbox, Grid, Responsive | - |
| Week 3 | ⏳ 예정 | JavaScript DOM 조작 | - |
| Week 4 | ⏳ 예정 | Async/Await, Fetch API | - |

**총 커밋**: 5개 (2026-03-18 기준)
**최근 커밋**: feat: add contact anchor link to footer

---

## 🔮 향후 계획 (Roadmap)

### Month 1 (4주)
- [x] Week 1: Semantic HTML + CSS Box Model
- [ ] Week 2: Flexbox, Grid, Responsive 완성
- [ ] Week 3: JavaScript Todo 리스트
- [ ] Week 4: Weather App + 포트폴리오 완성

### Month 2 (React)
- [ ] Week 5-8: React Todo 앱으로 리팩토링

### Month 3-12 (전체 커리큘럼)
[전체 커리큘럼](./docs/curriculum/overview.md) 참고

---

## 👨‍💻 저자

**이개발** (Lee Developer)
- 🌱 풀스택 개발자를 꿈꾸는 학습자
- 📚 학습 중: React, Next.js, Node.js
- 📍 위치: 대한민국
- 🔗 https://github.com/moony211
- 📧 moony211@gmail.com

---

## 📚 참고 자료

이 프로젝트 학습을 위해 참고한 자료들:

### 공식 문서
- [MDN Web Docs - HTML](https://developer.mozilla.org/ko/docs/Web/HTML)
- [MDN Web Docs - CSS](https://developer.mozilla.org/ko/docs/Web/CSS)
- [W3C HTML Validator](https://validator.w3.org/)

### 강의/책
- "HTML & CSS: Design and Build Websites" (Jon Duckett)
- 생활코딩 HTML/CSS 강의

### 커뮤니티
- [풀스택 개발자 마스터 프로그램](https://github.com/moony211/framework-learn)
- OKKY, Reddit r/webdev

---

## 📝 라이선스

이 프로젝트는 MIT 라이선스를 따릅니다. 자유롭게 사용, 수정, 배포하세요.

```
MIT License

Copyright (c) 2026 이개발

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

... (전체 라이선스 텍스트)
```

---

## 🙏 감사의 말

이 프로젝트는 다음과 같은 도움을 받았습니다:

- [Claude Code](https://claude.ai/) - 학습 가이드 제공
- [풀스택 개발자 마스터 프로그램](https://github.com/moony211/framework-learn) 커리큘럼
- 여러 온라인 커뮤니티의 도움

**감사합니다!** 🎉

---

## 🎯 **핵심 포인트**

### 1. 제목과 설명
- 첫 줄: 명확한 프로젝트 이름 + tagline
- Badge: 기술 스택 시각적 표시 (선택)

### 2. 학습 목표
- "이 프로젝트가 무엇을 위한 것인가"
- Week 1의 학습 목표와 연결

### 3. 기술 스택
- 표 형식으로 정리 (기술명, 설명, 버전)
- Badge로 시각적 강조 (선택)

### 4. 실행 방법
- 누구나 따라할 수 있는 상세한 단계
- 의존성 설치 명령어 (지금은 없음)

### 5. 배운 점 (가장 중요!)
- 실제로 배운 내용
- 이전에 몰랐던 것 → 깨달음 → 적용
- 나중에 면접 시 "이 프로젝트에서 뭘 배웠나요?" 질문에 바로 대답 가능

### 6. 알려진 이슈
- 완벽하지 않음을 인정
- 향후 개선 계획 명시 (성숙한 개발자 이미지)

### 7. 향후 계획
- 다음 주차 일정 포함
- 전체 커리큘럼 링크
