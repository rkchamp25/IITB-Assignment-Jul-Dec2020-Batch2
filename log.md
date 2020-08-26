23/08/2020


1. Created Github Repository
2. Shared the link
3. Installing some prerequisites and using anaconda instead of plain python.
4. Figuring out how to generate data
5. Tried the first two links -> Synth text and text renderer. Feel that text renderer is more suitable than the other one. Going to try the third link as well.
6. Trying to generate data using https://github.com/Belval/TextRecognitionDataGenerator
7. Third one has already a lot of built in options commpared to the text renderer and has the option of using all threads of cpu for the image generation process making it a lot faster. Therefore going to use this generator.
8. Trying to produce variations in the generated data and figuring out what to do with the boxes around characters
9. Trying to figure out how to organize the labels for the texts that are generated
10. Still looking for boxing the characters in the data and trying to create tfrecords of a small sample 


24/08/2020


1. Resolving version conflicts for aocr model and text generator to work side by side. Uninstalled tensorflow 2.1 and installed tensorflow 1.15. Rest remain unchanged.
2. Adding more fonts, backgrounds etc to the data generator and changing the default height and width options of the image.
3. Generating training data while maintaining an annotations file containing the location and label of each image.
4. Generated training data(60K) and train.tfrecords file. Time taken for creating train.tfrecords = 5 mins.
4. Generated testing data(10K) and test.tfrecords file. Time taken for creating test.tfrecords = 1 min.
5. Training the model with default hyperparameters i.e epochs 1000, initial learning rate is 1.0 but since learning rate is adaptive so it doesn't matter much, batch size = 65, using full ascii mode as data contains lowercase as well aas somtimes spaces are also there.


25/08/2020


1. So 1000 epochs set by default seems impossible as it is taking around 50 mins per epoch even when using gpu so stopping the training and restarting it with less number of epochs.
2. Updating the github repository.
3. Trained the model in around 6 hours and 30 mins(50 epochs). Final loss 0.142 and perplexity 1.04. Total steps 42713. Looks as if the model did not improve much after 30 epochs(around 26000 steps) or so as the loss was varying from 0.05 - 0.15 throughout.
4. Testing the model on custom test set generated randomly like the training set
5. Testing time = 15 min, Test Sample Size = 10k, Test Accuracy = 69.88%
6. Testing the model on given sample of 30 images -->> Accuracy = 31.70%
7. Thinking of modifying the dataset as earlier dataset has max length of string around 30 chars, the images used include colored images and also both upper case and lower case
8. Training the model again with 37 epochs instead of previous 50, reduced batch size of 60, increased steps per epoch of 1000 and most importantly the max prediction length now will be of length 15 which was 32 earlier


26/08/2020


1. The model is still training. Increased number of epochs by 10 as the loss was still decreasing (although slowly) when the training stopped at 37 epochs so increased it further to 47. This may be due to the modification in the dataset as the previous set had much more vaariation than required. Also earlier each step was around 0.5 s and now it is around 0.8 s due to the fact that now the max image width has been set to 650 pixels compared to previous width of 300 pixels.
2. Finished training in 12 hrs and 40 min. Final loss is around 0.06 and perplexity is 1.06. The 9 more epochs helped reduce the loss a little bit. 
3. The loss plots show that the loss is initially decrasing rapidly and then decrases gradually. After 40 epochs the decrease is very less and it becomes almost stagnant after  around 47 epochs i.e only a small change of 0.002 or 0.003 takes place.
4. Testing the models on self generated test set and the sample dataset provided today of around 1000 pics:

| model | self generated dataset | sample dataset provided |
| --- | --- | --- |           
| model trained for 37 epochs: | 74.45% | 48.30% |
| model trained for 46 epochs: | 76.80% | 56.54% |


