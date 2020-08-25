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
2. Updating the github repository with information on work done till now and how to do
