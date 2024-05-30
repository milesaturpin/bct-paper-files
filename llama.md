# BCT with Llama 3 8b Instruct works well

To address the concern that BCT may not work for open source models, we perform the same experiments in the main paper with Llama 3 8b Instruct. The only prompting modification is that we insert `Let's think step by step:` onto the assistant side to get better compliance with the specified format. We conduct fine-tuning using [fireworks.ai](https://fireworks.ai/) fine-tuning service which uses LoRA fine-tuning.


![Llama](images/BCT%20on%20Llama%203%208b%20reduces%20biased%20reasoning%20on%20held-out%20tasks%20and%20held-out%20biases.png)

BCT reduces biased reasoning on held-out tasks for the bias we train on (Suggested Answer), with a BRR ratio of X. It also generalizes to held-out biases with a BRR ratio of . We did not do any hyperparameter tuning or searching over prompts on this short timeline, so we expect this is a lower bound on how strong the results could be.

