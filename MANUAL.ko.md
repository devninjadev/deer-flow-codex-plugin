## DeerFlow란?

DeerFlow는 ByteDance가 공개한 오픈소스 AI 에이전트 실행 환경입니다. 예를 들어 조사 보고서를 만들 때, 여러 에이전트에게 자료 수집을 나눠 맡기고, 수집한 데이터를 별도의 작업 공간에서 코드로 분석할 수 있습니다. 이때 논문을 어떤 기준으로 읽고 데이터를 어떻게 집계할지 같은 작업 절차를 담은 것이 **스킬**입니다. [DeerFlow 공식 저장소 ↗](https://github.com/bytedance/deer-flow)

이 저장소에서 배포하는 **DeerFlow Skills**는 그중 공개 스킬 23개를 Codex에서 꺼내 쓰도록 묶은 플러그인입니다. 목차에서 할 일을 고르고 요청 예시를 복사해 Codex에 보내세요. 논문 비평이라면 읽을 PDF를, 매출 집계라면 분석할 표를 함께 첨부하면 됩니다. 별도 서버나 서비스 키가 필요한 작업은 해당 항목에서 확인할 수 있습니다.

<a name="toc"></a>

## 목차

### 조사와 문헌 검토

- [논문 한 편 비평하기](#academic-paper-review)
- [여러 논문을 한 기준으로 읽기](#systematic-literature-review)
- [하나의 질문을 여러 출처로 조사하기](#deep-research)
- [GitHub 프로젝트의 변화 추적하기](#github-deep-research)
- [의사결정용 보고서 설계하기](#consulting-analysis)

### 데이터와 콘텐츠

- [엑셀·CSV 집계하기](#data-analysis)
- [수치를 차트로 보여주기](#chart-visualization)
- [읽을거리를 뉴스레터로 편집하기](#newsletter-generation)
- [참고 이미지로 새 이미지 만들기](#image-generation)
- [배경음악이나 노래 만들기](#music-generation)
- [글을 두 진행자의 대화로 바꾸기](#podcast-generation)
- [장면 설명으로 영상 만들기](#video-generation)
- [이미지 중심 발표 자료 만들기](#ppt-generation)

### 웹과 개발

- [웹 화면 구현하기](#frontend-design)
- [웹 화면의 사용성 점검하기](#web-design-guidelines)
- [코드에서 사용 설명서 작성하기](#code-documentation)
- [웹 프로젝트를 미리보기로 배포하기](#vercel-deploy)

### 에이전트와 스킬 관리

- [AI 협업 방식 설정하기](#bootstrap)
- [실행 중인 DeerFlow에 작업 보내기](#claude-to-deerflow)
- [새 스킬 후보 찾기](#find-skills)
- [반복 작업을 스킬로 만들기](#skill-creator)
- [스킬 패키지 검토하기](#skill-reviewer)
- [여러 스킬을 조합해 결과물 만들기](#surprise-me)

[문제 해결과 업데이트](#maintenance)

<a name="group0"></a>

## 조사와 문헌 검토

<a name="academic-paper-review"></a>

academic-paper-review

### 논문 한 편 비평하기

논문 PDF나 원문 링크를 준비하세요. 연구 질문, 방법, 결과를 연결해 저자의 결론을 어디까지 뒷받침하는지 검토합니다.

#### 요청 예시

> DeerFlow의 academic-paper-review 스킬을 사용해줘. 첨부한 논문의 표 2를 중심으로 표본 선정과 측정 방법을 검토해줘. 저자가 주장한 내용과 표에서 확인되는 내용을 구분해줘.

[원본 지침 ↗](https://github.com/bytedance/deer-flow/blob/585abb979fbc483485c0fc53ed0e571ab7eebadb/skills/public/academic-paper-review/SKILL.md)

<a name="systematic-literature-review"></a>

systematic-literature-review

### 여러 논문을 한 기준으로 읽기

주제, 기간, 포함·제외 기준을 정합니다. 기본 검색 대상은 arXiv입니다. 국내 학술지까지 다룰 때는 별도로 확보한 서지 목록과 원문을 함께 제공하세요.

#### 요청 예시

> DeerFlow의 systematic-literature-review 스킬을 사용해줘. 장소 추천 알고리즘의 평가 방법을 조사해줘. arXiv 검색식과 선정 기준을 기록하고, 읽은 논문별 데이터셋·평가 지표·한계를 표로 만들어줘.

[원본 지침 ↗](https://github.com/bytedance/deer-flow/blob/585abb979fbc483485c0fc53ed0e571ab7eebadb/skills/public/systematic-literature-review/SKILL.md)

<a name="deep-research"></a>

deep-research

### 하나의 질문을 여러 출처로 조사하기

조사할 질문과 범위를 알려주세요. 웹 자료의 시점과 출처를 대조해 일치하는 결과와 엇갈리는 근거를 정리합니다.

#### 요청 예시

> DeerFlow의 deep-research 스킬을 사용해줘. 2019년 이후 국내 연구에서 핫플레이스를 어떻게 정의했는지 조사해줘. 정의마다 원문을 연결하고, 방문량과 소셜미디어 언급량을 쓴 연구를 구분해줘.

[원본 지침 ↗](https://github.com/bytedance/deer-flow/blob/585abb979fbc483485c0fc53ed0e571ab7eebadb/skills/public/deep-research/SKILL.md)

<a name="github-deep-research"></a>

github-deep-research

### GitHub 프로젝트의 변화 추적하기

공개 저장소 주소와 조사 기간을 줍니다. 커밋, 릴리스, 이슈 기록으로 연표와 기술 변화 보고서를 구성합니다. GitHub와 웹 접근이 필요합니다.

#### 요청 예시

> DeerFlow의 github-deep-research 스킬을 사용해줘. https://github.com/bytedance/deer-flow 의 1.x와 2.x를 비교해줘. 실행 구조가 달라진 지점마다 릴리스나 코드 근거를 붙여줘.

[원본 지침 ↗](https://github.com/bytedance/deer-flow/blob/585abb979fbc483485c0fc53ed0e571ab7eebadb/skills/public/github-deep-research/SKILL.md)

<a name="consulting-analysis"></a>

consulting-analysis

### 의사결정용 보고서 설계하기

결정할 사안과 독자를 정합니다. 먼저 목차와 필요한 데이터를 설계하고, 수집한 자료를 바탕으로 최종 보고서를 작성합니다.

#### 요청 예시

> DeerFlow의 consulting-analysis 스킬을 사용해줘. 독립서점의 두 번째 점포 후보를 비교하려고 해. 먼저 판단 기준, 필요한 자료, 보고서 목차를 짜줘. 자료가 없는 항목은 빈칸으로 둬.

[원본 지침 ↗](https://github.com/bytedance/deer-flow/blob/585abb979fbc483485c0fc53ed0e571ab7eebadb/skills/public/consulting-analysis/SKILL.md)

[목차로 돌아가기 ↑](#toc)

<a name="group1"></a>

## 데이터와 콘텐츠

<a name="data-analysis"></a>

data-analysis

### 엑셀·CSV 집계하기

표 파일과 열의 의미를 알려주세요. 동봉된 Python 스크립트가 DuckDB로 시트를 조회·집계하고 결과를 표나 CSV로 내보냅니다.

#### 요청 예시

> DeerFlow의 data-analysis 스킬을 사용해줘. 첨부한 매출 CSV에서 월별 주문 수와 객단가를 계산해줘. 취소 주문 처리 방식과 누락된 금액 건수를 적고 집계표를 CSV로 저장해줘.

[원본 지침 ↗](https://github.com/bytedance/deer-flow/blob/585abb979fbc483485c0fc53ed0e571ab7eebadb/skills/public/data-analysis/SKILL.md)

<a name="chart-visualization"></a>

chart-visualization

### 수치를 차트로 보여주기

데이터와 보여줄 관계를 줍니다. 원본 스크립트는 Node.js 18 이상을 사용하며 차트 데이터를 외부 렌더링 서비스로 전송합니다.

#### 요청 예시

> DeerFlow의 chart-visualization 스킬을 사용해줘. 공개 통계인 이 월별 방문자 표를 선그래프로 그려줘. 세로축 단위와 출처를 적고 가장 큰 변동을 한 문장으로 설명해줘.

[원본 지침 ↗](https://github.com/bytedance/deer-flow/blob/585abb979fbc483485c0fc53ed0e571ab7eebadb/skills/public/chart-visualization/SKILL.md)

<a name="newsletter-generation"></a>

newsletter-generation

### 읽을거리를 뉴스레터로 편집하기

기간, 독자, 기사 링크를 주면 수집한 소식을 주제별로 편집해 초안을 만듭니다.

#### 요청 예시

> DeerFlow의 newsletter-generation 스킬을 사용해줘. 첨부한 기사 5개로 문화산업 연구자용 주간 뉴스레터를 써줘. 기사마다 새로 확인된 사실 한 가지와 원문 링크를 넣어줘.

[원본 지침 ↗](https://github.com/bytedance/deer-flow/blob/585abb979fbc483485c0fc53ed0e571ab7eebadb/skills/public/newsletter-generation/SKILL.md)

<a name="image-generation"></a>

image-generation

### 참고 이미지로 새 이미지 만들기

대상, 구도, 용도와 참고 이미지를 준비합니다. 동봉 스크립트는 Gemini, MiniMax 또는 OpenAI 호환 이미지 서비스의 키를 사용합니다.

#### 요청 예시

> DeerFlow의 image-generation 스킬을 사용해줘. 첨부한 골목 사진의 구도를 참고해 도시문화 세미나 포스터용 가로 이미지를 만들어줘. 제목을 얹을 왼쪽은 비워줘.

[원본 지침 ↗](https://github.com/bytedance/deer-flow/blob/585abb979fbc483485c0fc53ed0e571ab7eebadb/skills/public/image-generation/SKILL.md)

<a name="music-generation"></a>

music-generation

### 배경음악이나 노래 만들기

분위기와 악기, 보컬 여부 또는 가사를 주면 MP3를 생성합니다. 원본 스크립트에는 MINIMAX_API_KEY가 필요합니다.

#### 요청 예시

> DeerFlow의 music-generation 스킬을 사용해줘. 도시 산책 팟캐스트의 오프닝 음악을 만들어줘. 보컬 없이 느린 베이스와 솔 드럼을 쓰고 MP3로 저장해줘.

[원본 지침 ↗](https://github.com/bytedance/deer-flow/blob/585abb979fbc483485c0fc53ed0e571ab7eebadb/skills/public/music-generation/SKILL.md)

<a name="podcast-generation"></a>

podcast-generation

### 글을 두 진행자의 대화로 바꾸기

기사나 보고서를 대본으로 바꾼 뒤 음성을 합성합니다. 음성 파일 생성에는 MiniMax 또는 Volcengine의 음성 합성 인증 정보가 필요합니다.

#### 요청 예시

> DeerFlow의 podcast-generation 스킬을 사용해줘. 첨부한 연구 요약을 두 진행자가 나누는 4분 분량 한국어 대본으로 바꿔줘. 두 진행자가 연구 질문과 결과를 한 번씩 짚게 해줘. 대본을 확인한 뒤 음성 파일도 만들어줘.

[원본 지침 ↗](https://github.com/bytedance/deer-flow/blob/585abb979fbc483485c0fc53ed0e571ab7eebadb/skills/public/podcast-generation/SKILL.md)

<a name="video-generation"></a>

video-generation

### 장면 설명으로 영상 만들기

장면과 움직임을 묘사하고 필요하면 참고 이미지를 줍니다. 원본 영상 생성에는 Gemini 또는 MiniMax 인증 정보가 필요합니다.

#### 요청 예시

> DeerFlow의 video-generation 스킬을 사용해줘. 이 사진을 첫 장면으로 삼아 비 오는 골목 영상을 만들어줘. 카메라는 고정하고 빗물과 간판 불빛만 움직이게 해줘.

[원본 지침 ↗](https://github.com/bytedance/deer-flow/blob/585abb979fbc483485c0fc53ed0e571ab7eebadb/skills/public/video-generation/SKILL.md)

<a name="ppt-generation"></a>

ppt-generation

### 이미지 중심 발표 자료 만들기

청중, 발표 시간, 자료를 줍니다. 슬라이드를 이미지로 생성해 PPTX로 조립하므로 이미지 생성 서비스 설정이 필요하며, 슬라이드 안 글자의 개별 편집에는 제약이 있습니다.

#### 요청 예시

> DeerFlow의 ppt-generation 스킬을 사용해줘. 첨부한 연구 결과로 학회용 6장 발표 자료를 만들어줘. 먼저 장별 주장과 도표를 제안하고, 승인하면 PPTX로 만들어줘.

[원본 지침 ↗](https://github.com/bytedance/deer-flow/blob/585abb979fbc483485c0fc53ed0e571ab7eebadb/skills/public/ppt-generation/SKILL.md)

[목차로 돌아가기 ↑](#toc)

<a name="group2"></a>

## 웹과 개발

<a name="frontend-design"></a>

frontend-design

### 웹 화면 구현하기

화면의 목적, 주요 동작, 대상 기기를 알려주세요. 웹 페이지나 컴포넌트를 코드로 구현합니다.

#### 요청 예시

> DeerFlow의 frontend-design 스킬을 사용해줘. 연구 참여자가 휴대폰에서 일정과 장소를 확인할 수 있는 단일 HTML 페이지를 만들어줘. 날짜별로 접었다 펼 수 있게 해줘.

[원본 지침 ↗](https://github.com/bytedance/deer-flow/blob/585abb979fbc483485c0fc53ed0e571ab7eebadb/skills/public/frontend-design/SKILL.md)

<a name="web-design-guidelines"></a>

web-design-guidelines

### 웹 화면의 사용성 점검하기

검토할 UI 소스 파일을 지정합니다. 최신 웹 인터페이스 가이드라인을 가져와 수정할 곳을 파일명·줄 번호와 함께 제시합니다.

#### 요청 예시

> DeerFlow의 web-design-guidelines 스킬을 사용해줘. 이 프로젝트의 신청 폼을 검토해줘. 키보드 이동, 입력 레이블, 오류 표시에서 고칠 지점을 파일과 줄 번호로 알려줘.

[원본 지침 ↗](https://github.com/bytedance/deer-flow/blob/585abb979fbc483485c0fc53ed0e571ab7eebadb/skills/public/web-design-guidelines/SKILL.md)

<a name="code-documentation"></a>

code-documentation

### 코드에서 사용 설명서 작성하기

저장소나 소스 폴더와 독자를 지정합니다. 구현을 읽고 README, API 문서 또는 개발자 가이드를 작성합니다.

#### 요청 예시

> DeerFlow의 code-documentation 스킬을 사용해줘. 이 저장소를 처음 쓰는 연구자를 위한 README를 작성해줘. 설치, 작은 입력 예시 하나, 결과 파일 위치를 실제 코드 기준으로 설명해줘.

[원본 지침 ↗](https://github.com/bytedance/deer-flow/blob/585abb979fbc483485c0fc53ed0e571ab7eebadb/skills/public/code-documentation/SKILL.md)

<a name="vercel-deploy"></a>

vercel-deploy

### 웹 프로젝트를 미리보기로 배포하기

배포할 폴더를 지정합니다. 스크립트가 프로젝트를 압축해 외부 배포 서비스에 업로드하고 미리보기 주소를 반환합니다.

#### 요청 예시

> DeerFlow의 vercel-deploy 스킬을 사용해줘. 공개용 파일만 담은 이 폴더를 Vercel 미리보기로 배포해줘. 완료되면 접속 주소를 알려줘.

[원본 지침 ↗](https://github.com/bytedance/deer-flow/blob/585abb979fbc483485c0fc53ed0e571ab7eebadb/skills/public/vercel-deploy/SKILL.md)

[목차로 돌아가기 ↑](#toc)

<a name="group3"></a>

## 에이전트와 스킬 관리

<a name="bootstrap"></a>

bootstrap

### AI 협업 방식 설정하기

선호하는 말투, 우선순위, 작업 습관을 대화로 정리해 SOUL.md를 작성합니다. 적용할 환경과 파일 위치를 지정하세요.

#### 요청 예시

> DeerFlow의 bootstrap 스킬을 사용해줘. 자료 조사에서 내가 선호하는 근거 수준과 보고 형식을 물어본 뒤, 이 프로젝트에 쓸 SOUL.md 초안을 작성해줘.

[원본 지침 ↗](https://github.com/bytedance/deer-flow/blob/585abb979fbc483485c0fc53ed0e571ab7eebadb/skills/public/bootstrap/SKILL.md)

<a name="claude-to-deerflow"></a>

claude-to-deerflow

### 실행 중인 DeerFlow에 작업 보내기

DeerFlow 서버의 HTTP API에 접속합니다. 서버 주소와 연결 가능한 인스턴스가 필요합니다. 대화 생성, 파일 업로드, 상태 조회 등을 지원합니다.

#### 요청 예시

> DeerFlow의 claude-to-deerflow 스킬을 사용해줘. 내가 지정한 DeerFlow 서버의 상태와 사용 가능한 모델 목록을 조회해줘. 새 대화는 아직 만들지 마.

[원본 지침 ↗](https://github.com/bytedance/deer-flow/blob/585abb979fbc483485c0fc53ed0e571ab7eebadb/skills/public/claude-to-deerflow/SKILL.md)

<a name="find-skills"></a>

find-skills

### 새 스킬 후보 찾기

반복하고 싶은 작업을 설명하면 외부 스킬 생태계에서 후보와 설치 방법을 찾습니다. 검색에는 네트워크 연결이 필요합니다.

#### 요청 예시

> DeerFlow의 find-skills 스킬을 사용해줘. 인터뷰 전사본을 질적 연구용으로 코딩하는 스킬을 찾아줘. 설치 전에 후보별 저장소와 입력 형식부터 비교해줘.

[원본 지침 ↗](https://github.com/bytedance/deer-flow/blob/585abb979fbc483485c0fc53ed0e571ab7eebadb/skills/public/find-skills/SKILL.md)

<a name="skill-creator"></a>

skill-creator

### 반복 작업을 스킬로 만들기

작업 예시와 성공 기준으로 스킬을 작성·평가합니다. 원본의 DeerFlow 사용자 스킬 저장 절차에는 전용 도구 skill_manage가 필요합니다.

#### 요청 예시

> DeerFlow의 skill-creator 스킬을 사용해줘. 매주 인터뷰 노트를 같은 형식으로 정리하는 스킬을 설계해줘. 먼저 지침 초안과 잘 작동하는지 확인할 예시 세 개를 보여줘.

[원본 지침 ↗](https://github.com/bytedance/deer-flow/blob/585abb979fbc483485c0fc53ed0e571ab7eebadb/skills/public/skill-creator/SKILL.md)

<a name="skill-reviewer"></a>

skill-reviewer

### 스킬 패키지 검토하기

검토할 패키지와 사용 목적을 줍니다. 호출 조건, 포함 파일, 실행 경계를 점검합니다. 원본의 자동 검토 도구는 review_skill_package입니다.

#### 요청 예시

> DeerFlow의 skill-reviewer 스킬을 사용해줘. 첨부한 스킬이 이름만 비슷한 요청에도 잘못 호출될지 검토해줘. 문제마다 재현할 요청문과 제안 문구를 붙여줘.

[원본 지침 ↗](https://github.com/bytedance/deer-flow/blob/585abb979fbc483485c0fc53ed0e571ab7eebadb/skills/public/skill-reviewer/SKILL.md)

<a name="surprise-me"></a>

surprise-me

### 여러 스킬을 조합해 결과물 만들기

주제나 재료 하나와 사용 가능한 도구를 바탕으로 여러 스킬을 골라 조합합니다. 원하는 결과물의 크기나 비용 범위를 지정할 수 있습니다.

#### 요청 예시

> DeerFlow의 surprise-me 스킬을 사용해줘. 우리 동네 공개 통계로 작은 전시물을 하나 만들어줘. 사용 가능한 스킬을 조합하되 유료 API 없이 열어볼 수 있는 파일로 만들어줘.

[원본 지침 ↗](https://github.com/bytedance/deer-flow/blob/585abb979fbc483485c0fc53ed0e571ab7eebadb/skills/public/surprise-me/SKILL.md)

[목차로 돌아가기 ↑](#toc)

<a name="maintenance"></a>

## 문제 해결과 업데이트

**스킬을 찾지 못할 때**

Codex 플러그인 목록에서 DeerFlow Skills가 활성화되어 있는지 확인하고 새 채팅을 여세요. 다른 플러그인에도 같은 이름의 스킬이 있으면 요청문에 DeerFlow와 영문 스킬 이름을 함께 적으세요.

**파일을 찾지 못할 때**

원본 지침에 나오는 `/mnt/skills/public/`와 `/mnt/user-data/`는 DeerFlow 서버의 경로입니다. Codex에는 “설치된 플러그인의 scripts 폴더와 이 채팅에 첨부한 파일을 사용하고 결과를 현재 프로젝트에 저장해줘”라고 요청하세요.

**서버나 인증 정보가 필요하다고 할 때**

이 설치본에는 스킬 지침과 보조 파일이 들어 있습니다. 서버 연결, 미디어 생성, 배포는 각 카드에 적힌 도구나 서비스를 사용합니다. 예를 들어 음악 파일 생성에는 MiniMax 키가 필요하지만, 곡의 분위기와 가사는 키를 설정하기 전에도 작성할 수 있습니다. 키는 실행 환경에 설정하세요.

**GitHub 변경분 반영하기**

현재 로컬 패키지는 **1.0.2**, 원본 기준은 `585abb9`입니다. 다음처럼 요청하세요. “DeerFlow의 설치 기준 커밋과 현재 main을 비교하고, skills/public의 변경을 로컬 플러그인에 반영해줘. 재설치 후 활성 버전과 스킬 목록을 확인해줘.”

[원본 저장소](https://github.com/bytedance/deer-flow) · [매뉴얼 기준 소스](https://github.com/bytedance/deer-flow/tree/585abb979fbc483485c0fc53ed0e571ab7eebadb/skills/public) · [이후 변경 내역](https://github.com/bytedance/deer-flow/compare/585abb979fbc483485c0fc53ed0e571ab7eebadb...main)
