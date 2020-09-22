# SRCNN (Super-resolution Convoutional Neural Network) <br><br>

기본적으로 SR문제는 ILL-posed problem이다. 따라서 LR을 복원한 고해상도 image는 여러개가 될 수 있는데 그 중에서 가장 적합한 HR image를 찾는 것이 SR 문제의 핵심이다. SRCNN은 SR(Super-resolution)을 위한 방법으로 CNN(Convoutional Neural Network)을 사용한 것이다. CNN은 단순한 구조지만 높은 복구 품질과 빠른 속도를 보여준다. <br><br>

## End-to-end mapping
SRCNN은 end-to-end mapping을 통해 학습한다. End-to-end 딥러닝은 학습시스템에서 거쳐야할 여러 단계의 과정을 하나의 network로 구성해 한번에 처리하는 것을 말한다. <br><br>
[기존의 파이프라인] <br>
![figure5](https://user-images.githubusercontent.com/57740560/93844550-725c2b80-fcd8-11ea-8f0a-cf333586b5a7.png) <br><br>

[End-to-end] <br>
![figure6](https://user-images.githubusercontent.com/57740560/93844551-738d5880-fcd8-11ea-92c6-d63266e55bfa.png) <br><br>

End-to-end learning의 장단점을 정리하면 다음과 같다. <br>
End-to-end learning의 경우에는 직접 설계한 파이프라인보다 중간 과정이 생략됨으로써 단순화될 수 있다.
하지만, End-to-end 방식은 데이터의 정보에만 의존해서 과정을 진행하기 때문에 학습 데이터가 적을 경우 직접 설계된 파이프라인 구조보다 더 안좋게 동작할 수 있다. <br><br><br>


다음은 SRCNN의 구조이다.<br>
![figure1](https://user-images.githubusercontent.com/57740560/93842837-10e58e00-fcd3-11ea-9d7c-454c96f68720.png) <br>

## Patch extraction & representation <br>
저해상도 image에서 patch들을 추출하는 과정이다. 이 patch들은 특징을 가진다. 첫 번째 layer는 다음과 같이 연산 F1으로 표현된다. <br><br>
![figure2](https://user-images.githubusercontent.com/57740560/93842841-1216bb00-fcd3-11ea-990e-f1a9db9eefde.png) <br><br>
여기서 W1과 B1은 각각 filters와 biases를 의미하며, * 는 convolutional 연산이다. network의 최적화에는 이러한 bases의 최적화가 포함된다. W1은 c×f1×f1의 n1 필터에 해당한다. 여기서 c는 입력 image의 채널 수, f1은 filter의 공간 크기다. 이후 filter의 결과에 ReLU 함수를 적용한다. <br><br>

## Non-linear mapping <br>
첫 번째 layer에서 각각의 patch에서 n1 차원의 feature을 추출했다면, 두 번째 layer에서는 n1 차원의 벡터들을 non-linear하게 n2 차원의 벡터들로 mapping한다. 두 번째 layer의 연산은 다음과 같이 표현된다. <br><br>
![figure3](https://user-images.githubusercontent.com/57740560/93842833-104cf780-fcd3-11ea-8379-7839ee336350.png) <br><br>
W2은 n1×f2×f2의 n2 filters에 해당하며, B2는 n2 차원이다. 각각의 n2 차원의 벡터는 HR patch를 의미한다. <br><br>

## Reconstruction <br>
다차원의 patch들을 통해 HR image를 복원시키는 과정이다. HR image를 생성하는 layer는 다음과 같이 정의할 수 있다. <br><br>
![figure4](https://user-images.githubusercontent.com/57740560/93842844-13e07e80-fcd3-11ea-9e70-76065e580f62.png)  <br><br>
W3은 n2×f3×f3의 c filters에 해당하며, B3는 c 차원이다. <br><br>

세 가지 연산은 다른 직관에 의해 공식화되었지만, 모두 convolutional layer라는 동일한 형태로 이어진다. 이 세 가지 연산은 모두 합쳐져 convolutional layer를 만든다. 이 모델에서 weight와 biases는 최적화된다. <br><br>


<br><br>
참고 문헌 및 이미지 출처 <br>
https://arxiv.org/pdf/1501.00092.pdf <br>
https://www.edwith.org/deeplearningai3/lecture/34893/ <br>


