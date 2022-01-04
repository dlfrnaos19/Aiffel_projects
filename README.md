# Rock_scissors_paper_classifier

### Dataset from https://laurencemoroney.com/datasets.html

### Rock Paper Scissors Dataset
---
### 데이터셋을 선택한 이유
LMS 예제에서는 본인이 직접 가위 바위 보 데이터셋을 만들어서 해보는 것으로 나왔지만
데이터의 품질과 양의 따라서 딥러닝의 효과가 극대화되기 때문에 공인(?)된 데이터셋을
사용해서 classification task를 해보고 싶었고, 검색 결과 해당 데이터셋이 존재하였음
처음에는 실습겸 tensorflow dataset 라이브러리를 활용하여 도전해보고자 했으나
tensorflow의 데이터셋 구조에 익숙하지 않아 사실상 클론코딩에 불과하다는 생각이 들어서
LMS에 나와있는 데이터 전처리 방식을 따라하기 위해 홈페이지에서 손으로 다운로드 받은 후
코랩 환경에 업로드함  
  
  
rps directory structure
* paper 840 
* rock 840
* scissors 840 images(png)

rps-test-set
* paper 124
* rock 124
* scissors 124 images(png)

### 데이터셋 전처리 중 발생한 일

LMS의 예제를 보고 따라하던 중 에러가 발생함
에러메세지는 이미지 파일을 (28,28,3)으로 바꾸는 과정에서 일어났는데
데이터셋의 차원은 (28,28,4)였음
따라서 기존의 LMS코드에서 차원에 해당하는 코드를 수정하여 문제해결.  


데이터셋을 전처리 하는 과정에서 rock 파일 중 하나가 읽어지지 않아서 에러가 발생함...
직접 열어봐도 열리지 않는 파일이라 손상된 것으로 보고 삭제함
데이터가 많았기 때문에 특별히 인식률에 문제는 없었음

### Original img size  
300 X 300  
  
### Input shape  
28 X 28 X 4  
  
데이터셋의 차원이 (28 x 28 x 4)로 맞춰졌기 때문에 입력층의 Input shape를 조정
  
### Dataset is normalized by x/255.0  

데이터셋의 정규화  
  
  
### Model structure
![image](https://user-images.githubusercontent.com/53106649/148017906-ff720575-828e-4a5b-8c2e-935857c1b580.png)

  
  from tensorflow.keras.utils import plot_model
  plot_model(model, to_file='model.png')
  plot_model(model, to_file='model_shapes.png', show_shapes=True)

해당 코드를 통해서 모델 구조를 그림으로 깔끔하게 볼 수 있다

### Model Hyperparameter
optimizer = adam  
loss = sparse_categorical_crossentropy  
epoch=7  

주로 에포크만 3~10까지 올렸는데
최고값은 에포크 7 에서 볼 수 있었음
이외에 입력단과 출력단의 dense를 랜덤하게 손봤지만 더 이상의 좋은 경과는 없었음  
(dense는 최대 256까지 테스트)

### accuracy
_train : 0.9992_  
_test : 0.8922_  

60% 이상의 정확도가 목표였기 때문에 목표는 달성했지만 해당 코드 대부분은 LMS의 예제코드를 따온 것으로
전처리 과정에 필요한 라이브러리들의 활용을 좀 더 자유롭게 할 필요가 있었음  
폴더에서 파일을 읽어오는 과정이나, 넘파이에 데이터셋 차원에 해당 데이터의 인덱스와 데이터를 넣는 것은
개념적으로는 이해가 되지만 판다스에 데이터를 넣는 것과는 또 다른 것이어서 좀 더 익숙해질 필요가 있었음  

glob, Image 라이브러리에 대한 공부예정

