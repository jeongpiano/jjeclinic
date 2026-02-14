# 호스팅/배포 가이드

## 호스팅 플랫폼 비교 및 추천

| 플랫폼 | 가격 | 난이도 | 속도 | SEO | 추천 대상 |
|--------|------|--------|------|-----|-----------|
| **Vercel** | 무료 (프로 $20/월) | ⭐ 쉬움 | ⚡ 매우 빠름 | ✅ 우수 | **최우선 추천** |
| **Netlify** | 무료 (프로 $19/월) | ⭐ 쉬움 | ⚡ 빠름 | ✅ 우수 | Vercel 대안 |
| **GitHub Pages** | 무료 | ⭐⭐ 보통 | 🐢 보통 | ⚠️ 제한적 | 비용 중시 |
| **Cloudflare Pages** | 무료 (프로 $20/월) | ⭐⭐ 보통 | ⚡ 매우 빠름 | ✅ 우수 | 고급 사용자 |

---

## 🏆 추천 1순위: Vercel

### 장점
- ✅ 무료 플랜으로 충분 (월 100GB 대역폭)
- ✅ Git 연동 자동 배포 (푸시만 하면 끝)
- ✅ 글로벌 CDN 자동 적용 (빠른 속도)
- ✅ 커스텀 도메인 무료 연결
- ✅ SSL 인증서 자동 발급 (HTTPS)
- ✅ SEO 최적화 (프리렌더링 지원)

### 배포 단계 (소요 시간: 10분)

#### 1. GitHub 저장소 생성

```bash
# 로컬 컴퓨터에서 실행
cd jeonju-e-rehab
git init
git add .
git commit -m "Initial commit: 전주E재활의학과 홈페이지"
```

GitHub에서 새 저장소 생성 (`jeonju-e-rehab`)

```bash
git remote add origin https://github.com/your-username/jeonju-e-rehab.git
git branch -M main
git push -u origin main
```

#### 2. Vercel 계정 생성 및 프로젝트 연결

1. [https://vercel.com](https://vercel.com) 접속
2. "Sign Up" → GitHub 계정으로 로그인
3. "New Project" 클릭
4. GitHub 저장소 `jeonju-e-rehab` 선택
5. "Import" 클릭

#### 3. 프로젝트 설정

```
Framework Preset: Other (HTML/CSS/JS)
Root Directory: ./
Build Command: (비워둠)
Output Directory: ./
```

"Deploy" 클릭 → 1-2분 후 배포 완료!

#### 4. 커스텀 도메인 연결 (선택)

**도메인 구입 처**: 가비아, 카페24, Namecheap 등

Vercel 대시보드에서:
1. "Settings" → "Domains"
2. 구입한 도메인 입력 (예: `jeonju-e-rehab.com`)
3. DNS 설정 안내 따라 하기

**DNS 레코드 설정** (도메인 제공업체에서):
```
Type: A
Name: @
Value: 76.76.21.21

Type: CNAME
Name: www
Value: cname.vercel-dns.com
```

**적용 시간**: 5분 ~ 24시간

---

## 추천 2순위: Netlify

### 장점
- ✅ Vercel과 거의 동일한 기능
- ✅ 무료 플랜 (월 100GB 대역폭)
- ✅ Form 처리 내장 (상담신청 폼 자동 저장)
- ✅ Netlify CMS 연동 가능

### 배포 단계 (소요 시간: 10분)

#### 1. GitHub 저장소 준비 (Vercel과 동일)

#### 2. Netlify 배포

**방법 1: 드래그 앤 드롭 (가장 빠름)**
1. [https://app.netlify.com](https://app.netlify.com) 접속
2. 계정 생성 (GitHub 로그인)
3. "Sites" → "Add new site" → "Deploy manually"
4. `jeonju-e-rehab` 폴더를 드래그 앤 드롭
5. 배포 완료! (URL: `random-name-12345.netlify.app`)

**방법 2: Git 연동 (자동 배포)**
1. "Add new site" → "Import from Git"
2. GitHub 선택 → 저장소 선택
3. Build settings:
   ```
   Build command: (비워둠)
   Publish directory: ./
   ```
4. "Deploy site" 클릭

#### 3. 커스텀 도메인 연결

Netlify 대시보드:
1. "Domain settings" → "Add custom domain"
2. 도메인 입력 → DNS 설정 안내 따라 하기

**DNS 레코드** (도메인 제공업체):
```
Type: A
Name: @
Value: 75.2.60.5

Type: CNAME
Name: www
Value: your-site.netlify.app
```

---

## 추천 3순위: GitHub Pages

### 장점
- ✅ 완전 무료
- ✅ GitHub 계정만 있으면 OK

### 단점
- ⚠️ 속도 느림 (CDN 없음)
- ⚠️ 커스텀 도메인 설정 복잡
- ⚠️ SEO 최적화 제한적

### 배포 단계

#### 1. GitHub 저장소 생성 (위와 동일)

#### 2. GitHub Pages 활성화

1. GitHub 저장소 페이지로 이동
2. "Settings" → "Pages"
3. "Source": `main` 브랜치 선택
4. "Folder": `/root` 선택
5. "Save" 클릭

#### 3. 배포 확인

URL: `https://your-username.github.io/jeonju-e-rehab/`

**주의**: 서브디렉토리 경로 (`/jeonju-e-rehab/`) 때문에 링크 수정 필요
```html
<!-- 변경 전 -->
<a href="/program-stroke.html">

<!-- 변경 후 -->
<a href="/jeonju-e-rehab/program-stroke.html">
```

**커스텀 도메인 연결**:
1. 저장소 루트에 `CNAME` 파일 생성:
   ```
   jeonju-e-rehab.com
   ```
2. 도메인 제공업체에서 DNS 설정:
   ```
   Type: A
   Name: @
   Value: 185.199.108.153 (GitHub Pages IP)
   
   Type: CNAME
   Name: www
   Value: your-username.github.io
   ```

---

## 상담신청 폼 처리 (백엔드 연동)

### 문제점
현재 `index.html`의 폼은 프론트엔드만 있어 제출 시 데이터가 저장되지 않습니다.

### 해결 방법 3가지

#### 방법 1: Netlify Forms (가장 간단)

**설정 (Netlify 배포 시)**:

`index.html` 폼 태그에 `netlify` 속성 추가:
```html
<form id="consultationForm" netlify>
  <!-- 폼 필드들 -->
</form>
```

폼 제출 시 Netlify가 자동으로 데이터 저장 → 이메일 알림 설정 가능

#### 방법 2: Google Forms 연동

1. Google Forms에서 상담신청 폼 생성
2. "미리 채워진 링크" 생성
3. `index.html`에서 Google Forms로 POST 요청:

```javascript
document.getElementById('consultationForm').addEventListener('submit', function(e) {
    e.preventDefault();
    
    const formData = new FormData(this);
    const data = Object.fromEntries(formData);
    
    // Google Forms URL (미리 채워진 링크에서 추출)
    const googleFormUrl = 'https://docs.google.com/forms/d/e/YOUR_FORM_ID/formResponse';
    
    fetch(googleFormUrl, {
        method: 'POST',
        mode: 'no-cors',
        headers: {
            'Content-Type': 'application/x-www-form-urlencoded'
        },
        body: new URLSearchParams({
            'entry.123456': data.name,
            'entry.234567': data.phone,
            'entry.345678': data.condition,
            'entry.456789': data.message
        })
    });
    
    // Thank you 메시지 표시
    document.getElementById('consultationForm').classList.add('hidden');
    document.getElementById('thankYouMessage').classList.remove('hidden');
});
```

#### 방법 3: Formspree (무료 플랜 50회/월)

1. [https://formspree.io](https://formspree.io) 가입
2. 폼 생성 → 엔드포인트 URL 받기
3. `index.html` 폼에 action 추가:

```html
<form id="consultationForm" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
  <input type="text" name="name" required>
  <input type="tel" name="phone" required>
  <select name="condition"></select>
  <textarea name="message"></textarea>
  <button type="submit">상담신청 제출하기</button>
</form>
```

제출 시 Formspree가 이메일로 자동 전송

---

## 도메인 구입 가이드

### 추천 도메인
- `jeonju-e-rehab.com` (최우선)
- `jeonju-e.com`
- `jeonjurehab.com`

### 구입 처
- **가비아**: [https://www.gabia.com](https://www.gabia.com) (한국어, 연 15,000원)
- **카페24**: [https://domain.cafe24.com](https://domain.cafe24.com) (연 12,000원)
- **Namecheap**: [https://www.namecheap.com](https://www.namecheap.com) (영어, 연 $10)

---

## SSL 인증서 (HTTPS)

Vercel, Netlify, Cloudflare Pages는 **자동으로 무료 SSL 발급** (Let's Encrypt)

GitHub Pages도 커스텀 도메인 설정 시 자동 SSL 발급

---

## 성능 최적화 체크리스트

### 배포 전
- [ ] 이미지 WebP 변환 (Squoosh.app 사용)
- [ ] 이미지 압축 (TinyPNG.com)
- [ ] CSS/JS minify (Vercel/Netlify 자동 처리)
- [ ] Lighthouse 스코어 90점 이상 확인

### 배포 후
- [ ] Google PageSpeed Insights 테스트
- [ ] 모바일/데스크톱 로딩 속도 확인
- [ ] 모든 링크 작동 확인 (404 에러 없는지)
- [ ] 폼 제출 테스트

---

## 모니터링 설정

### Google Analytics (GA4)

1. [https://analytics.google.com](https://analytics.google.com) 가입
2. 속성 생성 → 측정 ID 받기 (예: `G-XXXXXXXXXX`)
3. `index.html` `</head>` 전에 추가:

```html
<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

### Google Search Console

1. [https://search.google.com/search-console](https://search.google.com/search-console) 접속
2. "속성 추가" → URL 입력
3. 소유권 확인 (HTML 파일 업로드 또는 메타태그)
4. Sitemap 제출 (`https://jeonju-e-rehab.com/sitemap.xml`)

---

## 유지보수 가이드

### 정기 업데이트 (월 1회)
- 콘텐츠 업데이트 (새로운 프로그램, 공지사항)
- 사진 추가 (시설, 팀, 치료 모습)
- SEO 성과 확인 (Google Analytics)

### Git 워크플로우
```bash
# 로컬에서 수정
git add .
git commit -m "Update: 새로운 프로그램 추가"
git push origin main

# Vercel/Netlify가 자동으로 배포 (1-2분 소요)
```

---

## 최종 체크리스트

### 배포 전
- [ ] 모든 페이지 HTML 작성 완료
- [ ] placeholder 텍스트 실제 카피로 교체
- [ ] 이미지 준비 및 최적화
- [ ] 연락처, 주소 정확히 입력
- [ ] Google Analytics 설정

### 배포 단계
- [ ] GitHub 저장소 생성 및 푸시
- [ ] Vercel/Netlify 연동 및 배포
- [ ] 커스텀 도메인 연결 (선택)
- [ ] SSL 인증서 확인 (HTTPS 작동)

### 배포 후
- [ ] 모든 페이지 로딩 확인
- [ ] 모바일/데스크톱 반응형 확인
- [ ] 폼 제출 테스트
- [ ] Google Search Console 등록
- [ ] 네이버 서치어드바이저 등록

---

**추천 배포 경로**: GitHub → Vercel (10분 완료, 무료, 자동 배포)

문의사항이 있으면 Vercel Discord 또는 공식 문서를 참고하세요:
- Vercel 문서: [https://vercel.com/docs](https://vercel.com/docs)
- Netlify 문서: [https://docs.netlify.com](https://docs.netlify.com)
