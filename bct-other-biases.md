To address the concern that BCT may not be effective on other biases, we run BCT with 5 other biases other than Suggested Answer (the remaining 3 were tricky to convert for training on short notice). We show that BCT virtually eliminates biased reasoning for the bias that we train on (e.g. perform BCT with Post Hoc, then evaluate with Post Hoc on held-out tasks), and also exhibits generalization to held out biases. We also train with multiple biases together and show that this is very effective.

We test the following models:
- BCT with individual biases. 
- BCT with all 6 biases together.

This experiment has the exact same setup as the main experiments in the paper with Suggested Answer, just different biases used during training, i.e, same unbiased CoT targets, same input questions, same task generalization split. The only thing changing is the biasing text added to the inputs. All models trained on the same amount of data (10k BCT samples).

### Biased reasoning evaluated on the training biases on held-out tasks

![Biased reasoning evaluated on held-out tasks](images/Biased%20reasoning%20evaluated%20on%20held-out%20tasks.png)

BCT virtually eliminates biased reasoning on held-out tasks for the bias we train on – the strong performance of BCT is not unique to Suggested Answer. BCT with multiple biases is very effective, there is little trade-off.

### Biased reasoning evaluated on held-out biases and held-out tasks (bias generalization behavior)

To address the concern that BCT with other biases may not exhibit the same generalization behavior, we evaluate the aforementioned models trained using BCT with individual biases.

Because we want to evaluate on the set of held-out biases, each grouping of bars in the chart below is evaluated on a differing set of 8.  Because of this, we report numbers for GPT-3.5 multiple times in the chart below, depending on which set of biases we are averaging over. 
![Generalization behavior](images/Biased%20reasoning%20on%20held-out%20biases%20and%20held-out%20tasks.pdf)

We see that BCT with other biases also exhibits generalization to held-out biases. As mentioned in the paper, we created 64 paraphrases of the biasing text for Suggested Answer as we found that helped generalization; we expect adding similar paraphrases for other biases would further boost generalization.

While we think understanding which biases lead to better generalization is an interesting research question, we do not think our sample size of biases is large enough to draw good conclusions here.

