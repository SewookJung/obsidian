# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 이 저장소에 대해

Obsidian Vault 기반의 개인 지식 관리 시스템. 제텔카스텐 + PARA 방법론을 결합. 소프트웨어 프로젝트가 아니며, 빌드/테스트/배포가 없음. 자세한 구조는 README.md 참조.

## 폴더 구조 요약

- 01~03: 제텔카스텐 (Inbox, Literature Notes, Permanent Notes)
- 04~07: PARA (Projects, Areas, Resources, Archive)
- 08~10: 보조 (MOC, Templates, Attachments)

### Resources vs Attachments

- `06. Resources/` — 마크다운 노트만 (원본 자료를 설명/연결하는 노트)
- `10. Attachments/` — 물리적 파일만 (PDF, 이미지 등 마크다운이 아닌 파일)
- 이 둘을 섞지 말 것

## 편집 규칙

- `.obsidian/` 설정 파일은 Obsidian이 자동 관리하므로, 확인 없이 수정하지 말 것
- YAML frontmatter 구조를 유지할 것
- `[[링크]]`를 깨뜨리지 말 것 — 지식 그래프가 손상됨
- 영구 노트(`03. Permanent Notes/`)는 flat 구조 유지 — 하위 폴더로 분류하지 말 것
- 템플릿은 `09. Templates/`에 위치하며 Obsidian 템플릿 시스템이 참조함

## 컨벤션

### YAML Frontmatter (Properties)

모든 노트는 다음 속성을 포함:
- `type`: `fleeting` | `literature` | `permanent` | `moc`
- `created`: 생성 시각
- `status`: `inbox` → `seedling` → `growing` → `evergreen` (성숙도)
- `tags`: 태그 목록

### 태그 네임스페이스

- `#type/` — 노트 유형 (`#type/permanent`, `#type/literature` 등)
- `#status/` — 성숙도 (`#status/seedling`, `#status/evergreen` 등)
- `#source/` — 문헌 출처 (`#source/book`, `#source/article` 등)
- `#topic/` — 주제 분류 (유기적으로 성장, `#topic/생산성` 등)

### 파일 이름 규칙

| 노트 유형 | 형식                   | 예시                                |
| ----- | -------------------- | --------------------------------- |
| 영구 노트 | 서술적 제목               | `습관은 신호-반복-보상의 루프로 형성된다.md`       |
| 문헌 노트 | `[유형] - [제목] ([저자])` | `Book - 아주 작은 습관의 힘 (제임스 클리어).md` |
| MOC   | `MOC - [주제]`         | `MOC - 생산성.md`                    |
