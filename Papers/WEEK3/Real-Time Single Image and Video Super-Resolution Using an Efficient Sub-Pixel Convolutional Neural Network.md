# Sub-Pixel Convolutional Neural Network을 이용한 실시간 단일 이미지 및 영상 SR <br><br>

## Abstract <br>
이 논문에서 소개하는 방법은 reconstruction 이전에, LR 입력 이미지를 단일 필터로 스케일업한다. <br>
이러한 방법으로 CNN은 단일 K2 GPU에서 1080p 비디오 실시간 SR이 가능하다. <br>
논문에서 제안된 새로운 CNN은 LR 공간에서 feature maps을 추출하고 efficient sub-pixel convolution layer를 도입한다. <br>
따라서 각 feature map에 훈련된 복잡한 필터를 가진 기존 SR 파이프라인을 대체하고 SR 작업의 계산량을 줄일 수 있다. <br><br>

## Introduction <br>
SR 기법의 가정이 되는 주요 가정은 고주파 데이터의 많은 부분이 중복되므로 저주파 구성 요소에서 정확하게 재구성할 수 있다는 것이다. <br>
기존의 방법들은 계산이 복잡한 이미지 처리와 융합 단계를 거쳐야하지만, 제안된 방법은 단일 LR에서 누락된 HR 정보를 복구하기 위해 자연 데이터에 존재하는 implicit redundancy를 학습하고자 한다. <br><br>

논문 출처 <br>
Wenzhe Shi, Jose Caballero, Ferenc Huszár, Johannes Totz, Andrew P. Aitken, Rob Bishop, Daniel Rueckert, Zehan Wang, "Real-Time Single Image and Video Super-Resolution Using an Efficient Sub-Pixel Convolutional Neural Network", https://arxiv.org/abs/1609.05158
