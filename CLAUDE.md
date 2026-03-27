## 이 저장소에 대해

Obsidian Vault 기반의 개인 지식 관리 시스템. 제텔카스텐 + PARA 방법론을 결합. 소프트웨어 프로젝트가 아니며, 빌드/테스트/배포가 없음. 자세한 구조는 README.md 참조.

---

## 핵심 원칙

### 역할 분담

Claude는 **구조적/기계적 보조**만 수행한다:
- 파일 생성/이동, 메타데이터(`related`, `tags`) 작성, 첨부파일 정리, `[[링크]]` 제안
- 노트 본문(특히 Literature Notes, Permanent Notes)은 **사용자가 직접 작성**한다.
- Claude가 사용자의 생각을 대신 요약하거나 완성된 초안을 작성하지 않는다.
- 요청 시 **가이드/제안** 형태로만 제공한다.

### Literature Notes vs Resources

- `02. Literature Notes/`: 원본을 읽고 **사용자의 언어로 재해석/요약**한 노트. 단순 복붙 금지. 반드시 출처(`06. Resources/` 노트 또는 외부 URL)를 연결할 것
- `06. Resources/`: 가공되지 않은 원본 텍스트/웹 클리핑이 담겨있거나, `10. Attachments/`의 물리적 파일을 링크해 둔 **마크다운(.md) 노트**

## 폴더 구조 요약

- 01~03: 제텔카스텐 (Inbox, Literature Notes, Permanent Notes)
- 04~07: PARA (Projects, Areas, Resources, Archive)
- 08~10: 보조 (MOC, Templates, Attachments)

### 유의 사항
 - `03. Permanent Notes/`: 영구 노트는 하위 폴더 없는 flat 구조를 유지한다
 - `10. Attachments/`: 물리적 파일만 (PDF, 이미지 등 마크다운이 아닌 파일)

---

## 컨벤션

### 노트 생성 원칙

새로운 노트를 생성할 때는 임의로 파일을 만들지 않고, **반드시 Obsidian CLI를 사용**하여 `09. Templates/`의 적절한 템플릿이 적용되도록 생성한다. 파일명 컨벤션과 메타데이터 양식은 각 템플릿 내부의 규칙을 따른다.

### YAML Frontmatter (Properties)

YAML frontmatter 구조를 임의로 수정하지 않는다. 모든 노트는 템플릿의 형식에 따라 아래의 필수 속성을 포함해야 한다.

- `tags`: 태그 목록 (허용 목록 참조)
- `related`: 관련 키워드 목록 (허용 목록 참조)
- `created`: 생성 시각 (`YYYY-MM-DD HH:mm`)
- `updated`: 마지막 수정 시각 (`YYYY-MM-DD HH:mm`)

### 태그 (Tags)

태그는 넓은 범주에만 사용하며, 구체적인 명사는 `related` 또는 본문 `[[링크]]`를 사용한다.

**허용 태그 목록 (목록 외 추가 시 사용자 확인 필수):**
`#source/` — 문헌 출처:
- `book`: 도서
- `article`: 아티클, 블로그 글, 뉴스
- `video`: 영상, 강의
- `docs`: 공식 문서, 레퍼런스

`#topic/` — 주제 분류:
- `dev`: 코딩, 아키텍처, DevOps 등 소프트웨어 개발 전반
  - `frontend`: UI, 브라우저, React 등 프론트엔드
  - `backend`: 서버, API, DB 등 백엔드
  - `infra`: CI/CD, 클라우드, 배포, 모니터링
- `career`: 이직, 면접, 직장 생활, 커리어 성장
- `finance`: 투자, 주식, 재테크, 경제
- `growth`: 습관, 생산성, 자기계발, 독서법
- `english`: 영어 학습, 표현, 문법

### Related(관련 키워드 링크)

태그가 넓은 범주를 묶는다면, `related`는 구체적인 명사(기술, 도구, 인물 등)를 연결하여 지식 그래프를 형성한다. 사용 시 반드시 `[[키워드]]` 형태로 flat하게 나열한다.

**허용 related 키워드 (목록 외 추가 시 사용자 확인 필수):**
- backend: `Python`, `Django`, `Kotlin`, `Spring`
- frontend: `React`
- infra: `AWS`

---

## 시스템 안전 규칙

1. 사용자의 명시적 승인 없이 Git commit/push를 실행하지 않는다 (동기화 충돌 방지)
2. `.obsidian/` 디렉토리 내 설정 파일은 수정하지 않는다
3. 파일 이동/이름 변경 시 기존 `[[링크]]`가 깨지지 않도록 유지한다