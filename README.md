# Credit-card-fraud-detection-using-autoencoders

## Introduction
Anomaly detection is the process of finding abnormalities in data. Abnormal data is defined as the ones that deviate significantly from the general behavior of the data. AutoEncoder is an unsupervised Artificial Neural Network that attempts to encode the data by compressing it into the lower dimensions (bottleneck layer) and then decoding the data to reconstruct the original input. The bottleneck layer holds the compressed representation of the input data. The number of hidden units in the code is called code size. 
AutoEncoders are widely used in anomaly detection. The reconstruction errors are used as the anomaly scores. 
 
## About the problem and methodology
The dataset contains credit card transaction data containing around 280,000 rows with normalized values of 28 features along with the transaction amount and whether it is fraud or not. We are trying to predict whether a certain transaction is fraud or not, hence it is a binary classification problem. To implement the autoencoder, I created two stacks - one encoder stack which will compress the data into lower dimensions followed by the decoder stack which will reconstruct the data to the original form. We check the reconstruction error
#
Method 1: Using reconstruction error and autoencoders    
  
I have used encoder + decoder stack on normal transactions so that model captures high level features of normal transaction and the reconstruction error threshold is noted. Then while testing on normal + fraudulant transactions, if the error is above this threshold, that means that transaction will be fraudulant.  
  
Precision: [Normal: 0.99956679  ||  Recall: 0.02429585]  
Recall: [Normal: 0.94679641  ||  Recall: 0.76351351]    
  #  
Method 2: Using encoder part of autoencoder and KNN algorithm   

Here, I used the aencoder part of model to first convert the high dimensional data into lower dimensional data. Then I trained KNN algorithm on these lower level features along with 1/0 as target features. By keeping neighbours size = 3, I predicted the target variable.  
  
Precision: [Normal: 0.99955465  ||  Fraudulant 0.94827586]  
Recall: [Normal: 0.99992966  ||  Fraudulant: 0.74324324]  
