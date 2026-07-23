# 제 5 장 · Coding Agent와 코드 생성

> 코드는 "새로운 도구를 만들어내는 도구"이며, 프로덕션급 Coding Agent의 전체상을 다룬다

← [메인 README로 돌아가기](../docs/ko/README.md) · 📖 [본문 읽기](../book-ko/chapter5.ko.md)

## 함께 보는 프로젝트

| 프로젝트 | 유형 | 한 줄 설명 |
| --- | :--: | --- |
| [coding-agent](coding-agent/) | ✅ | Claude 기반 프로덕션급 코딩 어시스턴트로, 17개 도구 전부를 순수 Python으로 구현(ripgrep과 호환되는 순수 Python Grep 포함)하며 커맨드라인 의존이 없다 |
| [code-for-math](code-for-math/) | ✅ | 동일 모델·동일 문제 집합으로 "순수 사고 체인"과 "코드 보조"를 비교하며, 후자는 sympy/numpy/scipy를 샌드박스에서 실행해 정확도가 뚜렷하게 높다 |
| [code-for-logic](code-for-logic/) | ✅ | "기사와 건달" 퍼즐을 CSP로 변환하고 `python-constraint`로 제약을 정의·해결하여 자연어 추론과 코드 보조를 비교한다 |
| [small-model-codified-rules](small-model-codified-rules/) | ✅ | τ-bench 항공 고객 서비스 대조 실험: 환불 규칙을 프롬프트에서 코드/도구로 옮기면 소형 모델의 성공률과 일관성이 크게 향상된다 |
| [paper-to-ppt](paper-to-ppt/) | ✅ | "PPT 만들기"를 코드 생성으로 재구성: Proposer가 Slidev를 작성하고 Reviewer가 실제로 PNG로 렌더링해 Vision LLM으로 검토·반복한다 |
| [paper-to-video](paper-to-video/) | ✅ | "논문 → PPT"를 바탕으로 해설 대본을 생성하고 TTS로 합성한 뒤 ffmpeg로 페이지별로 동기화하여 나레이션이 있는 해설 영상을 만든다 |
| [video-edit](video-edit/) | ✅ | 다중 장면 영상과 자연어 요구 한 줄만으로 2단계 Vision 위치 파악으로 구간을 잘라내고, Reviewer가 프레임을 추출해 확인하며 불합격 시 반복한다 |
| [adaptive-log-parser](adaptive-log-parser/) | ✅ | 해석 불가능한 새 포맷을 만나도 오류를 내지 않고 코드 Agent에게 `parse` 함수 생성을 맡기며, 테스트 통과 후 사람 개입 없이 엔진에 핫 업데이트한다 |
| [log-diagnosis](log-diagnosis/) | ✅ | 진단 Agent가 트레이스 로그/아키텍처 문서/PRD를 읽어 근본 원인을 찾고, 회귀 테스트를 생성하며, 리플레이 프레임워크로 실제 검증하고 (모의로) GitHub과 연동한다 |
| [dynamic-form](dynamic-form/) | ✅ | 정보가 불완전할 때 계단식 로직이 포함된 HTML 폼을 동적으로 생성해 사용자가 한 번에 정보를 채우게 하고, 취합된 JSON을 Agent에 돌려준다 |
| [erp-agent](erp-agent/) | ✅ | 중국어 자연어를 SQL로 변환해 DB가 실행하며, artifact 패턴으로 LLM이 SQL 산출물만 생성하고 데이터를 옮기지 않아 토큰을 절약하고 오류를 방지한다 |
| [conversational-ui](conversational-ui/) | ✅ | 자연어로 UI 커스터마이징 요구(색상/폰트/문구/레이아웃)를 제시하면 Agent가 React 소스 코드를 수정하고 Vite HMR로 즉시 반영한다 |

## 프로젝트 유형 설명

| 아이콘 | 유형 | 의미 |
| :--: | --- | --- |
| ✅ | **독립 실행 가능** | 본 저장소에 완전한 코드가 포함되어 있으며 API Key만 설정하면 바로 실행 가능 |
| 📖 | **재현 가이드** | 직접 `git clone` 해야 하는 **외부 저장소**(학습 프레임워크, 평가 벤치마크 등)에 의존하는 상세 문서 |
| 🚧 | **설계 문서** | 아키텍처와 구현 방안만 포함되어 있으며 실행 가능한 코드는 아직 준비 중 |
