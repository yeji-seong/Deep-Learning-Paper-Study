# Deconvolution layer는 convolutional layer와 동일한가? <br><br>

[<a href = "https://github.com/yeji-seong/Deep-Learning-Paper-Study/blob/master/Papers/WEEK2/Is%20the%20deconvolution%20layer%20the%20same%20as%20a%20convolutional%20layer%3F.md"> WEEK2</a>] <br><br>

## Summary <br>
### Section 1: Transposed convolution and sub-pixel convolutional layers <br><br>
![figure1](https://user-images.githubusercontent.com/57740560/94166027-d1cb5e80-fec5-11ea-9b36-c48538e5f23c.png) <br>
그림에서 회색 영역으로 표시된 x는 0 패딩을 의미한다. f에서의 회색 영역은 곱으로 0이 된 영역이다. 따라서 화살표 방향에 따라 size가 8인 x는 size가 4인 filter(stride = 2)에 의해 size 5인 y로 downsampling 된다. <br><br>

![figure2](https://user-images.githubusercontent.com/57740560/94163300-a3984f80-fec2-11ea-82fc-4648a13c1cc2.png) <br>
다음은 upsampling 과정이다. (a) The transposed convolution은 중간에 나오는 행렬이 Figure 2의 전치 꼴이기 때문에 붙여진 이름이다. Transposed convolution의 경우 y의 회색 영역이 잘리지만, (b) sub-pixel layers에서는 원래의 픽셀 사이에 sub-pixel을 채워진다. 이 두 방법의 차이는 x가 y로 변환될 때 사용하는 weight가 다르다는 것이다. (a)에서는 x의 두 번째 픽셀은 weight가 차례로 [1 2 3 4]가 적용되는 반면, (b)에서는 [4 3 2 1]이 적용된다. 따라서 만약 filter의 요소를 뒤집으면 두 계층이 같아질 것이다. <br><br>

### Section 2: Deconvolution layer vs Convolution in LR <br>

### Section 3: What does this mean? <br>




논문 출처 <br>
Wenzhe Shi, Jose Caballero, Lucas Theis, Ferenc Huszar, Andrew Aitken, Christian Ledig, Zehan Wang, "Is the deconvolution layer the same as a convolutional layer?", https://arxiv.org/abs/1609.07009





