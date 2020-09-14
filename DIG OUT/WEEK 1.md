# CNN (Convolutional Neural Network) <br><br>

CNN은 image recognition과 같은 분야에서 좋은 성능을 나타낸다. image data는 인접하는 픽셀간의 상관관계가 높기 때문에 image를 벡터화 하면 정보 손실이 발생한다. <br><br>

![figure3](https://user-images.githubusercontent.com/57740560/93093000-23603600-f6db-11ea-9025-c3bf8e7d763b.png) <br><br>
![figure8](https://user-images.githubusercontent.com/57740560/93099754-5c040d80-f6e3-11ea-9b5d-bc1b3bb99a6e.png) <br><br>
(두 image는 모두 숫자 2를 표현하고 있지만 image를 벡터화 하면 둘 사이에 연관성을 찾아보기 힘들다.)

하지만 CNN은 공간 정보를 보존하는 형태로 데이터 입력을 받기 때문에 이미지를 벡터화하는 과정에서 발생하는 정보 손실을 막을 수 있다. <br><br>


다음은 CNN 구조의 예시이다.<br><br>

![figure4](https://user-images.githubusercontent.com/57740560/93093006-25c29000-f6db-11ea-8d57-c9146a8a6495.png) <br><br><br>


## Convolution layer <br><br>

![figure2](https://user-images.githubusercontent.com/57740560/93090286-82bc4700-f6d7-11ea-8e37-9e3a95117cc4.png) <br><br>

filter는 stride 만큼 옆으로 이동하며 합성곱 연산을 통해 image의 size를 줄인다. 이때 정보를 잃어버리게 되는데, padding을 통해 image의 size가 급격히 작아지는 것을 막고, image의 boundary를 분명하게 할 수 있다. <br><br>

![figure5](https://user-images.githubusercontent.com/57740560/93094721-3f64d700-f6dd-11ea-8e7e-d3e49233d61f.png) <br><br>

CNN에서는 위의 Convolution layer를 여러 개 통과하도록 한다. 예를 들어, image를 보고 고양이인지 아닌지를 판단하는 모델을 CNN으로 구현한다고 하자. 그러면 고양이의 image가 input이미지가 될 테고, 각각의 filter는 '귀가 있는가?' '수염이 있는가?' '귀가 뾰족한가?' 등을 확인하는 역할을 할 것이다. <br><br><br>

## Pooling layer <br><br>

Pooling layer는 Convolution layer로 부터 출력 데이터를 받아 resize한다. <br><br>

![figure6](https://user-images.githubusercontent.com/57740560/93095423-0a0cb900-f6de-11ea-801f-f9704b611cae.png) <br><br>

Pooling에는 두 종류가 있는데 하나의 filter에서 가장 큰 값을 뽑아내는 Max Pooling, filter의 평균을 뽑아내는 Mean Pooling이 있다. 주로 Max Pooling을 많이 사용하는데, 그 이유는 image 중에 특징값을 나타내는 부분을 더 강조해서 볼 것이라는 의미이다. <br><br><br>

## fully connected layer <br><br>

이렇게 Convolution layer와 Pooling layer를 거치는 과정이 feature extraction이며, 이후 fully connected network에 연결한다. <br><br>
![figure7](https://user-images.githubusercontent.com/57740560/93097819-04fd3900-f6e1-11ea-88f5-455c2bafcfd9.png) <br><br>

<br><br>

참고 문헌 및 이미지 출처 <br>
모두를 위한 딥러닝, https://www.youtube.com/watchv=Em63mknbtWo&list=PLlMkM4tgfjnLSOjrEJN31gZATbcj_MpUm&index=35 <br>
https://github.com/minsuk-heo/deeplearning/blob/master/src/CNN_Tensorflow.ipynb <br>
http://cs231n.stanford.edu/ <br>
