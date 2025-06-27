# Astro Starter - Jinseoit

Astro 기반으로 제작된 개인 기술 블로그 스타터 템플릿으로, 깔끔한 디자인과 빠른 성능을 갖춘 정적 웹사이트입니다.

![Astro Starter Jinseoit](/public/preview.png)

## ✨ 주요 기능

- 🎨 **다크/라이트 테마 지원** - 사용자 선호도에 따른 자동 테마 전환
- 📱 **완전 반응형 디자인** - 모든 디바이스에서 최적화된 경험
- ⚡ **빠른 로딩 속도** - 100/100 Lighthouse 성능 점수
- 🔍 **SEO 최적화** - 메타 태그, OpenGraph, 구조화된 데이터 지원
- 📝 **마크다운 지원** - 코드 하이라이팅과 복사 기능 포함
- 🏷️ **태그 시스템** - 포스트 분류 및 필터링 (무한 스크롤)
- 📡 **RSS 피드** - 구독자들을 위한 자동 피드 생성
- 🗺️ **사이트맵** - 검색 엔진 최적화
- 🎯 **접근성 고려** - 키보드 네비게이션 및 스크린 리더 지원
- 🖼️ **이미지 최적화** - 스켈레톤 로딩 및 지연 로딩
- 🔄 **무한 스크롤** - 성능 최적화된 포스트 로딩
- 🏗️ **SOLID 원칙** - 체계적인 코드 구조 및 타입 안전성

## 🚀 기술 스택

- **프레임워크**: [Astro](https://astro.build/) - 빠른 정적 사이트 생성
- **스타일링**: [Tailwind CSS](https://tailwindcss.com/) - 유틸리티 퍼스트 CSS
- **언어**: [TypeScript](https://www.typescriptlang.org/) - 타입 안전성
- **폰트**: [Pretendard](https://cactus.tistory.com/232) - 한글 최적화 폰트
- **패키지 매니저**: [pnpm](https://pnpm.io/) - 빠른 패키지 설치
- **아이콘**: [Lucide Icons](https://lucide.dev/) - 깔끔한 SVG 아이콘

## 📁 프로젝트 구조

```
astro-starter-jinseoit/
├── public/
│   ├── fonts/
│   └── favicon.svg
├── src/
│   ├── assets/
│   │   └── icons/
│   ├── components/
│   │   ├── Header.astro
│   │   ├── Footer.astro
│   │   ├── PostCard.astro
│   │   ├── TagList.astro
│   │   ├── ThemeToggle.astro
│   │   └── LoadingIndicator.astro
│   ├── constants/
│   │   ├── index.ts
│   │   ├── site.ts
│   │   ├── ui.ts
│   │   ├── routes.ts
│   │   └── events.ts
│   ├── content/
│   │   └── posts/
│   ├── layouts/
│   │   ├── BaseLayout.astro
│   │   ├── MainLayout.astro
│   │   └── PostLayout.astro
│   ├── pages/
│   │   ├── index.astro
│   │   ├── posts/
│   │   ├── tags/
│   │   └── rss.xml.js
│   ├── styles/
│   │   ├── global.css
│   │   └── markdown.css
│   ├── types/
│   │   └── index.ts
│   └── utils/
│       └── tagListLogic.ts
├── scripts/
│   └── new-post.js
├── astro.config.mjs
├── tailwind.config.ts
├── tsconfig.json
└── package.json
```

## 🛠️ 설치 및 실행

### 필수 요구사항

- Node.js 18.0.0 이상
- pnpm (권장) 또는 npm

### 설치

```bash
# 저장소 클론
git clone https://github.com/your-username/astro-starter-jinseoit.git
cd astro-starter-jinseoit

# 의존성 설치
pnpm install
```

### 개발 서버 실행

```bash
# 개발 서버 시작 (localhost:4321)
pnpm dev
```

### 빌드 및 배포

```bash
# 프로덕션 빌드
pnpm build

# 빌드 미리보기
pnpm preview
```

## 📝 포스트 작성

### 새 포스트 생성 스크립트 사용

```bash
# 새 포스트 생성 (자동으로 conents/posts 마크다운 파일 생성)
pnpm new-post
```

### 수동으로 포스트 작성

`src/content/posts/` 디렉토리에 마크다운 파일을 생성하세요:

```markdown
---
title: "포스트 제목"
description: "포스트 설명"
pubDate: 2024-01-01
tags: ["태그1", "태그2"]
---

포스트 내용...
```

### 지원하는 frontmatter 필드

- `title`: 포스트 제목 (필수)
- `description`: 포스트 설명 (선택)
- `pubDate`: 발행일 (필수)
- `tags`: 태그 배열 (선택)
- `image`: 대표 이미지 경로 (선택)
- `author`: 작성자 (선택, 기본값: DEFAULT_AUTHOR)

## 🎨 커스터마이징

### 사이트 정보 변경

`src/constants/site.ts`에서 사이트 기본 정보를 수정하세요:

```typescript
export const SITE_TITLE = "Jinseoit Blog";
export const SITE_DESCRIPTION = "개인 기술 블로그";
export const DEFAULT_AUTHOR = "jinseoit";
```

### 색상 테마 변경

`src/styles/global.css`에서 CSS 변수를 수정하여 색상을 변경할 수 있습니다:

```css
:root {
  --primary-color: #66cdaa; /* 메인 색상 */
  --text-color: oklch(30% 0 0); /* 텍스트 색상 */
  --card-color: oklch(100% 0 0); /* 카드 배경색 */
}
```

### UI 상수 변경

`src/constants/ui.ts`에서 UI 관련 상수들을 수정할 수 있습니다:

```typescript
export const UI_CONSTANTS = {
  IMAGE_LOAD_DELAY: 200,
  INTERSECTION_ROOT_MARGIN: "100px",
  INTERSECTION_THRESHOLD: 0.1,
  POSTS_PER_LOAD: 5, // 무한 스크롤 시 한 번에 로드할 포스트 수
};
```

## 🔧 주요 컴포넌트

### PostCard

포스트 목록에서 사용되는 카드 컴포넌트로, 이미지 로딩 스켈레톤과 호버 애니메이션을 지원합니다.

### ThemeToggle

다크/라이트 테마 전환 버튼으로, 사용자 선호도를 localStorage에 저장합니다.

### TagList

포스트 태그를 표시하고 필터링 기능을 제공하는 컴포넌트입니다. 무한 스크롤과 성능 최적화가 적용되어 있습니다.

### LoadingIndicator

무한 스크롤 시 로딩 상태를 표시하는 컴포넌트입니다.

## 🏗️ 아키텍처 특징

### SOLID 원칙 적용

- **단일 책임 원칙 (SRP)**: 각 모듈이 하나의 명확한 책임을 가짐
- **개방-폐쇄 원칙 (OCP)**: 확장에는 열려있고 수정에는 닫혀있음
- **의존성 역전 원칙 (DIP)**: 추상화에 의존하고 구체화에 의존하지 않음

### 타입 안전성

- TypeScript를 사용한 완전한 타입 안전성
- 중앙 집중식 타입 관리 (`src/types/`)
- 상수와 타입의 명확한 분리

### 성능 최적화

- **이미지 최적화**: WebP 포맷 사용 및 적응형 이미지
- **폰트 최적화**: Pretendard 폰트의 woff2 포맷 사용
- **CSS 최적화**: Tailwind CSS의 PurgeCSS로 사용하지 않는 스타일 제거
- **JavaScript 최적화**: Astro의 부분 하이드레이션으로 필요한 부분만 JS 로드
- **무한 스크롤**: Intersection Observer API를 사용한 효율적인 로딩
- **이미지 지연 로딩**: 스켈레톤 UI와 함께 부드러운 로딩 경험

## 🌐 배포

이 프로젝트는 정적 사이트이므로 다양한 플랫폼에 배포할 수 있습니다:

### Vercel (권장)

```bash
npm install -g vercel
vercel --prod
```

### Netlify

```bash
npm install -g netlify-cli
netlify deploy --prod
```

### GitHub Pages

GitHub Actions를 사용하여 자동 배포 설정 가능

### Cloudflare Pages

Git 저장소 연결 후 자동 배포 지원

## 📄 라이선스

MIT License - 자유롭게 사용하고 수정할 수 있습니다.

## 🤝 기여하기

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

**Made with 🙂 by Jinseoit**
