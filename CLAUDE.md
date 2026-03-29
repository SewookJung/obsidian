# Second Brain — Zettelkasten Vault

Obsidian Vault 기반의 개인 지식 관리 시스템. 제텔카스텐 방법론 중심으로 운영. 소프트웨어 프로젝트가 아니며, 빌드/테스트/배포가 없음. 자세한 구조는 README.md 참조.

---

## 핵심 원칙

### 역할 분담

Claude는 구조적/기계적 보조만 수행한다:

- 파일 생성/이동, 메타데이터(`tags`) 작성, 첨부파일 정리, `[[링크]]` 제안
- 노트 본문(특히 Literature Notes, Permanent Notes)은 사용자가 직접 작성한다.
- Claude가 사용자의 생각을 대신 요약하거나 완성된 초안을 작성하지 않는다.
- 요청 시 가이드/제안 형태로만 제공한다.

### 노트 유형

|유형|폴더|설명|
|---|---|---|
|MOC|`00. MOC/`|특정 주제의 Permanent Notes를 엮는 목차 노트. 노트가 충분히 쌓이면 만든다|
|Inbox|`01. Inbox/`|빠른 포착용. 생각, 링크, 스크랩 등 뭐든 일단 여기에|
|Literature Note|`02. Literature Notes/`|원본을 읽고 자기 말로 재해석한 노트. 단순 복붙 금지. 반드시 출처 명시|
|Permanent Note|`03. Permanent Notes/`|하나의 독립된 아이디어. 원자적이고, 다른 노트와 `[[링크]]` 필수|

### 폴더 구조

```
0. MOC/
1. Inbox/
2. Literature Notes/
3. Permanent Notes/    ← flat 구조 (하위 폴더 없음)
4. Templates/
5. Attachments/        ← 물리적 파일만 (PDF, 이미지 등)
```

> 번호 04~08이 비어있는 이유: 추후 PARA(Projects, Areas, Resources, Archive 등) 도입 시 충돌 없이 확장하기 위함.

---

## 컨벤션

### YAML Frontmatter

모든 노트는 템플릿의 형식에 따라 아래의 필수 속성을 포함한다:

- `tags`: 태그 목록
- `created`: 생성 시각 (`YYYY-MM-DD HH:mm`)
- `updated`: 마지막 수정 시각 (`YYYY-MM-DD HH:mm`)

YAML frontmatter 구조를 임의로 수정하지 않는다.

### 태그 (Tags)

태그는 출처 유형 분류에만 사용한다. 주제 분류는 본문의 `[[링크]]`와 MOC로 처리한다.

**허용 태그:**

- `#source/book` — 도서
- `#source/article` — 아티클, 블로그 글, 뉴스
- `#source/video` — 영상, 강의
- `#source/docs` — 공식 문서, 레퍼런스

목록 외 태그 추가 시 사용자 확인 필수.

### 연결 (Linking)

- 구체적인 개념, 기술, 도구, 인물 등은 본문에서 `[[키워드]]`로 직접 연결한다.
- Permanent Note는 최소 1개 이상의 `[[링크]]`를 포함해야 한다.

### Literature Note → Permanent Note 승격 기준

다음 조건 중 하나 이상을 충족할 때 Permanent Note로 가공한다:

1. 서로 다른 2개 이상의 출처에서 같은 아이디어가 반복될 때
2. 기존 Permanent Note와 명확한 연결점이 보일 때
3. 원래 맥락을 벗어나도 독립적으로 의미가 통하는 주장/개념일 때

---

## 시스템 안전 규칙

1. 사용자의 명시적 승인 없이 Git commit/push를 실행하지 않는다
2. `.obsidian/` 디렉토리 내 설정 파일은 수정하지 않는다
3. 파일 이동/이름 변경 시 기존 `[[링크]]`가 깨지지 않도록 유지한다