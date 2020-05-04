# Deep-Chatbot
Introduction:
This blog walks you through an example of a deep learning based  couseling chatbot.
The Dataset:
I downloaded the datasets from https://drive.google.com/file/d/1UijGI3dQMAFS8GWnwd8f5FdIZ4LPmQ4x/view. this is brief description of the datasets:
This dataset contains 11 column , namely:
questionID	
questionTitle	
questionText	
questionLink	
topic	
therapistInfo	
therapistURL	
answerText	
upvotes	
views	
split
with total of 2273 rows
 Data Preprocessing:
Here’s a description of the preprocessing operations performed on the data:
Character replacement: to make learning easier, I have replaced some characters with others if they convey the same meaning. For example, there are many types of brackets like square, round, curly and angle brackets and most likely they are used for the same purpose. Therefore, using one type of brackets would make it easier for the model to learn to use them.
Removal of unwanted characters: all three different datasets had so many characters of different nature like alphabets of different languages, numbers, special characters and even emojis. So, limiting the characters in the final dataset to only a chosen group of them like the alphabet of the English language, numbers and some special characters would result in a more consistent dataset.
Removal of extra whitespaces.
Dropping unnecessary duplicate pairs (rows) but keeping only one instance of those duplicates: for example, if the dataset contains three duplicates of the same question-answer pair, then two of them would be removed and one kept.
Dropping rows with an empty question or answer: these may appear because of the previous step or because they happen to be empty in the original dataset.
Dropping rows with more than 30 words: in either the question or the answer, also dropping rows if the answer has less than two characters. (Note: this is a hyperparameter and you can try other values.)
 
 However, after preprocessing it was left with 25 pair token to develop the deep learning. very small dataset though!!
 
 The Model:
I have used an encoder-decoder architecture with Bahdanau’s attention, which has been described in detail in this paper: Effective Approaches to Attention-based Neural Machine Translation


What can we do to improve performance?
More data: if we want to have good performance with more impressive responses, we need to train on a lot more data, maybe millions of pairs. However, training on a large scale dataset requires more computational power (like a more powerful GPU) and a more sophisticated model with more layers and units, let alone finding and acquiring such dataset.i wish to train this bot with BioBERT in order to make the bot more smart. i want to use multi-lable classification in order to make the bot respond based on the class of the question(LDA model).

