# CompQA

This system is an extended version of Comparative Argumentative Machine, whose detailed description can be found [here](https://github.com/uhh-lt/cam).

We have extended this system with generative transformer-models.

## T5, Flan-T5 for objects and aspect recognition
First of all, we finalized the part for entering a user request. The CAM tool prompts the user for explicitly specified objects and aspect for comparison as input. In our case, the user can ask a question in a natural language string format. Finetuned generative models T5 and Flan-T5 receive a request to search for objects and a comparison aspect in the requested sentence and generate a response in a format convenient for submitting to CAM.

The finetuned models were evaluated by us using a number of metrics: cosine similarity, Levenshtein distance, SEAF, MUC and others.

## GPT-2 for summarization
Further, the data is processed by the CAM system, which produces a list of statements in natural language in favor of each of the objects.

These statements go to the next generative model - GPT-2. The model summarizes the statements and produces a coherent answer in natural language.

We also finetuned this model and evaluated the results using the ROUGE and BLEU metrics.

## Other information
Detailed information about model evaluations can be found in the corresponding notebooks ([evaluating_object_recognition.ipynb](./evaluating_object_recognition.ipynb), [evaluating_finetuned_t5models.ipynb](./evaluating_finetuned_t5models.ipynb) and in the end of [GPT2_finetuning.ipynb](./GPT2_finetuning.ipynb)).

Infomation about finetuning can be found in [GPT2_finetuning.ipynb](./GPT2_finetuning.ipynb) and [T5models_finetuning.ipynb](./T5models_finetuning.ipynb).

The choice of model for object recognition can also be found in the notebook [object_recognition.ipynb](./object_recognition.ipynb).

[ChatGPT_dataset.ipynb](./ChatGPT_dataset.ipynb) contains some information about dataset statistics, evaluation and correction.

