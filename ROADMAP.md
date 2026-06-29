# 개발자 웹 이력서 개발 로드맵

## 프로젝트 개요

- **목표**: 개인 개발자 웹 이력서 제작
- **기술 스택**: HTML5, CSS3, JavaScript (Vanilla), TailwindCSS
- **배포 목표**: GitHub Pages 또는 Netlify
- **예상 기간**: 2주

---

## 이력서 구성 내용

### 기본 정보

```
이름     : 홍길동
직책     : 풀스택 웹 개발자 (3년 경력)
이메일   : hong@example.com
GitHub   : github.com/honggildong
LinkedIn : linkedin.com/in/honggildong
위치     : 서울, 대한민국
```

### 자기소개 (Hero / About)

> 사용자 경험을 중시하는 풀스택 웹 개발자입니다.
> React와 Node.js를 주력으로 사용하며, 읽기 쉬운 코드와
> 유지보수 가능한 아키텍처를 지향합니다.

### 기술 스택 (Skills)

| 분류       | 기술                                      |
|------------|-------------------------------------------|
| Frontend   | HTML, CSS, JavaScript, React, TailwindCSS |
| Backend    | Node.js, Express, REST API                |
| Database   | MySQL, MongoDB                            |
| DevOps     | Git, GitHub, Docker (기초), Vercel        |
| Tools      | VS Code, Figma, Postman                   |

### 경력 (Experience)

```
2022.03 ~ 현재   (주)ABC테크 — 프론트엔드 개발자
  - React 기반 사내 관리 시스템 개발 및 유지보수
  - TailwindCSS 도입으로 스타일 작업 시간 40% 단축
  - REST API 연동 및 상태 관리 (Redux) 적용

2021.01 ~ 2022.02  XYZ스타트업 — 주니어 웹 개발자
  - 반응형 랜딩 페이지 10건 이상 제작
  - Vanilla JS로 인터랙티브 UI 컴포넌트 개발
```

### 프로젝트 (Projects)

```
1. TodoMaster
   - 설명 : React + Node.js 기반 할 일 관리 앱
   - 역할 : 풀스택 개발 (1인 프로젝트)
   - 링크 : github.com/honggildong/todomaster

2. WeatherNow
   - 설명 : OpenWeather API 연동 날씨 대시보드
   - 역할 : 프론트엔드 개발
   - 링크 : github.com/honggildong/weathernow

3. DevBlog
   - 설명 : 마크다운 기반 개인 기술 블로그
   - 역할 : 풀스택 개발
   - 링크 : github.com/honggildong/devblog
```

### 학력 (Education)

```
2017.03 ~ 2021.02  한국대학교 컴퓨터공학과 졸업 (학사)
```

### 자격증 (Certifications)

```
- 정보처리기사 (2021.06)
- SQL 개발자 SQLD (2022.03)
```

---

## 페이지 섹션 구조

```
index.html
│
├── <header>       네비게이션 바 (이름 로고 + 섹션 링크 + 다크모드 토글)
│
├── #hero          이름, 직책, 한 줄 소개, CTA 버튼 (이력서 다운로드 / 연락하기)
│
├── #about         자기소개 텍스트 + 프로필 이미지
│
├── #skills        기술 스택 카드 그리드
│
├── #experience    타임라인 형태의 경력 사항
│
├── #projects      프로젝트 카드 (썸네일 + 설명 + GitHub 링크)
│
├── #education     학력 및 자격증
│
├── #contact       이메일 / GitHub / LinkedIn 링크 + 간단 문의 폼
│
└── <footer>       저작권 표기
```

---

## 개발 단계

### Phase 1 — 환경 설정 (1일)

- [ ] 프로젝트 폴더 구조 생성
- [ ] TailwindCSS CDN 또는 CLI 설정
- [ ] `index.html` 기본 뼈대 작성
- [ ] 폰트 설정 (Google Fonts — Noto Sans KR)
- [ ] CSS 변수 정의 (색상, 폰트 크기)
- [ ] Git 저장소 초기화 및 GitHub 연결

```
프로젝트 폴더 구조
├── index.html
├── style.css          (TailwindCSS 커스텀 스타일 보완용)
├── main.js            (인터랙션 스크립트)
├── assets/
│   ├── profile.jpg
│   ├── resume.pdf     (다운로드용 PDF 이력서)
│   └── projects/      (프로젝트 스크린샷)
└── ROADMAP.md
```

---

### Phase 2 — 레이아웃 & 섹션 마크업 (3일)

- [ ] 네비게이션 바 (sticky, 스크롤 시 배경 변화)
- [ ] Hero 섹션 (풀 뷰포트 높이, 타이핑 애니메이션)
- [ ] About 섹션 (2컬럼 레이아웃)
- [ ] Skills 섹션 (카드 그리드)
- [ ] Experience 섹션 (수직 타임라인)
- [ ] Projects 섹션 (카드 그리드, 호버 효과)
- [ ] Education 섹션
- [ ] Contact 섹션 (SNS 아이콘 + mailto 링크)
- [ ] Footer

---

### Phase 3 — 스타일링 (3일)

- [ ] TailwindCSS 유틸리티 클래스 적용
- [ ] 반응형 디자인 적용 (모바일 → 태블릿 → 데스크톱)
  - 모바일 기준(320px~): 단일 컬럼
  - 태블릿(768px~): 2컬럼
  - 데스크톱(1024px~): 최대 너비 제한 + 여백
- [ ] 다크 모드 구현 (TailwindCSS `dark:` 클래스 + JS 토글)
- [ ] 색상 테마 정의 (Primary: 인디고 계열)
- [ ] 호버 / 포커스 상태 스타일
- [ ] 스크롤바 커스텀

---

### Phase 4 — JavaScript 인터랙션 (2일)

- [ ] 스크롤 스파이 (현재 섹션 네비 링크 활성화)
- [ ] 스무스 스크롤 구현
- [ ] 다크모드 토글 + `localStorage` 저장
- [ ] 타이핑 애니메이션 (Hero 섹션 직책 텍스트)
- [ ] 스크롤 진입 시 요소 페이드인 (Intersection Observer API)
- [ ] 모바일 햄버거 메뉴
- [ ] 상단으로 이동 버튼 (일정 스크롤 후 표시)

---

### Phase 5 — 콘텐츠 입력 & 마무리 (2일)

- [ ] 실제 이력서 내용 입력 (텍스트, 이미지)
- [ ] PDF 이력서 파일 연결 (다운로드 버튼)
- [ ] Favicon 설정
- [ ] OG 태그 설정 (소셜 미리보기)
- [ ] 크로스 브라우저 테스트 (Chrome, Firefox, Safari, Edge)
- [ ] 모바일 기기 실제 테스트

---

### Phase 6 — 최적화 & 배포 (1일)

- [ ] 이미지 최적화 (WebP 변환, 적절한 크기)
- [ ] Lighthouse 성능 검사 (목표: 90점 이상)
- [ ] 접근성 검토 (alt 텍스트, aria-label, 키보드 내비게이션)
- [ ] GitHub Pages 또는 Netlify 배포
- [ ] 커스텀 도메인 연결 (선택 사항)

---

## 디자인 가이드

### 색상

| 용도          | 라이트 모드        | 다크 모드          |
|---------------|--------------------|--------------------|
| Primary       | `indigo-600`       | `indigo-400`       |
| Background    | `white` / `gray-50`| `gray-900`         |
| Text (주)     | `gray-900`         | `gray-100`         |
| Text (보조)   | `gray-500`         | `gray-400`         |
| Card 배경     | `white`            | `gray-800`         |
| Border        | `gray-200`         | `gray-700`         |

### 타이포그래피

| 용도           | 크기           | 굵기        |
|----------------|----------------|-------------|
| 이름 (Hero)    | `text-5xl`     | `font-bold` |
| 섹션 제목      | `text-3xl`     | `font-bold` |
| 서브 제목      | `text-xl`      | `font-semibold` |
| 본문           | `text-base`    | `font-normal` |
| 보조 텍스트    | `text-sm`      | `font-normal` |

### 간격

- 섹션 패딩: `py-20`
- 컨텐츠 최대 너비: `max-w-5xl mx-auto px-4`
- 카드 간격: `gap-6`

---

## 참고 라이브러리 (CDN)

```html
<!-- TailwindCSS -->
<script src="https://cdn.tailwindcss.com"></script>

<!-- Font Awesome (아이콘) -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<!-- Google Fonts -->
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@400;500;700&display=swap" rel="stylesheet">
```

---

## 완성 체크리스트

### 기능
- [ ] 모든 섹션 정상 표시
- [ ] 네비게이션 스크롤 이동 동작
- [ ] 다크모드 토글 및 유지
- [ ] 이력서 PDF 다운로드
- [ ] 모바일 햄버거 메뉴 동작
- [ ] 외부 링크 (GitHub, LinkedIn) 새 탭 열기

### 반응형
- [ ] 모바일 (360px) 정상 표시
- [ ] 태블릿 (768px) 정상 표시
- [ ] 데스크톱 (1280px) 정상 표시

### 성능 & 품질
- [ ] Lighthouse Performance 90+
- [ ] Lighthouse Accessibility 90+
- [ ] 이미지 alt 텍스트 전체 입력
- [ ] 콘솔 에러 없음

### 배포
- [ ] GitHub 저장소 public 설정
- [ ] GitHub Pages / Netlify 배포 완료
- [ ] 배포 URL 정상 접속 확인
