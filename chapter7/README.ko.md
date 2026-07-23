# 제 7 장 · 모델 후속 학습

> 사전학습/SFT/RL 3단계: SFT와 RL을 언제 선택할지, 도구 호출 내재화, 샘플 효율

← [메인 README로 돌아가기](../docs/ko/README.md) · 📖 [본문 읽기](../book-ko/chapter7.ko.md)

## 함께 보는 프로젝트

| 프로젝트 | 유형 | 한 줄 설명 |
| --- | :--: | --- |
| [AdaptThink](AdaptThink/) | 📖 | 추론 모델이 문제 난이도에 따라 Thinking/NoThinking을 적응적으로 선택하게 하며, 제약 최적화 + 중요도 샘플링으로 비용을 45~69% 낮추면서 정확도를 높인다 |
| [retool](retool/) | 📖 | 다중 턴 대화 + 코드 샌드박스로 수학적 추론을 향상시키며, SFT→RL 2단계 학습; Qwen2.5-32B + AIME 2024 + DAPO + SandboxFusion |
| `AWorld/` · [AWorld-train](AWorld-train/) | 📖 | AWorld 프레임워크 기반 체화(embodied) Agent 학습으로 가상 환경에서 작업을 수행하고 경험에서 학습한다 |
| `SFTvsRL/` | 📖 | 지도 미세조정과 강화학습이 서로 다른 작업에서 보이는 효과와 적용 시나리오를 체계적으로 비교한다 |
| `verl/` | 📖 | LLM RLHF를 위해 설계된 고효율 RL 프레임워크로 PPO/GRPO/DAPO 등을 지원한다 |
| [Intuitor](Intuitor/) | ✅ | 모델의 직관적 추론을 학습시켜 상세한 사고 체인 없이도 빠르고 합리적인 판단을 내리게 한다 |
| [MultilingualReasoning](MultilingualReasoning/) | ✅ | 다국어 환경에서 모델의 추론 능력을 학습시켜 언어 간 작업 성능을 향상시킨다 |
| [SpatialReasoning](SpatialReasoning/) | 📖 | 모델의 공간 추론 능력을 학습시켜 위치, 방향, 거리 등 공간 관계를 처리한다 |
| [SimpleVLA-RL](SimpleVLA-RL/) | 📖 | 시각-언어-행동 RL로 모델이 시각 입력을 이해하고 그에 맞는 행동을 수행하게 한다 |
| [continued-pretraining](continued-pretraining/) | ✅ | 특정 도메인 데이터로 지속적인 사전학습을 수행해 목표 도메인 성능을 향상시킨다 |
| [MiniMind-pretrain](MiniMind-pretrain/) | 📖 | 소형 LLM/VLM을 처음부터 사전학습하며 전체 사전학습 과정과 핵심 기술을 이해한다 |
| [sesame](sesame/) | ✅ | 시퀀스 모델링 작업의 학습 및 평가 방법에 중점을 둔다 |
| [orpheus](orpheus/) | ✅ | 모델의 음악 생성 및 이해 능력을 학습시킨다 |
| `tinker-cookbook/` | 📖 | 다양한 모델 학습의 실용적 팁과 모범 사례를 모은다 |
| [cot-distillation](cot-distillation/) | ✅ | OpenRouter를 통해 Claude 등 최전선 모델을 호출해 CoT 궤적을 증류하고, 규칙 검증기로 필터링해 SFT 데이터를 생성한다(실험 7-9 관련) |

## 프로젝트 유형 설명

| 아이콘 | 유형 | 의미 |
| :--: | --- | --- |
| ✅ | **독립 실행 가능** | 본 저장소에 완전한 코드가 포함되어 있으며 API Key만 설정하면 바로 실행 가능 |
| 📖 | **재현 가이드** | 직접 `git clone` 해야 하는 **외부 저장소**(학습 프레임워크, 평가 벤치마크 등)에 의존하는 상세 문서 |
| 🚧 | **설계 문서** | 아키텍처와 구현 방안만 포함되어 있으며 실행 가능한 코드는 아직 준비 중 |
