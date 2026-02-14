# SEO 기본 세팅 가이드

## 1. 메타태그 최적화

### 기본 메타태그 (이미 index.html에 포함됨)

```html
<title>전주E재활의학과의원 - 전주 통원재활 전문 | 뇌졸중·척추손상·보행재활</title>
<meta name="description" content="전주 통원재활 전문 의원. 뇌졸중, 척추손상, 보행장애, 근골격계 재활 프로그램. 일상으로의 복귀를 위한 맞춤형 치료 계획.">
<meta name="keywords" content="전주 재활의학과, 전주 통원재활, 뇌졸중 재활, 척추손상 재활, 보행재활, 전주 물리치료">
```

### 각 페이지별 맞춤 Title & Description

#### 통원재활 안내 페이지
```html
<title>통원재활이란? - 전주E재활의학과의원 | 입원 없이 일상 속 재활</title>
<meta name="description" content="통원재활의 장점과 프로세스. 입원 없이 일상을 유지하며 전문 재활 치료를 받을 수 있습니다. 전주 통원재활 전문.">
```

#### 뇌졸중 재활 프로그램
```html
<title>뇌졸중 재활 프로그램 - 전주 편마비·언어장애 치료 | 전주E재활의학과</title>
<meta name="description" content="뇌졸중 후 편마비, 언어장애, 인지장애 전문 재활. 보행훈련, 상지기능 회복, 일상동작 훈련. 전주 뇌졸중 재활 전문.">
```

#### 척추손상 재활 프로그램
```html
<title>척추손상 재활 - 전주 척수손상 전문 치료 | 전주E재활의학과의원</title>
<meta name="description" content="척수손상 후 기능 극대화. 근력강화, 이동능력 훈련, 욕창 예방. 전주 척추손상 재활 전문 의원.">
```

#### 치료 프로세스
```html
<title>재활 치료 과정 - 초기평가부터 일상복귀까지 | 전주E재활의학과</title>
<meta name="description" content="과학적 평가, 맞춤 계획, 집중 치료, 일상 복귀. 체계적인 5단계 재활 프로세스. 전주 통원재활.">
```

#### 시설·치료팀
```html
<title>시설 및 치료팀 소개 - 전주E재활의학과의원 | 최신 장비와 전문가</title>
<meta name="description" content="최신 재활 장비와 재활의학과 전문의, 물리치료사, 작업치료사로 구성된 전문 치료팀. 전주 재활의학과.">
```

### Open Graph (OG) 태그 (소셜 미디어 공유용)

```html
<meta property="og:type" content="website">
<meta property="og:title" content="전주E재활의학과의원 - 통원재활 전문">
<meta property="og:description" content="일상으로의 복귀, 통원재활로 시작하세요. 전주 통원재활 전문 의원.">
<meta property="og:url" content="https://jeonju-e-rehab.com">
<meta property="og:image" content="https://jeonju-e-rehab.com/og-image.jpg">
<meta property="og:locale" content="ko_KR">
```

**OG 이미지 권장 사양:**
- 크기: 1200 x 630px
- 포맷: JPG 또는 PNG
- 용량: 1MB 이하
- 내용: 의원 로고 + 핵심 메시지 ("전주 통원재활 전문")

---

## 2. 구조화 데이터 (Schema.org)

### LocalBusiness + MedicalClinic 통합

이미 `index.html`에 포함된 JSON-LD 코드:

```json
{
  "@context": "https://schema.org",
  "@type": "MedicalClinic",
  "name": "전주E재활의학과의원",
  "image": "https://jeonju-e-rehab.com/clinic-photo.jpg",
  "description": "전주 통원재활 전문 의원. 뇌졸중, 척추손상, 보행장애, 근골격계 재활 프로그램 제공.",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "전주시 덕진구 예시로 123",
    "addressLocality": "전주시",
    "addressRegion": "전라북도",
    "postalCode": "54900",
    "addressCountry": "KR"
  },
  "telephone": "+82-63-1234-5678",
  "openingHoursSpecification": [
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday"],
      "opens": "09:00",
      "closes": "18:00"
    },
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": "Saturday",
      "opens": "09:00",
      "closes": "13:00"
    }
  ],
  "priceRange": "₩₩",
  "medicalSpecialty": "Rehabilitation Medicine"
}
```

### 추가 권장 속성

```json
{
  "url": "https://jeonju-e-rehab.com",
  "logo": "https://jeonju-e-rehab.com/logo.png",
  "sameAs": [
    "https://www.facebook.com/jeonju-e-rehab",
    "https://blog.naver.com/jeonju-e-rehab"
  ],
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": "35.8242",
    "longitude": "127.1480"
  },
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "4.8",
    "reviewCount": "52"
  }
}
```

### FAQ 페이지용 구조화 데이터

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "통원재활은 누가 받을 수 있나요?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "뇌졸중, 척추손상, 파킨슨병, 외상성 뇌손상, 근골격계 질환 등 다양한 환자분들이 대상입니다. 입원 치료를 마친 후 지속적인 재활이 필요하거나, 일상생활을 유지하며 재활을 원하시는 분께 적합합니다."
      }
    }
  ]
}
</script>
```

---

## 3. 로컬 SEO 키워드 배치

### 핵심 키워드
- **메인**: 전주 통원재활, 전주 재활의학과
- **질환별**: 전주 뇌졸중 재활, 전주 척추손상 재활, 전주 보행재활
- **치료**: 전주 물리치료, 전주 작업치료
- **지역**: 전주시 재활, 덕진구 재활의학과

### 자연스러운 배치 전략

#### H1 태그 (페이지당 1개)
```html
<!-- 홈페이지 -->
<h1>통원으로 다시 일상으로 - 전주E재활의학과의원</h1>

<!-- 뇌졸중 프로그램 -->
<h1>전주 뇌졸중 재활 프로그램 - 편마비·언어장애 전문 치료</h1>
```

#### H2 태그 (섹션 제목)
```html
<h2>전주 통원재활, 왜 선택해야 할까요?</h2>
<h2>전주E재활의학과 치료 프로세스</h2>
```

#### 본문 내 자연스러운 키워드
```
전주 지역에서 통원재활을 찾고 계신다면, 
전주E재활의학과의원이 최선의 선택입니다. 
전주시 덕진구에 위치한 저희 의원은...
```

### 키워드 밀도 권장
- 1-2%: 자연스럽게 3-5회 언급 (1000자 기준)
- 과도한 키워드 stuffing 금지 (구글 패널티)

---

## 4. 기술적 SEO

### robots.txt
```
User-agent: *
Allow: /

Sitemap: https://jeonju-e-rehab.com/sitemap.xml
```

### sitemap.xml
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://jeonju-e-rehab.com/</loc>
    <lastmod>2025-02-13</lastmod>
    <changefreq>weekly</changefreq>
    <priority>1.0</priority>
  </url>
  <url>
    <loc>https://jeonju-e-rehab.com/outpatient-info.html</loc>
    <lastmod>2025-02-13</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.8</priority>
  </url>
  <url>
    <loc>https://jeonju-e-rehab.com/program-stroke.html</loc>
    <lastmod>2025-02-13</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.8</priority>
  </url>
  <!-- 나머지 페이지 추가 -->
</urlset>
```

### 페이지 속도 최적화
- **이미지**: WebP 포맷, lazy loading
- **CSS/JS**: 압축 (minify)
- **CDN**: Cloudflare 또는 AWS CloudFront 사용
- **캐싱**: 브라우저 캐싱 활성화

### 모바일 친화성
- 반응형 디자인 (이미 적용됨)
- 터치 타겟 44px 이상 (버튼 크기)
- 가독성: 16px 이상 폰트

---

## 5. 콘텐츠 SEO

### 블로그/소식 페이지 추가 권장
- "뇌졸중 후 재활, 언제 시작해야 할까요?"
- "통원재활 vs 입원재활, 무엇이 다를까?"
- "보행 보조기구 선택 가이드"
- "재활 운동 홈 트레이닝 팁"

→ 로컬 SEO + 롱테일 키워드 확보

### 내부 링크 구조
```
홈페이지 → 통원재활 안내 → 질환별 프로그램
       → 치료 프로세스 → 상담신청
       → 시설·치료팀
```

---

## 6. 로컬 SEO 추가 전략

### Google My Business (구글 비즈니스 프로필)
1. 프로필 등록 및 인증
2. 사진 업로드 (시설, 치료팀, 외관)
3. 운영시간, 연락처 정확히 입력
4. 리뷰 관리 (환자 후기 요청)

### 네이버 플레이스
→ 별도 체크리스트 참고 (`naver-place-checklist.md`)

### 지역 디렉토리 등록
- 네이버 지도
- 카카오맵
- 의료 포털 (굿닥, 병원정보 등)

---

## 7. 모니터링 도구

### Google Search Console
- 사이트 등록 및 소유권 인증
- 크롤링 오류 확인
- 검색 쿼리 분석

### Google Analytics (GA4)
- 트래픽 추적
- 전환 추적 (상담신청 제출)
- 사용자 행동 분석

### 네이버 서치어드바이저
- 네이버 검색 노출 최적화
- 수집 요청 (새 페이지 등록)

---

## 체크리스트

- [ ] 모든 페이지에 고유한 title, description 설정
- [ ] Schema.org 구조화 데이터 삽입
- [ ] robots.txt, sitemap.xml 생성 및 업로드
- [ ] Google Search Console 등록
- [ ] 네이버 서치어드바이저 등록
- [ ] 이미지 alt 텍스트 추가 (예: `<img alt="전주 통원재활 치료실">`)
- [ ] 페이지 속도 90점 이상 (PageSpeed Insights)
- [ ] 모바일 친화성 테스트 통과
- [ ] 로컬 키워드 자연스럽게 배치
- [ ] 내부 링크 구조 최적화
