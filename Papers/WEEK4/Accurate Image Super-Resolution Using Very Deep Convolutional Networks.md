# 초심층 Convolutional Networks를 이용한 정확한 Image Super-Resolution

[<a href = "https://github.com/yeji-seong/Deep-Learning-Paper-Study/blob/master/Papers/WEEK2/Accurate%20Image%20Super-Resolution%20Using%20Very%20Deep%20Convolutional%20Networks.md"> WEEK2</a>] <br><br>

## 기존의 SRCNN 문제점과 이를 보완한 VDSR
기존의 SRCNN의 문제점은 다음과 같다. <br><br>

Layer가 3개이기 때문에 좁은 context 밖에 반영하지 못 한다. <br>
학습 시 수렴 속도가 느리다. <br> 
Single scale에 대해서만 동작한다. <br><br>

이러한 문제점을 보완하기 위해 VDSR에서는 <br>
20개의 3 x 3 Convolutional layer로 field를 확장해 반영할 수 있는 region context 를 확장했다. <br>
SRCNN에서 사용한 Learning rate의 10^4배의 Learning rate를 적용하여 학습 속도를 높였다. <br>
Single convolutional network이 multi-scale factor SR에 사용될 수 있음을 보였다. <br><br><br>


## 제안된 네트워크
이 모델에서는 d 개의 layer를 사용한다. 여기서 첫 번째 layer와 마지막 layer는 filter가 3x3x64로 같은 타입이며, 64개의 채널을 걸쳐 3x3 영역에 작용한다. <br><br>

![figure1](https://user-images.githubusercontent.com/57740560/97185797-d7c59f80-17e3-11eb-8d79-6e0e5198b69a.png) <br><br><br>

중심 픽셀을 복원하기 위해서는 주변 픽셀의 정보가 중요하다. 하지만 테두리 영역의 경우 이러한 관계를 완전히 이용하기 어렵기 때문에 많은 SR 방법에서는 이미지를 자른다.
만약 잘라내야 할 영역이 너무 커진다면 남은 이미지의 크기가 너무 작아지기 때문에 이 방법은 유효하지 않다.
이 모델에서는 Zero padding을 통해 이러한 문제를 해결한다. Zero padding 을 한 이미지의 SR 결과는 이미지의 경계도 뚜렷하게 예측할 수 있다. <br><br><br>


## 학습
이 모델에서는 학습을 위해 mean squared error인 1/2 * ||y − f(x)||^2 을 최소화한다. <br><br>

### Residual-Learning


### High Learning Rates for Very Deep Networks
### Adjustable Gradient Clipping
### Multi-Scale
