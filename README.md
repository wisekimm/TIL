# TIL (Start from 2022.09.07)

### 2022.09.07

why not commit?? long time no see..

----------------

### 2022.09.14
 2022.09.14
transforms.Normalize((0.5, 0.5, 0.5), (0.5, 0.5, 0.5)) 적용
transofrms.Normalize()는 각 채널별 평균(mean)을 뺀 뒤 표준편차(std)로 나누어 정규화를 진행합니다.

transofrms.Normalize((R채널 평균, G채널 평균, B채널 평균), (R채널 표준편차, G채널 표준편차, B채널 표준편차))

로 입력하여 적용할 수 있습니다.

ex)
```python
transform = transforms.Compose([
    transforms.ToTensor(),
    transforms.Normalize((0.5, 0.5, 0.5), (0.5, 0.5, 0.5))
])
```

위의 예시와 같이 transforms.ToTensor() 후 (0.5, 0.5, 0.5), (0.5, 0.5, 0.5)로 정규화를 적용하게 되면

RGB 각 채널의 픽셀 값에서 0.5를 뺀 뒤 0.5로 나누어 정규화를 진행합니다.

즉, transforms.ToTensor()가 이미지 픽셀 값의 범위를 0 ~ 1 로 조정했으므로,

최소값(=-1)은 (0 - 0.5) / 0.5 = -1, 최대값(=1) 은 (1 - 0.5) / 0.5 = 1 로 조정됩니다.

결국, 위의 예시를 적용한 결과는 -1 ~ 1 범위로 변환됩니다.

https://teddylee777.github.io/pytorch/torchvision-transform

>Conv2d 와 관련한 참고할만한 블로그
* 테스트
https://blog.joonas.io/196?category=1016329

### 2022.09.15

Pooling : convolution으로 뽑아낸 값을 전부 가져가는 것이 아니라, 대표적인 특징만 남기는 작업
<image width = "70%" src = "https://user-images.githubusercontent.com/71629571/190331560-25a33d7e-5660-4253-8b7b-8ada64582817.gif"/>





