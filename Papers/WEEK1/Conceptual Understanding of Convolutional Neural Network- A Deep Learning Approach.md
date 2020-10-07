# Convolutional Neural Network의 개념적 이해 - Deep Learning 접근 <br><br>

## Abstract <br>
**CNN(Convolutional Neural Network)** 은 복잡한 문제를 해결하는 데 널리 사용되는 deep learning 접근법이다. 
이 연구의 동기는 CNN의 다양한 측면의 지식과 이해를 주기 위함이다. 
본 연구는 CNN의 3가지 가장 일반적인 아키텍처 및 학습 알고리즘과 함께 CNN에 대한 개념적 이해를 제공한다. <br><br>

## Introduction <br>
딥러닝 모델은 다양한 특성을 학습할 수 있는 여러 layer들로 구성되어 있어 구별되는 features를 학습할 수 있다. <br>
딥러닝 아키텍처로는 deep belief networks, recurrent neural networks, convolution neural networks 등이 있다.
그 중, CNN은 deep feed-forward 구조를 가지고 있으며, fully connected layers에 비해 일반화 하는데 더 뛰어나다.
CNN의 detectors는 추상적인 특징들을 배울 수 있으며, 사물 식별에 효율적이다. <br><br>

CNN의 장점은 다음과 같다. <br>
첫째, CNN의 주요 관심사는 weight이기 때문에 훈련을 필요로 하는 매개변수가 감소하여 훈련이 수월하고 overfitting의 위험도 없다.
둘째, 분류 단계는 특징 추출 단계와 통합되어 있으며, 둘 다 학습 과정을 이용한다. 
셋째, 인공신경망(ANN) 모델을 사용해 대규모 네트워크 구현하는 것보다 CNN에서 구현하는 것이 훨씬 쉽다. <br><br>

이 연구의 동기는 CNN에 대한 지식과 이해를 더하면서 이론적 틀을 확립하는 것이다. 
본 연구의 목적은 CNN의 기본 원칙의 융합을 제시하고, 일반 모델, 3가지 가장 일반적인 아키텍처 및 학습 알고리즘에 대한 세부사항을 제공하는 것이다. <br><br>

## Summary <br>
### General Model <br>
**CNN의 General Model : F(X, W) = Y** <br>
W는 인접한 두 층의 뉴런 사이의 상호연결 강도를 나타내는 weight 벡터를 의미한다. 일반적인 CNN 모델은 **convolution layer, pooling layer, activation function, fully connected layer** 이렇게 네개의 요소로 구성되어 있다. <br><br>
![figure1](https://user-images.githubusercontent.com/57740560/93219569-75ba5900-f7a6-11ea-9840-e2a543a8ad35.png) <br><br>

#### Convolution Layer <br>
분류할 이미지는 입력 layer에 제공되며 출력은 이미지에서 추출한 features을 사용하여 계산한 class label의 예측치이다. weight vector(or filter, kernel)는 옆으로 이동하며 입력 이미지의 feature map을 생성한다. filter는 옆으로 이동하며 convolution 연산을 하는데 이를 통해 단일 layer에서 N개의 features maps이 추출된다. 출력값은 다음과 같이 표현된다. <br><br>
![figure2](https://user-images.githubusercontent.com/57740560/93222083-7ef8f500-f7a9-11ea-90cc-e56c00d83b44.png) <br><br>
여기서, X는 layer로 받은 입력값, W는 input 위로 이동하는 filter, b는 bias, * 는 convolution 연산, σ는 network에서 비선형성을 의미한다. <br><br>

#### Pooling Layer <br>
Pooling 기술의 주요 장점은 training 가능한 매개변수의 수를 줄일 수 있다는 것이다. <br><br>
![figure3](https://user-images.githubusercontent.com/57740560/93225004-b4eba880-f7ac-11ea-83f5-2988fddc8a34.png) <br>
Pooling function은 출력값으로 다른 벡터를 만든다. 대표적인 Pooling 기술에는 **average pooling, max-pooling**이 있다. <br><br>

#### Fully Connected Layer <br>
반복적으로 Convolution Layer와 Pooling Layer를 거친 1단계 출력값은 Fully Connected Layer로 넘어가 최종 출력값을 얻기 위해 weight vector와 input vector의 dot product를 계산한다.
**Gradient descent**는 전체 학습 데이터셋에 대한 cost를 추정해 cost function을 줄이고 한번의 epoch후 파라미터를 업데이트한다. 이 방법은 minima를 산출하지만, 데이터의 크기가 클 경우 상당한 시간이 소요된다. 따라서 Gradient descent는 **Stochastic gradient descent**로 대체되었다. <br><br>

#### Activation Function <br>
ReLU은 partial derivative 계산이 간단하고, 비포화상태인 비선형성인 ReLU가 포화상태인 비선형성 sigmoid보다 training 시간이 짧다. 또한 ReLU에서는 gradients가 사라지지 않기 때문에 비선형성을 도입할 때 **sigmoid activation function**보다 **Rectified Linear Unit (ReLU)** 를 사용한다. 그러나 네트워크를 통해 큰 gradient가 흐를 때 ReLU의 효율성이 저하되고 weight의 업데이트가 뉴런을 활성화하지 못하게 하여 Dieing ReLU 문제로 이어지게 된다. 이 문제는 Leaky ReLU를 사용하여 해결할 수 있으며, x>0일 경우 f(x)=x로, x<0일 경우 αx로 활성화된다. (α는 작은 상수) <br><br>
<br>

### Architectures of Convolution Neural Network <br>
#### LeNet Architecture <br>
![figure4](https://user-images.githubusercontent.com/57740560/93228532-8bcd1700-f7b0-11ea-8853-8445460ea160.png) <br><br>

#### AlexNet Architecture <br>
![figure5](https://user-images.githubusercontent.com/57740560/93228536-8cfe4400-f7b0-11ea-8f4a-a27548bb5579.png) <br><br>

#### GoogleNet Architecture <br>
GoogleNet Architecture는 적은 매개 변수로 이미지 속의 물체를 보다 정밀하게 인식할 수 있는 network를 구축하는 것을 목표로 했다. 이는 네트워크의 크기를 증가시킴으로써 layer의 수를 증가시켜 달성할 수 있지만, 네트워크 크기를 증가시키면 training 할 매개변수의 수를 증가시켜 overfitting 문제를 야기한다. filter 수를 늘리면 연산량도 증가해 overhead 증가로 이어지는 것도 큰 단점이다. <br><br>

### Learning Algorithm <br>
**Learning Algorithm**은 weight, bias 등과 같이 다양한 학습 가능한 파라미터에 따라 loss function을 최소화함으로써 network에 유익하다. 주로 Learning Algorithm은 두 가지 범주로 나눌 수 있다. <br>
The First Order Optimization에는 Jacobian 행렬로 대표되는 gradient 연산이 포함되며, 널리 사용되는 기법은 **Gradient Descent**이다. <br>
반면 Second Order Optimization에는 Hessian Matrix로 대표되는 second order derivative 모델이 포함된다. 그러한 기술 중 하나는 **Adam Optimization**이다. <br><br>

#### Gradient Descent <br>
![figure7](https://user-images.githubusercontent.com/57740560/93242238-744a5a00-f7c1-11ea-9192-e632380cbbf7.png) <br><br>

#### Adaptive Moment Estimation (ADAM) Optimization <br>
![figure8](https://user-images.githubusercontent.com/57740560/93244294-782bab80-f7c4-11ea-93b8-a69ff796646c.png) <br><br>

CNN에 대해 더 공부한 내용을 <a href = "https://github.com/yeji-seong/Deep-Learning-Paper-Study/blob/master/DIG%20OUT/WEEK%201.md"> KEYWORD</a>에 정리했습니다. <br><br>

논문 출처 <br>
Sakshi Indolia, Anil Kumar Goswami, S. P. Mishra, Pooja Asopa (2018), "Conceptual Understanding of Convolutional Neural Network- A Deep Learning Approach" <br><br>


