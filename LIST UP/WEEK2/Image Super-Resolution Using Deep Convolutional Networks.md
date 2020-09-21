# Deep Convolutional Networks를 이용한 이미지 Super-Resolution <br><br>

[ 아직 공부 중이라 잘못된 내용이 있을 수 있습니다. 다음 메일로 피드백 부탁드립니다. yeji7874@khu.ac.kr ] <br><br>

[<a href = "https://github.com/yeji-seong/Deep-Learning-Paper-Study/blob/master/LIST%20UP/WEEK1/Image%20Super-Resolution%20Using%20Deep%20Convolutional%20Networks.md"> WEEK1</a>] <br><br>

## Summary <br>

단일 LR image를 bicubic 보간법을 이용해 원하는 크기로 스케일업한다. 보간된 LR image를 Y라고 하면, 우리의 목표는 Y를 복구해 HR image인 X와 가능한 한 유사한 F(Y)를 찾는 것이다. 우리는 다음의 세 가지 작업으로 mapping F를 찾고자 한다. <br>
1. Patch extraction and representation : 이 작업은 LR image Y에서 patch를 추출하며 각 patch를 고차원 벡터로 나타낸다. 이 벡터는 일련의 feature map으로 구성된다. <br>
2. Non-linear mapping : 이 작업은 각 고차원 벡터를 다른 고차원 벡터에 비선형적으로 mapping한다. 각각의 mapping된 벡터는 개념적으로 고해상도 patch를 나타낸다. 이 벡터는 다른 feature map 집합을 구성한다. <br>
3. Reconstruction : 이 작업은 최종 HR image를 생성하기 위해 위의 고해상도 patch 표현을 모은다. 이 image는 X와 유사할 것으로 예상된다. <br>
우리는 이 작업이 Convolutional neural network을 형성한다는 것을 보일 것이다. network의 개요는 아래 그림에 설명되어 있다. <br><br>

![figure1](https://user-images.githubusercontent.com/57740560/93770740-93306c80-fc57-11ea-988d-5e2eadd5e2b5.png) <br><br>

SRCNN에 대해 더 공부한 내용을 <a href = "https://github.com/yeji-seong/Deep-Learning-Paper-Study/blob/master/DIG%20OUT/WEEK%201.md"> KEYWORD</a>에 정리했습니다. <br><br>

논문 출처 <br>
Chao Dong, Chen Change Loy, Member, IEEE, Kaiming He, Member, IEEE, and Xiaoou Tang, Fellow, IEEE (2015). "Image Super-Resolution Using Deep Convolutional Networks", https://arxiv.org/pdf/1501.00092.pdf.
