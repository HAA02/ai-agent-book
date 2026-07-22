# 제 10 장 · 다중 Agent 협업

> 집단 지능은 개체보다 뛰어나다: 협업 프레임워크, 컨텍스트 공유/격리, 창발하는 "Agent 사회"

← [메인 README로 돌아가기](../docs/ko/README.md) · 📖 [본문 읽기](../book-ko/chapter10.ko.md)

## 함께 보는 프로젝트

| 프로젝트 | 유형 | 한 줄 설명 |
| --- | :--: | --- |
| `use-computer-while-calling/` | 📖 | 전화 Agent(Node.js)와 브라우저 Agent(Python)가 WebSocket으로 직접 통신하며 조정자 없이 병렬 협업한다; 코드는 [TalkAct](https://github.com/19PINE-AI/TalkAct)로 독립되었고 본 디렉터리에는 설명만 남아있다 |
| [staged-system-prompt](staged-system-prompt/) | ✅ | 동일한 Coding Agent가 요구사항 명확화/구현/검토 3단계마다 다른 프롬프트와 도구 세트를 로드하며, 대화 이력은 단계 간 공유되고 검토 실패 시 되돌아갈 수 있다 |
| [multi-role-transfer](multi-role-transfer/) | ✅ | 공유 컨텍스트 하의 체인형 handoff: 여러 역할이 각자 독립된 프롬프트와 도구를 가지며 `transfer_to_agent`로 자율적으로 전환한다 |
| [book-translation](book-translation/) | ✅ | 매니저 패턴으로 번역을 용어집/번역/교정 전담 Agent에 분배하며, Manager는 인덱스만 저장하고 번역문은 전부 디스크에 기록해 컨텍스트가 거의 일정하게 유지된다 |
| [parallel-web-research](parallel-web-research/) | ✅ | N개의 동형 하위 Agent가 병렬 검색을 수행하며 적중 시 연쇄적으로 종료된다; 메시지 버스/병렬 디스패치/실시간 모니터링/경쟁 상태 처리가 모두 실제로 구현되어 있다 |
| [voice-werewolf](voice-werewolf/) | ✅ | 다중 Agent 마피아 게임으로 "컨텍스트 비공유"의 정보 권한을 시연한다: 플레이어별 개인 컨텍스트가 엄격히 격리되며 결정론적 심판이 정보를 전달하고 감사한다 |

## 프로젝트 유형 설명

| 아이콘 | 유형 | 의미 |
| :--: | --- | --- |
| ✅ | **독립 실행 가능** | 본 저장소에 완전한 코드가 포함되어 있으며 API Key만 설정하면 바로 실행 가능 |
| 📖 | **재현 가이드** | 직접 `git clone` 해야 하는 **외부 저장소**(학습 프레임워크, 평가 벤치마크 등)에 의존하는 상세 문서 |
| 🚧 | **설계 문서** | 아키텍처와 구현 방안만 포함되어 있으며 실행 가능한 코드는 아직 준비 중 |
