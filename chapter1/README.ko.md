# 제 1 장 · Agent 기초

> "모델이 곧 Agent"라는 새로운 패러다임에서 출발해 **Agent = LLM + 컨텍스트 + 도구**라는 핵심 공식을 세우고, Harness 엔지니어링—모델을 넘어선 모든 엔지니어링 역량이야말로 진짜 경쟁력임—을 소개한다.

← [메인 README로 돌아가기](../docs/ko/README.md) · 📖 [본문 읽기](../book-ko/chapter1.ko.md)

## 함께 보는 프로젝트

| 프로젝트 | 유형 | 한 줄 설명 |
| --- | :--: | --- |
| [learning-from-experience](learning-from-experience/) | ✅ | 전통 강화학습(Q-learning)과 LLM 기반 인컨텍스트 학습을 비교하며 Shunyu Yao의 "The Second Half"의 핵심 통찰을 재현. 보물찾기 게임을 통해 LLM이 250~400배의 샘플 효율로 전통 RL을 능가함을 보여준다. |
| [web-search-agent](web-search-agent/) | ✅ | 기본적인 심층 검색 능력을 갖춘 Agent를 구현하여 다중 라운드 검색과 정보 통합을 수행한다. |
| [search-codegen](search-codegen/) | ✅ | 기본적인 심층 검색과 코드 샌드박스 능력을 갖춘 Agent를 구축하고, 웹 검색과 코드 실행 등의 도구를 활용해 복잡한 분석을 수행한다. |
| [context](context/) | ✅ | 체계적인 절제(ablation) 실험을 통해 Agent 컨텍스트 각 구성 요소의 중요성을 보여준다. 여러 LLM 제공자(SiliconFlow Qwen, ByteDance Doubao, Moonshot Kimi)를 지원하며, 다양한 컨텍스트 모드를 설정해 Agent 행동 변화를 관찰할 수 있다. |

## 프로젝트 유형 설명

| 아이콘 | 유형 | 의미 |
| :--: | --- | --- |
| ✅ | **독립 실행 가능** | 본 저장소에 완전한 코드가 포함되어 있으며 API Key만 설정하면 바로 실행 가능 |
| 📖 | **재현 가이드** | 직접 `git clone` 해야 하는 **외부 저장소**(학습 프레임워크, 평가 벤치마크 등)에 의존하는 상세 문서 |
| 🚧 | **설계 문서** | 아키텍처와 구현 방안만 포함되어 있으며 실행 가능한 코드는 아직 준비 중 |
