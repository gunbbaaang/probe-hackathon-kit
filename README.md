# Probe Hackathon Kit

AI 사원 인터뷰부터 문제 정의, MVP 구현, 검증, 참가자 설명까지 돕는 한국어 Codex 스킬입니다. 하나의 코치에 6개 모드를 담았으며, 스킬 자체에는 외부 API나 실행 스크립트 의존성이 없습니다.

공식 대회 운영사와 무관한 개인 준비용 자료입니다. 포함된 과거 평가항목은 준비를 위한 참고이며, 실제 대회 안내와 도구 사용 규칙을 우선합니다.

## 현장에서 한 줄 설치

Node.js 22.20 이상과 Git이 있는 환경에서 **대회 작업 폴더의 터미널**을 열고 실행하세요. 공개 저장소이므로 다운로드에 GitHub 로그인은 필요하지 않습니다. `skills` CLI 1.7.4로 설치를 검증했습니다.

Windows PowerShell:

```powershell
npx.cmd --yes skills@1.7.4 add gunbbaaang/probe-hackathon-kit --skill probe-hackathon-coach --agent codex --copy --yes
```

macOS / Linux:

```bash
npx --yes skills@1.7.4 add gunbbaaang/probe-hackathon-kit --skill probe-hackathon-coach --agent codex --copy --yes
```

현재 프로젝트 범위로 설치됩니다. `--copy`는 심볼릭 링크 권한이 없는 환경에서도 파일 복사로 설치하도록 합니다. 같은 이름의 스킬이 이미 있으면 기존 수정 내용을 먼저 백업하거나 비교하세요. 이 명령은 원격 저장소의 현재 버전을 가져옵니다.

설치 확인:

```powershell
npx.cmd --yes skills@1.7.4 list --agent codex
```

macOS/Linux에서는 `npx.cmd` 대신 `npx`를 사용합니다. Codex에서 `$probe-hackathon-coach`를 선택하거나 입력하세요. 목록이 갱신되지 않으면 Codex를 다시 시작합니다.

### Node.js가 없으면

Codex 채팅에서 기본 설치 스킬에 다음을 요청할 수 있습니다.

```text
$skill-installer install https://github.com/gunbbaaang/probe-hackathon-kit/tree/main/skills/probe-hackathon-coach
```

기본 설치 스킬도 없는 환경에서는 저장소 ZIP을 다운로드하고 `skills/probe-hackathon-coach` 폴더 전체를 작업 폴더의 `.agents/skills/` 아래 복사합니다. 최종 파일 위치는 `.agents/skills/probe-hackathon-coach/SKILL.md`입니다. `references`와 `agents` 폴더도 함께 복사해야 합니다.

## 바로 시작

```text
$probe-hackathon-coach
제한 시간은 4시간이고, 아래에 과제와 공식 안내를 붙일게.
확인된 사실과 가설을 구분하고 다음 행동부터 진행해 줘.
AI 사원에게 물을 질문은 설계 결정을 바꿀 수 있는 순서로 제안해 줘.
실행한 검증과 미실행 검증을 구분하고, 마지막에는 내가 직접 설명할 수 있는지 한 문제씩 확인해 줘.
```

| 모드 | 요청 예 |
|---|---|
| 인터뷰 | 이 대화에서 확인된 사실과 미확인 조건을 나누고 다음 질문 3개를 골라 줘. |
| 범위 확정 | 4시간 안에 검증할 수 있는 MVP 계약과 제외 범위를 정해 줘. |
| 구현 | 수용 기준에 따라 입력부터 출력까지 핵심 흐름을 작동하게 해 줘. |
| 검증 | 예상 결과를 먼저 정하고 가능한 테스트를 실제 실행해 줘. |
| 이해도 점검 | 실제 코드로 한 문제씩 묻고 내 답을 기다려 줘. |
| 제출 점검 | 평가항목별 근거와 누락을 확인하고 실제 확인한 내용만 정리해 줘. |

## 들어 있는 자료

- [스킬 본문](skills/probe-hackathon-coach/SKILL.md)
- [사진에서 정리한 16개 평가항목](skills/probe-hackathon-coach/references/rubric.md)
- [AI 사원 인터뷰](skills/probe-hackathon-coach/references/discovery.md)
- [MVP 계약과 4시간 운영안](skills/probe-hackathon-coach/references/delivery.md)
- [검증 루프](skills/probe-hackathon-coach/references/verification.md)
- [참가자 이해도 점검](skills/probe-hackathon-coach/references/explainback.md)
- [최소 기록과 제출 점검](skills/probe-hackathon-coach/references/records.md)
- [함께 쓸 스킬과 GitHub 후보 안내](docs/preparation-guide.md)

원본 평가 화면, 참가자 이름·연락처, 개인 대화 로그, 자격 증명은 포함하지 않습니다. 평가항목의 설명과 행동 예시는 자체 준비 지침이며 공식 상세 채점 기준이 아닙니다.

## 확인 범위

스킬 형식, 내부 참고 링크, 대표 가상 상황의 응답을 점검했습니다. 실제 대회 채점에서 점수 상승을 검증한 것은 아닙니다. 설치 확인 결과는 [검증 기록](docs/validation.md)에 기록합니다.

설치 방식: [skills CLI 공식 안내](https://github.com/vercel-labs/skills) · [Codex 스킬 공식 안내](https://learn.chatgpt.com/docs/build-skills)
