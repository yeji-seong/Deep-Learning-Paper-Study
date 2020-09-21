# Deconvolution layer는 convolutional layer와 동일한가?
[ 아직 공부 중이라 잘못된 내용이 있을 수 있습니다. 피드백은 다음 메일로 부탁드립니다. yeji7874@khu.ac.kr ] <br>
## Abstract <br>
기존의 CNN 기반의 SR 기법의 대부분은 우선 bicubic 보간법을 이용해 upsample 한후 convolutional network를 적용한다. 하지만 <a href = "https://arxiv.org/abs/1609.05158"> 논문</a>에서는 대신에 그림에 나온 것처럼 subpixel CNN에 LR을 직접 입력한다. <br>
![figure1](https://user-images.githubusercontent.com/57740560/93749143-5c952a80-fc34-11ea-8062-63b468b769a4.png) <br>
이전의 논문에 따르면 위와 같은 방법으로 HR image를 나타낼 수 있다. 이에 대하여 사람들이 많이 묻는 두 가지 질문에 대한 설명을 하려 한다. <br><br>

## Introduction <br>
첫째, 논문에서 제안한 layer와 deconvolution layer의 관계는 무엇인가? 둘째, 왜 저해상도(LR) 공간에서 convolutions을 일으키는 것이 더 나은 선택일까? 이러한 질문에 대답하기 위해, transposed convolution layer, the sub-pixel convolutional layer 및 제안된 효율적인 sub-pixel convolutional layer의 형태에서 deconvolution layer 사이의 관계를 논한다. 또한 LR 공간에만 convolution이 있는 네트워크는 HR 공간에서 입력을 먼저 upsampling하는 네트워크보다 같은 속도로 표현력이 더 높다는 것을 보인다. <br><br>
결국, deconvolution layer와 r^d channel의 결과를 갖는 convolution layer와 동일하다는 것을 보임으로써 network가 권장할 경우 하나의 HR image/ feature map을 나타내기 위해 LR image/ feature map의 r^2 channel을 사용할 수 있다. 그리고 r^2 channel을 만드는 데 사용된 것은 단순한 convolutions이며, 이전에 feature map을 만드는 데 사용된 작업과 다를 바 없다.
<br><br>
논문 출처 <br>
Wenzhe Shi, Jose Caballero, Lucas Theis, Ferenc Huszar, Andrew Aitken, Christian Ledig, Zehan Wang, "Is the deconvolution layer the same as a convolutional layer?", https://arxiv.org/abs/1609.07009

