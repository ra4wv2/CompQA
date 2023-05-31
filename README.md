# CompQA

[This system is an extended version of Comparative Argumentative Machine, whose detailed description can be found here](https://github.com/uhh-lt/cam "here").

We have extended this system with generative transformer-models.

## T5, Flan-T5 for objects and aspect recognition
First of all, we finalized the part for entering a user request. The KAM tool prompts the user for explicitly specified objects and aspect for comparison as input. In our case, the user can ask a question in a natural language string format. Finetuned generative models T5 and Flan-T5 receive a request to search for objects and a comparison aspect in the requested sentence and generate a response in a format convenient for submitting to CAM.

The finetuned models were evaluated by us using a number of metrics: cosine similarity, Levenshtein distance, SEAF, MUC and others.

## CAM level
Further, the data is processed by the CAM system, which produces a list of statements in natural language in favor of each of the objects.

## GPT-2 for summarization
These statements go to the next generative model - GPT-2. The model summarizes the statements and produces a coherent answer in natural language.

We also finetuned this model and evaluated the results using the ROUGE and BLEU metrics.

## Other information
Detailed information about model evaluations can be found in the corresponding notebooks.

The choice of model for object recognition can also be found in the notebook.
