# 제 2 장 · 컨텍스트 엔지니어링

> 컨텍스트는 Agent 능력의 상한을 결정한다: KV Cache, 프롬프트 엔지니어링, Agent Skills, 컨텍스트 압축

← [메인 README로 돌아가기](../docs/ko/README.md) · 📖 [본문 읽기](../book-ko/chapter2.ko.md)

## 함께 보는 프로젝트

| 프로젝트 | 유형 | 한 줄 설명 |
| --- | :--: | --- |
| [local_llm_serving](local_llm_serving/) | ✅ | 크로스 플랫폼 로컬 LLM 배포, vLLM/Ollama 백엔드를 자동 선택하며 0.6B 소형 모델도 우수한 도구 호출이 가능함을 보여준다 |
| [attention_visualization](attention_visualization/) | ✅ | LLM의 전체 토큰 시퀀스와 어텐션 가중치 분포를 시각화하여 모델이 컨텍스트를 처리하고 추론하며 도구를 호출하는 방식을 이해한다 |
| [kv-cache](kv-cache/) | ✅ | 서로 다른 컨텍스트 관리 방식이 KV Cache에 미치는 영향을 탐구하고, 잘못된 패턴이 캐시 효율을 어떻게 파괴하는지 보여준다 |
| [context-compression](context-compression/) | ✅ | 요약, 핵심 정보 추출, 의미 압축 등 여러 전략을 구현·비교하여 능력을 유지하면서 토큰을 절감한다 |
| [prompt-engineering](prompt-engineering/) | ✅ | Tau-Bench를 확장하여 어조, 지시 구성, 도구 설명 등의 요인이 작업 완료율에 미치는 영향을 정량화한다 |
| [system-hint](system-hint/) | ✅ | 시스템 프롬프트가 Agent 행동에 미치는 영향을 연구하고, 시스템 프롬프트 최적화를 통한 성능 향상 방법을 탐구한다 |
| [log-sanitization](log-sanitization/) | ✅ | 디버깅 정보를 유지하면서 민감한 데이터를 보호하는 지능형 로그 마스킹 시스템 |
| [prompt-injection](prompt-injection/) | ✅ | 3가지 공격 시나리오 × 4가지 방어 구성의 대조 실험으로, 방어를 겹겹이 쌓을수록 주입 성공률이 낮아짐을 직관적으로 보여준다 |
| [agent-skills-ppt](agent-skills-ppt/) | ✅ | Agent Skills의 "점진적 공개(progressive disclosure)"를 재현: 필요할 때만 전체 워크플로를 로드한 뒤 python-pptx로 실제 `.pptx`를 생성한다 |

## 프로젝트 유형 설명

| 아이콘 | 유형 | 의미 |
| :--: | --- | --- |
| ✅ | **독립 실행 가능** | 본 저장소에 완전한 코드가 포함되어 있으며 API Key만 설정하면 바로 실행 가능 |
| 📖 | **재현 가이드** | 직접 `git clone` 해야 하는 **외부 저장소**(학습 프레임워크, 평가 벤치마크 등)에 의존하는 상세 문서 |
| 🚧 | **설계 문서** | 아키텍처와 구현 방안만 포함되어 있으며 실행 가능한 코드는 아직 준비 중 |
