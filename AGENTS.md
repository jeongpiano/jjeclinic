# 전주E재활의학과의원 홈페이지

> **통원으로 다시 일상으로** - 전주 통원재활 전문 의원 홈페이지 프로젝트

모바일 우선 반응형 웹사이트. HTML5 + Tailwind CSS 정적 사이트.

## 프로젝트 개요

- **목적:** 통원재활 중심 의원 홈페이지
- **목표:** 모바일 우선, 빠른 전환 동선 (이해 → 신뢰 → 상담신청)
- **기술:** HTML5 + Tailwind CSS (CDN)
- **배포:** Vercel / Netlify
- **타겟:** 50-70대 환자 및 보호자

## 빠른 시작

### 로컬 실행
```bash
# 브라우저로 열기
open index.html  # macOS
start index.html # Windows

# 또는 VSCode Live Server
# index.html 우클릭 → Open with Live Server
```

### 배포
```bash
# Vercel CLI (권장)
npm i -g vercel
vercel

# 또는 GitHub 연동
# 1. GitHub에 푸시
# 2. vercel.com → New Project → Import
```

**자세한 가이드:** `deployment-guide.md`

## 파일 구조

```
jeonju-e-rehab/
├── index.html              # 메인 사이트 (단일 페이지, 822줄)
├── README.md               # 프로젝트 소개
├── AGENTS.md               # 이 파일
├── deployment-guide.md     # Vercel/Netlify 배포 가이드
├── seo-guide.md            # SEO 최적화 가이드
├── naver-place-checklist.md # 네이버 플레이스 등록 체크리스트
└── wireframe.md            # 페이지 구조/와이어프레임
```

## 페이지 구성 (섹션별)

### 1. Hero Section
- **목적:** 첫인상 + 핵심 메시지
- **내용:** "통원으로 다시 일상으로" + 주요 치료 분야
- **CTA:** 상담신청 버튼 (즉시 전환)

### 2. 통원재활 안내
- **목적:** 통원재활 개념 설명
- **내용:** 
  - 통원재활이란?
  - 입원과의 차이
  - 장점 (일상 병행, 비용 절감)
- **시각 자료:** 비교 표, 일정 예시

### 3. 질환별 프로그램 (4개)
- **뇌졸중 재활**
- **척추손상 재활**
- **파킨슨병 재활**
- **기타 신경계 질환**

각 프로그램:
- 대상 환자
- 주요 증상
- 치료 방법
- 기대 효과

### 4. 치료 프로세스
- **목적:** 신뢰 구축
- **단계:**
  1. 초기 평가 (무료 상담)
  2. 맞춤 치료 계획 수립
  3. 집중 치료 (주 3-5회)
  4. 정기 재평가
  5. 유지 관리

### 5. 시설·치료팀
- **의료진 소개** (원장, 물리치료사, 작업치료사)
- **시설 사진** (치료실, 기구)
- **인증/자격** (전문의 자격, 장비 인증)

### 6. 상담신청 + 오시는길
- **상담 신청 폼** (이름, 연락처, 간단 문의)
- **전화 번호** (클릭 시 바로 전화)
- **카카오톡 상담** (링크)
- **지도** (네이버 지도 embed)
- **대중교통 안내**

## 기술 스택

### HTML5
- **시맨틱 태그 사용** (`<header>`, `<main>`, `<section>`, `<article>`)
- **접근성 속성** (`alt`, `aria-label`, `role`)
- **Open Graph 메타 태그** (SNS 공유 최적화)

### Tailwind CSS (CDN)
```html
<script src="https://cdn.tailwindcss.com"></script>
```

**주요 클래스:**
- **반응형:** `md:`, `lg:` 브레이크포인트
- **간격:** `p-4`, `m-8`, `gap-6`
- **색상:** `bg-blue-600`, `text-gray-800`
- **버튼:** `bg-blue-600 hover:bg-blue-700 px-6 py-3 rounded-lg`

### JavaScript (최소화)
- **스크롤 이벤트** (네비게이션 고정, 섹션 표시)
- **폼 제출** (상담 신청)
- **모바일 메뉴** (햄버거 메뉴 토글)

## 개발 워크플로우

### 새 섹션 추가
1. **HTML 구조 작성**
   ```html
   <section id="new-section" class="py-16 bg-gray-50">
     <div class="container mx-auto px-4">
       <h2 class="text-3xl font-bold mb-8">섹션 제목</h2>
       <!-- 내용 -->
     </div>
   </section>
   ```

2. **Tailwind 스타일링**
   - 모바일 우선 (기본 클래스)
   - 태블릿: `md:` 접두사
   - 데스크톱: `lg:` 접두사

3. **접근성 체크**
   - 제목 계층 (h1 → h2 → h3)
   - 이미지 alt 텍스트
   - 버튼 aria-label

4. **로컬 테스트**
   - 브라우저에서 열기
   - 반응형 확인 (DevTools)
   - 모바일 시뮬레이터

### 콘텐츠 수정
1. **index.html에서 해당 섹션 찾기**
   - Cmd+F / Ctrl+F로 섹션 id 검색
   - 예: `id="treatment-process"`

2. **텍스트 수정**
   - 환자 중심 언어 사용
   - 전문 용어 최소화
   - 구체적 혜택 강조

3. **이미지 교체**
   ```html
   <img src="https://example.com/image.jpg" 
        alt="구체적인 설명" 
        class="w-full h-auto rounded-lg">
   ```

4. **CTA 버튼 수정**
   ```html
   <a href="tel:063-123-4567" 
      class="bg-blue-600 hover:bg-blue-700 text-white px-6 py-3 rounded-lg">
     지금 상담 신청
   </a>
   ```

## SEO 최적화

### 메타 태그 (필수)
```html
<title>전주E재활의학과의원 | 통원재활 전문</title>
<meta name="description" content="전주 통원재활 전문 의원. 뇌졸중, 척추손상, 파킨슨병 재활 프로그램. 일상과 병행하는 맞춤 치료.">
<meta name="keywords" content="전주 재활의학과, 통원재활, 뇌졸중 재활, 척추손상 재활">
```

### Open Graph (SNS 공유)
```html
<meta property="og:title" content="전주E재활의학과의원">
<meta property="og:description" content="통원으로 다시 일상으로">
<meta property="og:image" content="https://example.com/og-image.jpg">
```

### 구조화된 데이터 (Schema.org)
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "MedicalClinic",
  "name": "전주E재활의학과의원",
  "address": {
    "@type": "PostalAddress",
    "addressLocality": "전주시",
    "addressRegion": "전라북도",
    "streetAddress": "..."
  },
  "telephone": "063-123-4567"
}
</script>
```

**자세한 가이드:** `seo-guide.md`

## 네이버 플레이스 연동

### 필수 작업
1. **네이버 비즈니스 등록**
2. **사업자 정보 입력**
3. **대표 사진 업로드** (외관, 내부, 치료실)
4. **운영 시간 설정**
5. **예약 링크 연결**

**자세한 체크리스트:** `naver-place-checklist.md`

## 콘텐츠 가이드라인

### 환자 중심 언어
❌ **나쁜 예:**
- "본원은 재활의학과 전문의가 운영합니다"
- "최신 장비를 보유하고 있습니다"

✅ **좋은 예:**
- "뇌졸중 이후 일상 복귀를 도와드립니다"
- "집에서 가까운 곳에서 꾸준히 치료받으세요"

### 신뢰 요소
- **자격증/인증** 명시
- **치료 과정** 투명하게 공개
- **환자 사례** (개인정보 보호)
- **전후 비교** (객관적 지표)

### CTA (전환 유도)
- **명확한 행동** - "상담 신청", "전화하기"
- **긴급성** - "오늘 문의 시 초기평가 무료"
- **간편성** - "클릭 한 번으로 전화 연결"

## 반응형 디자인

### 브레이크포인트
- **모바일:** 기본 (< 768px)
- **태블릿:** `md:` (≥ 768px)
- **데스크톱:** `lg:` (≥ 1024px)

### 모바일 우선 패턴
```html
<!-- 모바일: 1열, 태블릿: 2열, 데스크톱: 3열 -->
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
  <!-- 카드들 -->
</div>

<!-- 모바일: 작은 텍스트, 데스크톱: 큰 텍스트 -->
<h1 class="text-2xl md:text-4xl lg:text-5xl">제목</h1>
```

## 성능 최적화

### 이미지
- **포맷:** WebP 권장 (JPEG fallback)
- **크기:** 모바일 800px, 데스크톱 1920px
- **압축:** TinyPNG, ImageOptim
- **Lazy Loading:**
  ```html
  <img loading="lazy" src="..." alt="...">
  ```

### CSS/JS
- **Tailwind CDN 사용** (빠른 프로토타입)
- **프로덕션:** Tailwind CLI로 빌드 (파일 크기 90% 감소)
- **JavaScript 최소화** - 바닐라 JS 선호

### 배포 최적화
- **Vercel/Netlify** - 자동 CDN, HTTPS
- **압축** - Gzip/Brotli 자동 적용
- **캐싱** - 정적 파일 캐시 설정

## 자주 쓰는 패턴

### 섹션 헤더
```html
<div class="text-center mb-12">
  <h2 class="text-3xl font-bold mb-4">섹션 제목</h2>
  <p class="text-gray-600 max-w-2xl mx-auto">
    섹션 설명 텍스트
  </p>
</div>
```

### 카드 그리드
```html
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
  <div class="bg-white p-6 rounded-lg shadow-md">
    <h3 class="text-xl font-bold mb-2">카드 제목</h3>
    <p class="text-gray-600">카드 내용</p>
  </div>
  <!-- 더 많은 카드들 -->
</div>
```

### CTA 버튼
```html
<!-- 전화 -->
<a href="tel:063-123-4567" 
   class="inline-block bg-blue-600 hover:bg-blue-700 text-white px-8 py-4 rounded-lg text-lg font-bold transition">
  📞 전화 상담
</a>

<!-- 카카오톡 -->
<a href="https://pf.kakao.com/_xyz" 
   class="inline-block bg-yellow-400 hover:bg-yellow-500 text-gray-900 px-8 py-4 rounded-lg text-lg font-bold transition">
  💬 카카오톡 상담
</a>
```

## OpenClaw 스킬 연동

이 프로젝트는 다음 스킬과 함께 사용하세요:

### rehab-blog-post
```bash
# 블로그 포스트 작성
"통원재활 vs 입원재활 비교" 주제로 블로그 포스트 써줘
```

### rehab-homepage-section
```bash
# 홈페이지 섹션 추가/수정
"환자 후기" 섹션 추가해줘
```

### rehab-sns-content
```bash
# SNS 컨텐츠 생성
Instagram Reels 스크립트: "뇌졸중 재활 5단계"
```

## 업데이트 체크리스트

### 콘텐츠 업데이트
- [ ] 환자 사례 추가 (분기별)
- [ ] 치료팀 정보 갱신 (변동 시)
- [ ] 운영 시간 확인 (명절/휴진)
- [ ] 이벤트/프로모션 추가

### 기술 유지보수
- [ ] 링크 체크 (깨진 링크 확인)
- [ ] 이미지 최적화
- [ ] 네이버 플레이스 정보 동기화
- [ ] Google Analytics 확인

### SEO 모니터링
- [ ] 네이버/구글 검색 노출 확인
- [ ] 키워드 순위 체크
- [ ] 페이지 속도 측정 (PageSpeed Insights)

## 배포 가이드

### Vercel (권장)
1. **GitHub 연동**
   ```bash
   git remote add origin https://github.com/your-username/jeonju-e-rehab.git
   git push -u origin main
   ```

2. **Vercel Import**
   - vercel.com → New Project
   - Import Git Repository
   - Deploy (자동)

3. **도메인 연결**
   - Settings → Domains
   - 커스텀 도메인 추가

**상세 가이드:** `deployment-guide.md`

## 문의/지원

- **프로젝트 관리:** jeongpiano
- **텔레그램:** (토미에게 문의)
- **관련 스킬:**
  - rehab-blog-post
  - rehab-homepage-section
  - rehab-sns-content

---

**마지막 업데이트:** 2026-02-14  
**OpenClaw AGENTS.md 표준 준수**
