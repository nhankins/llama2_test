# Llama2 Jeopardy

# Information and hypotheses:

Testing out Llama2 by fine-tuning the pre-trained model with jeopardy prompt questions and answers.

This repository contains notebook files to test different methods of fine-tuning Llama2. More specifically, using a jeopardy Q&A corpus, I constructed an instruction task where around 216k questions and answers are fine-tuned with Llama2's 7 billion parameter model. Given the nature of Jeopardy, being a trivia game show, it is well-equipped to handle the prompt and response format of a standard instruction task. 

# Use cases, notes, and Prerequisites

Potential use cases can be to help train for applying to the game show, Jeopardy!, given that there has been sufficent instruction on what questions might be expected. The fine-tuned result should be able to demonstrate an understanding of the style of Jeopardy question formats.

It requires at least a T4 GPU to fine-tune. The version of the Llama2 model is sharded to try and increase efficiency. The questions and answers columns passed through are packed for training efficiency, as suggested by Hugging Face's documentation (https://huggingface.co/docs/trl/v0.4.7/en/sft_trainer). Some other adjustments also had to be made to account for the format of the data (iterative) and the task itself (instruction). 


# Explanation of repository files:

-llama-2-jeopardy-model - trained model for inference on smaller dataset (coming soon). Will continue to tweak and play around with papermeters locally before uploading.

-main_modified_small.ipynb - contains code that will generate the fine-tuned instruction task model 

-main_modified.ipynb - Increases batch sizes and max_seq_length to speed up training efficiency, yet ran out of memory. Will cut down on number of Q&A pairs for ease on current training resources

-main.ipynb = Main trainer notebook. Contains commented information on decisions made to customize the experiment for an intruction task, i.e. passing both questions and answers as parameters. Was able to have a friend train on a compute cluster, yet I wanted to adjust parameters before completion. Still unsure how to load the saved model at this time with the qLoRA adapter model. 


-Jeopardy_CSV.csv = A copy of the HuggingFace corpus of jeopardy question and answer data

-jeopardy_smaller.csv - smaller version of jeopardy data

-first_try.ipynb = This includes my first try. It is notebook code that needs an adjustment to the text_column parameter in order to load the data into the correct format to complete fine-tuning. The dataset text field should be 'question' and 'answer' not 'text'



# Credit for code and data:

The HuggingFace JeopardyBot model (https://huggingface.co/openaccess-ai-collective/jeopardy-bot/tree/main) inspired me to do this experiment. It uses the first Llama LLM and Hugging Face jeopardy data so I wanted to update it with the second version of the LLM.


Used the following notebook code yet adjusted the model and datset to fit purposes of use case(https://towardsdatascience.com/fine-tune-your-own-llama-2-model-in-a-colab-notebook-df9823a04a32) as well as added some misc details like mounting google drive. I commented out a lot of the LoRA implementation and tensorboard logging for later tests.
    |
    |
    --- > "Initial notebook created by [@maximelabonne](https://twitter.com/maximelabonne), based on Younes Belkada's [GitHub Gist](https://gist.github.com/younesbelkada/9f7f75c94bdc1981c8ca5cc937d4a4da). Special thanks to Tolga HOŞGÖR for his solution to empty the VRAM."



Llama2 paper (https://arxiv.org/pdf/2307.09288.pdf)

Llama2 Github (https://github.com/facebookresearch/llama)


