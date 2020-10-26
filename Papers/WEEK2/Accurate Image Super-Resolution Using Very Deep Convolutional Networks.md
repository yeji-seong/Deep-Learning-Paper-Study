# 초심층 Convolutional Networks를 이용한 정확한 Image Super-Resolution <br><br>

## Abstract <br>
이 논문에서는 매우 정확한 단일 이미지 SR 방법(VDSR)을 제시한다. 이 논문에서 소개할 모델은 네트워크 깊이를 증가시키면 정확도가 크게 향상되며, 최종 모델에서 20개의 weight layers를 사용한다. <br><br>

이 모델은 간단하지만 수렴 속도가 빠르고 효과적인 훈련 절차인 **잔여 학습**을 사용한다. 이 방법은 정확도 측면에서 기존 방법보다 성능이 좋으며, SR의 결과 또한 우수하다.
뿐만 아니라 기존 SRCNN 보다 10^4배 높은 learning rate를 사용한다.
<br><br>

## Introduction <br>
2차 보간과 같은 초기의 방법과는 달리 현재는 LR에서 HR 패치로의 mapping을 모델링하는 학습 방법이 널리 사용되고 있다. 최근에는 CNN도 생겨나고 있으며, 정확도가 크게 향상되어 사용되었다. 그 중에서 CNN은 LR에서 HR까지의 mapping을 end-to-end로 학습하는 데 사용될 수 있다. 또한 SRCNN은 좋은 성능을 보인다. <br><br>

하지만 SRCNN은 다음과 같은 단점이 있다. <br>
1. 작은 image 영역의 context에 의존한다. <br>
2. 훈련 시 수렴속도가 느리다. <br>
3. network는 단일 규모에서만 작동한다. <br>

이 연구에서는 위의 문제를 실질적으로 해결하기 위한 새로운 방법을 제시한다. <br><br>

### Context
대규모 인자의 경우 작은 patch에 포함된 정보가 detail recovery 에 충분하지 않은 경우가 많다. 따라서 우리는 매우 큰 image 영역에 퍼진 contextual 정보를 활용한다. <br><br>

### Converge
우리는 훈련 속도를 높일 수 있는 residual-learning과 높은 learning rate을 적용한다. LR image와 HR image는 동일한 정보를 공유하므로 HR image와 LR image의 차이인 residual image를 모델링하는 것이 유리하다. 또한 learning rate는 SRCNN보다 10^4배 더 높다. <br><br>

### Scale Factor
Scale은 일반적으로 사용자가 지정한다. 가능한 모든 시나리오에 대비하여 규모에 의존하는 많은 모델을 훈련하고 저장하는 것은 비현실적이다. 또한 multi-scalefactor에는 하나의 convolutional network가 충분하다. <br><br>

### Contribution
Very deep convolutional network를 기반으로 하는 매우 정확한 SR 방법을 제안한다. 기존의 Very deep convolutional network는 작은 learning rate를 사용하면 수렴 속도가 느리며, 높은 learning rate로 convergence rate을 높이면 Gradient Exploding 문제가 발생한다. 따라서 residual-learning과 gradient clipping을 도입해 문제를 해결한다. 또한, 우리는 multiscale SR 문제를 해결하기 위해 단일 네트워크로 확장한다. 
이 방법은 그림에 나타낸 것과 같이 비교적 정확하고 빠르다. <br><br>

![figure1](https://user-images.githubusercontent.com/57740560/93744042-18059100-fc2c-11ea-96b7-8c28b82477fc.png) <br><br>

[<a href = "https://github.com/yeji-seong/Deep-Learning-Paper-Study/blob/master/Papers/WEEK4/Accurate%20Image%20Super-Resolution%20Using%20Very%20Deep%20Convolutional%20Networks.md"> WEEK4</a>] <br><br>

논문 출처 <br>
Jiwon Kim, Jung Kwon Lee and Kyoung Mu Lee, Department of ECE, ASRI, Seoul National University, Korea, "Accurate Image Super-Resolution Using Very Deep Convolutional Networks", https://arxiv.org/pdf/1511.04587.pdf
