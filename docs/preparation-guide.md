# Probe 해커톤 준비 키트

2026-10-30 작성. 사진의 평가항목을 인터뷰, 구현, 검증, 참가자 설명에 연결하는 휴대용 Codex 스킬이다. 스킬 1개에 Probe 실전 모드와 6개 작업 모드를 담았다. 실행 스크립트와 외부 API 의존성 없이 Markdown 참고자료로 구성했다.

Probe 안의 터미널 Codex 대화가 평가된다면 그 환경에 설치하고 ‘Probe 실전 모드’를 요청한다. 목표·선택 이유·실제 검증·방향 변경을 현재 대화에서 짧게 설명하고, 참가자 본인의 판단과 이해를 확인한다. 구체적인 시작 문구와 설치 방법은 [저장소 README](../README.md), 진행 방식은 [실전 대화 참고자료](../skills/probe-hackathon-coach/references/dialogue.md)를 따른다.

## 바로 사용할 파일

- [스킬 본문](../skills/probe-hackathon-coach/SKILL.md)
- [사진의 16개 평가항목과 준비 기준](../skills/probe-hackathon-coach/references/rubric.md)
- [AI 사원 인터뷰](../skills/probe-hackathon-coach/references/discovery.md)
- [MVP 계약과 4시간 운영안](../skills/probe-hackathon-coach/references/delivery.md)
- [검증 루프](../skills/probe-hackathon-coach/references/verification.md)
- [참가자 이해도 점검](../skills/probe-hackathon-coach/references/explainback.md)
- [최소 기록과 제출 점검](../skills/probe-hackathon-coach/references/records.md)

## 사용 방법

별도 설치 없이 Codex에 이 폴더의 SKILL.md를 지정하고 “이 스킬을 읽고 다음 과제를 도와줘”라고 요청할 수 있다. 자동 발견을 원하면 `skills/probe-hackathon-coach` 폴더 전체를 대회 작업 폴더의 `.agents/skills/` 아래 복사한다. 결과는 `.agents/skills/probe-hackathon-coach/SKILL.md`가 된다. 기존 동명 스킬이 있으면 덮어쓰기 전에 내용을 비교한다.

설치 방법은 저장소 루트의 README를 따른다. 현재 공식 문서는 프로젝트 `.agents/skills`와 사용자 `~/.agents/skills`를 로컬 스킬 경로로 안내한다. 새 스킬이 목록에 나타나지 않으면 Codex를 다시 시작한다. [OpenAI 공식 스킬 문서](https://learn.chatgpt.com/docs/build-skills)

시작 예:

```text
$probe-hackathon-coach
이번 과제와 공식 안내를 아래에 붙일게. 제한 시간은 4시간이야.
확인된 사실과 가설을 구분하고, 지금 해야 할 다음 행동부터 진행해 줘.
AI 사원에게 물을 질문은 설계 결정을 바꿀 수 있는 순서로 제안해 줘.
```

단계별 예:

```text
$probe-hackathon-coach 인터뷰: 이 대화에서 확인된 사실과 미확인 조건을 나누고 다음 질문 3개를 골라 줘.
$probe-hackathon-coach 범위 확정: 이 요구사항을 4시간 안에 검증할 수 있는 MVP 계약으로 바꿔 줘.
$probe-hackathon-coach 구현: 수용 기준에 따라 핵심 입력부터 출력까지 먼저 작동하게 해 줘.
$probe-hackathon-coach 검증: 예상 결과를 먼저 정하고 가능한 테스트를 실제 실행해 줘.
$probe-hackathon-coach 이해도 점검: 실제 코드로 한 문제씩 묻고 내 답을 기다려 줘.
$probe-hackathon-coach 제출 점검: 평가항목별 근거와 누락을 확인해 줘. 실제로 확인한 내용만 써 줘.
```

## 확인된 대회 정보

SK하이닉스 공식 발표는 온라인 예선에서 Cofa-Probe 등으로 문제 정의, AI 활용, 결과 검증을 평가한다고 안내한다. 과거 크래프톤 대회와 동일한 세부 배점·4시간 구성·AI 사원 대화 구조·외부 Codex 및 사전 스킬 허용까지 확정한 것은 아니다. [SK하이닉스 공식 발표](https://talent.skhynix.com/hub/ko/company/story/237)

공식 일정은 2차 예선 2026년 10월 31일~11월 1일 중 1일, 본선 11월 11일이다. 실제 응시 일시와 도구 사용 조건은 참가자 안내를 우선한다. [대회 홈페이지](https://skhynix-hackathon.com/ai-2026)

## 함께 사용할 수 있는 스킬

아래 스킬은 역할별 참고 후보다. 각 도구와 스킬은 대회 환경에서 별도로 설치하고 동작을 확인해야 한다.

| 상황 | 스킬 | 활용 방법 |
|---|---|---|
| 웹 앱 실제 동작 | playwright-cli | 입력·버튼·오류·재시도를 브라우저에서 확인 |
| CSV·Excel 문제 | spreadsheets:Spreadsheets | 누락·중복·날짜·단위·집계 기준 확인 |
| 요구사항과 화면 흐름 | product-design:audit | 사용자가 핵심 작업을 끝낼 수 있는지 검토 |
| 작은 MVP 구현 | ponytail:ponytail | 필요한 동작을 해결하는 작은 변경에 집중 |
| 원인을 모르는 오류 | superpowers:systematic-debugging | 재현 사례와 원인 확인 후 수정 |
| 완료 전 실제 확인 | superpowers:verification-before-completion | 주장과 검증 결과 일치 여부 확인 |
| 생성 코드 이해 | understand-anything:understand-explain | 특정 파일·함수·데이터 흐름 설명 |
| 구조가 큰 기존 코드 | understand-anything:understand | 필요할 때 전체 구조 파악; 작은 MVP에는 과할 수 있음 |
| 발표 자료 | presentations:Presentations | 실제 문제·시연·검증 근거 중심으로 구성 |
| 제출 문서 | documents:documents, pdf:pdf | 읽기 쉬운 문서와 PDF 확인 |
| 수치·효과 해석 | stats | 잘못된 분모, 인과 과장, 평가 설계 점검 |

메인 진행 스킬은 이 코치처럼 하나를 중심으로 두고, 기능별 스킬을 필요한 순간에 선택하는 구성을 권한다. Superpowers와 다른 전체 개발 절차 패키지를 동시에 자동 적용하면 계획·확인·검토가 중복될 수 있다.

## GitHub 추천 저장소

최근 7일 증가량은 The Skill Leaderboard의 2026-10-29까지 집계다. 2026-10-30 확인했으며 GitHub 공식 일간 순위가 아니다. 단위 k는 약 1천 개다. 기능은 각 저장소 README에서 별도로 확인했다. GitHub Trending 조회 결과에는 지난달 캐시가 표시되어 오늘의 순위로 사용하지 않았다. [집계 출처](https://www.skillleaderboard.com/agent/codex)

| 저장소 | 최근 7일 별 증가 | 해커톤 활용 판단 |
|---|---:|---|
| [pbakaus/impeccable](https://github.com/pbakaus/impeccable) | +9.4k | UI 검토·개선. 핵심 흐름 구현 후 적용. Codex 안내 있음 |
| [DietrichGebert/ponytail](https://github.com/DietrichGebert/ponytail) | +7.1k | 작은 변경과 코드 검토. 필요한 기능을 선별해 활용 |
| [mattpocock/skills](https://github.com/mattpocock/skills) | +5.8k | grill-me·grill-with-docs로 요구와 설계의 빈틈 점검. 질문 시간 제한을 주면 유용 |
| [obra/superpowers](https://github.com/obra/superpowers) | +4.5k | 계획·구현·검증 절차. 필요한 기능을 선별해 활용 |
| [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills) | +2.1k | 요구사항·구현·검토의 대안 패키지. 기존 전체 절차와 겹침 |
| [vercel-labs/agent-skills](https://github.com/vercel-labs/agent-skills) | +387 | React 성능과 web-design-guidelines. 웹 과제일 때 선택 |
| [OthmanAdi/planning-with-files](https://github.com/OthmanAdi/planning-with-files) | +169 | 파일 기반 계획·발견·진행 기록. 현재 기록 방식이 있으면 통합해서 사용 |
| [openai/skills](https://github.com/openai/skills) | +142 | 공식 Codex 스킬 출발점. 필요한 스킬만 선별 |

‘최근 인기’와 ‘이 과제에 유용함’은 다른 기준이다. 추가 후보의 우선순위는 인터뷰 보완용 Matt Pocock, 맥락 보존용 planning-with-files, UI 보완용 Impeccable 순으로 권한다. 첫 두 기능을 이 코치와 기존 기록으로 충분히 수행할 수 있다면 추가 설치가 필수는 아니다.

설치할 때는 저장소의 현재 Codex 안내를 따른다. `.claude` 전용 명령·hook·외부 서비스 연결을 Markdown 스킬만 복사해도 동작한다고 가정하지 않는다. 특히 addyosmani 저장소는 단일 스킬 설치 시 루트의 공용 references가 누락될 수 있다고 안내하므로 참조까지 확인한다.

## 사전 리허설

익숙한 프로게이머 인터뷰 문제로 인터뷰→MVP→검증→직접 설명을 한 차례 연습한다. 이후 다른 업무인 교대 인수인계나 문서 검색을 합성 자료로 연습하면 특정 주제에만 의존하는 준비를 줄일 수 있다. 이 예시는 실제 출제 예상이나 회사 내부 업무 사실이 아니다.

연습 때는 대회에서 사용할 PC·도구로 파일 읽기, 실행, 브라우저 확인, 결과 저장을 한 번 끝까지 수행한다. 스킬을 많이 모았는지보다 각 도구가 실제 환경에서 필요한 순간에 작동하는지 확인하는 것이 중요하다.

이 스킬은 평가항목별 준비를 돕는 초안이다. 형식과 참고 링크, 대표 시나리오의 응답을 점검했으며 실제 대회 채점에서의 점수 상승은 검증하지 않았다.
