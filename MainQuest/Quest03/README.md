# How to Quantify Bias in Word Embedding: WEAT

## 프로젝트 개요

본 프로젝트는 AI 윤리 이슈 중 하나인 **임베딩 모델의 편향성**을 주제로 진행한 논문 작성 실습입니다.

워드 임베딩 모델은 학습 데이터에 포함된 사회적·문화적 편향을 벡터 공간에 반영할 수 있습니다.  
따라서 편향을 완화하거나 윤리적으로 개선하기 위해서는 먼저 임베딩 공간 안에 존재하는 편향을 정량적으로 측정하고 해석할 수 있어야 합니다.

이 프로젝트에서는 **WEAT(Word Embedding Association Test)** 를 활용하여 워드 임베딩 내 편향성을 측정하는 방법을 정리하고,  
해당 내용을 처음 발견한 연구자라는 가정하에 논문 형식의 리포트를 작성했습니다.

## 작성한 논문

- [How to quantify bias in word embedding.pdf](./How%20to%20quantify%20bias%20in%20word%20embedding.pdf)

논문은 다음과 같은 구조로 작성했습니다.

- Abstract
- Introduction
- Method
- Result
- Conclusion
- References

## 실험 코드

본 논문형 리포트의 기반이 된 실험 코드는 아래 경로에 있습니다.

- [GoingDeeper/Deep0506 - Movie WEAT 실험 코드](https://github.com/lucy071101/AIFFEL_quest_rs/tree/main/GoingDeeper/Deep0506)

해당 실험에서는 한국어 영화 시놉시스 데이터를 활용하여 Word2Vec 임베딩을 학습하고,  
TF-IDF로 예술영화/일반영화 및 장르별 대표 단어를 추출한 뒤 WEAT score를 계산했습니다.

## 실험 과정 요약

1. 한국어 영화 시놉시스 데이터 전처리
2. Okt 형태소 분석기를 활용한 명사 중심 토큰 추출
3. Word2Vec 기반 워드 임베딩 모델 학습
4. TF-IDF를 활용한 대표 단어 집합 구성
5. Cosine similarity 기반 WEAT score 계산
6. Heatmap 및 PCA를 통한 편향성 시각화
7. 실험 결과를 바탕으로 논문 형식 리포트 작성

## 핵심 기술

- Python
- Word2Vec
- WEAT Score
- Cosine Similarity
- TF-IDF
- KoNLPy / Okt
- Scikit-learn
- Seaborn
- Matplotlib
- PCA

## 결과 및 의의

실험을 통해 영화 장르와 예술영화/일반영화 속성 간의 연관성이 임베딩 공간에서 다르게 나타남을 확인했습니다.

이를 통해 워드 임베딩 모델이 단어의 의미뿐 아니라 데이터에 포함된 문화적·분류적 편향까지 함께 학습할 수 있음을 이해했습니다.  
또한 실험 결과를 논문 형식으로 재구성하며, AI 편향성 분석을 문제 제기, 방법론 설계, 정량 평가, 시각화, 한계점 정리의 흐름으로 설명하는 경험을 얻었습니다.
