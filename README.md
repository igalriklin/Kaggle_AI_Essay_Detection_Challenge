# Kaggle_AI_Essay_Detection_Challenge
My submissions to the Kaggle competition:
https://www.kaggle.com/competitions/llm-detect-ai-generated-text

The goal of the competition is to develop a machine learning model capable of accurately distinguishing between essays written by middle and high school students and those generated by large language models. I joined the competition as part of the NLP-IL mentorship program with guidance from mentors who accompanied us regularly via Zoom sessions.
Initially, I experimented with a Deberta V3 model with 256 tokens, but encountered challenges due to its lengthy runtime and moderate score of 0.75. I compared it to a logistic regression model using TF-IDF of words as tokens, which demonstrated a better results with a score of 0.82. Since it ran much faster and gave better result I decided to continue to work in that direction. My final model is an ensamble of four pipelines. Each pipeline employed a different tokenizer—sentence piece, word piece, bytepair, and unigram—followed by TF-IDF transformation, scaling, and logistic regression. This comprehensive approach yielded a notable improvement, achieving a score of 0.88.

In the end, our score didn't make it to the top 25%. Many top submissions were similar to a single notebook that scored 0.96. One of our team members tried adjusting settings like others did, but I don't consider that score as my achievement. 

I decided to focus on building models rather than creating datasets for this project. The competition didn't provide much data, just a few examples. So, I used a dataset shared by another competitor. However, this dataset had a different distribution than the one used internally in the competition. Because of this difference, checking the model's performance internally didn't really help, as models that seemed to perform really well during testing gave much lower scores when officially submitted. That's why I used all the available data for training. Improving the dataset would have likely boosted the submission scores, but I chose not to work on that aspect.
