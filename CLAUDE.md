# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

---

## 언어 및 커뮤니케이션 규칙

- **기본 응답 언어**: 한국어
- **코드 주석**: 한국어로 작성
- **커밋 메시지**: 한국어로 작성
- **문서화**: 한국어로 작성
- **변수명/함수명**: 영어 (코드 표준 준수)

---

## 프로젝트 개요

개인 개발자 웹 이력서 사이트. 빌드 도구 없이 브라우저에서 직접 실행되는 순수 정적 사이트다.

- **기술 스택**: HTML5, CSS3, Vanilla JavaScript, TailwindCSS (CDN)
- **외부 의존성**: TailwindCSS CDN, Font Awesome CDN, Google Fonts
- **배포**: GitHub Pages 또는 Netlify (정적 파일 그대로 배포)

---

## 실행 방법

빌드 과정이 없으므로 `index.html`을 브라우저에서 직접 열면 된다.

```bash
# VS Code Live Server 사용 (권장)
# 우클릭 → "Open with Live Server"

# 또는 Python 로컬 서버
python -m http.server 3000
# → http://localhost:3000 접속
```

TailwindCSS는 CDN으로 로드되므로 별도 설치나 빌드 명령이 없다.

---

## 프로젝트 구조

```
├── index.html          # 단일 페이지 — 모든 섹션 포함
├── style.css           # TailwindCSS로 표현 안 되는 커스텀 스타일 (타이핑 커서, 스크롤바 등)
├── main.js             # 모든 인터랙션 로직
├── assets/
│   ├── profile.jpg     # 프로필 이미지
│   ├── resume.pdf      # 다운로드용 PDF 이력서
│   └── projects/       # 프로젝트 스크린샷 이미지
└── ROADMAP.md          # 개발 단계별 체크리스트
```

---

## 아키텍처 핵심 사항

### HTML 섹션 구조

`index.html`은 단일 파일 SPA 형태다. 섹션 순서: `header` → `#hero` → `#about` → `#skills` → `#experience` → `#projects` → `#education` → `#contact` → `footer`.

각 섹션은 `id`로 앵커 링크 타깃이 되며, 네비게이션 스크롤 스파이가 이 `id`를 기준으로 활성 링크를 판별한다.

### TailwindCSS 사용 방식

CDN 방식이므로 `tailwind.config` 없이 사용한다. 다크모드는 `class` 전략(`dark:` 접두사)으로 구현하며, `<html>` 태그에 `class="dark"`를 JS로 토글한다.

```html
<script>
  // TailwindCSS CDN에 darkMode: 'class' 설정 주입
  tailwind.config = { darkMode: 'class' }
</script>
```

TailwindCSS로 표현하기 어려운 스타일(타이핑 커서 깜빡임, 커스텀 스크롤바, 타임라인 세로선 등)만 `style.css`에 작성한다.

### JavaScript (`main.js`) 구조

빌드 도구 없이 ES 모듈을 사용하지 않는 단순 스크립트다. 기능별로 함수를 분리하되 전역 스코프 오염을 최소화한다.

| 기능 | 구현 방식 |
|------|-----------|
| 다크모드 토글 | `localStorage` + `<html>` class 토글 |
| 스크롤 스파이 | `IntersectionObserver` API |
| 타이핑 애니메이션 | `setInterval` + 텍스트 배열 순환 |
| 스크롤 진입 애니메이션 | `IntersectionObserver` API |
| 햄버거 메뉴 | CSS `hidden`/`block` 토글 |
| 상단 이동 버튼 | `scroll` 이벤트 + `scrollY` 임계값 |

### 반응형 브레이크포인트

TailwindCSS 기본 브레이크포인트를 그대로 사용한다.

- 모바일: 기본 (단일 컬럼)
- 태블릿: `md:` (768px~)
- 데스크톱: `lg:` (1024px~)

컨텐츠 최대 너비는 `max-w-5xl mx-auto px-4`로 고정한다.

### 디자인 토큰

| 용도 | 라이트 | 다크 |
|------|--------|------|
| Primary | `indigo-600` | `indigo-400` |
| 배경 | `gray-50` | `gray-900` |
| 카드 | `white` | `gray-800` |
| 본문 텍스트 | `gray-900` | `gray-100` |
| 보조 텍스트 | `gray-500` | `gray-400` |

---

## 커밋 메시지 규칙

```
타입: 변경 내용 요약

타입 목록:
  feat     새 기능 추가
  fix      버그 수정
  style    CSS/스타일 변경 (기능 변경 없음)
  refactor 코드 리팩토링
  content  이력서 콘텐츠 수정
  docs     문서 수정
  chore    설정, 파일 구조 변경

예시:
  feat: 다크모드 토글 기능 구현
  style: Hero 섹션 모바일 반응형 수정
  content: 프로젝트 섹션 WeatherNow 설명 업데이트
```
