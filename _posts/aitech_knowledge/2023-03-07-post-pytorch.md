---
title: "Post: Pytorch "
last_modified_at: 2023-03-07T16:20:02-05:00
categories:
    - aitech_knowledge
tages:
    - aitech
    - nlp
toc: true
toc_sticky: true
toc_label: "목차"
image: image/aitech.png

---


![image](../../../image/aitech.png)


# ✅ Introduction to PyTorch
밑바닥부터 딥러닝 코드 짜기를 짤 수도 있습니다. [책](https://www.aladin.co.kr/shop/wproduct.aspx?ItemId=256067157&start=slayer)
하지만 저희는 딥러닝 프레임워크를 사용합니다. 예를 들어서 텐서플로와 파이토치가 있습니다. 텐서플로는 구글에서 만들었고, 파이토치는 페이스북에서 만들었습니다. 

저희는 파이토치를 사용할 것입니다. 파이토치는 장점이 꽤 많습니다. 대표적으로 Define by Run 이라는 작동 방식인데요. 이것은 실행을 한면서 계산 그래프(Computational Graph)를 생성하는 것을 말합니다. 반면 텐서플로는 Define by Run 이라고 해서 그래프를 먼저 정의하는 방식입니다. 파이토치는 학회, 논문에 강점을 가지고 있으며 텐서플로는 실무(프로덕션)에 강점을 가지고 있다고 할 수 있죠. 그리고 파이토치는 즉시 딥러닝 코드가 작동하는지 확인을 할 수가 있으며 numpy, autograd, function 의 기능을 모두 제공합니다. 



<br>
<br>
<br>
<br>




# ✅  Dive To Pytorch
이제 파이토치 기본에 대해서 공부해 봅시다. 
먼저 autugrad 에 대해서 공부해봅시다. 
아래 코드는 파이토치를 통해 오차 역전파를 계산하는 식입니다.
backward 라는 함수는 연쇄법칙을 적용시켜 역전파를 계산합니다.
그러면 자연스래 w.grad 값을 구할 수 있겠죠.

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




<br>
<br>
<br>
<br>


# ✅ Use Template
여러분은 언제까지 코랩을 쓰실 생각입니까? 템플릿을 씁시다. 고수가 되는 지름길이죠. 우리는 미래로 가야합니다. 템플릿을 사용함으로써 우리는 그 미래로 갈 수 있습니다. `실행, 데이터, 모델,  설정, 로깅, 지표, 유틸리티` 이 대표적이죠.
다음 오픈 소스에서 파이토치 템플릿을 다운 받고 면밀하게 분석해보세요. 면밀하게 분석을 해봅시다. [링크](https://github.com/victoresque/pytorch-template)
코딩 능력이 많이 필요하다는 것을 분명 느끼셨을 겁니다. 코딩 역량을 기르십시오.


<br>
<br>
<br>
<br>




# ✅ AutoGrad & Optimizer
논문을 한 번 구현해봅시다.
딥러닝이란 layer를 쌓고 레고 블럭을 쌓는 일련의 과정이라고 할 수 있습니다. input, output, forward, backward가 복잡한 상호작용을 가지고 있는 것이죠.
- torch.nn.Module 클래스 
  - 이 모듈은 기본적인 input, output, forward, backward 구현을 지원합니다.
- torch.nn.Parameter 
  - required_grad=True 옵션을 줘야 gradient 가 최신화 됩니다.
  
파이토치를 사용함으로써 우리는 backward 함수를 직접 구현할 일은 없습니다. 하지만 실제 어떻게 작동하고 있는지 분명하게 이해할 필요가 있습니다.

```
import torch
from torch.autograd import Variable

class LinearRegression(torch.nn.Module):
    def __init__(self, inputSize, outputSize):
        super(LinearRegression, self).__init__()

        ## 토치가 liner를 구현해줬다.
        ## 코드 레벨에서 직접 보시라.
        self.linear = torch.nn.Linear(inputSize, outputSize)

    def forward(self, x):
        out = self.linear(x)
        return out
    
inputDim = 1
outputDim = 1
learningRate = 0.01
epochs = 100

model = LinearRegression(inputDim, outputDim)

# 모델 학습 시킬 때 쿠다 넣기
if torch.cuda.is_available():
    model.cuda()


criterion = torch.nn.MSELoss()
optimizer = torch.optim.SGD(model.parameters(), lr=learningRate)


# 에포크를 돌리란 말이여!! 
for epochs in range(epochs):
    if torch.cuda.is_available():
        inputs = Variable(torch.from_numpy(x_train).cuda())
        labels = Variable(torch.from_numpy(y_train).cuda())
    else:
        inputs = Variable(torch.from_numpy(x_train))
        lables = Variable(torch.from_numpy(y_train))

    # 이걸 해줘야 한다.
    optimizer.zero_grad()

    ## 돌려돌려 
    outputs = model(inputs)


    ## 요것이 손실함수다!
    loss = criterion(outputs, lables)

    # 오케이. 경사하강법!
    loss.backward()

    # 오차역전파 적용 -> 옵티마이저
    optimizer.step()


    print('epochs {}, loss {}'.format(epochs, loss.item()))


Output exceeds the size limit. Open the full output data in a text editor
epochs 0, loss 0.0023449501022696495
epochs 1, loss 0.0023187585175037384
epochs 2, loss 0.002292879391461611
epochs 3, loss 0.0022672710474580526
epochs 4, loss 0.0022419483866542578
epochs 5, loss 0.002216903492808342
epochs 6, loss 0.002192169427871704
epochs 7, loss 0.002167687052860856
epochs 8, loss 0.002143467077985406
epochs 9, loss 0.0021195358131080866
epochs 10, loss 0.0020958760287612677
epochs 11, loss 0.0020724674686789513
epochs 12, loss 0.0020493241026997566
epochs 13, loss 0.002026451053097844
epochs 14, loss 0.002003807807341218
epochs 15, loss 0.001981443725526333
epochs 16, loss 0.0019593113102018833
epochs 17, loss 0.0019374340772628784
epochs 18, loss 0.0019157928181812167
epochs 19, loss 0.0018943949835374951
epochs 20, loss 0.0018732366152107716
epochs 21, loss 0.0018523228354752064
epochs 22, loss 0.0018316390924155712
epochs 23, loss 0.0018111761892214417
epochs 24, loss 0.001790948212146759
...
epochs 95, loss 0.0008068863535299897
epochs 96, loss 0.0007978747016750276
epochs 97, loss 0.0007889581611379981
epochs 98, loss 0.0007801674073562026

```  

- 코드레벨에서 보는 습관을 들여보세요. 
  


```
optimizer.zero_grad() 를 안쓰면 어떻게 될까?
- gradient 가 초기화가 되지 않으면 다음 학습에 영향을 주기 때문에 올바른 학습이 되지 않습니다.
```


<br>
<br>
<br>
<br>




# ✅ [데이터를 불러오자~] Dataset & Dataloader
모델도 중요하지만, 데이터를 어떻게 잘 다루느냐도 중요합니다. 엄청나게 많은 데이터가 있습니다. 이것을 어찌해야 할까요? 우리에겐 파이토치가 있습니다. 

## Pytorch Dataset
먼저 데이터를 텐서로 바꾸고 DataLoder 로 모델에 먹이기(Feeding)
1. 데이터 모으기
2. data 받기
3. transform : 데이터 전처리
  - ToTensor()
  - CenterCrop()

파이토치의 DataSet을 사용함으로써 많은 장점을 가진다.

CustomDataset 와의 결합해봅시다. CustomDataset을 정의 하기 위해서 3개의 메소드를 반드시 정의해야 합니다.

- init
- len
- getitem

utils.data.Dataset 상속
이때 Datase$$t 클래스 사용

## Pytorch Dataloader
이제 DataLoder 모듈을 배워봅시다. CustomDataset, 기타 옵션으로 실제 데이터에 적용하면 됩니다. 옵션으로 다양한 것이 있습니다. 미니배치 사이즈 등이 있겠죠. 코드를 직접 뜻으면서 DataLoader를 해보세요. 



```
실전 연습
Mnist 클론 코딩을 해보세요.
```








<br>
<br>
<br>
<br>




# ✅ [Save Model] 모델을 저장하고 불러오기
우리는 실제 라벨과 예측 라벨의 오차 함수의 그레디언트를 계산하고 오차역전파를 계산하여 W 가중치 텐서를 업데이트 시켰다고 가정합니다. 우리는 이 결과를 전달하려 한다.**어떻게** 하는게 좋을까요 ?

`model.save()` 함수를 사용합시다. 이를 이용해서 모델의 형태와 파라메터를 저장할 수 있습니다. 

저장법 2가지가 있습니다. 

1. 파라메터만 저장
2. 모델형테 + 파라메터 저장

## check point
중간중간에 loss 와 metric을 지속적으로 저장하는 것을 말합니다. 코드 중간에 pickle 형태로 저장하세요. 중간에 Earlystopping(조기 종료) 처리를 할 수 도 있습니다. 

전이학습(Transfer learning) 을 위해 구글, 페이스북에서 학습한 모델을 가져오려고 합니다. 어떻게 할까요?  NLP 분야에서는 `Huggingface`가 대표적입니다.  `Freezing` 는 Transfer 를 적용시키기 위해서 일부분의 가중치를 학습 시키지 않는것을 말합니다. 트랜스퍼 러닝은 외부 모듈에서 전이학습을 가져오고 자신만의 layer를 추가 시켜 학습시키는 방식으로 하면 됩니다. 굉장히 많이 쓰니 집중해서 공부하시기 바랍니다. 



<br>
<br>
<br>
<br>




# ✅ 모니터링 합시다 - Monitoring tools for PyTorch

`Logging`이란 학습이 진행되면서 주요하다고 생각되는 지표들이나 학습의 상태 등 관련된 정보들을 기록하는 것을 말합니다.

`Tensorboard`는 TensorFlow의 프로젝트로 만들어진 시각화 도구로 학습 그래프, Metric, 학습 결과의 시각화를 지원합니다.

`Weight, Biases`는 머신러닝 실험을 원활하게 지원하기 위한 상용 도구로써, 협업, code versioning, 실험 결과 기록 등의 기능을 제공하는 시각화 툴을 말합니다.



```

import os
logs_base_dir = 'logs'
os.makedirs(logs_base_dir, exist_ok=True)

from torch.utils.tensorboard import SummaryWriter
import numpy as np

exp = f"{logs_base_dir}/ex3"
writer = SummaryWriter(exp)
for n_iter in range(100):
  writer.add_scalar('Loss/train', np.random.random(), n_iter)
  writer.add_scalar('Loss/test', np.random.random(), n_iter)
  writer.add_scalar('Accuracy/train', np.random.random(), n_iter)  
  writer.add_scalar('Accuracy/test', np.random.random(), n_iter)
writer.flush()

%load_ext tensorboard
%tensorboard --logdir {"logs"}

```

```
# 분포를 본다.

from torch.utils.tensorboard import SummaryWriter
import numpy as np
writer = SummaryWriter(logs_base_dir)
for i in range(10):
  x = np.random.random(1000)
  writer.add_histogram('distribution centers', x+i, i)
writer.close()

```


<br>
<br>
<br>
<br>




# ✅ Muti-GPU





<br>
<br>
<br>
<br>



# ✅ Hyperparameter Tuning
제대로 학습하기 위해선 하이퍼 파라메터 튜닝을 해야 합니다. 하이퍼 파라메티는 dl 이 학습하지 않는 변수값이죠. 

- 학습률(Learning rate)
- 최적화 함수(Optimizer)
- 손실 함수(Loss Fucnction)

잘 정리하고 잘 변수를 조정해야 합니다. 데이터와 모델을 수정해서 성능을 향상하는 것이 가장 빠르긴 하지만 하이퍼 파라메터를 튜닝하는 힘은 분명 필요합니다. 요즘들어서는 그렇게 많이하는 추세는 아닙니다. 아래 두 가지 방법이 있습니다.

- Grid LayOut
  - 균일적으로 파라메터를 변화시켜나가는 방법
- Random LayOut
  - 랜덤적으로 파라메터를 변화시켜나가는 방법

Ray는 멀티 노드 멀티 프로세스 지원 모듈이다. 분산병령 ml/dl 의 표준이라 할 수 있다.

```
하이퍼 파라메터 튜닝은 어느정도 학습 모델을 완전하게 만들어 놓고 수정하는 것을 추천합니다. 데이터와 모델에 집중하세요.
```






<br>
<br>
<br>
<br>



# ✅ PyTorch Troubleshooting
OOM(Out Of Memory) 란 무엇일까요. GPU 메모리 오류를 말합니다. 
이를 방지하는 방법은 두가지가 있습니다. 하나는 batchSize를 줄이는 것이고, 둘째는 memory를 줄이는 방법입니다. `GPUutil` 모듈을 사용하세요. 사용하지 않는 gpu cache 를 삭제해야 합니다. `torch.no_grad()` 를 사용도 좋습니다. tensor의 float precision을 줄여도 된다.

하지만 결국 중요한 것은 발생할 때마다 직접 트러블 슈팅을 다루는 능력입니다.

```
밑바닥 부터 시작하는 딥러닝 3 추천합니다.
```





<br>
<br>
<br>
<br>


