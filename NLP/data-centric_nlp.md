# Data-Centric AI: 데이터 중심의 AI 접근법
- 출처: 네이버 부스트캠프 AI Tech 7기 NLP Track 강의

## 1. AI 시스템의 본질: 코드와 데이터

<h3 align="center">AI 시스템 = 코드(모델/알고리즘) + 데이터</h3>

- **AI 프로젝트의 시간 비율**: 좋은 데이터 확보에 약 80%, 모델 학습에 20%의 시간이 소요됨. 우수한 품질의 데이터를 관리하는 작업이 모델 구조를 개선하는 것보다 성능에 더 큰 영향을 줄 수 있음.
- **서비스 출시 전후의 시간 배분**: 서비스 출시 전에는 데이터와 모델에 각각 50%의 비중을 두지만, 출시 후에는 성능 개선의 대부분(80%)이 데이터 품질 개선에 집중되며, 이는 모델 변경보다 비용이 덜 듦.

### AI 서비스 개발 사이클
1. 프로젝트 정의
2. 데이터셋 준비 (Data-centric view)
3. 모델 학습 및 디버깅 (Model-centric view)
4. 설치 및 유지보수

### Model-Centric vs. Data-Centric 접근 방식
|               | Model-Centric view                        | Data-Centric view      |
| ------------- | ----------------------------------------- | ---------------------- |
| 데이터 수집 방향 | 데이터의 양                            | 데이터의 질 (일관성 등)            |
| 성능 향상 방법      | 모델 구조 개선 | 데이터 퀄리티 개선            |

---

## 2. Data-Centric AI
- **Data-centric**: 데이터를 중심으로 AI 시스템의 성능을 향상시키는 접근 방식
- 모델을 바꾸기보다는 데이터의 수집, 저장, 관리, 분석 등 전 과정에서 데이터의 품질을 개선하는 데 중점을 둠
- 일반적으로 학계에서 논의되는 model-centric 접근과 대비됨

### 주요 전략
1. Data Management: 새로운 데이터 수집
2. 토큰화 방식 교체
3. Data Quality Control
    - Data Filtering: 이상치 탐지 및 제거
        - Parallel Corpus Filtering
        - rule base + NMT Based
    - Data Cleaning: 잘못된 값 및 라벨 오류 수정
        - 데이터 전처리와 비슷한 개념 (불용어 처리, stemming, lemmatization 등)
    - Data Consistency
    - Label Consistency: 라벨링 방법 체계화 (크라우드소싱 데이터 등)
    - Data Tool: 라벨링 도구를 사용한 데이터 개선
4. Data Augmentation: 사전 지식을 인코딩하기 위한 예제 추가
    1. rule-based 기법: EDA(SR, RI, RS, RD), UDA
    2. example interpolation 기법: MixUp, MSDA(Mixed Sample Data Augmentation)
    3. Model-based technique: BT(Back-Translation), Fine-Tuning LLM for paraphrasing
5. Synthetic Data: 인공적으로 생성된 데이터 활용
6. Feature Engineering: 데이터 표현 방식 조정
7. 데이터 이해를 위한 AI 알고리즘
   - Curriculum Learning: 쉬운 예제부터 어려운 예제 순으로 학습
   - Active Learning: 중요한 데이터를 우선적으로 라벨링


### Data-Centric Evaluation
- 모델 성능 평가: 다양한 지표를 통해 데이터 중심 성능 평가 수행
- Data Measurement: 데이터 품질과 가치 측정
    - IAA (Inter-Annotator Agreement)
        - 2명 이상의 어노테이터가 생성한 레이블이 얼마나 일관성 있는지에 관한 지표
        - Cohen's Kappa, Fleiss' Kappa, Krippendorff's Aplha



## 3. Data-Centric AI in Real World
### 좋은 데이터란
- 일관성있게 라벨링된 데이터
- 중요한 케이스와 예상치 못한 케이스를 포함한 데이터
- 적절한 크기의 데이터
- 균형이 맞는 데이터
- 서비스 요구사항에 맞는 데이터

### Data Cascade
- 데이터 문제로 발생하는 하위 태스크에서의 복합적인 부정적 이슈

### Data Management 프로세스
- 데이터의 라이프사이클을 관리하고 효율적으로 활용할 수 있는 프로세스를 구축하는 일련의 과정
- 데이터의 수집, 저장, 관리, 보호, 분석, 활용 등을 포함
- 좋은 데이터를 만들기 위해서는 특이 케이스를 발견하고 해당 샘플들을 수집하며, 이를 포함하는 라벨링 가이드를 만들어야 함

### Data Flywheel
- 반복적으로 개선되는 데이터-모델 피드백 루프
- Model based Data-Centric AI
    - 모델을 통해 에러를 발견하고 사람이 해결해야 함

## 4. DMOps
- DMOps는 데이터 처리의 전 과정을 체계화하여 모든 유형의 태스크에 적용할 수 있는 범용 파이프라인을 제공
- AI 데이터 구축의 필수 12단계를 포함
- 주요 단계
    - Schema Design: 데이터 구조 설계
    - Collection: 데이터 수집
    - Annotation: 데이터 라벨링
    - Evaluation: 데이터 평가
    - Versioning: 데이터 버전 관리


## 5. Data Team Process & DataPerf
### Data Team Process
- 크라우드소싱: 라벨링 및 데이터 수집을 외부 인력을 활용하여 효율성 극대화

### DataPerf
- DataPerf 목표: 데이터 품질을 향상하고 반복 가능한 Data-centric ML 파이프라인을 벤치마크.
- DataPerf Design: 모델을 고정하고 데이터셋만 (시스템적/알고리즘적으로) 개선하여 성능을 측정하는 벤치마크 태스크.

#### DataPerf Benchmark Types

| 벤치마크 타입               | 벤치마크 기법                                          | 벤치마크 지표                                 |
| --------------------- | ------------------------------------------------ | --------------------------------------- |
| Training Set Creation | 학습 데이터셋 대체                       | 새 데이터셋으로 학습한 모델의 정확도                  |
| Test Set Creation     | 테스트 데이터셋 추가                           | 모델이 오분류하고, 사람이 올바르게 라벨링한 테스트 데이터의 개수 |
| Selection Algorithm   | 학습 데이터셋의 subset으로 학습                            | subset 학습 모델의 정확도                    |
| Debugging Algorithm   | 잘못된 라벨이 포함된 학습 데이터셋 식별                           | 식별된 라벨이 수정된 후 학습한 모델의 정확도               |
| Slicing Algorithm     | 학습 데이터셋을 의미적으로 일관된 그룹으로 분할                       | 올바른 그룹에 할당된 데이터 개수                      |
| Valuation Algorithm   | 데이터셋 추가 시 훈련 정확도 예상 (추가한 데이터에는 라벨 없음) | 예측 정확도와 실제 정확도 간 차이                   |

