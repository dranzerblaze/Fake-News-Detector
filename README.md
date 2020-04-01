# Fake-News-Detector
Predicting whether a news is reliable or not using LSTM &amp; Gated Recurrent Unit (GRU) Network.


Dataset Link :- https://www.kaggle.com/c/fake-news/data

For vectorizing words & sentences, GloVe pre-trained vectors were used.

LSTM Model Summary :-

Layer (type)                 Output Shape              Param #   
=================================================================
embedding_1 (Embedding)      (None, 1000, 100)         25187700  
_________________________________________________________________
dropout_2 (Dropout)          (None, 1000, 100)         0         
_________________________________________________________________
conv1d_3 (Conv1D)            (None, 1000, 32)          16032     
_________________________________________________________________
max_pooling1d_3 (MaxPooling1 (None, 500, 32)           0         
_________________________________________________________________
conv1d_4 (Conv1D)            (None, 500, 64)           6208      
_________________________________________________________________
max_pooling1d_4 (MaxPooling1 (None, 250, 64)           0         
_________________________________________________________________
lstm_2 (LSTM)                (None, 100)               66000     
_________________________________________________________________
batch_normalization_2 (Batch (None, 100)               400       
_________________________________________________________________
dense_5 (Dense)              (None, 256)               25856     
_________________________________________________________________
dense_6 (Dense)              (None, 128)               32896     
_________________________________________________________________
dense_7 (Dense)              (None, 64)                8256      
_________________________________________________________________
dense_8 (Dense)              (None, 2)                 130       
=================================================================

Batch Size :- 300
Epochs : 1
Accuracy acheived :- 72.12 % 

GRU Network Summary :-
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
embedding_1 (Embedding)      (None, 1000, 100)         25187700  
_________________________________________________________________
gru_2 (GRU)                  (None, 100)               60300     
_________________________________________________________________
batch_normalization_4 (Batch (None, 100)               400       
_________________________________________________________________
dense_10 (Dense)             (None, 2)                 202       
=================================================================

Batch Size :- 300
Epochs : 1
Accuracy acheived :- 75.74 % 


Result :- The GRU Network performs better than the LSTM Network significantly in just 1 Epoch. If we increase the number of epochs, we can see drastic changes in both accuracies.
