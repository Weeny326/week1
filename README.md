# Week 1: LLM의 기본 이해하기

## 학습할 내용
* LLM API의 호출 방법을 알고 그 쓰임새에 대해 이해한다.
* LLM 을 이해할 때 `이것 만큼은 알아야 한다` 라고 하는 기본 지식을 살펴봅니다.

## 주요 개념
* LLM 을 이해할 때 꼭 알아야 하는 개념들 [BASIC_LLM.md](docs/BASIC_LLM.md)
* 프롬프트 엔지니어링이란 무엇일까? [PROMPT_ENGINEERING.md](docs/PROMPT_ENGINEERING.md)

## 미션
### 첫 번째 공통 미션: 나만의 LLM 벤치마크 만들어보기
* 요구사항
  * 나만의 LLM의 성능과 속도를 판단하는 기준을 만들어보자. 즉, 나만의 벤치마크를 만들어보자.
  * 벤치마크의 목표와 방법, 성능을 평가하는 기준, 속도를 평가하는 기준을 알아야 한다.
  * 어떤 모델의 특징을 조사한 뒤, 어떤 모델을 대상으로 평가할 지 생각해본다.
  * 3~5개의 모델을 평가하는 것을 추천한다. 단, 최소 1 개 이상의 Gemini 모델을 포함해야 한다.
  * 소모한 비용과 토큰도 내용에 반드시 포함해주세요.

```markdown
1. 이름: 계엄 벤치마크
2. 목적: 사진이 주어졌을 때 할루시네이션 없이 LLM이 정확하게 표 안의 표를 인식하는지를 확인한다.
3. 평가 데이터셋: https://x.com/taekie/status/1871444223410716699 에 있는 사진
4. 평가 항목: 탄핵반대 시국선언을 한 교수와 대학 이름이 Markdown 형태로 반환되어야 한다.
5. 출력 예시:
---
대학 교수이름
건국대 박인환, 김원식
...
---

6. 정답 세트: https://x.com/taekie/status/1871444223410716699
7. 평가 대상 모델: GPT-o3 (ChatGPT), Gemini 2.5 Pro (Google AI Studio), Gemini 2.5 Flash (Google AI Studio), DeepSeek R1 (OpenRouter)
8. 평가 결과
---
GPT-o3 (ChatGPT) / 파라미터 미공개 / 정답률 80%, 속도: 15m 30s
DeepSeek R1 (OpenRouter) / 500B / 정답률 30%, 속도: ...
...
---
```
# 🗺️ 수도 맞히기 벤치마크 (LLM Capital Benchmark) _ 이주영

## 🎯 목적 (Objective)
대규모 언어 모델(Large Language Models, LLM)이 일반 상식, 특히 세계 국가들의 수도에 대한 지식 정확도를 평가합니다.

## 🧪 테스트 방식 (Test Method)
- 15개 국가명을 모델에게 입력하고 "[국가명]의 수도는 어디인가요?"라고 질문합니다.
- 출력은 "국가명: 수도명" 형식으로 요청합니다.
- 정확한 수도명을 답한 경우에만 정답 처리합니다.
- 동일한 질문을 3~5개 LLM 모델에 적용합니다.

## 📁 평가 데이터셋 (Evaluation Dataset)
다음은 테스트에 사용된 15개 국가와 수도 목록입니다.

| 국가 (Country) | 수도 (Capital) |
|----------------|-----------------|
| 대한민국       | 서울            |
| 일본           | 도쿄            |
| 미국           | 워싱턴 D.C.     |
| 프랑스         | 파리            |
| 독일           | 베를린          |
| 캐나다         | 오타와          |
| 이집트         | 카이로          |
| 브라질         | 브라질리아      |
| 중국           | 베이징          |
| 인도           | 뉴델리          |
| 호주           | 캔버라          |
| 영국           | 런던            |
| 러시아         | 모스크바        |
| 이탈리아       | 로마            |
| 스페인         | 마드리드        |

## 📏 평가 기준 (Evaluation Metrics)
- **정답률 (Accuracy)** = (맞힌 문항 수 / 총 문항 수) × 100%
- **응답 속도 (Latency)** = 질문 후 응답까지 소요 시간 (평균, 초 단위)
- **비용 (Cost)** = 사용된 토큰 수 및 API 과금 기준으로 계산

## 🤖 평가 대상 모델 (Models Tested)
- `GPT-4o` (ChatGPT, OpenAI)
- `Gemini 1.5 Pro` (Google AI Studio)
- `Gemini 1.5 Flash` (Google AI Studio)
- `Claude 3 Sonnet` (Anthropic, claude.ai)
- `DeepSeek R1` (OpenRouter)

## 📊 결과 예시 (Example Results)

| 모델명             | 정답률 | 평균 응답 시간 | 토큰 수 | 비용 (USD) |
|---------------------|--------|----------------|----------|-------------|
| GPT-4o              | 93%    | 7초            | 220      | $0.02       |
| Gemini 1.5 Pro      | 100%   | 6초            | 180      | 무료        |
| Claude 3 Sonnet     | 86%    | 5초            | N/A      | 무료        |
| DeepSeek R1         | 66%    | 9초            | 260      | 무료        |

## ✅ 사용 방법 (Usage Guide)
1. 각 모델에 대해 동일한 15개 질문을 차례로 입력합니다.
2. 응답 결과를 표 형식으로 정리합니다.
3. 정답과 비교해 정확도를 계산합니다.
4. 응답 시간, 토큰 수, 비용 등을 함께 기록합니다.

## 📌 참고사항 (Notes)
- 질문 형식을 통일해 공정성을 확보하세요 (예: "[국가명]의 수도는 어디인가요?").
- 답변 형식은 "국가명: 수도명"으로 요청하여 파싱을 쉽게 만듭니다.
- 자동화를 위해 Python + API(OpenAI, Google, etc)를 이용할 수 있습니다.
- 결과를 기반으로 모델별 일반 상식 이해도 및 비용 효율성을 비교할 수 있습니다.

---




### 두 번째 미션

#### 기획자 전용: Vibe Coding으로 포트폴리오 사이트 만들기
* 과제 목표: 개발자의 도움 없이도 바이브 코딩으로 프론트엔드를 만들어볼 수 있다.
* https://firebase.google.com/docs/studio 에 가입해서 나를 소개하는 이력서 기반 포트폴리오 사이트 하나를 만들어보세요.
* 최종 URL을 마크다운에 담아 제출해주세요.
* 참고자료
  * https://firebase.google.com/docs/studio/get-started
  * https://www.youtube.com/watch?v=d5x2Hq94yKY

## 제출 방법
* YouTube 링크를 참조 해주세요.
* [Markdown 사용법](https://m.youtube.com/watch?v=kMEb_BzyUqk&t=0s) 을 익혀봅니다.
* GitHub Pull Request를 이용하여 제출 합니다. 이름: `제출자_이름.md` 팀인 경우 `제출자이름1_제출자이름2.md` 로 적어주세요.
