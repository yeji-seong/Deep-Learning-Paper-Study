# Deep Convolutional Networks를 이용한 이미지 Super-Resolution <br><br>

## Abstract <br>
단일 이미지 Super-Resolution를 위한 딥러닝 방법으로 저해상도/고해상도 이미지 사이의 end to end mapping을 직접 학습하는 모델을 제안한다. mapping은 저해상도 영상을 입력으로 받아 고해상도 영상을 출력하는 깊은 경련 신경망(CNN)으로 표현된다. 각 구성요소를 별도로 취급하는 기존의 방법과 달리, 우리의 방법은 모든 층을 공동으로 최적화한다. Deep CNN은 단순한 구조지만 높은 복구 품질을 보여주며 속도 또한 빠르다. 성능과 속도 사이의 절충을 달성하기 위해 서로 다른 네트워크 구조와 매개변수 설정을 탐색한다. <br><br>

## Introduction <br>
우리는 저해상도 영상과 고해상도 영상 사이의 end-to-end을 직접 학습하는 CNN에 대하여 다룰 것이다. 이 방법은 패치 공간을 모델링하기 위해 명시적으로 학습하지 않는다는 점에서 기존의 example-based approaches와 근본적으로 다르다. 학습은 hidden layers를 통해 달성되며, 패치 추출 및 집계는 convolutional layers로 공식화되어 최적화에 관여한다. <br>
SRCNN의 특징은 다음과 같다. 첫 번째로, SRCNN은 단순한 구조이며 높은 정확성을 가진다. <br>
![Figure1](https://user-images.githubusercontent.com/57740560/93069093-36154380-f6b8-11ea-81fb-fd70e7c22a13.png) <br>
![Figure2](https://user-images.githubusercontent.com/57740560/93069391-90ae9f80-f6b8-11ea-9bfd-ab03e6fa3f56.png) <br>



논문 출처<br>
Chao Dong, Chen Change Loy, Member, IEEE, Kaiming He, Member, IEEE, and Xiaoou Tang, Fellow, IEEE (2015). "Image Super-Resolution Using Deep Convolutional Networks", https://arxiv.org/pdf/1501.00092.pdf.
