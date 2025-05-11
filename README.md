# disaster-tweets-classification

We want to idetify if a tweet is related to a disaster or it is a nor mal tweet. This is again a supervised learning model. 

The data can be downloaded through here:

https://github.com/laxmimerit/All-CSV-ML-Data-Files-Download

The "twitter_disaster_tweets.csv" is our intended dataset here. 

From the datset, we will be using only text and target features. Target is a binary variable as 1 representing disatster and 0 for normal tweet. We will do the processing and modeling and evaluation using the huggingface transformers. The model used is TinyBERT. This model is selected for acceptable accuracy and deployment purposes. If there is no resource limitation, we could have used more advanced models with more parameters and higher accuracy. Then we will save the model parameters for later production. 

## Comparision of TinyBERT and BERT as an example

BERT: has larger feedforward networks (768 and 1024 nodes in Base and Large respectively) and more attention heads (12 and 16 respectively). BERT was trained on Wikipedia and Book Corpus, a dataset containing +10,000 books of different genres. BERT has ~110 Million parameters and BERT Large has ~300 Million parameters. 

TinyBERT: is a distilled version of BERT. It uses 4 encoder layers (attention heads) and has 312 embedding size. It has ~15 Million parameters. 

The model then will be pushed to AWS S3 bucket. After, we will work on the server side on AWS EC2 service. 

Then we can feed the real time tweets to the model and distinguish if they are about a disaster or not. We should also distinguish fake tweets about disaster in our model finetuning using our task specific data. 
