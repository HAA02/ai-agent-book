# 제 6 장 · Agent 평가

> 성능을 비교 가능한 신호로 바꾼다: 평가 환경, 지표, 통계적 유의성, 평가 기반 모델 선택

← [메인 README로 돌아가기](../docs/ko/README.md) · 📖 [본문 읽기](../book-ko/chapter6.ko.md)

## 함께 보는 프로젝트

| 프로젝트 | 유형 | 한 줄 설명 |
| --- | :--: | --- |
| `terminal-bench/` | 📖 | 실제 터미널 환경(컴파일/학습/배포)에서 Agent의 엔드투엔드 능력을 테스트한다, 약 100개 작업 + 실행 프레임워크 |
| `SWE-bench/` | 📖 | 실제 GitHub 이슈를 해결하는 LLM의 능력을 평가하며 SWE-bench/Lite/Verified/Multimodal 등 여러 버전을 포함한다 |
| `GAIA/` | 📖 | 차세대 LLM의 도구/검색/자율 능력을 평가하며, 답이 명확한 비자명 문제 450개 이상을 3단계 난이도로 나눈다 |
| `OSWorld/` | 📖 | 완전한 OS 환경에서 복잡한 작업(파일 관리, 앱 조작, 시스템 설정)을 수행하는 Agent 능력을 평가한다 |
| `android_world/` | 📖 | Android 환경에서 Agent의 앱 내비게이션, UI 상호작용, 작업 완료 능력을 평가한다 |
| `tau2-bench/` | 📖 | Agent가 도구를 사용해 복잡한 추론(계산, 검색, 데이터 처리)을 수행하는 능력을 집중 평가한다 |
| [elo-leaderboard](elo-leaderboard/) | ✅ | ELO 평점 기반 Agent 성능 리더보드로, 대결을 통해 상대적 능력을 비교한다 |
| [model-benchmark](model-benchmark/) | ✅ | 여러 OpenAI 호환 API에 대해 TTFT, p50/p95 지연, 처리량, 성공률을 횡단 벤치마크하고 명령 한 번으로 비교표를 생성한다 |
| [agent-cost-analysis](agent-cost-analysis/) | ✅ | 다중 턴 Agent 작업(고객 서비스 환불)의 전체 비용을 분해하고, KV-cache 친화 설계/컨텍스트 압축의 A/B 절감량을 정량화한다 |
| [tts-quality-eval](tts-quality-eval/) | ✅ | 여러 TTS 구성으로 도전적인 텍스트를 합성하고, LLM-as-a-Judge가 Rubric에 따라 차원별로 채점해 재현 가능한 비교표를 출력한다 |
| [public-health-reporting-eval](public-health-reporting-eval/) | ✅ | 합성된 DHIS2 스타일 집계 데이터를 기반으로 공중보건 보고 Agent의 도구 호출, 계산 정확성, 근거 인용, 무근거 주장을 객관적으로 평가한다 |

> 📖 제 6 장은 전부 외부 평가 벤치마크 저장소이며, 클론 명령은 부록 《외부 저장소 가져오기》를 참고한다. [`chapter6/android-world/`](android-world/)(하이픈 명명)는 벤치마크 코드가 아니라, 본 책이 T3A Agent의 android_world 실패 사례를 분석한 노트(`t3a*.md`)로 읽기 자료로 참고할 수 있다.

## 프로젝트 유형 설명

| 아이콘 | 유형 | 의미 |
| :--: | --- | --- |
| ✅ | **독립 실행 가능** | 본 저장소에 완전한 코드가 포함되어 있으며 API Key만 설정하면 바로 실행 가능 |
| 📖 | **재현 가이드** | 직접 `git clone` 해야 하는 **외부 저장소**(학습 프레임워크, 평가 벤치마크 등)에 의존하는 상세 문서 |
| 🚧 | **설계 문서** | 아키텍처와 구현 방안만 포함되어 있으며 실행 가능한 코드는 아직 준비 중 |
