# 제 3 장 · 사용자 기억과 지식 베이스

> 세션을 넘어 사용자를 기억하고 외부 지식을 연결한다: 사용자 기억, RAG, 구조화 인덱스, 지식 그래프

← [메인 README로 돌아가기](../docs/ko/README.md) · 📖 [본문 읽기](../book-ko/chapter3.ko.md)

## 함께 보는 프로젝트

| 프로젝트 | 유형 | 한 줄 설명 |
| --- | :--: | --- |
| [user-memory](user-memory/) | ✅ | 장기 사용자 기억 시스템을 구축하여 Agent가 사용자 선호와 과거 상호작용을 기억하고 개인화된 서비스를 제공하게 한다 |
| [mem0](mem0/) · [memobase](memobase/) | ✅ | mem0와 Memobase 두 오픈소스 프레임워크로 각각 사용자 기억을 구현하며, 실험 3-2의 비교 대상으로 사용한다 |
| [user-memory-evaluation](user-memory-evaluation/) | ✅ | 사용자 기억 시스템의 정확성, 관련성, 유효성을 체계적으로 평가한다 |
| [dense-embedding](dense-embedding/) | ✅ | 벡터 유사도 검색 서비스를 구축하여 ANNOY(트리 기반)와 HNSW(그래프 기반) 두 ANN 알고리즘의 트레이드오프를 비교한다 |
| [sparse-embedding](sparse-embedding/) | ✅ | BM25 기반 희소 벡터 검색 엔진을 처음부터 구현하고 내부 동작 방식을 시각화한다 |
| [retrieval-pipeline](retrieval-pipeline/) | ✅ | 밀집(dense) + 희소(sparse) + 신경망 재순위화의 완전한 파이프라인을 구축하여 테스트 케이스로 하이브리드 검색의 상호보완 효과를 보여준다 |
| [multimodal-agent](multimodal-agent/) | ✅ | 네이티브 멀티모달 처리, 텍스트 추출, 도구화 분석 세 가지 전략의 충실도/비용/유연성 트레이드오프를 비교한다 |
| [structured-index](structured-index/) | ✅ | RAPTOR(재귀적 요약 트리)와 GraphRAG(지식 그래프) 두 가지 구조화 인덱스를 구현·비교한다 |
| [agentic-rag](agentic-rag/) | ✅ | Non-Agentic RAG와 Agentic RAG를 비교하여, ReAct 기반의 반복적 검색이 사법 질의응답에서 갖는 우위를 보여준다 |
| [agentic-rag-for-user-memory](agentic-rag-for-user-memory/) | ✅ | Agentic RAG로 사용자 대화 이력을 관리하여 세션을 넘나드는 기억 검색을 구현한다 |
| [contextual-retrieval](contextual-retrieval/) | ✅ | Anthropic의 컨텍스트 인식 검색을 구현하여 청크마다 접두 요약을 생성하고, 검색 실패율을 49~67% 낮춘다 |
| [contextual-retrieval-for-user-memory](contextual-retrieval-for-user-memory/) | ✅ | Advanced JSON Cards와 컨텍스트 인식 RAG를 결합하여 이중 계층 기억 구조로 능동적 서비스를 구현한다 |
| [structured-knowledge-extraction](structured-knowledge-extraction/) | ✅ | 사법 판례를 대상으로 "요인 발견 → 클러스터 원형화 → 대화형 조언" 3단계 파이프라인을 구현한다 |

## 프로젝트 유형 설명

| 아이콘 | 유형 | 의미 |
| :--: | --- | --- |
| ✅ | **독립 실행 가능** | 본 저장소에 완전한 코드가 포함되어 있으며 API Key만 설정하면 바로 실행 가능 |
| 📖 | **재현 가이드** | 직접 `git clone` 해야 하는 **외부 저장소**(학습 프레임워크, 평가 벤치마크 등)에 의존하는 상세 문서 |
| 🚧 | **설계 문서** | 아키텍처와 구현 방안만 포함되어 있으며 실행 가능한 코드는 아직 준비 중 |
