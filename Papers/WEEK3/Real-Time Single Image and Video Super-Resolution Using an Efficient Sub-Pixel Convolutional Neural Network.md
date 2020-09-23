# Sub-Pixel Convolutional Neural Network을 이용한 실시간 단일 이미지 및 영상 SR <br><br>

## Abstract <br>
이 논문에서 소개하는 방법은 reconstruction 이전에, LR 입력 이미지를 단일 필터로 스케일업한다. 즉 SR은 HR 공간에서 진행한다. 이러한 방법으로 CNN은 단일 K2 GPU에서 1080p 비디오 실시간 SR이 가능하다.
논문에서 제안된 새로운 CNN은 LR 공간에서 feature maps을 추출하고 efficient sub-pixel convolution layer를 도입한다. 따라서 각 feature map에 훈련된 복잡한 필터를 가진 기존 SR 파이프라인을 대체하고
SR 작업의 계산량을 줄일 수 있다. <br><br>
