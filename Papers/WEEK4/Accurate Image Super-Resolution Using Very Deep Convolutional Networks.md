# 초심층 Convolutional Networks를 이용한 정확한 Image Super-Resolution

[<a href = "https://github.com/yeji-seong/Deep-Learning-Paper-Study/blob/master/Papers/WEEK2/Accurate%20Image%20Super-Resolution%20Using%20Very%20Deep%20Convolutional%20Networks.md"> WEEK2</a>] <br><br>

## 기존의 SRCNN 문제점과 이를 보완한 VDSR
기존의 SRCNN의 문제점은 다음과 같다. <br>
1. Layer가 3개이기 때문에 좁은 context 밖에 반영하지 못 한다. <br>
2. 학습 시 수렴 속도가 느리다. <br> 
3. Single scale에 대해서만 동작한다. <br><br>

이러한 문제점을 보완하기 위해 VDSR에서는 <br>
1. 20개의 3 x 3 Convolutional layer로 field를 확장해 반영할 수 있는 region context 를 확장했다. <br>
2. SRCNN에서 사용한 Learning rate의 10^4배의 Learning rate를 적용하여 학습 속도를 높였다. <br>
3. Single convolutional network이 multi-scale factor SR에 사용될 수 있음을 보였다. <br><br><br>


## 제안된 네트워크
이 모델에서는 d 개의 layer를 사용한다. 여기서 첫 번째 layer와 마지막 layer는 filter가 3x3x64로 같은 타입이며, 64개의 채널을 걸쳐 3x3 영역에 작용한다. <br><br>

![figure1](https://user-images.githubusercontent.com/57740560/97185797-d7c59f80-17e3-11eb-8d79-6e0e5198b69a.png) <br><br><br>

중심 픽셀을 복원하기 위해서는 주변 픽셀의 정보가 중요하다. 하지만 테두리 영역의 경우 이러한 관계를 완전히 이용하기 어렵기 때문에 많은 SR 방법에서는 이미지를 자른다.
만약 잘라내야 할 영역이 너무 크다면 남은 이미지의 크기가 너무 작아지기 때문에 이 방법은 유효하지 않다. <br>
이 모델에서는 Zero padding을 통해 이러한 문제를 해결한다. Zero padding 을 한 이미지의 SR 결과는 이미지의 경계도 뚜렷하게 예측할 수 있다. <br><br><br>


## 학습
이 모델에서는 학습을 위해 mean squared error인 1/2 * ||y − f(x)||^2 을 최소화한다. <br><br>

### Residual-Learning
기존의 SRCNN은 모든 input detail을 유지해야했기 때문에 long-term 메모리가 필요하고, vanishing/exploding gradients 문제가 중요했다. 이 모델에서는 Residual-Learning 을 통해서 이러한 문제를 해결한다. <br>
input image 와 output image 가 매우 유사하기 때문에 이 둘의 차이 이미지를 r = y - x 와 같이 정의한다. 이렇게 하면 대부분의 값은 0이거나 매우 작을 것이다. 이후 loss function을 1/2 * ||y − f(x)||^2 로 하여 예측값 f(x)를 구한다. 이 모델의 loss function은 세 가지 input을 갖는다: residual image, ILR image, (ground truth) HR image. loss는 재구성된 이미지와 사실 값 사이의 유클리드 거리가 된다. 학습은 back propagation 방법으로 mini-batch gradient descent를 통해 회귀를 최적화한다. <br><br>

### High Learning Rates for Very Deep Networks
SRCNN은 3개 이상의 weight layer에서 우수한 성능을 보이지 않는다. 그 이유 중 하나가 network가 수렴하기 전에 training을 멈추기 때문이다. SRCNN에서 사용하는 learning rate 10^(-5)는 network가 일반적인 GPU에서 수렴하기에 너무 작다. <br>
단순히 learning rate를 높이면 gradient vanishing/exploding 문제가 발생할 수 있다. 따라서 이 모델에서는 training 속도를 최대화 시킬 수 있는 적절한 gradient clipping을 소개한다. <br><br>

### Adjustable Gradient Clipping
위와 같은 문제를 해결하는 일반적인 방법은 gradient를 [-θ, θ] 범위에 속하도록 먼저 정의하는 것이다. 이렇게 하면 training에 사용되는 stochastic gradient descent는 learning rate에 곱해져 크기를 조정한다. 즉 빠른 수렴을 위해서 gradient를 [-θ/r, θ/r]에 클리핑한다. (r은 learning rate) <br><br>

### Multi-Scale
깊은 모델은 성능을 향상시킬 수 있지만, network를 정의하기 위해 더 많은 parameter를 필요로 한다. 따라서 네트워크를 저장하고 검색하기에 경제적인 방법인 multi-scale model을 제안한다. <br>
multi-scale model은 몇 가지 특정 규모에 대한 training dataset은 하나의 큰 dataset으로 결합된다. multi-scale model은 MatConvNet1 패키지를 사용하여 모델을 구현한다. <br><br>

