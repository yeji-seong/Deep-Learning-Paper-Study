# 초심층 Convolutional Networks를 이용한 정확한 Image Super-Resolution <br>
[ 아직 공부 중이라 잘못된 내용이 있을 수 있습니다. 피드백은 다음 메일로 부탁드립니다. yeji7874@khu.ac.kr ] <br><br>

## Abstract <br>
이 논문에서는 매우 정확한 단일 이미지 SR 방법(VDSR)을 제시한다. 네트워크 깊이를 증가시키면 정확도가 크게 향상된다는 사실에 의거해 우리는 최종 모델에서 20개의 weight layers를 사용한다.
deep network structure에서 여러 번 작은 filter를 계단식으로 배치하여 큰 이미지 영역에 걸친 정보를 효율적으로 얻는다. <br>
그러나, deep network는 training에서 수렴 속도가 중요한 문제가 된다. 이 논문에서는 간단하지만 효과적인 훈련 절차를 제안한다. 잔차만 학습하고 매우 높은 learning rate를 사용한다. 
이 방법은 정확도에서 기존 방법보다 성능이 우수하며, SR의 결과는 시각적으로 눈에 띄게 향상한다. <br><br>

## Introduction <br>
초기의 방법에는 2차 보간과 같은 보간법과 statisitical image 이전 또는 내부 patch recurrence를 활용하는 재샘플링 방법을 포함한다. 현재는 LR에서 HR 패치로의 mapping을 모델링하는 학습 방법이 널리 사용되고 있다. 최근에는 random forest와 CNN도 생겨나고 있으며, 정확도가 크게 향상되어 사용되었다. 그 중에서 CNN은 LR에서 HR까지의 mapping을 end-to-end로 학습하는 데 사용될 수 있다. 또한 SRCNN은 다른 방법에 필요한 어떤 engineer 기능도 필요하지 않으며, 좋은 성능을 보여준다. <br><br>
![figure1](https://user-images.githubusercontent.com/57740560/93742400-02db3300-fc29-11ea-9a4e-9feeb9b18d3f.png) <br>
하지만 SRCNN은 다음과 같은 단점이 있다. <br>
1. 작은 image 영역의 context에 의존한다. <br>
2. 훈련시 수렴속도가 느리다. <br>
3. network는 단일 규모에서만 작동한다. <br>
이 연구에서는 위의 문제를 실질적으로 해결하기 위한 새로운 방법을 제시한다. <br><br>









논문 출처 <br>
Jiwon Kim, Jung Kwon Lee and Kyoung Mu Lee, Department of ECE, ASRI, Seoul National University, Korea, "Accurate Image Super-Resolution Using Very Deep Convolutional Networks", https://arxiv.org/pdf/1511.04587.pdf
