---
title: "딥러닝 모니터링(Monintoring) 하기"
last_modified_at: 2023-03-09T20:20:02-05:00
categories:
    - a04_aitech_knowledge
tages:
    - aitech
    - nlp
toc: true
toc_sticky: true
toc_label: "목차"
---

![image](../../../image/aitech.png)



# Monitoring
학습을 하는 데 굉장히 긴 시간이 걸립니다. 학습 과정을 기록하는게 좋겠죠. `TensorBoard`와 `Weight & Bias`를 이용해봅시다.

# Tensorboard
- scalar : metric 표시
- graph : 계산 그래프 
- histogram : weight 분포
- image: 예측 값과 실게 값을 비교 표시
- mesh : 3d 형태의 데이터를 표현하는 도구


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



# Weight & Bias
