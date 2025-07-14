we are training the model of machine learnig from the chatbot Arena conversation.
The goal is we have to predict what answer of LLm should have prefered by users, either Model A OR Model B.
This task is similar to LLM reward modeling — but instead of calling LLM APIs, it uses purely data-driven prediction techniques.

In other words, you're training a model to understand and predict human preferences based on already-generated LLM responses, without interacting with the models themselves. This way, the classifier learns what kind of response resonates with users by analyzing patterns in the dataset.
🗂️ Dataset
Kaggle Competition: LLM Classification Finetuning

Files used:

train.csv: training data with prompts, responses & user choices

test.csv: unseen prompts & responses for prediction

sample_submission.csv: format for submission file

Approach:
Data Analysis — explored prompts & LLM responses

Feature Engineering — created metrics like response length, sentiment, keyword overlap

Label Encoding — converted user choices into numerical labels (0: Model A, 1: Model B, 2: Tie)

Transformer Fine-Tuning — used RoBERTa-base for classification

Submission Generation — created a CSV with probabilities for each class
🧪 Model Used
text
Model: RoBERTa-base
Framework: Hugging Face Transformers
Type: Sequence classification (3 classes)
OUTPUT:
id,winner_model_a,winner_model_b,winner_tie
123456,0.21,0.72,0.07
...
