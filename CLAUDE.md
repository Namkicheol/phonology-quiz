# 임용 음운론 서브노트 마스터

임용고시 대비 음성학·음운론 OX 퀴즈 + 개념 정리 웹 애플리케이션.  
순수 HTML/CSS/JS (백엔드 없음). **서브노트 개념** — 책 통째 정리가 아니라 기출 분류 구조 중심.

---

## 🔗 testmaster(giulmmaster) 연동 — concept_link 자동 적용 (필수)

이 레포의 `_study.html` 챕터를 만들거나 변경하면, testmaster의 기출 데이터가 자동으로 그 챕터를 "💎 합격자 노트에서 더 자세히" 링크로 가리키도록 매핑표를 갱신해야 한다.

**이 레포명 (concept_anchors.json key): `phonetics-phonology`**

### 새 챕터 만들 때 절차

1. `_study.html` 안 각 섹션에 `id="..."` anchor 부여 (지금처럼 `s1`, `s2`도 OK, 의미 있는 이름이면 더 좋음)
2. testmaster의 `data/concept_anchors.json` 갱신 — 해당 챕터의 anchor·title·terms 추가:
   ```json
   "phonetics-phonology": {
     "<chapter>_study.html": [
       { "anchor": "s1", "title": "음절 무게", "terms": ["Syllable Weight", "mora", "..."] }
     ]
   }
   ```
3. testmaster에서 자동 적용 + 검증 실행:
   ```bash
   cd ~/Library/CloudStorage/OneDrive-학장중학교/giulmmaster
   python3 scripts/wire_concept_links.py
   ```
4. 출력에서 `깨진링크: 0건` 확인. 깨졌으면 anchor 이름 수정.

### 트리거 (Claude 자동 실행)

다음 상황에서 별도 지시 없이 위 절차를 실행한다:
- 새 `_study.html` 챕터 생성/완성 직후
- 기존 `_study.html`에 섹션 추가/제거/anchor 변경 시
- 사용자가 "기출 연동", "concept_link", "testmaster 적용", "wire" 등 언급 시

### testmaster 위치

`/Users/namgicheol/Library/CloudStorage/OneDrive-학장중학교/giulmmaster/`  
규칙 원본: 위 디렉토리의 `CLAUDE.md` "concept_link 자동 적용" 섹션

---

## 콘텐츠 뼈대 — 기출 분석 분류 구조

> 모든 페이지 제작은 아래 분류를 기준으로 삼는다.

| 분류 | 주제 | 핵심 기출 포인트 | 최근 출제 |
|------|------|-----------------|---------|
| 분류 1 | Place / Manner / Distinctive Features | +/−continuant, coronal/anterior/labial/dorsal, NC vs Glides, j-dropping | **2026 A06** |
| 분류 2 | Phoneme & Allophone | complementary distribution, free variation, allophones, geminate | **2026 A04** |
| 분류 3 | Syllable | sonority, syllabic nasals/liquids, -ization, onset/coda | 2023 |
| 분류 4/5 | Phonological Rules | aspiration, flapping, palatalization, /t//g//r/ deletion, nasal place assimilation, voice assimilation, devoicing, schwa insertion, CCS, neutralization, liquid assim./dissim., epenthesis, metathesis, schwa deletion, trisyllabic laxing, vowel neutralization | **2024 A04·B04** |
| 분류 6 | Stress & Intonation | heavy/light syllable, stress rules (N/V/Adj/compound), stress-shifting suffix, foot structure (trochaic/iambic), nuclear stress, prosodic condition | **2025 B04** |

---

## 참고 자료 (refs/ 폴더) — 우선순위

### 1순위 — 항상 먼저 참조 (기출 분석 · 합격자 노트)

**[AEP/EPP 정리]**

| 파일 | 내용 |
|------|------|
| `refs/음운론_AEP_EPP_정리/음운론_기출_분析_pdf.md` | 기출 주제별 분류 분析 18장 — 골격 |
| `refs/음운론_AEP_EPP_정리/EPP_정리.md` | 합격자 정리 노트 |
| `refs/음운론_AEP_EPP_정리/AEP_데일리_밴드_문제.md` | AEP 수업 데일리 문제 (합격자 자료) |
| `refs/음운론_AEP_EPP_정리/AEP_보충_프린트.md` | AEP 보충 프린트 (합격자 자료) |
| `refs/음운론_AEP_EPP_정리/멘토영어학_바탕_rule_도출_문제.md` | 멘토영어학 기반 rule 도출 문제 |
| `refs/음운론_AEP_EPP_정리/멘토영어학_바탕_rule_도출_문제_정답.md` | 위 문제 정답 |
| `refs/음운론_AEP_EPP_정리/음운론_연습_문제_답.md` | 음운론 연습 문제 답안 |

> 이미지 경로: `refs/음운론_AEP_EPP_정리/images/`

**[STRESS 드릴]** — 단어 주고 강세 표시하는 실전 드릴

| 파일 | 내용 |
|------|------|
| `refs/［문제］모든 STRESS 표시하시오 히또리/［문제］모든 STRESS 표시하시오 히또리.md` | 문제 (8p) |
| `refs/［문제］모든 STRESS 표시하시오 히또리(수정)/［문제］모든 STRESS 표시하시오 히또리(수정).md` | 문제 수정본 (1p) |
| `refs/［정답］모든 STRESS 표시하시오 히또리/［정답］모든 STRESS 표시하시오 히또리.md` | 정답 (8p) |

**[합격자 이미지 노트]** — 이미지 스캔 OCR; 텍스트 품질 낮을 수 있음 — 이미지 직접 참조 권장

| 파일 | 내용 |
|------|------|
| `refs/features_가루미.md` | 변별자질(distinctive features) 파트 |
| `refs/Phonological Rules_가루미.md` | 음운규칙 파트 |
| `refs/영어학 짱은 나야!!!_가루미 복사본.md` | 영어학 종합 노트 |
| `refs/응완벽해질게_가루미.md` | 합격자 노트 |
| `refs/Phonology & Phonetics 헷갈리는 개념 ex..md` | 음운론·음성학 헷갈리는 개념 예제 정리 |

### 2순위 — 기출 해설집 + 교재

| 파일 | 내용 | 범위 |
|------|------|------|
| `refs/루이스기출 5판.md` | 루이스 기출분석 5판 (OCR) — 2002~2021 영어학 기출 해설·분류 | 음운론 파트 |
| `refs/메가쌤 전공영어 기출분析.md` | 메가쌤 기출분析 (현재 내용 거의 없음 — 추후 추가 가능) | — |
| `refs/최진호_고급/최진호_고급.md` | 최진호 고급 교재 (419p, 이미지) | 음운론 전범위 |
| `refs/최진호_중급/최진호_중급.md` | 최진호 중급 교재 (318p, 이미지) | 음운론 전범위 |
| `refs/AEP 단권화(루이스합격자)/AEP 단권화(루이스합격자).md` | AEP 합격자 단권화 (15p) | 음운론 전범위 |
| `refs/AEP 보충프린트_앤드류 강의/AEP 보충프린트_앤드류 강의.md` | AEP 보충프린트 (43p) | 음운론 전범위 |
| `refs/7. 정T_AEP Chap.7 정리/7. 정T_AEP Chap.7 정리.md` | 정T AEP Chap.7 강세 정리 (17p) | 강세 |
| `refs/5.멘토영어학 rule 도출 문제/5.멘토영어학 rule 도출 문제.md` | 멘토영어학 rule 도출 문제 이미지 원본 (13p) | 음운규칙 |
| `refs/5.멘토영어학 rule 도출 문제 답/5.멘토영어학 rule 도출 문제 답.md` | 멘토영어학 rule 도출 문제 답 이미지 (2p) | 음운규칙 |
| `refs/10.영어학 정리 156p/10.영어학 정리 156p.md` | 영어학 종합 정리 (156p) | 전범위 |

### 3순위 — 개념 깊이 보충 (원서)

| 파일 | 내용 | 참조 범위 |
|------|------|-----------|
| `refs/aep.md` | Applied English Phonology (Yavaş) — AEP 교재 전체 | **전체** |
| `refs/ail.md` | An Introduction to Language 10판 | **음성·음운론 파트만** |
| `refs/윤도형2015.md` | 전공영어학 (윤도형, 2015) | **음성·음운론 파트만** |
| `refs/English_Phonetics_and_Phonology.md` | English Phonetics and Phonology (Roach) | **음성·음운론 파트만** |
| `refs/introducing-phonetics-and-phonology-3nbsped-9781444109887-144410988x_compress.md` | Introducing Phonetics and Phonology 3판 | **음성·음운론 파트만** |

> 이미지: `refs/aep_images/`, `refs/ail_images/`, `refs/윤도형2015_images/`, `refs/English_Phonetics_and_Phonology_images/`, `refs/introducing-phonetics-and-phonology-3nbsped-9781444109887-144410988x_compress_images/`

### 4순위 — 기출 문항 DB

> 경로: `/Users/namgicheol/Library/CloudStorage/OneDrive-학장중학교/giulmmaster/data/`  
> `linguistics_YYYY_*_draft.json` — `derivation.steps`, `answer.model_answer`, `source.references` 조회

---

## 파일 구조

**단원당 2파일 구조**: `[topic].html` (OX 퀴즈) + `[topic]_study.html` (개념 정리)  
영어교육론 레포와 동일 패턴. 기존 `*_ox.html` / `*_exercises.html` 혼용 파일은 이 구조로 통합 대상.

| 단원 | OX/적용 퀴즈 | 개념 정리 | 비고 |
|------|---------|---------|------|
| 분류 1 — 음성자질 | `features.html` | `features_study.html` | |
| 분류 2 — 음소/변이음 | `allophone.html` | `allophone_study.html` | |
| 분류 3 — 음절 | `syllable.html` | `syllable_study.html` | |
| 분류 4/5 — 음운규칙 | `rules.html` | `rules_study.html` | **규칙도출 문항 두껍게** |
| 분류 6 — 강세/인토네이션 | `stress.html` (개념 OX 28Q)<br>`stress_practice.html` (적용 30Q) | `stress_study.html` | ✅ **완료** |
| (인덱스) | `index.html` | — | ✅ 갱신 완료 |

| 공용 파일 | 역할 |
|----------|------|
| `sounds.js` | 효과음 (Web Audio API) |
| `score-popup.js` | 결과 팝업 + 최고기록 |

> **stress / 규칙도출 단원**: OX 외에 IPA 전사·rule 기술·파생어 체인 문항을 OX 퀴즈 페이지 하단에 추가 섹션으로 포함.  
> 기존 `*_ox.html` / `*_exercises.html` 파일은 구버전 — 새 구조로 재작성 시 삭제.

---

## 개발 핵심 규칙

- 백엔드 없음 — 순수 클라이언트사이드
- CSS 변수 사용 금지, 클래스 스타일로 처리
- `sounds.js` + `score-popup.js` 반드시 포함, 퀴즈 JS보다 먼저 로드
- 새 단원 추가 시 `index.html`도 함께 업데이트
- 기존 HTML은 영어교육론 레포의 quiz/study 구조 참조하여 리팩터링

---

## 방향 원칙

- **서브노트 접근**: 책 전체 정리 X → 기출 분류 분석에서 출발해 핵심만 압축
- **콘텐츠 우선순위**: 기출 분석 분류 구조 → 합격자 노트 → 원서 보충
- 기존 Phase 1/2 블로그 기획안(`docs/plans/`)은 참고용, 현재 방향과 다름

---

## 🚨 기출 추정 절대 금지 (전 콘텐츠 공통)

블로그·사이트 콘텐츠·해설·OX 어디든 임용 **기출 관련 정보(연도·출제 의도·답안 패턴 등) 추정 금지**. 검증된 refs에서만 인용한다.

**검증 절차** (음운론):
1. **1차**: `refs/루이스기출 5판.md` 음운론 파트 — 연도-rule/IPA/단원 매핑
2. **2차**: `refs/음운론_AEP_EPP_정리/` — 단원별 기출 분석 PDF
3. **3차**: `refs/메가쌤 전공영어 기출분析.md` 등 보조 자료
4. **2022년 이후**: 루이스 5판 범위 밖 → giulmmaster의 `refs/2025 전공 기출 김재균해설.md`, `refs/2026 기출 권두걸팀 해설서.md` 음운론 파트

**원칙**:
- **연도·기출 정보 표기는 OPTIONAL** — 블로그 작성 시 검증 부담스러우면 본문에 박지 않아도 됨. 개념 위주로 작성해도 무방
- **박는 경우에만** refs 검증 필수. 검증 매칭 0건이면 표기 **생략**. "그럴법한" 추정값 박지 말 것
- 추정 = 수험생에게 잘못된 정보 제공 = **치명적 오류**

---

## 블로그 글 작성

전역 블로그 지침 `~/Library/CloudStorage/OneDrive-학장중학교/blog write.md` 의 **"임용고시 (영어학·영교론)"** 섹션과 그 하위 **"📚 임용 블로그 글쓰기 규칙"** 을 따른다.

본 레포 유형: **A형 (음운론 서브노트)** — 블로그 작성 대상.

핵심:
- 블로그 글은 `.md` 파일로 작성
- **본문 = 서브노트 핵심 + 4섹션 보강** (① 개념 정의 [필수] + ②③④ 중 최소 2개)
  - ② 기출 맥락 / ③ 키텀 비교 / ④ 수험 활용 팁
  - **합격자 노트(`refs/`)에 팁 있으면 ④ 무조건 포함**
- **한글 설명 시 용어는 영어 원문 그대로** (예: `place assimilation`을 "조음위치 동화"로 번역 X). 학자명·이론명·기술 용어는 모두 영어 유지
- **본문에 출처 인용 표기 불필요** (`— Roca & Johnson 2.3` 같은 표기 X)
- **키워드 하이라이트 필수** (5색): 이론명·rule·기술 용어 → 파랑 `#3182ce` / 학자명 → 보라 `#805ad5` / 함정·주의 → 빨강 `#c53030` / 장점·긍정 → 청록 `#319795` / 현직쌤 팁 → 주황 `#dd6b20`
- **기출 연도 빨간색 인라인** (`#c53030`) — 출처 검색: `refs/루이스기출 5판.md` 음운론 파트, `refs/음운론_AEP_EPP_정리/`
- 핵심 개념은 **영어 원문 한 문단 + 한글 설명 한 문단** 교차 (개념정리 페이지 수록 개념 + 알파)
- **신규 글 썸네일은 Pencil MCP** (`blog-image-pencil` 스킬)로 생성. 기존 글은 그대로 유지
- **SVG 사용 금지** (블로그 한정. 웹앱 페이지의 SVG 다이어그램은 별개)

### 음운론 블로그 고유 규칙

**사이트 구조 → 블로그 매핑**
- 사이트는 단원당: `*_study.html` (개념정리) + `*.html` (OX) + 응용 페이지(`stress_practice.html` 등 단원별로 추가됨)
- **블로그 글 단위 옵션**:
  - **단원당 1편**: study + OX + 응용 모두 한 글에 통합 (기본)
  - **개념편 + 응용 풀이편 분리**: stress·rule 도출·IPA 전사 응용이 많은 단원은 별도 응용 풀이 글 작성 가능 (예: "강세 규칙 시리즈")

**iframe / 링크 배치 — iframe 미사용 원칙**
- ❌ **개념정리(`*_study.html`) iframe 임베드 금지** — 4섹션 본문에 이미 개념·rule·IPA를 풀어 썼으므로 중복
- ❌ **OX·응용(`*.html`, `stress_practice.html` 등) iframe 임베드 금지** — 이미 별도 obangti.tistory.com 글로 발행됨
- ✅ **본문 끝에 OX·응용 링크 버튼**만 추가 — `obangti.tistory.com/<post-id>` 형식
- 링크 버튼 템플릿:
  ```html
  <p align="center">
  <a href="https://obangti.tistory.com/<post-id>" target="_blank" style="display:inline-block;padding:14px 28px;background:#3182ce;color:#fff;text-decoration:none;border-radius:8px;font-weight:bold;font-size:15px;">📝 [단원명] OX·응용 풀러 가기 →</a>
  </p>
  ```

**📝 OX·응용 블로그 글 구조** (별도 발행 — 해설 중심 3섹션)
- ① 짧은 도입 (1-2줄)
- ② 본문 = **N문항 × 자세한 해설** (90%): 문항/답(✅❌)/영어 원문 인용 1-2문장/한글 풀이/⚠️ 함정/빨간 연도/5색 하이라이트
- ③ 개념정리 글로 돌아가기 링크 버튼 (사이클 형성)
- 음운론 특화: rule 적용 문항은 **단계별 derivation 시연** 해설에 포함 (Underlying → Step → Surface)
- IPA 전사 해설은 풍부하게
- 분량: 5,000~10,000자 (문항당 250-500자)
- 자세한 규칙은 `blog write.md` "📝 OX·실전·응용 블로그 글 구조" 참조

**4섹션 보강 포인트 (음운론 특화)**
- ① **개념 정의**: IPA 전사·rule 표기 예시를 **풍부하게**. 서브노트가 1~2개 예시면 블로그는 5~10개로 확장. `refs/transcription_collection/` 활용
- ② **기출 맥락**: `refs/루이스기출 5판.md` 음운론 파트 + `refs/음운론_AEP_EPP_정리/` 우선 활용
- ④ **rule 단원은 단계별 derivation 시연 필수**: phonological rule(예: nasal place assimilation, flapping, vowel reduction 등)을 다룰 때 입력 → 단계별 적용 → 출력을 마크다운으로 시연. 예:
  ```
  Underlying:  /ɪn + p ə s ɪ b əl/
  Step 1 (place assim): /ɪmpəsɪbəl/
  Surface:     [ɪmpɑsəbl̩]
  ```
