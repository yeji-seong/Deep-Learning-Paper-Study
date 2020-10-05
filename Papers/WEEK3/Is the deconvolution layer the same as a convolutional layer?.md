# Deconvolution layer는 convolutional layer와 동일한가? <br><br>

[<a href = "https://github.com/yeji-seong/Deep-Learning-Paper-Study/blob/master/Papers/WEEK2/Is%20the%20deconvolution%20layer%20the%20same%20as%20a%20convolutional%20layer%3F.md"> WEEK2</a>] <br><br>

## Summary <br>
### Section 1: Transposed convolution and sub-pixel convolutional layers <br><br>
![figure1](https://user-images.githubusercontent.com/57740560/94166027-d1cb5e80-fec5-11ea-9b36-c48538e5f23c.png) <br>
그림에서 회색 영역으로 표시된 x는 0 패딩을 의미한다. f에서의 회색 영역은 곱으로 0이 된 영역이다. 따라서 화살표 방향에 따라 size가 8인 x는 size가 4인 filter(stride = 2)에 의해 size 5인 y로 downsampling 된다. <br><br>

![figure2](https://user-images.githubusercontent.com/57740560/94163300-a3984f80-fec2-11ea-82fc-4648a13c1cc2.png) <br>
다음은 upsampling 과정이다. (a) Transposed convolution는 y의 회색 영역이 잘린다. (b) sub-pixel layers에서는 원래의 픽셀 사이에 sub-pixel을 채워진다. 이 두 방법의 차이는 x가 y로 변환될 때 사용하는 filter(weight)가 다르다는 것이다. (a)에서는 x의 두 번째 픽셀은 weight가 차례로 [1 2 3 4]가 적용되는 반면, (b)에서는 [4 3 2 1]이 적용된다. 따라서 filter의 요소를 뒤집으면 두 layer가 같아진다. <br><br>

### Section 2: Deconvolution layer vs Convolution in LR <br>
kernel size가 (o* r^2 , i, k, k)인 convolutional layer가 kernal size가 (o, i, k * r , k * r)인 deconvolutional layer와 같다는 것을 보일 것이다. <br><br>

![figure1](https://user-images.githubusercontent.com/57740560/95039326-637b6d00-070b-11eb-8991-d0742114b743.png) <br>
Step1. LR image에 값이 0인 sub-pixel을 만든다. <br><br>

![figure2](https://user-images.githubusercontent.com/57740560/95039328-64140380-070b-11eb-914d-fb633e74e7fe.png) <br>
Step2. Step2. sub-pixel space에서 (1, 1, 4, 4)인 kernel과 합성곱 연산을 한다. <br><br>

![figure3](https://user-images.githubusercontent.com/57740560/95039329-64ac9a00-070b-11eb-940f-22fdd38bd7fa.png) <br>
합성곱 연산의 결과 첫 번째 픽셀 값은 보라색, 두 번째 픽셀 값은 파란색... 이 된다. <br><br>

![figure1](https://user-images.githubusercontent.com/57740560/95039999-5a8b9b00-070d-11eb-9c50-9ade63da4775.png) <br>
(1, 1, 4, 4) kernel을 (4, 1, 2, 2) kernel은 same dimension이기 때문에 서로 전환할 수 있기 때문에, 앞선 convolution의 결과는 (1, 1, 4, 4) kernel을 (4, 1, 2, 2)로 나누어 합성곱 연산을 해준 뒤, shuffling 한 것과 같다. <br><br>

![figure2](https://user-images.githubusercontent.com/57740560/95040001-5bbcc800-070d-11eb-9343-65d79d09aa41.png) <br><br>

### Section 3: What does this mean? <br><br>
결론적으로 deconvolutional layer는 데이터의 차원이 d인 r^d 채널 출력을 가진 LR의 convolution과 동일하다. 따라서 하나의 HR image/ feature map을 나타내기 위해 LR image/ feature map의 r^2 채널을 사용하는 방법을 배울 수 있다는 것을 의미한다. 
그리고 r^2 채널을 만드는 데 사용되는 연산은 단순한 convolution일 뿐, 그 이전에 n_l-1 feature map을 만드는 데 사용한 연산과 다를 바 없다. <br><br>

논문 출처 <br>
Wenzhe Shi, Jose Caballero, Lucas Theis, Ferenc Huszar, Andrew Aitken, Christian Ledig, Zehan Wang, "Is the deconvolution layer the same as a convolutional layer?", https://arxiv.org/abs/1609.07009





