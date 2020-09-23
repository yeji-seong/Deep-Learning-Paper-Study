# 초심층 Convolutional Networks를 이용한 정확한 Image Super-Resolution <br><br>

[ 아직 공부 중이라 잘못된 내용이 있을 수 있습니다. 다음 메일로 피드백 부탁드립니다. yeji7874@khu.ac.kr ]  <br><br>

## Abstract <br>
이 논문에서는 매우 정확한 단일 이미지 SR 방법(VDSR)을 제시한다. 네트워크 깊이를 증가시키면 정확도가 크게 향상된다는 사실에 의거해 우리는 최종 모델에서 20개의 weight layers를 사용한다.
deep network structure에서 여러 번 작은 filter를 계단식으로 배치하여 큰 이미지 영역에 걸친 정보를 효율적으로 얻는다. <br>
그러나, deep network는 training에서 수렴 속도가 중요한 문제가 된다. 이 논문에서는 간단하지만 효과적인 훈련 절차를 제안한다. 잔차만 학습하고 매우 높은 learning rate를 사용한다. 
이 방법은 정확도에서 기존 방법보다 성능이 우수하며, SR의 결과는 시각적으로 눈에 띄게 향상한다. <br><br>

## Introduction <br>
초기의 방법에는 2차 보간과 같은 보간법과 statisitical image 이전 또는 내부 patch recurrence를 활용하는 재샘플링 방법을 포함한다. 현재는 LR에서 HR 패치로의 mapping을 모델링하는 학습 방법이 널리 사용되고 있다. 최근에는 random forest와 CNN도 생겨나고 있으며, 정확도가 크게 향상되어 사용되었다. 그 중에서 CNN은 LR에서 HR까지의 mapping을 end-to-end로 학습하는 데 사용될 수 있다. 또한 SRCNN은 다른 방법에 필요한 어떤 engineer 기능도 필요하지 않으며, 좋은 성능을 보여준다. <br><br>

하지만 SRCNN은 다음과 같은 단점이 있다. <br>
1. 작은 image 영역의 context에 의존한다. <br>
2. 훈련시 수렴속도가 느리다. <br>
3. network는 단일 규모에서만 작동한다. <br>
이 연구에서는 위의 문제를 실질적으로 해결하기 위한 새로운 방법을 제시한다. <br><br>

### Context
대규모 인자의 경우 작은 patch에 포함된 정보가 detail recovery 에 충분하지 않은 경우가 많다. 우리는 매우 큰 image 영역에 퍼진 contextual 정보를 활용한다. <br><br>

### Converge
우리는 훈련 속도를 높일 수 있는 residual-learning CNN과 높은 learning rate을 적용한다. LR image와 HR image는 동일한 정보를 공유하므로 HR image와 LR image의 차이인 residual image를 명시적으로 모델링하는 것이 유리하다. 게다가, 우리의 초기 learning rate는 SRCNN보다 10^4배 더 높다. <br><br>

### Scale Factor
Scale은 일반적으로 사용자가 지정한다. 가능한 모든 시나리오에 대비하여 규모에 의존하는 많은 모델을 훈련하고 저장하는 것은 비현실적이며, multi=scalefactor에는 하나의 convolutional network가 충분하다는 것을 알게 되었다. <br><br>

### Contribution
Very deep convolutional network를 기반으로 하는 매우 정확한 SR 방법을 제안한다. Very deep convolutional network는 작은 learning rate를 사용하면 너무 느리게 수렴된다. 높은 learning rate로 convergence rate을 높이면 그라데이션이 폭발적으로 증가하며, 우리는 residual-learning과 gradient clipping으로 문제를 해결한다. 또한, 우리는 multiscale SR 문제에 대처하기 위해 단일 네트워크로 확장한다. 
이 방법은 그림에 나타낸 것과 같이 비교적 정확하고 빠르다. <br><br>

![figure1](https://user-images.githubusercontent.com/57740560/93744042-18059100-fc2c-11ea-96b7-8c28b82477fc.png) <br><br>

논문 출처 <br>
Jiwon Kim, Jung Kwon Lee and Kyoung Mu Lee, Department of ECE, ASRI, Seoul National University, Korea, "Accurate Image Super-Resolution Using Very Deep Convolutional Networks", https://arxiv.org/pdf/1511.04587.pdf