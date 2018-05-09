
# Usage:
Run the following command to install the keras, flask and other dependency modules:

```bash
sudo pip install -r requirements.txt
```
To run the chatbot on browser, goto chatbot_web directory and run the following command:

```bash
python flaskr.py
```

Now navigate your browser to http://localhost:5000 and you can try out various predictors for replying.

# About
On the homepage of this chatbot, there are 6 options which depicts that it works in 6 different ways:
* Trained with Gunthercox dataset on word level using GloVe encoding
* Trained with Gunthercox dataset on word level using One-hot encoding
* Trained with Gunthercox dataset on character level
* Trained with Cornell dataset on word level using GloVe encoding
* Trained with Cornell dataset on word level using One-hot encoding
* Trained with Cornell dataset on character level 

# Code:

Code for the chatbot is divided in 2 parts:
* Machine Learning part (using keras)
* Web deployment part (using Flask)

## Machine Learning part ( chatbot_train):
     
* First subdirectory in this folder is data which have both the datasets.
    
* Second subdirectory is models, which have saved ml models for chatbot trained on both the dataset. The chatbot is built based on seq2seq models, and can infer based on either character-level or word-level. The seq2seq model is implemented using LSTM encoder-decoder on Keras. During runtime, these models are used to reply.

* And the last subdirectory is  very_large_data which would have gloVe file(if your system doesn’t have gloVe file then it will be downloaded automatically when running the chatbot).

* Other files present in the folder are for training(optional) the existing models again. if you like to tune the parameters of the seq2seq and retrain the models, you can use the following command to run the training:

```bash
cd chatbot_train
python cornell_char_seq2seq_train.py
```
The above commands will train seq2seq model using cornell dialogs on the character-level and store the trained model in "chatbot_train/models/cornell/char-**".  Similarly, other models can be trained.

## Web deployment part( chatbot_web):

* Static contains css file

* Templates contain various HTML files for rendering

* flaskr.py is for running the chatbot on localhost. All the conversations with various models are stored in lists here, and next conversations are further appended to store the chat. These lists are cleared after restarting the chatbot. 

* Other files are for predicting the reply using various chatbot trained models.




    






