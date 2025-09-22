To run the code, download the data file spotify-popularity-songs.zip from https://www.kaggle.com/datasets/ahmadrazakashif/spotify-popularity-songs. 
Unzip the file and place spotify_songs.csv in the same folder as your Jupyter notebook. In the code, you can then load the data with pd.read_csv('spotify_songs.csv').

1. Why is this problem interesting to solve with machine learning?

This problem is interesting because a song's popularity is difficult for a human to predict. There are many factors at play (such as danceability, energy, tempo, and acoustic properties), and it's virtually impossible for us to manually assess all these factors simultaneously for thousands of songs. Machine learning is a great tool that can analyze these complex relationships and find patterns in the large dataset to make an educated guess about a song's popularity. In other words, it can make a better "educated guess" than a human.

2. Why did you choose Logistic Regression as the algorithm?

Logistic Regression was chosen because it is a simple and effective algorithm for binary classification, which fits our problem perfectly since we are classifying songs as either "popular" or "not popular." The algorithm is also easy to understand and evaluate, which makes it suitable for demonstrating fundamental machine learning workflows.

3. Why was it necessary to balance the dataset?

As the first graph shows, the dataset was extremely imbalanced. There were almost three times as many songs in the "not popular" category as in the "popular" category. A model trained on imbalanced data risks becoming "lazy" and learning to always guess the most common class to achieve high overall accuracy. Our baseline model did exactly this, failing to find a single popular song. To get a fair and useful model, we used RandomOverSampler to create a balanced dataset, which forced the model to learn to recognize both classes equally well.

4. Why is the new model better, even though the accuracy is lower?

Although the overall accuracy decreased from 74% to 52% after the optimization, the new model is far superior. A high accuracy on an imbalanced dataset can be misleading. The first model had high accuracy because it always guessed "not popular," which was correct in 74% of cases. Our new, balanced model has a much better ability to predict both classes. This is clearly seen in our evaluation: the precision, recall, and f1-score are now much more evenly distributed between the two categories, which shows that the model has actually learned to differentiate between a popular and a not-popular song.
