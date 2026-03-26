# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 이 저장소에 대해

Obsidian Vault 기반의 개인 지식 관리 시스템. 제텔카스텐 + PARA 방법론을 결합. 소프트웨어 프로젝트가 아니며, 빌드/테스트/배포가 없음. 자세한 구조는 README.md 참조.

## 핵심 원칙

### 역할 분담

Claude는 **구조적/기계적 보조**만 수행한다:
- 파일 생성/이동, 메타데이터(`related`, `tags`) 작성, 첨부파일 정리, `[[링크]]` 제안

노트 본문(특히 Literature Notes, Permanent Notes)은 **사용자가 직접 작성**한다.
Claude가 사용자의 생각을 대신 요약하거나 완성된 초안을 작성하지 않는다.
요청 시 **가이드/제안** 형태로만 제공한다.

### Literature Notes vs Resources

- `02. Literature Notes/`: 원본을 읽고 **사용자의 언어로 재해석/요약**한 노트. 단순 복붙 금지. 반드시 출처(`06. Resources/` 노트 또는 외부 URL)를 연결할 것
- `06. Resources/`: 가공되지 않은 **외부 원본 자료 그대로** 보관하는 창고 (웹 스크랩, 공식 문서 등)

## 폴더 구조 요약

- 01~03: 제텔카스텐 (Inbox, Literature Notes, Permanent Notes)
- 04~07: PARA (Projects, Areas, Resources, Archive)
- 08~10: 보조 (MOC, Templates, Attachments)

`06. Resources/`: 마크다운 노트만 (원본 자료를 설명/연결하는 노트)
`10. Attachments/`: 물리적 파일만 (PDF, 이미지 등 마크다운이 아닌 파일)

## 컨벤션

### YAML Frontmatter (Properties)

모든 노트는 다음 속성을 포함:
- `created`: 생성 시각
- `updated`: 마지막 수정 시각
- `tags`: 태그 목록
- `related`: 관련 개념/기술 링크 목록 (예: `[[Python]], [[Django]]`)

### 태그

태그는 넓은 범주(분야/문맥)에만 사용. 구체적인 명사(기술, 도구, 인물 등)는 `related` 또는 본문 `[[링크]]`로 연결한다.

`#source/` — 문헌 출처:
- `book`: 도서
- `article`: 아티클, 블로그 글
- `video`: 영상, 강의
- `website`: 웹사이트, 공식 문서

`#topic/` — 주제 분류:
- `dev`: 코딩, 아키텍처, DevOps 등 소프트웨어 개발 전반
  - `frontend`: UI, 브라우저, React 등 프론트엔드
  - `backend`: 서버, API, DB 등 백엔드
  - `infra`: CI/CD, 클라우드, 배포, 모니터링
- `career`: 이직, 면접, 직장 생활, 커리어 성장
- `finance`: 투자, 주식, 재테크, 경제
- `growth`: 습관, 생산성, 자기계발, 독서법
- `english`: 영어 학습, 표현, 문법

### 파일 이름 규칙

| 노트 유형 | 형식                   | 예시                                |
| ----- | -------------------- | --------------------------------- |
| 영구 노트 | 서술적 제목               | `습관은 신호-반복-보상의 루프로 형성된다.md`       |
| 문헌 노트 | `[유형] - [제목] ([저자])` | `Book - 아주 작은 습관의 힘 (제임스 클리어).md` |
| MOC   | `MOC - [주제]`         | `MOC - 생산성.md`                    |

## 주의사항

- `.obsidian/` 설정 파일은 Obsidian이 자동 관리하므로, 확인 없이 수정하지 말 것
- YAML frontmatter 구조를 유지할 것
- `[[링크]]`를 깨뜨리지 말 것 — 지식 그래프가 손상됨
- 영구 노트(`03. Permanent Notes/`)는 flat 구조 유지 — 하위 폴더로 분류하지 말 것
- 템플릿은 `09. Templates/`에 위치하며 Obsidian 템플릿 시스템이 참조함
- `06. Resources/`와 `10. Attachments/`를 섞지 말 것
- 허용 태그 목록에 없는 태그는 사용자 확인 후 추가할 것
