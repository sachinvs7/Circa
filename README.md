# Experiments and findings with Google's Circa dataset 

Google regularly releases fascinating datasets, intended to serve as a foundation for tackling challenging problems. Among the numerous options available at https://research.google/resources/datasets/, Circa particularly caught my attention for its obvious benefit in mining valuable consumer feedback/data. Conversational AI and Chatbots is also an obvious application. Another example I can think of is market research -- companies conducting surveys can use models trained on this dataset to better categorize responses that may not be straightforward yes or no answers. 

## What is Circa?: 
This project is primarily centered around an effort to reproduce/recreate findings from a 2020 EMNLP paper: ***"I'd rather just go to bed": Understanding Indirect Answers***. The paper's authors have shared the full details and relevant data at: https://github.com/google-research-datasets/circa. From the authors' README: "The Circa (meaning ‘approximately’) dataset aims to help machine learning systems to solve the problem of interpreting indirect answers to polar questions. The dataset contains pairs of yes/no questions and indirect answers, together with annotations for the interpretation of the answer. The data is collected in 10 different social conversational situations (eg. food preferences of a friend)."


## Things that I tried: 
1. Feature extraction and fine-tuning with BERT and GPT-3 (GPT-Neo 125M via HuggingFace, currently GPU poor). The former delivered better loss and accuracy; also performed well for complicated scenarios -- examples from the .ipynb file (circa_bert) below.
2. Explored topic modeling with LDA (circa_tm) to identify common themes in responses. By grouping responses into topics, LDA can assist in categorizing indirect responses based on any underlying reasons. This, in turn, can be helpful in scenarios where predicting the direct answer is not relevant but rather what the response is talking about. 
   
![Circa BERT classification](/circa_ss_unseen.PNG "screenshot")

