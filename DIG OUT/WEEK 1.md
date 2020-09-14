# CNN (Convolutional Neural Network) <br><br>
CNN은 image recognition과 같은 분야에서 좋은 성능을 나타낸다. image data는 인접하는 픽셀간의 상관관계가 높기 때문에 이미지를 벡터화 하면 정보 손실이 발생한다. <br><br>
![figure3](https://user-images.githubusercontent.com/57740560/93093000-23603600-f6db-11ea-9025-c3bf8e7d763b.png) <br><br>
하지만 CNN은 공간 정보를 보존하는 형태로 데이터 입력을 받기 때문에 이미지를 벡터화하는 과정에서 발생하는 정보 손실을 막을 수 있다. <br><br>

## convolution layer <br><br>

![figure2](https://user-images.githubusercontent.com/57740560/93090286-82bc4700-f6d7-11ea-8e37-9e3a95117cc4.png) <br><br>

filter는 stride 만큼 옆으로 이동하며 합성곱 연산을 통해 image의 size를 줄인다. 이때 정보를 잃어버리게 되는데, padding을 통해 image의 size가 급격히 작아지는 것을 막고, image의 boundary를 분명하게 할 수 있다.



## pooling layer <br>
## fully connected layer <br>



<br><br>
# SRCNN (Super-resolution Convoutional Neural Network) <br>
## Patch extraction & representation

## Non-linear mapping


## Reconstruction <br>


이미지 출처
https://github.com/minsuk-heo/deeplearning/blob/master/src/CNN_Tensorflow.ipynb
http://cs231n.stanford.edu/
