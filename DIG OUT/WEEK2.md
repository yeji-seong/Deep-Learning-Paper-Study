# SRCNN (Super-resolution Convoutional Neural Network) <br><br>

기본적으로 SR문제는 ILL-posed problem이다. 따라서 LR을 복원한 고해상도 image는 여러개가 될 수 있는데 그 중에서 가장 적합한 HR image를 찾는 것이 SR 문제의 핵심이다. SRCNN은 SR(Super-resolution)을 위한 방법으로 CNN(Convoutional Neural Network)을 사용한 것이다. CNN은 단순한 구조지만 높은 복구 품질과 빠른 속도를 보여준다. <br><br>

## Patch extraction & representation <br>
저해상도 image에서 patch들을 추출하는 과정이다. 이 patch들은 특징을 가진다. <br><br>


## Non-linear mapping <br>
다차원의 patch들을 non-linear하게 다른 다차원의 patch들로 mapping한다. <br><br>

## Reconstruction <br>
다차원의 patch들을 통해 HR image를 복원시키는 과정이다. <br><br>

참고 문헌 및 이미지 출처 <br>
https://arxiv.org/pdf/1501.00092.pdf


