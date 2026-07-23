# 제 9 장 · 멀티모달과 실시간 상호작용

> 텍스트에서 음성, GUI, 물리 세계로 확장한다: 음성 3대 패러다임, Computer Use, 로봇

← [메인 README로 돌아가기](../docs/ko/README.md) · 📖 [본문 읽기](../book-ko/chapter9.ko.md)

## 함께 보는 프로젝트

| 프로젝트 | 유형 | 한 줄 설명 |
| --- | :--: | --- |
| [live-audio](live-audio/) | ✅ | 실시간 음성 채팅으로 VAD + ASR(Whisper/SenseVoice) + LLM(GPT-4o/Gemini/Doubao) + TTS(Fish Audio)를 통합하며 WebSocket으로 저지연을 구현한다 |
| `browser-use/` | 📖 | LLM 기반 브라우저 자동화 프레임워크로 폼 작성/웹 내비게이션/데이터 추출을 지원하며 다양한 LLM과 클라우드/샌드박스 배포를 지원한다 |
| `claude-quickstarts/` | 📖 | Claude API 빠른 시작 예제와 모범 사례로 다양한 사용 시나리오를 다룬다 |
| [phone-agent](phone-agent/) | ✅ | 표준 ReAct Agent가 스스로 번호와 목표를 정리하고 `make_phone_call`(전화 음성 API 추상화)을 호출해 통화를 완료하며 필요 시 재통화로 추가 질문한다 |
| [end-to-end-speech](end-to-end-speech/) | ✅ | Step-Audio R1의 엔드투엔드 음성 사고("듣기→생각→말하기")에 대응하며, ASR→LLM→TTS 캐스케이드와 지연·부차언어 손실을 비교한다 |
| [streaming-speech](streaming-speech/) | ✅ | 오디오를 점증하는 길이로 청크화해 ASR에 공급하고 각 구간마다 즉시 텍스트를 출력해 첫 응답 지연을 낮추며, "문장 전체를 기다린 뒤 인식"하는 고정확도·고지연 방식과 비교한다 |
| [controllable-tts](controllable-tts/) | ✅ | LLM 출력에 제어 태그(감정/속도/멈춤/웃음)를 담고, 실행 계층이 이를 파싱해 참조 음성 라이브러리의 스타일 프로파일에 매핑한 뒤 합성한다 |

## 프로젝트 유형 설명

| 아이콘 | 유형 | 의미 |
| :--: | --- | --- |
| ✅ | **독립 실행 가능** | 본 저장소에 완전한 코드가 포함되어 있으며 API Key만 설정하면 바로 실행 가능 |
| 📖 | **재현 가이드** | 직접 `git clone` 해야 하는 **외부 저장소**(학습 프레임워크, 평가 벤치마크 등)에 의존하는 상세 문서 |
| 🚧 | **설계 문서** | 아키텍처와 구현 방안만 포함되어 있으며 실행 가능한 코드는 아직 준비 중 |
