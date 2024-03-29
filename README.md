## Predicting Yelp Reviews with Natural Language Processing

Using a linear regression deep learning model, trained with real reviews made by users on the Yelp website, this model will determine the star rating of a business based on the reviews a business has received.

Since the core problem is a regression problem, my first focus was to transform the provided dataset into a dataframe that would work in a TensorFlow model with no issues. I researched the traditional format of datasets used in regression models and eventually settled on a dataframe with the words collected from max_feature as the column headers, with their corresponding TF-IDF values listed in the rows. When designing my model, I initially made dramatic changes to the hyperparameters to understand which direction the model's performance will take, and then afterwards small, incremental changes once the RMSE score began improving between each iteration.

Once the data was prepared to be used for the model, I verified that the newly created dataframe could be read by a simple TensorFlow model with 30 neurons total and one hidden layer. After the initial experiment passed I began the process of tuning various hyperparameters to observe the changes in the models performance, with the RMSE ranging between 0.57 to 0.38 in the first few model designs. Later on in the experimentation process I began adjusting function parameters outside of the main model parameters, such as the total number of unique businesses used in the model and max_features/min_df parameters used in the tfidfVectorizer function. 

Regarding the hyperparameters, I found that using the ‘relu’ activation with the ‘adam’ optimizer yielded the best results, using the ‘sigmoid’ function along with the ‘SGD’ optimizer resulted in the model not making progress past 0.77xx loss. Using a high neuron count resulted in similar RMSE scores, but much longer run time. The best RMSE scores the final model design was able to achieve was 0.30xx - 0.27xx, which resulted in some very accurate star rating predictions for many of the businesses.

### Example output
![exImg](images/ExampleOutput.png)
