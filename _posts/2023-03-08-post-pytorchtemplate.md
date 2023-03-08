---
title: "Post: ai tech - pytorch Template 완전 분석 "
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

# boostcamp_AITech_5th
![image](../../../image/aitech.png)



# Pytorch 템플릿을 문석해봅시다.
 [링크](https://github.com/victoresque/pytorch-template)
 여기 오픈 소스가 하나 있습니다. 이 포스팅을 통해 이 템플릿을 분해, 분석 해보는 시간을 가지려고 합니다.

 ![파일 ](../../../image/aitech/pytorchtemplatetree.png)

```
* train.py              -> 실행
* test.py               -> 실행
* config                -> 설정
* parse_config          -> 설정
* base                  -> base 모델
* data_loader ~         -> data 
* model ~               -> 모델
* save ~                -> 저장소
* trainer ~             -> 학습
* logger ~              -> 로깅
* utils ~               -> 유틸
```

---
## 실행 방법입니다
루트 디렉토리에서 `python train.py -c config.json` 을 치세요.

## 분해
- train.py
  - arg.add_argument
- config.json
  - util의 `read_josn` 을 보라.
- train/tariner.py
- baser/base_tariner.py
  - 학습의 원천이 되는 소스

## 아하 그러니까요.
스프링 부트와 같은 웹 프레임워크를 사용하신 분들에는 익숙한 구조일겁니다.
가령 우리는 yml 파일을 수정함으로써 configuration을 바꿉니다. 소스 전체를 바꾸는 것이 아니라 특정 config 요소만 바꿈으로써 소스 전체에 영향을 끼치는 겁니다.
이것이 템플릿, 프레임워크의 힘의 근원이라고 할 수 있는 것이죠.

pytorch-template 도 같은 시각에서 접근해봅시다. 
config.json 만 바꿈으로써 우리는 새로운 데이터를 로딩할 수 있는 것이고 batch_size, validation_split 도 변경 할 수 가 있습니다. 
train.py 만 바꿈으로써 우리는 모델을 손쉽게 교체할 수 가 있습니다.
