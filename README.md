# Experiments and findings with Google's Circa dataset 

![Circa BERT classification](/Capture1.PNG "Example 1")


### This project is primarily centered around an effort to reproduce/recreate findings from a EMNLP 2020 paper: ***"I'd rather just go to bed": Understanding Indirect Answers***; and exploring a possible idea for a real-world "extension". The paper's authors have shared the full details and relevant data at: https://github.com/google-research-datasets/circa Google publishes interesting datasets regularly as a foundation to solve complex problems. There are plenty, but this one particularly caught my eye. 

## What is Circa?
### From their README: "The Circa (meaning ‘approximately’) dataset aims to help machine learning systems to solve the problem of interpreting indirect answers to polar questions. The dataset contains pairs of yes/no questions and indirect answers, together with annotations for the interpretation of the answer. The data is collected in 10 different social conversational situations (eg. food preferences of a friend)."


## Why do we need Circa? / My intuition: 
### There is a clear technical appeal to this dataset, the process behind its creation, and the solution that can be built on top of it. Kindly refer to the authors' great work in the paper for such info. But in many ways, I believe the development of such a dataset is brilliant in an overarching business context, and here are my reasons: 

1. We live in an age where any effort to mine consumer information is heavily scrutinized, and rightfully so.
2. But there are occasions where some form of this "consumer information" or at least details that tie in with individual consumers is voluntarily given or made accessible. Think surveys, complaints, quality checks, customer support, feedback for improvement, etc
3. Clearly scenario-driven, but imagine a company that has launched a new product or service, they would (should) usually expect feedback to determine ease of experience routinely or at every nth cycle. It allows them to ensure said service's functionality is sustained and the end users continue to be happy and more importantly - figure out areas of improvement. 
4. Among the domains mentioned earlier, the simplest form of to-fro communication (between the end-user and the establishment that wants to monitor the end-user) is questions and answers. Qualtrics is doing a lot of exciting things in experience management when it comes to surveys but the very base or skeleton layout for that form of querying is questions and answers. 
5. It is not uncommon for consumers to give indirect responses to questions that seek a binary response; for example, the question can be along the lines of "did X work right?", or "did Y behave the way you expected it to be?". Unless the response format is constrained, many can provide a lengthy response instead of a succinct "yes" or "no".
6. But the above is just an example of voluntary information; open-ended questions exist separately. 
7. When you leverage the right AI techniques to mine such responses - you solve the immediate need to predict the binary answer from the response. The precursor to that process is the creation of a dataset like Circa. And the solution built on top of it goes on to show how far we have come in our efforts to build smarter, larger language models that can perform a wide variety of NLP tasks. 
8. <strong>The questions that I asked myself after reading the paper were, a) Can I recreate that solution and b) what else can one extract from indirect responses besides the binary answer? An ideal addition would be context -> based on the response and divergent from the question. The dataset itself has a context column, that houses the situational scenarios for the question-answer pairs. They were designed by the authors to populate the question-answer dialogs via crowdsourcing. Its purpose is to aid in the creation of such dialogs. The context that I posit here is purely response driven and based on the premise to extract more valuable information besides the main intent in the indirect response.</strong> 

Back to business again, the context will give you a chance to segment or categorize indirect responses into different buckets that can be monitored over time to see if consumers are experiencing issues in a particular aspect. I keep resorting to studying experience or processing complaints but the opportunities are endless in any domain where there is end-user text input. 

## Solutions Developed:
### 1. Performed feature extraction and fine-tuning with BERT to predict the direct answer from the indirect response to a question; test accuracy and F1 reached north of 90%. Did well even for complicated scenarios such as the one below: 
![Circa BERT classification 2](/Capture2.PNG "Example 2")
### 2. Investigated the responses and performed topic modeling with LDA to determine what themes the responses were based on to establish a singular context.

## Two notebooks show findings in both solutions. Backed by comments, thoughts, and figures. 
