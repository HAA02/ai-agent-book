# Agent Team: kotrans

## 팀 구조도
```
메인 세션 (리더)
 └─ pm (sonnet/high) — 역할 분해·반복 정책 조정
     ├─ Phase 1 (병렬)
     │   ├─ dev-book-ko   (sonnet/low) — book/ → book-ko/ 순차 번역 (용어 일관성 유지)
     │   └─ dev-docs-config (sonnet/low) — docs/ko, chapter README.ko.md, mkdocs.yml, 빌드/폰트 설정
     └─ Phase 2
         └─ qa-i18n (sonnet/low) — check_i18n_consistency.py 검증 + 교차확인
```

## 역할 및 모델·effort 배정
| 역할 | kind | 모델 | effort | tools | maxTurns | 배정 근거 |
|---|---|---|---|---|---|---|
| pm | pm | sonnet | high | — | — | 사용자가 `/TeamPM sonnet`으로 override |
| dev-book-ko | dev | sonnet | low | Read, Write, Edit, Bash | 60 | 구조보존 번역 — book-ta/translate_to_tamil.py 기존 패턴 그대로 적용 가능한 정형 작업, 설계 판단 불필요 |
| dev-docs-config | dev | sonnet | low | Read, Write, Edit, Bash | 40 | zh-CN/book-ta 패턴을 복제·치환하는 정형 작업 |
| qa-i18n | qa | sonnet | low | Read, Bash, Grep | 20 | 자동검증 스크립트 판정 + 구조적 교차비교. 위음성 시 번역 누락이 그대로 배포될 위험이 있어 haiku 단독 배정은 피함 |

## 파일 소유권 (충돌 방지)
| 역할 | 소유(쓰기) | 참조(읽기) |
|---|---|---|
| dev-book-ko | `book-ko/introduction.ko.md`, `book-ko/chapter{1..10}.ko.md`, `book-ko/afterword.ko.md` | `book/**`, `book-ta/translate_to_tamil.py`, `book-ta/**` |
| dev-docs-config | `docs/ko/**`, `chapter{1..10}/README.ko.md`, `index.md`(ko 관련 항목), `README.ko.md`, `mkdocs.yml`, `extras/lang-switcher.js`, `scripts/build_site.sh`, `.github/workflows/build-latest.yml`, `build_epub.sh`, `book-ko/preamble.tex`, `book-ko/cover.tex`, `book-ko/korean-fonts.tex`, `book-ko/build_pdf.sh` | `docs/zh-CN/**`, `chapter{1..10}/README.md`, `book-ta/**`(폰트/빌드 패턴), 기존 `mkdocs.yml`/`build_epub.sh`/workflow 원본 |
| qa-i18n | (없음 — 검증 전용) | `book-ko/**`, `docs/ko/**`, `chapter{1..10}/README.ko.md`, `scripts/check_i18n_consistency.py`, `mkdocs.yml`, `build_epub.sh`, `.github/workflows/build-latest.yml` |

## Phase / 의존관계
| Phase | 역할 | 작업 | 병렬 가능 | 의존성 |
|---|---|---|---|---|
| 1 | dev-book-ko | introduction → chapter1~10 → afterword 순서로 순차 번역 (용어집 일관성 유지 목적, 단일 에이전트 내부에서 순차 처리) | dev-docs-config와 병렬 가능 | 없음 |
| 1 | dev-docs-config | docs/ko, chapter README.ko.md, mkdocs.yml, lang-switcher.js, build 스크립트, LaTeX 폰트 설정 | dev-book-ko와 병렬 가능 | 없음 (book-ko 본문 내용에 의존하지 않음) |
| 2 | qa-i18n | `python scripts/check_i18n_consistency.py` 실행 + 결과 해석, 번역 누락/구조 불일치 확인 | — | dev-book-ko, dev-docs-config 완료 후 |

## loop-engineer 연동
이 팀은 `~/.claude/loop-settings/-run-media-iaan-1TB-WD-Github-ai-agent-book/config.yml`의 `team:` 블록으로 연결되어 있다.
루프 실행: `/loop-engineer` (이 문서를 직접 붙여넣을 필요 없음 — config.yml이 이미 참조한다).

## 재생성/갱신
    /TeamPM [목표]   ← 이 문서·`.claude/agents/kotrans-*.md`·config.yml의 team 블록을 함께 갱신
