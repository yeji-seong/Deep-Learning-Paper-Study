# ESCPN (Efficient Sub-Pixel Convolutional Neural Network) <br><br>

![figure1](https://user-images.githubusercontent.com/57740560/93749143-5c952a80-fc34-11ea-8062-63b468b769a4.png) <br>
ESCPN은 기존의 <a href = "https://github.com/yeji-seong/Deep-Learning-Paper-Study/blob/master/Keyword/WEEK2.md"> SRCNN</a>에 sub-pixel layer를 적용시켜 image upscale(확대)을 마지막 layer에서 함으로써 메모리, 속도 측면에서 효율을 높였다. 기존의 SRCNN이 LR image를 upscale 한 후 feature map 추출 및 non=linear mapping, reconstruction 했다면 ESPCN에서는 LR image에서 feature map을 추출한 뒤, 이를 shuffling해 HR image를 구현한다. <br><br><br>




일반적으로 Transposed Convolution 와 Deconvolution을 혼동하는 경우가 많다. 둘은 모두 Convolution에서 사용한 Input 이미지 크기의 Output을 출력하지만, 서로 다른 연산이다. 차이점은 아래와 같다. <br><br>
![figure3](https://user-images.githubusercontent.com/57740560/95059132-75710600-0733-11eb-9f0f-10bf396d2f1d.png) <br>

## Deconvolutional layer <br><br>
Deconvolution은 Convolution을 거꾸로 수행하는 것이다. Output 이미지와 filter를 사용해 Input 이미지를 얻어내기 위한 역연산을 한다. <br><br>

## Transposed convolutional layer <br><br>
Transposed Convolution은 Input 이미지 크기의 이미지를 얻기 위해 Convolution 과정을 그대로 수행한다. 따라서, Transposed Convolution의 Output은 Convolution의 Input과 크기는 같지만 그 값은 다를 수 있다. <br><br>

예를 들어, (1, 5 ,5) Input image를 (1, 3, 3) filter를 stride 2로 움직여 (1, 2, 2) feature map을 얻었다 (Convolution). 이를 되돌리기 위해서는 (1, 2, 2) feature map의 각 픽셀마다 9개의 값을 추출한 뒤  stride 2로 움직여 (1, 5, 5) 크기의 이미지를 얻어낸다 (Deconvolution). <br><br>
![figure1](https://user-images.githubusercontent.com/57740560/95058303-4c03aa80-0732-11eb-867d-cc22b10d0086.gif) <br><br>

반면, Transposed convolution의 경우 (1, 2, 2)이미지를 upsampling하여(zero padding) (1, 7, 7) size로 만든 뒤 (1, 3, 3) filter를 stride 1로 움직여 (1, 5, 5) image를 얻어낸다(Transposed Convolution). <br><br>
![figure1](https://user-images.githubusercontent.com/57740560/95059782-53c44e80-0734-11eb-8331-7aba1eaeb89a.gif) <br><br>

## Sub-pixel convolutional layer <br><br>






참고 문헌 및 이미지 출처 <br>
https://arxiv.org/abs/1609.05158 <br>
https://arxiv.org/abs/1609.07009 <br>
https://blog.naver.com/9709193/221974662268 <br>
https://towardsdatascience.com/what-is-transposed-convolutional-layer-40e5e6e31c11 <br>


