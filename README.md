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
(submission 에 이주영.md 파일에 결과 작성했습니다.)




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
