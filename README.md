# llama2_test

Testing out Llama2 by fine-tuning the pre-trained model with jeopardy questions and answers.

Will use this repository as a way to test different methods of fine-tuning Llama2 (https://github.com/facebookresearch/llama). Using this jeopardy Q&A corpus, the goal is to change the writing style, since it may require billions of tokens to make an extreme change, based on assumptions made from the Llama2 paper (https://arxiv.org/pdf/2307.09288.pdf).

Potential use cases can be to help train for applying to the game show, Jeopardy!


-Jeopardy_CSV.csv = corpus of jeopardy question and answer data


-llama2_jeopardy.ipynb = notebook code that needs an adjustment to the text_column parameter in order to load the data into the correct format to complete fine-tuning. The dataset text field should be 'question' not 'text'

-




Found HuggingFace JeopardyBot model (https://huggingface.co/openaccess-ai-collective/jeopardy-bot/tree/main) that uses the first Llama LLM.


Used this code yet adjusted the model and datset to fit purposes of use case(https://towardsdatascience.com/fine-tune-your-own-llama-2-model-in-a-colab-notebook-df9823a04a32)