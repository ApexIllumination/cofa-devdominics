# Cofa 최소 작업 kit

## 바로 시작하기

Clone 후 제공된 Codex에 **“cofa-kit/README.md를 읽고 시작해 줘”**라고 요청한다. 폴더명이 다르면 실제 경로로 바꾼다.

사용자가 이 kit를 적용해 작업을 시작하도록 요청했다면 다음 지침을 따른다. 단순 설명·검토 요청이면 그 요청 범위만 수행한다.

> 이 README와 같은 폴더의 [CORE.md](CORE.md)와 [EXAM.md](EXAM.md)를 읽고, 최신 시험 안내를 우선해 적용한다. 실제 과제의 README와 제출 조건부터 확인하고 필요한 스킬만 선택한다. 핵심 사용자 흐름을 먼저 구현·검증하고, 중요한 판단 근거와 미확인은 기존 과제 기록 한 곳에 남긴다. 큰 설계 결정 후와 제출 준비 때 사용자가 구현을 이해하고 설명할 시간을 둔다.

이 저장소의 README는 kit 사용 안내이며 실제 과제 README를 대신하지 않는다. Clone만으로 지침이 자동 적용되지는 않는다.

과제 범위·데이터 계약·실행 검증·구현 이해를 돕는 비공식 지침과 Python 보조 도구다. 특정 과제의 답안·공정 임계값·완성 서비스를 포함하지 않는다. 실제 과제 안내와 제공 환경의 권한이 우선한다.

## 공개 저장소에서 가져오기

배포자는 이 패키지의 내용만 별도 공개 저장소의 루트에 올리고 URL을 안내한다. 사용자는 제공 환경 안에서 공개 저장소를 Clone하거나 허용된 다운로드 경로로 가져온다. 개인 PC 파일 업로드는 사용하지 않는다. 2026 SK하이닉스 Cofa 2차 예선에 적용할 때는 [시험 적용 규칙](EXAM.md)을 확인한다.

아래는 제공 환경의 터미널에서 실행하는 예다. `COFA_PUBLIC_REPO_URL`에 확인한 공개 저장소 URL을 먼저 설정하고, `cofa-kit`이라는 폴더가 이미 있다면 다른 새 이름을 사용한다.

```sh
: "${COFA_PUBLIC_REPO_URL:?확인한 공개 저장소 URL을 먼저 설정하세요}"
git clone --depth 1 "$COFA_PUBLIC_REPO_URL" cofa-kit
```

Clone할 수 없으면 제공 환경의 허용된 다운로드 방식이나 Cofa Helper 안내를 따른다. 차단·업로드 제한을 다른 경로로 우회하지 않는다. 가져오기만으로 스킬·hook·MCP가 자동 등록되지는 않는다.

## 스킬 선택

CORE는 선택 기준만 안내한다. 여섯 스킬을 전부 읽거나 실행할 필요는 없다. 자동 발견 기능이 확인되지 않은 환경에서는 해당 `SKILL.md`의 경로를 지정하면 된다. 같은 스킬의 여러 사본을 동시에 등록하지 않는다.

## 필요할 때만 사용하는 파일

| 필요 | 읽거나 실행할 파일 |
| --- | --- |
| 공통 운영·스킬 선택 | [CORE.md](CORE.md) |
| 이번 시험의 도구·단계·제출 제한 | [EXAM.md](EXAM.md) |
| 과제 범위·성공 조건 | [task-scope](skills/task-scope/SKILL.md) |
| 업무 규칙·예외 | [decision-rules](skills/decision-rules/SKILL.md) |
| 현업 질문으로 목적·판단·데이터 의미를 확인해야 함 | [공용 질의응답 참조](skills/task-scope/references/stakeholder-elicitation.md) |
| 데이터·도구 입출력 | [tool-contracts](skills/tool-contracts/SKILL.md) |
| 실제 결과 대조 | [verify-results](skills/verify-results/SKILL.md) |
| 중단·재개 | [session-handoff](skills/session-handoff/SKILL.md) |
| 구현 설명 연습 | [explain-work](skills/explain-work/SKILL.md) |
| 구조 지도·변경 검사·골든셋 실행 | [OPERATIONS.md](OPERATIONS.md), [cofa.py](scripts/cofa.py) |
| 기존 상태 문서가 없을 때의 빈 양식 | [task-state.md](templates/task-state.md) |

CLI 보조 도구는 Python 3.9 이상과 표준 라이브러리만 사용한다. CLI가 필요할 때만 `python3 --version`과 `python3 cofa-kit/scripts/cofa.py --help`로 확인한다. 추가 모델 실행기·네트워크 연결·네이티브 hook·Computer Use·설치 자동화는 포함하지 않는다. 보조 도구가 지원되지 않아도 지침을 읽고 제공된 도구로 작업할 수 있다.

`templates/`는 현재 과제 기록이나 실행 가능한 정답이 아닌 양식이다. 파일명과 `.cofa/` 디렉터리는 제안이며 공식 제출 규격이 아니다. 실제 과제의 필수 파일·경로를 우선한다. 배포본의 `MANIFEST.json`은 파일 목록과 SHA-256을 제공하며 서명이나 공식 승인 증명은 아니다.
