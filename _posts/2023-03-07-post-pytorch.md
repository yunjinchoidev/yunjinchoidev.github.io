---
title: "Post: Pytorch "
last_modified_at: 2023-03-07T16:20:02-05:00
categories:
    - aitech
tages:
    - aitech
    - nlp
toc: true
toc_sticky: true
toc_label: "Contents"
---

---
# 1.  Introduction to PyTorch
밑바닥부터 딥러닝 코드 짜기를 짤 수도 있습니다. [책](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=256067157&start=slayer)
하지만 저희는 딥러닝 프레임워크를 사용합니다. 예를 들어서 텐서플로와 파이토치가 있습니다. 텐서플로는 구글에서 만들었고, 파이토치는 페이스북에서 만들었습니다. 

저희는 파이토치를 사용할 것입니다. 파이토치는 장점이 꽤 많습니다. 대표적으로 Define by Run 이라는 작동 방식인데요. 이것은 실행을 한면서 계산 그래프(Computational Graph)를 생성하는 것을 말합니다. 반면 텐서플로는 Define by Run 이라고 해서 그래프를 먼저 정의하는 방식입니다. 파이토치는 학회, 논문에 강점을 가지고 있으며 텐서플로는 실무(프로덕션)에 강점을 가지고 있다고 할 수 있죠. 그리고 파이토치는 즉시 딥러닝 코드가 작동하는지 확인을 할 수가 있으며 numpy, autograd, function 의 기능을 모두 제공합니다. 

# 2. Dive To Pytorch
이제 파이토치 기본에 대해서 공부해 봅시다. 
먼저 autugrad 에 대해서 공부해봅시다. 
아래 코드는 파이토치를 통해 오차 역전파를 계산하는 식입니다.

```
w = torch.tensor(2.0, requires_grad=True)
y = w**2
z = 10*y + 25
z.backward()
w.grad

> z.backward() 를 통해 오차역전파를 계산
> w.grad 를 통해 z 에 대한 w 그레디언트 추출
```

## 여기서 잠깐 ! 
> 최대가능도 추정법이란 뭘까요? 관찰된 데이터가 어떠한 모수로부터 나왔을 가능성이 가장 높은지를 추정하는 방법입니다. 모수란 무엇일까요? 모수는 모집단의 특성(모평균,모분산 등..)을 나타내는 값으로, 이 값을 모집단을 전수조사해야만 알수있는 값입니다. 실질적으로 모집단의 크기와 범위가 너무 방대하기에 전수조사를 실시하지 않고 표본조사를 하는데 표본평균,표본분산 등으로 모평균, 모분산등을 추정할수가 있다.


# 3. 템플릿을 사용합시다.
여러분은 언제까지 코랩을 쓰실 생각입니까? 템플릿을 씁시다. 고수가 되는 지름길이죠. 템플릿을 사용함으로써 우리는 많은 강점을 가져갈 수 있습니다. `실행, 데이터, 모델,  설정, 로깅, 지표, 유틸리티` 이 대표적이죠. 

다음 오픈 소스에서 파이토치 템플릿을 다운 받고 면밀하게 분석해보십시요. 면밀하게 분석을 해봅시다. [링크](https://github.com/victoresque/pytorch-template)


# 4. AutoGrad & Optimizer
논문을 한 번 구현해봅시다. 딥러닝이란 layer를 쌓고 레고 블럭을 쌓는 일련의 과정이라고 할 수 있습니다. input
- 딥러닝 -> layer 쌓기 -> 레고 블럭 쌓기
- 4요소
  - input
  - output
  - forward
  - backward




---

# 5. Dataset & Dataloader
모델도 중요하지만, 데이터를 어떻게 잘 다루느냐도 중요합니다. 엄청나게 많은 데이터가 있습니다. 이것을 어찌해야 할까요? 우리에겐 파이토치가 있습니다. 
- **Pytorch Dataset**
  - 먼저 데이터를 텐서로 바꾸고 DataLoder 로 모델에 먹이기
- **CustomDataset**
  - CustomDataset을 정의 하기 위해서 3개의 메소드를 반드시 정의해야 한다.
    - init, len, getitem
    - utils.data.Dataset 상속
- DataLoder
  - CustomDataset, 기타 옵션으로 실제 데이터에 적용하면 된다.
  - 옵션
    - 미니배치 사이즈
    - ... 많다.
  - 코드를 뜯어보시라.


---
# 6. 모델 불러오기
- 상황
  - 이 말인 즉슨 우리는 실제 라벨과 예측 라벨의 오차 함수의 그레디언트를 계산하고 오차역전파를 계산하여 W 가중치 텐서를 업데이트 시켰다. (공부를 했다. 경험을 했다. 수련을 했다.)
  - 우리는 이 결과를 전달하려 한다.
- model.save() 
- 저장법 2가지
  - 파라메터만 저장
  - 모델형테 + 파라메터 저장




---
# 7. Monitoring tools for PyTorch
- 체크포인트
  - 학습의 중간 결과를 저장
  - earlystopping 
  - loss, metric
  - Earlystopping : 조기 종료

- Loggin
  - Logging이란, 학습이 진행되면서 주요하다고 생각되는 지표들이나 학습의 상태 등 관련된 정보들을 기록하는 것

- Tensorboard
- Tensorboard는 TensorFlow의 프로젝트로 만들어진 시각화 도구로 학습 그래프, Metric, 학습 결과의 시각화를 지원

- Weight, Biases
  - 머신러닝 실험을 원활하게 지원하기 위한 상용 도구로써, 협업, code versioning, 실험 결과 기록 등의 기능을 제공하는 시각화 툴
---
# 8. Muti-GPU




---

# 9. Hyperparameter Tuning
- 학습률(Learning rate)
- 최적화 함수(Optimizer)
- 손실 함수(Loss Fucnction)
-  


---

# 10. PyTorch Troubleshooting




---


---
# 생각해볼점
- AutoGrad 작동 방식 ? 
- 

