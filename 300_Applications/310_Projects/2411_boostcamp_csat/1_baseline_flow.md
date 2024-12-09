
retrieval 할 때, 지문/질문/보기 가중치 둬서 가져와야 하나? 고정 가중치 두는게 맞음?
다언어로 Retrieval 한다면, 데이터 어떻게 구성하고 임베딩 어떻게 구워야 함?
DB는 뭘 쓸까?

## Tip


### Multilingual LLM
- 데이터셋: 수능 데이터 사용은 못하지만, 비슷한 도메인 데이터셋 훈련 (SATII, 중국 수능)
    - 외국의 데이터 확인해봐도 좋을 것
- 훈련 방식
    - fine-tuning
    - rlhf

## 질의응답
- 모델, 프롬프트, 하이퍼파라미터, 데이터셋 중 어떤것에 집중할까? 그 외에 다른 방법 있을까?
- 한국어 시험이다 보니 한국어에 특화된 모델
- 모델이 작을수록 데이터가 중요
    - 하이퍼파라미터 수정은 데이터, 모델 fix되고 마지막에 권장
    - overfitting 조심
- 프롬프트 엔지니어링도 중요
    - - 가성비 가장 좋은 방법일 것
- 여러 종류의 파인튜닝 적용해보기 
    
LLM이 답변을 생성할 때의 reasoning을 사용해 성능을 올리는 방법 있을까?
- teacher-student 구조로 성능이 좋은 모델에게 질문-답 pair를 input으로 받고, 
- 문제 풀이나 해설을 생성한 후
- 이 데이터를 사용해 student 모델을 학습시킬 수 있을 것 같음
- (큰 모델의 reasoning을 배울 수 있는 방법)

데싸 대학원 준비하기 위해 중요한 역량?
- 입시: 논문 >>>>>>>>>>>> 모든 것
- 연구: 기초(딥러닝, AI, NLP), 영어

라벨링이 잘못된 경우 존재함
- 사람이 직접 걸러내야 하나?
- train에서 제외 권장 
- 그 시대의 제일 좋은 모델에게 거르게 시키는 것도 방법



---
양자화 개념 궁금

---
gpt-4o로 풀어보게 시키자
- 각 카테고리별로 대표 예시 few-shot
- 답변 낼 수 없는거 내기 (품질이상, 문맥과 문제, 지문 따로 노는것들 few-shot)

RAG 시 고려사항
- 어떤 문서 가져와야 하나?
    - 보기에 개념들 등장하는 경우, 이 개념에 대한 문서 가져와야 함
    - 한국사는 개념 이해하고 관련 문서 가져와야
    - 문제 유형 분류하고, 어떤 문서 추가 탐색 필요한지 LLM에게 자체 탐색하도록 구성?