# 제 4 장 · 도구

> 도구는 Agent의 손이다: MCP 프로토콜, 인지/실행/협업 세 가지 도구 유형, 이벤트 기반 비동기 Agent

← [메인 README로 돌아가기](../docs/ko/README.md) · 📖 [본문 읽기](../book-ko/chapter4.ko.md)

## 함께 보는 프로젝트

| 프로젝트 | 유형 | 한 줄 설명 |
| --- | :--: | --- |
| [perception-tools](perception-tools/) | ✅ | 인지 도구 MCP: 웹 검색, 멀티모달 이해, 파일 시스템, 공개 데이터 소스(DuckDuckGo/Open-Meteo/Yahoo/OpenStreetMap)로 대부분 API Key가 필요 없다 |
| [execution-tools](execution-tools/) | ✅ | 실행 도구 MCP: 파일 조작, 코드 인터프리터, 가상 터미널, 외부 시스템 통합, LLM 재승인으로 오작동을 방지한다 |
| [collaboration-tools](collaboration-tools/) | ✅ | 협업 도구 MCP: 브라우저 자동화, HITL, Email/Telegram/Slack/Discord 알림, 타이머로 관리자 승인을 지원한다 |
| [agent-with-event-trigger](agent-with-event-trigger/) | ✅ | FastAPI 기반 이벤트 구동 Agent로, 네이티브 비동기 방식으로 앞 세 그룹의 MCP 도구를 통합하고 HTTP API로 Web/IM/GitHub/타이머 이벤트를 수신한다 |
| [active-tool-selection](active-tool-selection/) | ✅ | 사전 정의된 도구 세트를 수동적으로 받아들이는 대신, Agent가 작업 요구에 따라 능동적으로 최적의 도구 조합을 선택하게 한다 |
| [active-tool-discovery](active-tool-discovery/) | ✅ | "120개 이상 도구 스키마 전체 주입"과 "소수의 기본 도구 + discover_tools 메타 도구로 필요 시 검색"을 비교하여 토큰을 절약하고 오선택을 방지한다 |
| [async-agent](async-agent/) | ✅ | asyncio 단일 스레드 이벤트 구동 프레임워크 Flux: 긴급도에 따른 이벤트 큐 디스패치, 비동기 도구 병렬 실행, 실행 중 중단, 장시간 작업의 취소 및 상태 조회 |

> 또한 [`chapter4/docker-compose.yml`](docker-compose.yml)과 [`chapter4/DOCKER_DEPLOYMENT.md`](DOCKER_DEPLOYMENT.md)는 위 MCP 도구 서버를 컨테이너화하여 배포하는 참고 방안을 제공한다.

## 프로젝트 유형 설명

| 아이콘 | 유형 | 의미 |
| :--: | --- | --- |
| ✅ | **독립 실행 가능** | 본 저장소에 완전한 코드가 포함되어 있으며 API Key만 설정하면 바로 실행 가능 |
| 📖 | **재현 가이드** | 직접 `git clone` 해야 하는 **외부 저장소**(학습 프레임워크, 평가 벤치마크 등)에 의존하는 상세 문서 |
| 🚧 | **설계 문서** | 아키텍처와 구현 방안만 포함되어 있으며 실행 가능한 코드는 아직 준비 중 |
