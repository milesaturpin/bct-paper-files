
Outline
- Motivation, reviewer concerns
- Experimental setup, describe models
- Add plot, maybe table
- Add captions worth of commentary

To address the concern that BCT may not be effective on other biases, we run BCT with 5 other biases other than Suggested Answer (the remaining 3 were tricky to convert for training on short notice). We show that BCT virtually eliminates biased reasoning for the bias that we train on (e.g. perform BCT with Post Hoc, then evaluate with Post Hoc on held-out tasks). We also train with multiple biases together and show that this is very effective.

We test the following models:
- BCT with individual biases. 
- BCT with all 6 biases together.

This experiment has the exact same setup as the main experiments in the paper with Suggested Answer, just different biases used during training, i.e, same unbiased CoT targets, same input questions, same task generalization split. The only thing changing is the biasing text added to the inputs. All models trained on the same amount of data (10k BCT samples).

![Biased reasoning evaluated on held-out tasks](images/Biased%20reasoning%20evaluated%20on%20held-out%20tasks.png)

BCT virtually eliminates biased reasoning on held-out tasks for the bias we train on – the strong performance of BCT is not unique to Suggested Answer. BCT with multiple biases is very effective, there is little trade-off.

To see generalization behavior of these finetunes, see [ood-distribution-bias-ood-tasks.md](ood-distribution-bias-ood-tasks.md).