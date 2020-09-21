# Deep Convolutional Networks를 이용한 이미지 Super-Resolution <br><br>

[ 아직 공부 중이라 잘못된 내용이 있을 수 있습니다. 다음 메일로 피드백 부탁드립니다. yeji7874@khu.ac.kr ] <br><br>

## Abstract <br>
단일 이미지 Super-Resolution를 위한 딥러닝 방법으로 저해상도/고해상도 이미지 사이의 end to end mapping을 직접 학습하는 모델을 제안한다. mapping은 저해상도 영상을 입력으로 받아 고해상도 영상을 출력하는 깊은 경련 신경망(CNN)으로 표현된다. 각 구성요소를 별도로 취급하는 기존의 방법과 달리, 우리의 방법은 모든 층을 공동으로 최적화한다. Deep CNN은 단순한 구조지만 높은 복구 품질을 보여주며 속도 또한 빠르다. 성능과 속도 사이의 절충을 달성하기 위해 서로 다른 네트워크 구조와 매개변수 설정을 탐색한다. <br><br>

## Introduction <br>
우리는 저해상도 영상과 고해상도 영상 사이의 end-to-end을 직접 학습하는 CNN에 대하여 다룰 것이다. 이 방법은 패치 공간을 모델링하기 위해 명시적으로 학습하지 않는다는 점에서 기존의 example-based approaches와 근본적으로 다르다. 학습은 hidden layers를 통해 달성되며, 패치 추출 및 집계는 convolutional layers로 공식화되어 최적화에 관여한다. <br><br>

SRCNN의 특징은 다음과 같다. <br>
첫 번째로, SRCNN은 단순한 구조이며 높은 정확성을 가진다. <br><br>
![Figure1](https://user-images.githubusercontent.com/57740560/93069093-36154380-f6b8-11ea-81fb-fd70e7c22a13.png) <br>
두 번째로, 적당한 수의 필터와 레이어를 사용하여 CPU에서도 실제 온라인 사용을 위한 빠른 속도를 달성한다. <br>
세 번째로, 실험 결과 더 크고 다양한 데이터셋을 사용하거나 더 크고 deep한 모델을 사용할 경우 복구 품질이 더 향상될 수 있음을 알 수 있다. <br>
더욱이, 제안된 네트워크는 3개의 컬러 영상 채널을 동시에 처리할 수 있어 향상된 초고해상도 성능을 달성할 수 있다. <br><br>

전반적으로 본 연구의 기여도는 주로 세 가지 측면에 있다. <br>
1) 우리는 이미지 SR을 위한 완전한 CNN을 제시한다. <br>
2) 딥러닝 기반 SR method와 기존의 SR method 사이에 관계를 설립한다. <br>
3) 딥러닝이 SR 문제에 유용하며, 좋은 품질과 속도를 얻을 수 있다는 것을 증명한다. <br><br>

<a href = "https://github.com/yeji-seong/Deep-Learning-Paper-Study/blob/master/LIST%20UP/WEEK2/Image%20Super-Resolution%20Using%20Deep%20Convolutional%20Networks.md"> WEEK2</a> 에서 계속 <br><br>

논문 출처 <br>
Chao Dong, Chen Change Loy, Member, IEEE, Kaiming He, Member, IEEE, and Xiaoou Tang, Fellow, IEEE (2015). "Image Super-Resolution Using Deep Convolutional Networks", https://arxiv.org/pdf/1501.00092.pdf.
