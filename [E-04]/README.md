# Exploration 4 a Cool Lyricist
## World coolest Lyricist ever

Data size(sentence): 187088  
Data Split  
Train = 124981, 14    
Test = 31246, 14  

Deep Learning Framework: Tensorflow

Tokenizer: tf.keras.preprocessing.text.Tokenizer  
num_words=28000  
filters=' '  
oov_token="< unk >"  
  
batch_size = 256  
vocab_size = 28001  

### Model Structure    
---
Embedding  
lstm  
lstm  
dense  
---
Total params: 22,607,961  
Trainable params: 22,607,961  
Non-trainable params: 0

### Model Hyperparameter
embedding_size = 256  
hidden_size = 2048
epoch = 10
```
start_lyric="""<start> man in the mirror"""
generate_text(model, tokenizer, init_sentence=start_lyric, max_len=20)  
```
```
#result
'<start> man in the mirror , let me see you dance <end> '