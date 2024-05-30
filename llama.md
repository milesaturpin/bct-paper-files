# BCT with Llama 3 8b Instruct works well

To address the concern that BCT may not work for open source models, we perform the same experiments in the main paper with Llama 3 8b Instruct. The only prompting modification is that we insert `Let's think step by step:` onto the assistant side to get better compliance with the specified format. We conduct fine-tuning using [fireworks.ai](https://fireworks.ai/) fine-tuning service which uses LoRA fine-tuning. We also do not average over Positional Bias or Hindsight Neglect in these plots due to some issues with prompting that we couldn't resolve on short notice. Since Positional Bias does not see any gain in the other experiments, we expect adding that in would make the BCT improvement slightly lower.


![Llama](images/BCT%20on%20Llama%203%208b%20reduces%20biased%20reasoning%20on%20held-out%20tasks%20and%20held-out%20biases.png)

We see the same pattern of results as for GPT-3.5T: BCT virtually eliminates biased reasoning on held-out tasks for the bias we train on (Suggested Answer). It also exhibits good generalization to held-out biases. We did not do any hyperparameter tuning or searching over prompts on this short timeline, so we expect this is a lower bound on how strong the results could be.

