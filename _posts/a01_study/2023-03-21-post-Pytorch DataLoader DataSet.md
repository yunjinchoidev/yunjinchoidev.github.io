---
title: "Pytorch DataLoader DataSet"
last_modified_at: 2023-03-21T20:20:02-05:00
categories:
    - a01_study
tages:
    - nlp
toc: true
toc_sticky: true
toc_label: "목차"
---


<p align="center">
<img src="../../../image/ai.png" 
width="400" height="400"/>
</p>

# Pytorch DataLoader DataSet

## 옵션
데이터 집합: 로드할 데이터 집합 개체를 지정하는 필수 인수입니다. 데이터 집합 개체는 torch.utils.data에서 파생된 클래스의 인스턴스여야 합니다.__getitem__ 및 __len__ 메서드가 구현된 데이터 세트.

배치_크기: 이 옵션 인수는 각 배치에서 로드하고 처리할 샘플 수를 정의합니다. 기본적으로 1(즉, 배치 없음)로 설정됩니다. 배치 크기가 클수록 교육 효율성이 향상될 수 있지만 메모리도 더 많이 필요합니다.

셔플: 이 선택적 부울 인수는 배치를 만들기 전에 데이터 집합을 섞을지 여부를 나타냅니다. 셔플링은 연속된 표본 간의 상관 관계를 줄임으로써 과적합을 방지하는 데 도움이 됩니다. 기본적으로 False로 설정됩니다.

샘플러: 이 옵션 인수를 사용하면 샘플러 개체를 사용하여 사용자 지정 샘플링 전략을 지정할 수 있습니다. torch.utils.data에서 파생된 클래스의 인스턴스여야 합니다.샘플러. 제공된 경우 샘플러가 샘플 순서를 정의하므로 shuffle 인수를 False로 설정해야 합니다.

num_workers: 이 옵션 인수는 데이터 로드에 사용할 하위 프로세스의 수를 지정합니다. 기본적으로 이 값은 0으로 설정되며, 이는 주 프로세스가 데이터를 로드함을 의미합니다. 작업자 수를 늘리면 데이터 로드 속도를 향상시킬 수 있지만 메모리 사용량도 증가할 수 있습니다.

collate_fn: 이 옵션 인수를 사용하면 개별 표본을 배치로 병합하는 사용자 정의 함수를 지정할 수 있습니다. 함수는 샘플 목록을 입력으로 가져가서 배치를 반환해야 합니다. 기본적으로 DataLoader는 torch.utils.data를 사용합니다.0번째 차원을 따라 텐서를 연결하는 _delocs.collate.default_collate.

핀_메모리: 이 선택적 부울 인수를 True로 설정하면 DataLoader가 고정 메모리(페이지 잠금 메모리)의 텐서를 할당하여 GPU를 사용할 때 전송 속도를 향상시킬 수 있습니다. 기본적으로 False로 설정됩니다.

drop_last: 이 선택적 부울 인수는 데이터 집합 크기를 배치 크기로 구분할 수 없는 경우 마지막 불완전한 배치를 삭제할지 여부를 나타냅니다. 기본적으로 False로 설정됩니다.

시간 초과: 이 선택적 인수는 작업자로부터 배치를 수집하기 위한 시간 초과 값(초)을 지정합니다. 기본적으로 0으로 설정되어 시간 초과가 없음을 의미합니다.

worker_init_fn: 이 옵션 인수를 사용하면 초기화 시 각 작업자 하위 프로세스에서 호출할 함수를 지정할 수 있습니다. 함수는 작업자 ID를 나타내는 단일 정수 인수를 사용해야 합니다.



## 예시
```
from torch.utils.data import DataLoader

data_loader = DataLoader(
    dataset=my_dataset,
    batch_size=64,
    shuffle=True,
    num_workers=4,
    pin_memory=True,
    drop_last=True
)
```
