# Convolutional Neural Network의 개념적 이해 - Deep Learning 접근 <br><br>

[ 아직 공부 중이라 잘못된 내용이 있을 수 있습니다. 피드백은 언제나 환영입니다. yeji7874@khu.ac.kr ] <br><br>

## Abstract <br>
CNN(Convolutional Neural Network)은 복잡한 문제를 해결하는 데 널리 사용되는 deep learning 접근법이다. 
이 연구의 동기는 CNN의 다양한 측면의 지식과 이해를 주기 위함이다. 
본 연구는 CNN의 3가지 가장 일반적인 아키텍처 및 학습 알고리즘과 함께 CNN에 대한 개념적 이해를 제공한다. <br><br>

## Introduction <br>
feature extraction이 필요한 머신러닝에 반해 딥러닝 기법은 feature extraction이 필요하지 않고, 당면한 문제에 대해 중요한 기능을 자동으로 추출한다.
딥러닝 모델은 다양한 특성을 학습할 수 있는 여러 layer들로 구성되어 있어 구별되는 features를 학습할 수 있다. <br>
딥러닝 아키텍처로는 deep belief networks, recurrent neural networks, convolution neural networks 등이 있다.
그 중, CNN은 deep feed-forward 구조를 가지고 있으며, fully connected layers에 비해 일반화 하는데 더 뛰어나다.
CNN의 detectors는 매우 추상적인 특징들을 배울 수 있으며, 효율적으로 사물을 식별할 수 있다. <br>
CNN이 다른 모델들보다 우선시되는 이유는 다음과 같다. 
첫째, CNN을 적용하기 위한 주요 관심사는 weight를 공유하는 것이다. 
따라서 훈련을 필요로 하는 매개변수가 감소하여 일반화가 개선되며, 매개 변수가 적어 훈련이 수월하고 overfitting의 위험도 없다.
둘째, 분류 단계는 특징 추출 단계와 통합되어 있으며, 둘 다 학습 과정을 이용한다. 
셋째, 인공신경망(ANN) 모델을 사용해 대규모 네트워크 구현하는 것보다 CNN에서 구현하는 것이 훨씬 쉽다. <br>
이 연구의 동기는 CNN에 대한 지식과 이해를 더하면서 이론적 틀을 확립하는 것이다. 
본 연구의 목적은 CNN의 기본 원칙의 융합을 제시하고, 일반 모델, 3가지 가장 일반적인 아키텍처 및 학습 알고리즘에 대한 세부사항을 제공하는 것이다. <br><br>

논문 출처 <br>
Sakshi Indolia, Anil Kumar Goswami, S. P. Mishra, Pooja Asopa (2018), "Conceptual Understanding of Convolutional Neural Network- A Deep Learning Approach" <br><br>


