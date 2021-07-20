# Fake News Detection Vulnerability

As the spread of false information on the internet has increased dramatically in recent years, more and more attention is being paid to automated fake news detection. Some fake news detection methods are already quite successful. Nevertheless, there are still many vulnerabilities in the detection algorithms. The reason for this is that fake news publishers can structure and formulate their texts in such a way that a detection algorithm does not expose this text as fake news. This paper shows that it is possible to automatically attack state-of-the-art models that have been trained to detect Fake News, making these vulnerable. For this purpose, corresponding models were first trained based on a data set. Then, using Text-Attack, an attempt was made to manipulate the trained models in such a way that previously correctly identified fake news was classified as true news. The results show that it is possible to automatically bypass Fake News detection mechanisms, leading to implications concerning existing policy initiatives. 

## Goal
Main goal of this work was to train several Natural Language Processing (NLP) models and apply [TextAttack](https://github.com/QData/TextAttack) to detect their vulnerability against Fake News. For our experiments the following models were trained and attacked:
* [BERTweet](https://huggingface.co/vinai/bertweet-base)
* [RoBERTa](https://huggingface.co/roberta-base)
* [Flair Embeddings](https://github.com/flairNLP/flair)
More infomration on the used models, the dataset and the TextAttack recipes can be found in our paper.

## Code and Usage
The `/code` directory includes the `.ipynb` files to train the models and the skeleton to apply TextAttack:
* `TextClassificationModels`
    * Use this notebook to train the models
    * Before running the code you need to choose between binary (only TRUE/FALSE statements) and multi class (all statements) training (set the `binaryClassification` variable to `True`/`False`)
    * In case you choose a model from [Hugging Face](https://huggingface.co/) enter the name of the model in the section **TRAIN HUGGING FACE MODEL**
    * Should you decide to run Flair Embeddings as the NLP model ignore the above mentioned section and run **TRAIN FLAIR EMBEDDING** instead
* `TextAttack`
    * Run this notebook to apply all TextAttack recipes mentioned in our paper
    * The attacks are applied on pre-trained models. If you choose to run the attacks on your own models you will need to upload them to Google Drive and paste the download link into the code.
    * Our attack results can be found in the `/reults` directory

_The easiest way to run the notebooks without any import issues is through [Google Colab](https://colab.research.google.com/)_

## Paper
Find the full paper [here](https://arxiv.org/abs/2107.07970).

## Authors
Nicolai Schneider, Camille Koenders, Johannes Filla and Vinicius Woloszyn
