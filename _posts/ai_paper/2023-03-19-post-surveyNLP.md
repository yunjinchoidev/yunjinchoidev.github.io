---
title: "[논문리뷰] A Survey of the Usages of Deep Learning for Natural Language Processing(2017)"
last_modified_at: 2023-03-19T20:20:02-05:00
categories:
    - paper
tages:
    - aitech
    - nlp
toc: true
toc_sticky: true
toc_label: "목차"
---

![paper.png](../../../image/paper.png)


<br><br><br><br>


# A Survey of the Usages of Deep Learning for Natural Language Processing

<br><br><br><br>



```
💡 2018년

1. Introduction
2. Fundamentals of Deep Learning and NLP
2.1 Deep Learning
2.2 Natural Language Processing
3. Deep Learning Architectures for NLP
3.1 Convolutional Neural Networks
3.2 Recurrent Neural Networks
3.3 Transformers
4. Use Cases of Deep Learning for NLP
4.1 Language Modeling
4.2 Sentiment Analysis
4.3 Text Classification
4.4 Machine Translation
4.5 Question Answering
5. Challenges and Future Directions
5.1 Challenges
5.2 Future Directions
6. Conclusion
7. References

```



- 1장
    - 딥러닝에 대한 간략한 소개와 딥 러닝 아키텍처 및 방법에 대한 간략한 개요를 제공 (딥 러닝, 신경망, 자연어 처리, 컴퓨터 언어학, 기계 학습)
    - 
    
- 2장
    
    # 2장
    
    - 딥 러닝 및 자연어 처리(NLP)의 기본 개념을 소개합니다. 이 장은 인공 신경망, 역전파 및 활성화 기능과 같은 딥 러닝 개념에 대한 개요로 시작
    - 이러한 개념을 텍스트 분류 및 감정 분석과 같은 NLP 작업에 어떻게 적용할 수 있는지 설명
    - 토큰화, 형태소 분석 및 불용어 제거와 같은 데이터 전처리 기술을 포함하여 NLP의 기본 사항을 다룹니다. 저자는 이러한 기술을 사용하여 텍스트 데이터를 딥 러닝 모델에 공급하기 전에 정리하고 사전 처리하는 방법을 설명
    - 데이터 전처리, 기능 추출 및 모델 훈련과 같은 NLP를 위한 일반적인 딥 러닝 파이프라인의 다양한 구성 요소를 설명
    - 저자는 컨볼루션 신경망(CNN) 및 순환 신경망(RNN)과 같은 NLP에 사용되는 일반적인 딥 러닝 아키텍처의 예를 제공
    - 이 장에서는 주석이 달린 대량의 데이터가 필요하고 결과 모델을 해석하는 어려움과 같이 NLP에 딥러닝을 사용하는 것과 관련된 문제에 대해 논의하면서 결론을 내립
    
    - 자연어 처리 분야는 컴퓨터 언어학이라고도 하며, 인간 언어를 이해하는 데 있어 실질적인 문제를 해결하기 위한 계산 모델과 프로세스의 엔지니어링을 포함한다
    - 핵심 영역은 자연적으로 발생하는 단어 간의 정량화 연관성을 강조하는 언어 모델링, 단어의 의미 있는 구성 요소의 분할 및 사용된 단어의 실제 발화 부분을 식별하는 형태학적 처리와 같은 근본적인 문제를 다룬다
    - Currently, NLP is primarily a data-driven field using sta- tistical and probabilistic computations along with machine learning.
    - 
- 3장
- 4장
- 5장 V. APPLICATIONS OF NATURAL LANGUAGE PROCESSING USING DEEP LEARNING
    - *Information Retrieval*
        - 기존 정보 검색 시스템을 ..
        - 맥아베니 외. [171] 사전 훈련된 두 가지 상황별 언어 모델인 ELMo [70]와 BERT [71]에서 쿼리 용어 표현을 추출하고, 표현을 사용하여 애드혹 문서 순위를 위해 기존의 3개의 경쟁 신경 순위 아키텍처를 보강했다. 그 중 하나는 DRMM [169]이다. 그들은 또한 BERT의 분류 벡터를 이러한 아키텍처와 결합하여 두 가지 접근법의 이점을 얻는 공동 모델을 제시했다. MacAveney의 CEDR(문서 랭킹을 위한 컨텍스트 임베딩)이라는 시스템은 이전 모델 세 가지 모두의 성능을 향상시켰고, BERT의 토큰 표현을 사용하여 최첨단 결과를 생성했습니다
    - Sentiment analysis
        - 
    - Machine translation
    - Text classification
    - Question answering
    - Named entity recognition
    - Summarization
    - Conversational agents
    - Text generation
- V. CONCLUSIONS
    - 자연어 처리(NLP)를 위한 딥 러닝 사용에 대한 개요를 제공하고 이 분야의 최근 진행 상황을 강조합니다. 딥 러닝 기술은 감정 분석, 기계 번역, 텍스트 분류 및 질문 답변과 같은 NLP 작업에서 큰 성공을 거두었습니다. 그러나 딥 러닝 모델의 해석 가능성 부족과 많은 양의 데이터 및 계산 리소스가 필요하다는 문제가 남아 있습니다. 이 논문은 복잡한 모델을 위한 고도로 전문화된 구성 요소를 개발하는 것보다 사전 교육 방법론에 더 많은 연구 노력을 기울여야 한다고 제안합니다. 또한 이 백서는 향후 작업이 보다 다양한 언어와 분석되지 않은 언어를 사용하는 NLP 모델의 유효성 검사로 향할 것을 권장합니다. 딥 러닝 모델은 데이터가 매우 부족하지만 사전 훈련 및 전이 학습이 매우 영향력 있는 역할을 수행하면서 컴퓨터 언어학의 표준이 될 것으로 예상됩니다. 마지막으로, 이 논문은 뉴로모픽 칩과 같은 계산 장비의 발전이 NLP의 지속적인 발전에 도움이 될 것이라고 제안합니다.
    - 매우 최근에는 인코더 및 종종 디코더로서 주의력을 동력으로 하는 `트랜스포머` 유닛의 스택이 NLP 필드의 풍부하고 다양한 지형에서 일관되게 우수한 결과를 생성했다.
    - 이 최종 관찰 이후, 복잡한 모델에서 마지막 성능 드롭을 짜내기 위해 고도로 전문화된 구성 요소를 개발하는 것보다 `사전 훈련 방법론에 더 많은 연구 노력을 기울이는 것이 유용`할 수 있다.
    - ***인간의 언어 능력이 우리의 감성의 한 부분에 불과하듯이, 언어 처리도 인공지능의 작은 한 부분에 불과하다.*** 이러한 구성 요소가 어떻게 상호 연관되어 있는지 이해하는 것은 보다 완벽한 AI 시스템을 구성하는 데 중요하며, 통합된 NLP 아키텍처를 만드는 것은 이러한 시스템을 현실화하기 위한 또 다른 단계이다.
    - 그러나 딥 러닝 모델의 해석 가능성 부족과 많은 양의 데이터 및 계산 리소스가 필요하다는 문제가 남아 있습니다.
    - GPU 의 발전
