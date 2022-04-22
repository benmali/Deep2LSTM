## Deep Learning NLP LSTM task

### Python version
 - This project can run on python 3.6, 3.7 or 3.8. Greater Python versions are not supported
 
#### Python packages required
- please run `pip install -r requirements.txt`


#### About the task

In this exercise we have implemented an LSTM NN Model that will predict
whether a review that was posted in IMDB is a positive review or a negative review.

The input of the model were user reviews on IMDB that went through different embedding models (Word2Vec and Glove).
The models were trained specifcally for this task (we have not used a pre-trained model).

We have also decided to filter out the reviews taken from the dataset, to include only those with a rating number, so we can be sure they are either positive or negative (and weren't in the dataset by accident).

Along the task we have decided to explore different architechtures of the embedding models and of the LSTM model, 
by investigating hyperparameters such as window size (the distance between two words algo should consider to find some relationship between them)
,vector size (number of elements in each word's vector representation), learning rate, batch size and number of epochs.

Overall, we have trained 4 models - 2 LSTM models using different W2V models (different hyperparameters) and 2 LSTM models using different Glove models (different hyperparameters).

The LSTM models were identical to the LSTM model we have learned about in lectures and recitations, with a classification head added to the model (using a fully connected linear layer and a sigmoid activation function).

In the training process, we had to split the data into train and validation sets, and have encountered memory and time limitations. 

Therefore, we have decided to lower the number of reviews taken for training and testing the model.
We have also trained the model using 1 batch at a time, with a low amount of epochs (5 for each model).

Thus, the results should be considered under these circumstances.
We have tested the model's training loss using Binary Cross Entropy loss, the model's training accuracy and the model's validation accuracy, for each model of the 4 we had implemented.

We have also tested out the quality of the embedding models using "most_similar" function on a known movie character.

The accuracy was determined using a 0.5 threshold (a naive threshold).

The LSTM models based on W2V embeddings have produced higher results than the LSTM models based on Glove embeddings, and were not high overall (around 50-60 % Accuracy for the validation set).

For further exploration and confirmation of the models' abilities, we suggest
using more train data and using a higher amount of epochs, alongside a more broad random search (especially by changing the window size and vector size of the embedding model, and learning rate of the optimizer) may result in better performence.

Moreover, using AUC as another metric can result in a better understanding of the adequate threshold for the classification.