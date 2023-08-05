# llama2_test

Testing out Llama2 by fine-tuning the pre-trained model with jeopardy questions and answers.

Will use this repository as a way to test different methods of fine-tuning Llama2 (https://github.com/facebookresearch/llama). Using this jeopardy Q&A corpus, the goal is to change the writing style, since it may require billions of tokens to make an extreme change, based on assumptions made from the Llama2 paper (https://arxiv.org/pdf/2307.09288.pdf).

Potential use cases can be to help train for applying to the game show, Jeopardy!


-Jeopardy_CSV.csv = corpus of jeopardy question and answer data


-llama2_jeopardy.ipynb = notebook code that needs some work in loading the data into the correct format to complete fine-tuning process. Using autotrain one line to simplify process. 

*** However, need to fix the KeyError in the data.

Found HuggingFace JeopardyBot model (https://huggingface.co/openaccess-ai-collective/jeopardy-bot/tree/main) that uses the first Llama LLM. May try to use their code to improve this one