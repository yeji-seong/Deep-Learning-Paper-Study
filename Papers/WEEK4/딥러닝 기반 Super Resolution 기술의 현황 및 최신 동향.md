# 딥러닝 기반 Super Resolution 기술의 현황 및 최신 동향 <br>

## 요약 <br>
![figure1](https://user-images.githubusercontent.com/57740560/95460757-503cfb80-09b0-11eb-8024-7fb542a20892.png) <br>
기존의 SR 기법은 HR 이미지를 복원하는 과정에서 디테일한 부분의 화질 저하가 존재했다. 이러한 문제 해결을 위해 최근에는 딥러닝 기반의 SR 알고리즘에 대한 연구가 이루어지고 있다. 
본 논문에서는 이러한 연구의 최신 기술 현황 및 동향을 소개한다. 
우선 딥러닝 기반 SR 알고리즘 중 대표적인 네트워크를 분석하고, 여러 데이터 셋을 통해 네트워크의 성능을 확인한다. <br><br>

## 딥러닝 기반의 초해상화 알고리즘 기술 현황 및 동향 <br>
![figure2](https://user-images.githubusercontent.com/57740560/95460762-50d59200-09b0-11eb-87ce-c1287c7c7fed.png) <br>
기존의 SR 방법들은 복잡하고 비선형적인 모델을 구현하기 어려웠다. 따라서 최근 딥러닝 기반의 초해상화 알고리즘, 그 중에서도 CNN을 통한 연구가 다양하게 진행중이다. <br>
처음으로 딥러닝을 도입한 네트워크는 **Super Resolution Convolutional Neural Network(SRCNN)** 이다. 바이큐빅 보간법을 적용해 업스케일링 된 이미지는 CNN 네트워크를 통과하며 Patch Extraction, Nonlinear Mapping, Reconstruction의 과정을 거치게 된다. <br><br>

SRCNN 이후 LR 영상을 바이큐빅 보간법을 사용해 업스케일링 하지 않고 바로 네트워크에 넣는 **FSRCNN**이 나왔다. 기존 SRCNN에서 사용했던 방법대로 입력 LR 영상을 HR의 해상도로 업스케일링 시켜 연산을 하면 속도와 메모리 측면에서 비효율적이라는 사실에 기반해 해당 네트워크에서는 영상의 해상도를 높이기 위해 Deconvolution layer를 사용하였다. 그 결과 FSRCNN은 파라미터의 수가 감소하고 연산 속도가 빨라졌으며 성능 또한 향상했다. <br><br>

![figure3](https://user-images.githubusercontent.com/57740560/95460763-516e2880-09b0-11eb-9ebb-8748e993a802.png)<br>
이후, ResNet에서 영감을 얻어 Residual learning을 이용해 깊은 네트워크를 효율적으로 학습할 수 있는 **VDSR** 이 등장했다. 일반적으로 깊은 네트워크를 설계하면 Backpropagation 과정에서 Gradient Vanishing, Gradient Exploding 등의 문제가 발생한다. 따라서 네트워크의 깊이가 네트워크의 성능을 보장하는 것은 아니었다. 이러한 문제를 해결하기 위해 제안된것이 VDSR이다. VDSR에서는 Residual learning을 통해 LR 영상을 최종 출력 HR 영상에 더해주고 두 영상의 차이를 학습한다. 이렇게 하면 그 차이 값은 매우 작기 때문에 Gradient Vanishing, Gradient Exploding 문제를 해결할 수 있다. VDSR은 SRCNN과 마찬가지로 바이큐빅 보간법으로 업스케일링 된 입력 LR 영상과 출력 HR 영상을 사용해 학습한다. 이렇게 하면 깊은 네트워크에서도 최적화가 가능하다. <br><br>

![figure4](https://user-images.githubusercontent.com/57740560/95460765-5206bf00-09b0-11eb-8789-9e44bf2cca0a.png) <br>
VDSR 등장 이후, Residual learning을 이용해 매우 깊고 넓은 네트워크인 **EDSR**이 등장했고 높은 성능을 보였다. EDSR은 Residual learning 뿐만 아니라 네트워크를 안정적으로 학습하기 위해  네트워크를 Residual Block 별로 나누고 Skip Connection으로 연결해 파라미터의 최적화를 개선했으며, Multi layer를 추가해 feature map의 분산이 커져 학습이 잘 안되는 문제를 해결했다. 또한 Pixel Shuffle을 통해 원하는 해상도의 HR 영상을 복원했다. <br><br>





## 네트워크 결과 성능 비교 <br>




Reference <br>
서유림, 강석주, "딥러닝 기반 Super Resolution 기술의 현황 및 최신 동향", http://www.kibme.org/resources/journal/20200504094149078.pdf
