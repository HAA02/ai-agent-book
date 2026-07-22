# 제 8 장 · Agent의 자기 진화

> 가중치를 바꾸지 않고도 성장한다: 경험 학습, 도구 사용자에서 창조자로

← [메인 README로 돌아가기](../docs/ko/README.md) · 📖 [본문 읽기](../book-ko/chapter8.ko.md)

## 함께 보는 프로젝트

| 프로젝트 | 유형 | 한 줄 설명 |
| --- | :--: | --- |
| [gaia-experience](gaia-experience/) | ✅ | AWorld + GAIA 기반 "학습-적용" 폐루프: 성공한 궤적을 구조화된 경험으로 자동 요약해 새 작업에서 검색·적용한다 |
| [browser-use-rpa](browser-use-rpa/) | ✅ | 브라우저 워크플로 녹화 시스템으로 반복 작업을 매개변수화된 도구로 캡슐화하며, LLM 추론에서 자동화 실행으로 전환해 3~5배 가속한다 |
| [prompt-distillation](prompt-distillation/) | ✅ | 복잡한 프롬프트의 효과를 모델 파라미터에 증류해 추론 시 프롬프트 길이를 줄이고, 컨텍스트 경험을 파라미터화된 지식으로 고정한다 |
| [prompt-auto-optimization](prompt-auto-optimization/) | ✅ | tau-bench 항공 고객 서비스의 "과도한 이관" 문제를 예로, Coding Agent가 프롬프트 파일을 읽고/수정 → 재평가 → 검증하는 폐루프를 구성한다 |
| [self-evolving-tools](self-evolving-tools/) | ✅ | Alita 방식의 "최소 사전 정의, 최대 자기 진화": 5개의 범용 메타 도구로 직접 라이브러리를 검색하고 문서를 읽어 샌드박스에서 테스트하고 재사용 가능하게 캡슐화한다 |
| [self-evolution-eval](self-evolution-eval/) | ✅ | 20개의 도메인 횡단 작업 + 4계층 검증 harness + 제어 가능한 참조 Agent로 발견/창조/재사용의 품질을 평가한다 |

## 프로젝트 유형 설명

| 아이콘 | 유형 | 의미 |
| :--: | --- | --- |
| ✅ | **독립 실행 가능** | 본 저장소에 완전한 코드가 포함되어 있으며 API Key만 설정하면 바로 실행 가능 |
| 📖 | **재현 가이드** | 직접 `git clone` 해야 하는 **외부 저장소**(학습 프레임워크, 평가 벤치마크 등)에 의존하는 상세 문서 |
| 🚧 | **설계 문서** | 아키텍처와 구현 방안만 포함되어 있으며 실행 가능한 코드는 아직 준비 중 |
