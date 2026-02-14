# 전주E재활의학과의원 홈페이지

> **통원으로 다시 일상으로** - 전주 통원재활 전문 의원 홈페이지

모바일 우선 반응형 웹사이트로, 이해 → 신뢰 → 전환(상담/초기평가) 최단 동선을 구현한 MVP입니다.

---

## 📋 프로젝트 개요

- **목적**: 통원재활 중심 의원 홈페이지
- **목표**: 모바일 우선 반응형, 빠른 전환 동선
- **기술 스택**: HTML5 + Tailwind CSS (CDN)
- **페이지 구성**: 6개 (홈, 통원재활 안내, 질환별 프로그램 4개, 치료 프로세스, 시설·치료팀, 상담신청+오시는길)
- **배포 플랫폼**: Vercel (권장) 또는 Netlify

---

## 🚀 빠른 시작

### 1. 로컬에서 실행 (즉시 확인)

```bash
# 저장소 클론
git clone https://github.com/your-username/jeonju-e-rehab.git
cd jeonju-e-rehab

# 브라우저로 index.html 열기
open index.html  # macOS
start index.html # Windows
xdg-open index.html # Linux
```

또는 VSCode Live Server 사용:
1. VSCode에서 폴더 열기
2. `index.html` 우클릭 → "Open with Live Server"

### 2. Vercel에 배포 (10분 완료)

```bash
# GitHub에 푸시
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/your-username/jeonju-e-rehab.git
git push -u origin main

# Vercel에서 Import
# 1. vercel.com 접속 → GitHub 로그인
# 2. New Project → 저장소 선택 → Deploy
```

자세한 배포 가이드: [`deployment-guide.md`](./deployment-guide.md)

---

## 📁 파일 구조

```
jeonju-e-rehab/
├── index.html                     # 홈페이지 (MVP)
├── wireframe.md                   # 와이어프레임 문서
├── seo-guide.md                   # SEO 최적화 가이드
├── naver-place-checklist.md       # 네이버 플레이스 체크리스트
├── deployment-guide.md            # 호스팅/배포 가이드
└── README.md                      # 이 파일
```

---

## 🎨 주요 기능

### 모바일 우선 반응형 디자인
- 320px ~ 2560px 완벽 대응
- Tailwind CSS 기반 유틸리티 클래스
- 터치 최적화 UI (버튼, 폼)

### CTA 최적화
- **상단 고정**: 전화 / 카톡 / 상담신청 버튼
- **하단 고정 바**: 모바일 항상 표시, 데스크톱 스크롤 시 표시
- **인라인 CTA**: 히어로 섹션, 프로그램 카드, FAQ 하단

### 주요 섹션
1. **히어로**: 핵심 메시지 + 큰 CTA
2. **상황 선택기**: 4개 버튼 (뇌졸중/척추손상/보행장애/근골격계)
3. **통원재활 3가지 장점**: 아이콘 + 설명
4. **치료 프로세스**: 5단계 타임라인
5. **질환별 프로그램**: 2x2 그리드 카드
6. **시설 & 치료팀**: 갤러리 미리보기
7. **FAQ**: 아코디언 (5개 질문)
8. **상담신청 폼**: 유효성 검사 포함

### SEO 최적화
- 메타태그 (title, description, OG)
- Schema.org 구조화 데이터 (MedicalClinic)
- 로컬 SEO 키워드 자연 배치
- 시맨틱 HTML5

---

## 🛠️ 커스터마이징 가이드

### 1. 연락처 변경

`index.html`에서 다음 부분 수정:

```html
<!-- 전화번호 -->
<a href="tel:063-1234-5678">

<!-- 카카오톡 채널 -->
<a href="http://pf.kakao.com/_xxxxx">

<!-- 주소 -->
전라북도 전주시 덕진구 예시로 123
```

### 2. 카피 교체

placeholder 텍스트를 실제 카피로 교체하세요:
- 히어로 섹션 헤드라인
- 통원재활 3가지 장점 설명
- FAQ 답변

### 3. 이미지 추가

placeholder `<div>`를 실제 `<img>` 태그로 교체:

```html
<!-- 변경 전 -->
<div class="bg-gray-300 rounded-lg aspect-video flex items-center justify-center">
    <span class="text-gray-500 text-sm">[재활 치료 이미지]</span>
</div>

<!-- 변경 후 -->
<img src="images/rehab-therapy.jpg" alt="전주 통원재활 치료실" class="rounded-lg aspect-video object-cover">
```

**이미지 최적화**:
- WebP 포맷 변환 (Squoosh.app)
- 압축 (TinyPNG.com)
- lazy loading 추가: `loading="lazy"`

### 4. 색상 변경

Tailwind 색상 클래스 교체 (예: `blue-600` → `teal-600`):

```html
<!-- 파란색 (기본) -->
<button class="bg-blue-600 hover:bg-blue-700">

<!-- 청록색 (변경) -->
<button class="bg-teal-600 hover:bg-teal-700">
```

---

## 📊 SEO 체크리스트

### 기본 설정 (완료됨)
- [x] 메타태그 (title, description, keywords)
- [x] Open Graph 태그 (소셜 공유)
- [x] Schema.org 구조화 데이터
- [x] 시맨틱 HTML5
- [x] 모바일 친화적 디자인

### 추가 작업 필요
- [ ] robots.txt 생성
- [ ] sitemap.xml 생성
- [ ] Google Search Console 등록
- [ ] 네이버 서치어드바이저 등록
- [ ] Google Analytics 설치

자세한 가이드: [`seo-guide.md`](./seo-guide.md)

---

## 🗺️ 네이버 플레이스 최적화

### 필수 작업
- [ ] 플레이스 등록 (업체명, 주소, 연락처)
- [ ] 사진 10장 이상 업로드 (외관, 내부, 장비, 팀)
- [ ] 소개글 작성 (키워드 포함, 500자)
- [ ] 운영시간, 편의시설 입력

### 리뷰 관리
- [ ] 환자 후기 요청 시스템 구축
- [ ] 긍정/부정 리뷰 응답 매뉴얼 작성
- [ ] 월 5개 이상 리뷰 목표

자세한 체크리스트: [`naver-place-checklist.md`](./naver-place-checklist.md)

---

## 🔧 상담신청 폼 연동

현재 폼은 프론트엔드만 구현되어 있습니다. 백엔드 연동 옵션:

### 옵션 1: Netlify Forms (추천)
```html
<form id="consultationForm" netlify>
  <!-- 자동으로 데이터 저장 및 이메일 알림 -->
</form>
```

### 옵션 2: Google Forms
Google Forms 미리 채워진 링크를 사용해 POST 요청

### 옵션 3: Formspree
무료 플랜 (50회/월) 사용

자세한 설정: [`deployment-guide.md#상담신청-폼-처리`](./deployment-guide.md)

---

## 🚢 배포 가이드

### 추천 플랫폼

| 플랫폼 | 비용 | 난이도 | 속도 | 추천 |
|--------|------|--------|------|------|
| **Vercel** | 무료 | ⭐ 쉬움 | ⚡ 매우 빠름 | ✅ 최우선 |
| **Netlify** | 무료 | ⭐ 쉬움 | ⚡ 빠름 | ✅ 대안 |
| **GitHub Pages** | 무료 | ⭐⭐ 보통 | 🐢 보통 | 비용 중시 |

### Vercel 배포 (10분)
```bash
# 1. GitHub에 푸시
git add . && git commit -m "Deploy" && git push

# 2. vercel.com → New Project → Import from GitHub

# 3. 완료! (자동 SSL, CDN, 도메인 연결)
```

자세한 가이드: [`deployment-guide.md`](./deployment-guide.md)

---

## 📈 성능 최적화

### Lighthouse 스코어 목표
- Performance: 90+ ✅
- Accessibility: 95+ ✅
- Best Practices: 95+ ✅
- SEO: 100 ✅

### 최적화 체크리스트
- [x] Tailwind CSS CDN (프로덕션에서는 빌드 권장)
- [ ] 이미지 WebP 변환 및 lazy loading
- [ ] 폰트 최적화 (Pretendard CDN)
- [ ] CSS/JS minify (Vercel/Netlify 자동)

---

## 📚 문서 가이드

| 파일 | 설명 |
|------|------|
| [`wireframe.md`](./wireframe.md) | 와이어프레임, 레이아웃, 인터랙션 |
| [`seo-guide.md`](./seo-guide.md) | SEO 메타태그, 구조화 데이터, 키워드 |
| [`naver-place-checklist.md`](./naver-place-checklist.md) | 네이버 플레이스 최적화 |
| [`deployment-guide.md`](./deployment-guide.md) | 호스팅 플랫폼, 배포, 도메인 |

---

## 🛣️ 다음 단계 (MVP 이후)

### 추가 페이지 개발
- [ ] 통원재활 안내 (`outpatient-info.html`)
- [ ] 질환별 프로그램 4개 (뇌졸중, 척추손상, 보행장애, 근골격계)
- [ ] 치료 프로세스 상세 (`process.html`)
- [ ] 시설·치료팀 (`facility.html`)

### 콘텐츠 마케팅
- [ ] 블로그/포스트 시작 (주 1-2회)
- [ ] 네이버 포스트 연동
- [ ] 환자 후기 영상 (동의 필수)

### 전환 최적화
- [ ] Google Analytics 전환 추적
- [ ] A/B 테스트 (히어로 섹션 CTA)
- [ ] 히트맵 분석 (Hotjar)

---

## 🤝 기여 및 피드백

질문이나 개선 제안이 있으시면:
- GitHub Issues 생성
- 이메일: dev@jeonju-e-rehab.com (placeholder)

---

## 📄 라이선스

이 프로젝트는 전주E재활의학과의원의 소유입니다.

---

## 📞 연락처

**전주E재활의학과의원**
- 주소: 전라북도 전주시 덕진구 예시로 123 (예시동) 2층
- 전화: 063-1234-5678
- 홈페이지: https://jeonju-e-rehab.com (배포 후 업데이트)
- 카카오톡: http://pf.kakao.com/_xxxxx

---

**Built with ❤️ for 전주E재활의학과의원**
