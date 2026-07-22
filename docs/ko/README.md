# AI Agent 심층 탐구: 설계 원리와 엔지니어링 실무

[![Stars](https://img.shields.io/github/stars/bojieli/ai-agent-book?style=social)](https://github.com/bojieli/ai-agent-book) [![License](https://img.shields.io/badge/license-Apache--2.0-blue.svg)](../../LICENSE) [![PDF](https://img.shields.io/badge/PDF-download-success.svg)](#-전자책) [![Languages](https://img.shields.io/badge/translations-6%20languages-informational.svg)](#-전자책)

**[中文](../../README.md) · [中文繁體](../zh-TW/README.md) · [English](../en/README.md) · [Tiếng Việt](../vi/README.md) · [தமிழ்](../ta/README.md) · 한국어 ← 현재**

**Agent = LLM + Context + Tools** — 이 책은 이 핵심 공식을 바탕으로 10개 장에 걸쳐 AI Agent를 원리에서 엔지니어링 실무까지 다룹니다. 전체 본문, 삽화, **88개의 부속 실험**이 모두 오픈소스로 공개되어 있습니다. 직접 실험을 실행해 보시기 바랍니다.

| 📚 **10개 장**의 본문, 기초부터 프로덕션까지 | 📂 **88개** 부속 프로젝트(70개 이상 독립 실행 가능) | 🌐 **6개 언어**: 중국어(간체) / 중국어(번체) / 영어 / 타밀어 / 베트남어 / 한국어 |
| :---: | :---: | :---: |

## 📖 전자책

> 📥 **다운로드**(전체 본문, 무료 오픈소스). 아래 링크는 항상 `main` 브랜치의 최신 빌드를 가리킵니다; 고정판은 [Releases](https://github.com/bojieli/ai-agent-book/releases) 페이지를 참고하세요:
> - **중국어(원본)**: [PDF](https://github.com/bojieli/ai-agent-book/releases/download/latest/AI-Agents-in-Depth-zh-CN.pdf) · [EPUB](https://github.com/bojieli/ai-agent-book/releases/download/latest/AI-Agents-in-Depth-zh-CN.epub)
> - **중국어 번체(대만)**(커뮤니티 번역, by [@tigercosmos](https://github.com/tigercosmos)): [PDF](https://github.com/bojieli/ai-agent-book/releases/download/latest/AI-Agents-in-Depth-zh-TW.pdf) · [EPUB](https://github.com/bojieli/ai-agent-book/releases/download/latest/AI-Agents-in-Depth-zh-TW.epub)
> - **영어**(커뮤니티 번역, by [@nsdevaraj](https://github.com/nsdevaraj)): [PDF](https://github.com/bojieli/ai-agent-book/releases/download/latest/AI-Agents-in-Depth-en.pdf) · [EPUB](https://github.com/bojieli/ai-agent-book/releases/download/latest/AI-Agents-in-Depth-en.epub)
> - **타밀어**(커뮤니티 번역, by [@nsdevaraj](https://github.com/nsdevaraj)): [PDF](https://github.com/bojieli/ai-agent-book/releases/download/latest/AI-Agents-in-Depth-ta.pdf) · [EPUB](https://github.com/bojieli/ai-agent-book/releases/download/latest/AI-Agents-in-Depth-ta.epub)
> - **베트남어**(커뮤니티 번역, by [@toanalien](https://github.com/toanalien)): [PDF](https://github.com/bojieli/ai-agent-book/releases/download/latest/AI-Agents-in-Depth-vi.pdf) · [EPUB](https://github.com/bojieli/ai-agent-book/releases/download/latest/AI-Agents-in-Depth-vi.epub)
> - **한국어**(커뮤니티 번역, kotrans 팀): [PDF](https://github.com/bojieli/ai-agent-book/releases/download/latest/AI-Agents-in-Depth-ko.pdf) · [EPUB](https://github.com/bojieli/ai-agent-book/releases/download/latest/AI-Agents-in-Depth-ko.epub)

중국어 본문 소스는 [`book/`](../../book/)에 있습니다; 중국어 번체(대만)/영어/타밀어/베트남어/한국어 버전은 커뮤니티 기여물(중국어 원본보다 뒤처질 수 있음)이며, 각각 [`book-zhtw/`](../../book-zhtw/), [`book-en/`](../../book-en/), [`book-ta/`](../../book-ta/), [`book-vi/`](../../book-vi/), [`book-ko/`](../../book-ko/)에 있습니다.

공통 빌더가 중국어 간체, 중국어 번체(대만), 영어, 타밀어, 베트남어, 한국어의 EPUB 3 판을 생성합니다. [EPUB 빌드 안내](../../EPUB.md)를 참고하세요.

<details>
<summary><b>🔧 직접 PDF를 빌드하고 싶으신가요?</b> (pandoc / xelatex / ElegantBook 필요)</summary>

- **본문 소스**: `book/introduction.md`(서문), `book/chapter1.md` ~ `book/chapter10.md`(제1~10장), `book/afterword.md`(후기)
- **빌드**: pandoc, xelatex, ElegantBook 문서 클래스와 필요한 폰트를 설치한 뒤 다음을 실행합니다

  ```bash
  cd book && bash build_pdf.sh
  ```

  그림은 `book/gen_*_figs.py`가 생성하며 `book/images/`에 저장됩니다; 조판 세부 사항은 `book/preamble.tex`와 `book/*.lua`를 참고하세요.

</details>

## 📑 내용 개요 (제1~10장)

이 책은 핵심 공식 **Agent = LLM + Context + Tools**를 중심으로, 10개 장에서 점진적으로 내용을 전개합니다:

| 장 | 주제 | 한 줄 요약 | 본문 | 코드 |
| :--: | --- | --- | :--: | :--: |
| 1 | 🚀 **Agent 기초** | "Model as Agent" 패러다임 + **Agent = LLM + Context + Tools**; Harness 엔지니어링이 진짜 경쟁력 | [읽기](../../book-ko/chapter1.ko.md) | [4](../../chapter1/README.ko.md) |
| 2 | 🎯 **Context 엔지니어링** | Context가 Agent 능력의 상한을 결정: KV Cache, 프롬프트 엔지니어링, Agent Skills, context 압축 | [읽기](../../book-ko/chapter2.ko.md) | [9](../../chapter2/README.ko.md) |
| 3 | 📚 **사용자 메모리와 지식 베이스** | 세션 간 사용자 메모리 + 외부 지식: 사용자 메모리, RAG, 구조화 인덱스, 지식 그래프 | [읽기](../../book-ko/chapter3.ko.md) | [13](../../chapter3/README.ko.md) |
| 4 | 🛠️ **도구** | 도구는 Agent의 손: MCP 프로토콜, 인지/실행/협업 도구, 이벤트 기반 비동기 Agent, 능동적 도구 발견 | [읽기](../../book-ko/chapter4.ko.md) | [7](../../chapter4/README.ko.md) |
| 5 | 💻 **Coding Agent와 코드 생성** | 코드는 "새 도구를 만드는 도구"; 프로덕션 수준 Coding Agent 전체 구현 | [읽기](../../book-ko/chapter5.ko.md) | [12](../../chapter5/README.ko.md) |
| 6 | 🎯 **Agent 평가** | 성능을 비교 가능한 신호로 전환: 환경, 지표, 통계적 유의성, 평가 기반 선택 | [읽기](../../book-ko/chapter6.ko.md) | [10](../../chapter6/README.ko.md) |
| 7 | 🧠 **모델 사후 학습** | 사전학습/SFT/RL 3단계: SFT와 RL을 언제 선택할지, 도구 호출의 내재화, 샘플 효율성 | [읽기](../../book-ko/chapter7.ko.md) | [14](../../chapter7/README.ko.md) |
| 8 | 🔄 **Agent 자기 진화** | 가중치를 바꾸지 않는 성장: 경험으로부터 학습, 도구 사용자에서 도구 창조자로 | [읽기](../../book-ko/chapter8.ko.md) | [6](../../chapter8/README.ko.md) |
| 9 | 🎙️ **멀티모달과 실시간 상호작용** | 텍스트에서 음성, GUI, 물리 세계로 확장: 세 가지 음성 패러다임, Computer Use, 로보틱스 | [읽기](../../book-ko/chapter9.ko.md) | [7](../../chapter9/README.ko.md) |
| 10 | 🤝 **멀티 Agent 협업** | 집단 지성 > 개별 지성: 협업 프레임워크, context 공유/격리, 창발적 "Agent Society" | [읽기](../../book-ko/chapter10.ko.md) | [6](../../chapter10/README.ko.md) |

> 💡 **읽기** = GitHub에서 장 본문(markdown)을 읽습니다; **N** = 부속 프로젝트 수, 클릭하면 코드로 이동합니다. 프로젝트 유형(✅ 독립 실행 / 📖 재현 / 🚧 설계)은 각 장의 README에 설명되어 있습니다.
>
> 📚 이 책을 효율적으로 읽는 방법은? **[학습 가이드](LEARNING.md)**를 참고하세요 (핵심 개념, 학습 경로, 난이도 분류, 실천 팁).

## 🔑 API 키

편리한 학습을 위해 여러 플랫폼에서 API 키를 발급받는 것을 권장합니다. 모델 선택은 [이 가이드](https://01.me/2025/07/llm-api-setup/)를 참고하세요.

| 플랫폼 | 링크 | 비고 |
| --- | --- | --- |
| **Kimi** (Moonshot) | <https://platform.moonshot.cn/> | Kimi 시리즈, 긴 context와 Agent 능력이 강함 |
| **Zhipu GLM** | <https://open.bigmodel.cn/> | GLM-4.6 등, 중국어 능력이 뛰어나고 비용 효율적 |
| **Siliconflow** | <https://siliconflow.cn/> | 다양한 오픈소스 모델(DeepSeek, Qwen 등) |
| **Volcano Engine** | <https://www.volcengine.com/product/ark> | ByteDance Doubao(폐쇄형), 중국 내 지연시간이 낮음 |
| **OpenRouter** | <https://openrouter.ai/> | Gemini / Claude / GPT-5 등을 한 번에 이용(공식 API는 해외 IP/결제가 필요하며, OpenAI는 해외 신원 인증도 필요) |

## 📦 부록 · 외부 저장소 가져오기

제6, 7, 9, 10장에 등장하는 벤치마크, 학습 프레임워크, 로봇 플랫폼 관련 외부 저장소 20개는 (크기와 라이선스 문제로) **번들에 포함되어 있지 않으며**, 해당 디렉터리에 직접 clone해야 합니다.

### 일괄 Clone 스크립트

<details>
<summary><b>🔧 clone 명령 펼치기</b> (외부 저장소 20개)</summary>

```bash
# 제6장 · 평가 벤치마크
git clone https://github.com/google-research/android_world.git         chapter6/android_world
git clone https://huggingface.co/datasets/gaia-benchmark/GAIA          chapter6/GAIA
git clone https://github.com/xlang-ai/OSWorld.git                      chapter6/OSWorld
git clone https://github.com/SWE-bench/SWE-bench.git                   chapter6/SWE-bench
git clone https://github.com/sierra-research/tau2-bench.git            chapter6/tau2-bench
git clone https://github.com/laude-institute/terminal-bench.git        chapter6/terminal-bench

# 제7장 · 학습 프레임워크 (bojieli/*는 책에 맞게 조정한 fork)
git clone https://github.com/bojieli/minimind.git                      chapter7/MiniMind-pretrain/minimind      # 실험 7-3 LLM을 처음부터 학습
git clone https://github.com/bojieli/minimind-v.git                    chapter7/MiniMind-pretrain/minimind-v    # 실험 7-4 VLM을 처음부터 학습(projection layer)
git clone https://github.com/bojieli/AdaptThink.git                    chapter7/AdaptThink-original
git clone https://github.com/bojieli/AWorld.git                        chapter7/AWorld
git clone https://github.com/bojieli/SFTvsRL.git                       chapter7/SFTvsRL
git clone https://github.com/bojieli/verl.git                          chapter7/verl
git clone https://github.com/thinking-machines-lab/tinker-cookbook.git chapter7/tinker-cookbook
git clone https://github.com/bojieli/lighteval.git                     chapter7/Intuitor/lighteval
git clone https://github.com/19PINE-AI/rlvp.git                        chapter7/RLVP/rlvp                       # 실험 7-14 RLVP 논문 코드
git clone https://github.com/PRIME-RL/SimpleVLA-RL.git                 chapter7/SimpleVLA-RL/SimpleVLA-RL       # 실험 7-13 vision-language-action RL

# 제9장 · 브라우저 자동화 & Claude 예제
git clone https://github.com/browser-use/browser-use.git               chapter9/browser-use
git clone https://github.com/anthropics/claude-quickstarts.git         chapter9/claude-quickstarts

# 제10장 · 듀얼 Agent 아키텍처(현재 독립 TalkAct 프로젝트) + Stanford AI Town
git clone https://github.com/19PINE-AI/TalkAct.git                     chapter10/use-computer-while-calling
git clone https://github.com/joonspk-research/generative_agents.git    chapter10/generative_agents             # 실험 10-7 Stanford AI Town
```

> 프로젝트 README에 특정 커밋이 지정되어 있다면, 재현성을 위해 해당 버전으로 `git checkout`하세요. 제10장의 `use-computer-while-calling`은 독립적으로 유지되는 [19PINE-AI/TalkAct](https://github.com/19PINE-AI/TalkAct)로 발전했습니다; 이 저장소는 참조 문서만 유지합니다.

</details>

### 그 밖의 재현 경로

아래 실험들은 전용 clone 명령은 없지만 구체적인 재현 방법이 있습니다:

| 실험 | 유형 | 비고 |
| --- | :--: | --- |
| 6-2 / 6-3 / 6-4 / 6-9 | 📝 독자 연습 | Human benchmark, memory 평가, JSON Cards vs RAG, memory 선택 — 제3장의 `user-memory` / `user-memory-evaluation` / `contextual-retrieval`을 응용 |
| 5-12 | 📝 독자 연습 | Agent를 만드는 Agent — `chapter5/coding-agent`에서 시작 |
| 7-8 | 📝 독자 연습 | Prompt distillation — `chapter8/prompt-distillation` 참고(장 간 재사용) |
| 7-9 | 📝 독자 연습 | CoT distillation `[확장]` — 책에 설계와 채점 기준 있음, 전용 코드 없음 |
| 6-11 | 🤖 시뮬레이션 평가 | OpenVLA + RoboTwin2 — VLA 학습/환경 의존성은 `chapter7/SimpleVLA-RL` README 참고 |
| 9-8 / 9-9 | 🔧 실제 하드웨어 | XLeRobot teleoperation과 LLM Agent 제어 — SO-100 팔 필요, [Teleop](https://xlerobot.readthedocs.io/en/latest/software/getting_started/XLeRobot_teleop.html) · [LLM Agent](https://xlerobot.readthedocs.io/en/latest/software/getting_started/LLM_agent.html) |
| 9-10 | 🔧 실제 하드웨어 | RGB zero-shot Sim2Real grasping — [`StoneT2000/lerobot-sim2real`](https://github.com/StoneT2000/lerobot-sim2real)(시뮬레이션은 순수 GPU로 실행; 배포에는 SO-100 필요) |

## 🤝 기여하기

이 책과 부속 코드는 완전히 오픈소스입니다. Pull Request를 환영합니다:

| 유형 | 비고 |
| --- | --- |
| 📝 **책 내용 개선** | 오탈자 수정, 보완, 더 명확한 표현, 새로운 발전 사항(내용은 `book/chapter*.md`) |
| 🐛 **코드 개선 및 버그 수정** | 부속 프로젝트를 더 견고하고 사용하기 쉽고 프로덕션에 가깝게 |
| 🧪 **새 실습 프로젝트** | 실험을 위한 더 나은 구현을 추가/대체하거나 새로운 예제 기여 |
| 🎨 **그림 디자인** | `book/images/`의 차트를 더 명확하고 세련되게(`book/gen_*_figs.py`가 생성) |
| 🌐 **새로운 번역** | 더 많은 언어로의 번역을 환영합니다; 참고용으로 중국어 번체/대만(`book-zhtw/`), 영어(`book-en/`), 타밀어(`book-ta/`), 베트남어(`book-vi/`), 한국어(`book-ko/`) 확인 |

제출 전에 관련 실험을 실행해 재현 가능성을 확인해 주세요; 아이디어를 먼저 논의하고 싶다면 issue를 열어도 좋습니다.

## 📄 라이선스

이 프로젝트는 [Apache License 2.0](../../LICENSE)을 따릅니다. 자세한 내용은 [`LICENSE`](../../LICENSE) 파일을 참고하세요. 일부 하위 프로젝트는 자체 라이선스 정보를 포함할 수 있으니, 해당 하위 프로젝트를 참고하세요.

## ⭐ Star 히스토리

<a href="https://star-history.com/#bojieli/ai-agent-book&Date">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="../../assets/star-history-dark.png" />
    <source media="(prefers-color-scheme: light)" srcset="../../assets/star-history-light.png" />
    <img alt="Star History Chart" src="../../assets/star-history-light.png" width="100%" />
  </picture>
</a>

<sub>[`scripts/gen_star_history.py`](../../scripts/gen_star_history.py)로 생성되며, [GitHub Actions](../../.github/workflows/star-history.yml)를 통해 매일 갱신됩니다 · 이미지를 클릭하면 실시간 데이터를 볼 수 있습니다</sub>
