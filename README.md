# Rock_scissors_paper_classifier

### Dataset from https://laurencemoroney.com/datasets.html

### Rock Paper Scissors Dataset
---

rps directory structure
* paper 840 
* rock 840
* scissors 840 images(png)

rps-test-set
* paper 124
* rock 124
* scissors 124 images(png)

### Original img size  
300 X 300
  
  
### Input shape  
28 X 28 X 4  
  
  
### Dataset is normalized by x/255.0  
  
  
### Model structure
![image](https://user-images.githubusercontent.com/53106649/148017906-ff720575-828e-4a5b-8c2e-935857c1b580.png)


### Model Hyperparameter
optimizer = adam  
loss = sparse_categorical_crossentropy  
epoch=7  


### accuracy
train : 0.9992  
test : 0.8922  
