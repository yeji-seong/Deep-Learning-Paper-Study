# Deconvolution layer는 convolutional layer와 동일한가?
## Abstract <br>
첫째, CVPR

https://arxiv.org/abs/1609.05158논문에서 제안한 layer와 deconvolution layer의 관계는 무엇인가? 둘째, 왜 저해상도(LR) 공간에서 convolutions을 일으키는 것이 더 나은 선택일까? 이러한 질문에 대답하기 위해, transposed convolution layer, the sub-pixel convolutional layer 및 제안된 효율적인 sub-pixel convolutional layer의 형태에서 deconvolution layer 사이의 관계를 논한다. 그런 다음 LR 공간에만 convolution이 있는 네트워크는 HR 공간에서 입력을 먼저 upsampling하는 네트워크보다 같은 속도로 표현력이 더 높다는 것을 보여줄 것이다. <br><br>

## Introduction <br>

<br><br>
논문 출처 <br>
Wenzhe Shi, Jose Caballero, Lucas Theis, Ferenc Huszar, Andrew Aitken, Christian Ledig, Zehan Wang, "Is the deconvolution layer the same as a convolutional layer?", https://arxiv.org/abs/1609.07009

