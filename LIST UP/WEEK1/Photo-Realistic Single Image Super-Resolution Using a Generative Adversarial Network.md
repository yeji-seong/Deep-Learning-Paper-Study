# GAN을 이용한 단일 이미지 초고해상도 복원 <br><br>

[ 아직 공부 중이라 잘못된 내용이 있을 수 있습니다. 피드백은 다음 메일로 부탁드립니다. yeji7874@khu.ac.kr ]<br><br>

## Abstract <br>
현재 SR이 해결해야 할 문제는 대규모의 업스케일링에서 미세한 질감 디테일을 어떻게 복원할 것인가이다. 최근의 연구들은 MSE를 최소화하는데에 초점을 두고 있다. 결과 추정치는 피크 신호 대 잡음 비율이 높지만 고주파 세부 정보가 부족한 경우가 많으며 고해상도에서 기대하는 정확도에 미치지 못한다. <br>
이 논문에서는 super-resolution(SR)을 위한 generative adversarial network(GAN)인 SRGAN을 소개할 것이다. SRGAN에서는 adversarial loss와 a content loss로 구성된 loss function을 제안한다. adversarial losss는 discriminator network를 통해 초해상 이미지와 원본 이미지를 비슷하게 만든다. 또한 content loss는 픽셀 공간에서의 유사성보다는 지각적 유사성을 추구한다. MOS를 측정한 결과 SRGAN을 사용했을때 기존의 방식들보다 원래의 초해상 이미지와 근접한 이미지를 생성했다. <br><br>

## Introduction <br>
저해상도(LR)에서 고해상도(HR) 이미지를 추정하는 어려운 작업을 초해상도(SR)이라고 한다. 결정되지 않은 SR 문제는 재구성된 SR의 텍스처 디테일이 일반적으로 가지지 않는 높은 업스케일 인자에서 두드러진다. supervised SR 알고리즘의 최적화 목표는 일반적으로 복구된 HR 영상과 원본 사이의 평균 제곱 오차(MSE)를 최소화하는 것이다. MSE를 최소화하는 것은 대 신호 대 잡음 비(PSNR)를 최대화하기 때문에 편리하지만, 이는 픽셀별 이미지 차이를 기반으로 정의되기 때문에 매우 제한적이다. 본 연구에서는 super-resolution generative adversarial network (SRGAN)을 제안하며, 여기에는 MSE와는 분리하여 스킵-연결을 포함한 ResNet를 채택하고 유일한 최적화 대상으로 한다. 또한, 이전 연구와는 달리 우리는 VGG 네트워크의 high-level feature maps과 HR 이미지와 구별이 어려운 이미지를 장려하는 discriminator를 결합하여 새로운 perceptual loss을 정의한다. <br><br>
 
논문 출처 <br>
LEDLG, Christian, et al. (2016). "Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network" arXiv preprint arXiv : 1609.04802, http://arxiv.org/abs/1609. 04802).
