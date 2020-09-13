# GAN을 이용한 단일 이미지 초고해상도 복원 <br>
## Abstract <br>
현재 SR이 해결해야 할 문제는 대규모의 업스케일링에서 미세한 질감 디테일을 어떻게 복원할 것인가이다. 최근의 연구들은 MSE를 최소화하는데에 초점을 두고 있다. 결과 추정치는 피크 신호 대 잡음 비율이 높지만 고주파 세부 정보가 부족한 경우가 많으며 고해상도에서 기대하는 정확도에 미치지 못한다. <br>
이 논문에서는 super-resolution(SR)을 위한 generative adversarial network(GAN)인 SRGAN을 소개할 것이다. SRGAN에서는 adversarial loss와 a content loss로 구성된 loss function을 제안한다. adversarial losss는 discriminator network를 통해 초해상 이미지와 원본 이미지를 비슷하게 만든다. 또한 content loss는 픽셀 공간에서의 유사성보다는 지각적 유사성을 추구한다. MOS를 측정한 결과 SRGAN을 사용했을때 기존의 방식들보다 원래의 초해상 이미지와 근접한 이미지를 생성했다. <br>

## Introduction


논문 출처 <br>
LEDLG, Christian, et al. (2016). "Photo-Realistic Single Image Super-Resolution Using a Generative Adversarial Network" arXiv preprint arXiv : 1609.04802, http://arxiv.org/abs/1609. 04802).
