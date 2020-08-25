23/08/2020

1. Created Github Repository
2. Shared the link
3. Figuring out how to generate data
4. Trying to generate data using https://github.com/Belval/TextRecognitionDataGenerator
5. Trying to produce variations in the generated data and figuring out what to do with the boxes around characters
6. Trying to figure out how to organize the labels for the texts that are generated
7. Still looking for boxing the characters in the data and trying to create tfrecords of a small sample 

24/08/2020

1. Resolving version conflicts for aocr model and text generator to work side by side
2. Generating training data
3. Trying to create box data and looking for alternatives
4. Generated training data(60K) and train.tfrecords file
5. Generated testing data(10K) and test.tfrecords file
6. Training the model with default hyperparameters

25/08/2020

1. So 1000 epochs set by default seems impossible as it is taking around 50 mins per epoch using gpu so stopping the training and restarting it with less number of epochs
2. Updating the github repository
3. Trained the model in around 6 hours and 30 mins(50 epochs). Final loss 0.142 and perplexity 1.04. Total steps 42713. Looks as if the model did not improve much after 30 epochs(around 26000 steps) or so as the loss was varying from 0.05 - 0.15 throughout.
4. Testing the model on custom test set generated randomly like the training set
5. Testing time = 15 min, Test Sample Size = 10k, Test Accuracy = 69.88%
6. Testing the model on given sample of 30 images -->> Accuracy = 31.70%
7. Thinking of modifying the dataset as earlier dataset has max length of string around 30 chars, the images used include colored images and also both upper case and lower case
8. Training the model again with 37 epochs instead of previous 50, reduced batch size of 60, increased steps per epoch of 1000 and most importantly the max prediction length now will be of length 15 which was 32 earlier
