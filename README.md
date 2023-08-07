# llama2_test

Information and hypotheses:

Testing out Llama2 by fine-tuning the pre-trained model with jeopardy prompt questions and answers.

This repository contains notebook files to test different methods of fine-tuning Llama2. More specifically, using a jeopardy Q&A corpus, I constructed an instruction task where around 216k questions and answers are fine-tuned with Llama2's 7 billion parameter model. Given the nature of Jeopardy, being a trivia game show, it is well-equipped to handle the prompt and response format of a standard instruction task. 


Potential use cases can be to help train for applying to the game show, Jeopardy!, given that there has been sufficent instruction on what questions might be expected. The fine-tuned result should be able to demonstrate an understanding of the style of Jeopardy question formats.

It requires at least a T4 GPU to fine-tune. The version of the Llama2 model is sharded to try and increase efficiency. The questions and answers columns passed through are packed for training efficiency, as suggested by Hugging Face's documentation (https://huggingface.co/docs/trl/v0.4.7/en/sft_trainer). Some other adjustments also had to be made to account for the format of the data (iterative) and the task itself (instruction). 


Explanation of repository files:

-main.ipynb = Main trainer notebook. Contains commented information on decisions made to customize the experiment for an intruction task, i.e. passing both questions and answers as parameters.


-Jeopardy_CSV.csv = A copy of the HuggingFace corpus of jeopardy question and answer data


-first_try.ipynb = This includes my first try. It is notebook code that needs an adjustment to the text_column parameter in order to load the data into the correct format to complete fine-tuning. The dataset text field should be 'question' and 'answer' not 'text'



Credit for code and data:

Found HuggingFace JeopardyBot model (https://huggingface.co/openaccess-ai-collective/jeopardy-bot/tree/main) that uses the first Llama LLM.


Used this code yet adjusted the model and datset to fit purposes of use case(https://towardsdatascience.com/fine-tune-your-own-llama-2-model-in-a-colab-notebook-df9823a04a32)


"Initial notebook created by [@maximelabonne](https://twitter.com/maximelabonne), based on Younes Belkada's [GitHub Gist](https://gist.github.com/younesbelkada/9f7f75c94bdc1981c8ca5cc937d4a4da). Special thanks to Tolga HOŞGÖR for his solution to empty the VRAM."

Llama2 paper (https://arxiv.org/pdf/2307.09288.pdf)

Llama2 Github (https://github.com/facebookresearch/llama)


