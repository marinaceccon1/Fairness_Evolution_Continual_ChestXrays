# Fairness Evolution in Continual Learning for Medical Imaging - Appendix
## Label distribution for CXP and NIH dataset
Here we present the visual representation of the frequency of each pathology in each task for CXP and NIH datasets respectively. 
The blue bars correspond to the pathologies associated with the current task, while the light blue bars correspond to the other pathologies, and the blue contour represents the frequency of each disease in the original dataset. During each task, we keep all the images in the dataset containing at least one of the pathologies associated to the task; however, other diseases may be present even though the information on the presence of such pathologies is not available, hence they’re hidden pathologies.

<div style="text-align: center;">
  <img src="https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/assets/107349467/ff765ec4-7700-4f5e-9ccd-e32a0d61db7a" alt="Label distribution for CXP dataset" width="1000"/>
  <p><em>Figure 1: Label distribution for CXP dataset</em></p>
</div>

<div style="text-align: center;">
  <img src="https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/assets/107349467/b62afd44-dd11-4bbc-8076-a0077c615cef" alt="Label distribution for NIH dataset" width="1000"/>
  <p><em>Figure 2: Label distribution for NIH dataset</em></p>
</div>

In the case of CXP, Task 0 contains information on the classes Consolidation, Pneumonia, and Pneumothorax, Task 1 involves Lung Opacity, Enlarged Cardiomediastinum, and Fracture, Task 2 considers Lung Lesion and Pleural Other, while Task 3 includes Atelectasis and Cardiomegaly and finally Task 4 revolves around Edema and Effusion.

Instead, concerning the NIH dataset, Task 0 contains information on the classes Consolidation, Pneumonia, and Pneumothorax, Task 1 involves Atelectasis, Cardiomegaly, Edema, Task 2 considers Effusion, Emphysema and Fibrosis, while Task 3 includes Hernia and Infiltration and finally Task 4 revolves around Mass, Nodule and Pleural Thickening.

<div style="text-align: center;">
  <img src="https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/assets/107349467/239d4eba-fcd3-46d7-ae0d-140c1329904c" alt="Label distribution for CXP dataset" width="400"/>
    <img src="https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/assets/107349467/e876d514-4ed6-4155-b753-a999f9e21d19" alt="Label distribution for CXP dataset" width="1000"/>
  <p><em>Figure 3: Visual representation of the frequency of the two genders in the whole dataset (on the top) and in all tasks (on the bottom), considering the CXP dataset.</em></p>
</div>


<div style="text-align: center;">
  <img src="https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/assets/107349467/c7cda470-2438-4049-8acf-30e92b23f828" alt="Label distribution for CXP dataset" width="400"/>
    <img src="https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/assets/107349467/8e93faf0-b3d7-4bdb-915c-11a44b817334" alt="Label distribution for CXP dataset" width="1000"/>
  <p><em>Figure 4: Visual representation of the frequency of the two genders in the whole dataset (on the top) and in all tasks (on the bottom), considering the NIH dataset.</em></p>
</div>

Here we present the visual representation of the frequency of the two genders in the whole dataset (on the top) and in all tasks (on the bottom), considering both the CXP and NIH datasets.

## Age groups frequency for each task

Here we present the visual representation of the frequency of the four age groups in the whole dataset (on the top) and in all tasks (on the bottom), considering the CXP and NIH datasets.

<div style="text-align: center;">
  <img src="https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/assets/107349467/4d9c910f-1b19-4a4d-a56c-74b5639ca641" alt="Label distribution for CXP dataset" width="400"/>
    <img src="https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/assets/107349467/8ac9b4b9-e2ea-4721-9376-f9e97d4633da" alt="Label distribution for CXP dataset" width="1000"/>
  <p><em>Figure 5: Visual representation of the frequency of the four age groups in the whole dataset (on the top) and in all tasks (on the bottom), considering the CXP dataset.</em></p>
</div>


<div style="text-align: center;">
  <img src="https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/assets/107349467/b5683c37-1f2d-498d-b860-321e1700f95f" alt="Label distribution for CXP dataset" width="400"/>
    <img src="https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/assets/107349467/689e71e9-745c-44e3-bb40-7490bdb04613" alt="Label distribution for CXP dataset" width="1000"/>
  <p><em>Figure 6: Visual representation of the frequency of the four age groups in the whole dataset (on the top) and in all tasks (on the bottom), considering the NIH dataset.</em></p>
</div>

## PseudoCode of Lwf and Pseudo-Label
### LwF
LwF is a technique that uses knowledge distillation to transfer knowledge from previous tasks to new ones. During training on a new task, the model is trained to mimic its own predictions on the previous task, in addition to making predictions on the new task. This helps the model retain knowledge about the previous task while learning the new one.

<div style="text-align: center;">
  <img src="https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/assets/107349467/d47d0bb9-b956-416d-bc82-246b963551b3" alt="Label distribution for CXP dataset" width="500"/>
  <p><em>Figure 7: Learning without Forgeting algorithm.</em></p>
</div>

### Pseudo-Label
Initially, we start by initializing the model parameters.
These parameters will be updated throughout the training process to adapt to the current task.
After training on previous tasks, it uses the previous model to make predictions on new data encountered in the current task.
To filter out unreliable predictions, a confidence threshold $\tau$ is applied to the model's predictions.
This threshold tau determines the level of confidence required for a prediction to be considered reliable. 
Predictions with confidence scores below this threshold are discarded.
Then this pseudo-predictions are incorporated in the ground-truth labels of the data from the current task.
At this point, the loss for the mini-batch is computed and the model is updated accordingly.
By iteratively repeating these steps for each mini-batch in the current task dataset, the model learns not only from the labeled data of the current task but also from the pseudo-labeled data generated from the previous model.
This allows the model to retain knowledge from previous tasks while adapting to new tasks, thus addressing the challenge of catastrophic forgetting in CL scenarios. 

<div style="text-align: center;">
  <img src="https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/assets/107349467/6ac16524-5167-41a2-ad50-a325b2b07f87" alt="Label distribution for CXP dataset" width="500"/>
  <p><em>Figure 8: Pseudo-Label algorithm.</em></p>
</div>

## Results on NIH

<div style="text-align: center;">
  <img src="https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/assets/107349467/408a6151-dfc7-4ab9-a021-4bff73c0993a" alt="Label distribution for CXP dataset" width="500"/>
  <p><em>Figure 9: AUC metric, evaluated on each strategy, averaged on all the pathologies seen so far.</em></p>
</div>

As is notable from figure 9, the average AUC on the model trained in the Joint Training on NIH is 0.782.

As it was observed in the case of the CXP dataset, the Fine-Tuning approach fails at maintaining the knowledge of previous tasks. Indeed, the trend on the overall average AUC is strongly decreasing. Similarly, Replay performs poorly on this dataset, in this scenario, exhibiting only a small improvement with respect to the Fine-Tuning approach. 

In particular, the replay method achieves a final ROC AUC of 0.60, compared to the 0.57 achieved by the Fine-Tuning approach. 

On the other hand, the LwF, Pseudo-Label and LwF Replay strategies perform well on this dataset. The main difference with respect to the results on the CXP dataset is that LwF Replay performs very similarly to LwF, and both exhibit a slightly lower AUC with respect to Pseudo-Label. Indeed, the final value of AUC of both LwF Replay and LwF is 0.65, while the final value of the Pseudo-Label strategy is 0.68. As it was for the CXP dataset, there is a notable gap between the optimal performance represented by the Joint Training strategy, which achieves a final value of 0.78, and the optimal CL strategy, i.e., Pseudo-Label.

<div style="text-align: center;">
  <img src="https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/assets/107349467/4fbc7d13-8ede-4ea3-9f1a-1543bcbaa963" alt="Label distribution for CXP dataset" width="500"/>
  <p><em>Figure 10: Sex TPR gap on NIH of all the considered CL strategies.</em></p>
</div>

<div style="text-align: center;">
  <img src="https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/assets/107349467/bf0ee9fe-0573-42ef-9077-f876a0eff751" alt="Label distribution for CXP dataset" width="500"/>
  <p><em>Figure 11: Fairness metric results on NIH.</em></p>
</div>

Concerning the gender TPR gap, previous works had found that the models trained on NIH were biased toward males [1]. In the case of the NIH dataset, we find that the TPR is slighlty higher for females, and it takes the value of $-0.010$, where the minus indicates that females are the advantaged group.

As previously stated, there are many factors that may contribute to the difference in results with respect to the SOTA, for example the choice of only keeping one image per patient and of not considering "No Finding" images. 

In figure 10, we display the plots of the gap disparity between males and females for all strategies. As done in the case of the CXP dataset, we decide to focus on the TPR of the three best methods: LwF, Pseudo-Label and LwF Replay. The plots relative to the male and female TPR of these approaches are reported in Figure 11.

From the Figure we can notice that, as it was for the CXP dataset, the model resulting from training on all tasks using the Pseudo-Label strategy displays an almost null gap, while instead the LwF approach slightly favours the performance on males. However, the gap of the LwF approach is smaller with respect to the one observed on the CXP dataset. On the other hand, the use of the LwF Replay approach results in a gap favoring the performance on females.


<div style="text-align: center;">
  <img src="https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/assets/107349467/2f8af94a-1b54-4a67-af26-a6e3b0077a73" alt="Label distribution for CXP dataset" width="500"/>
  <p><em>Figure 12: Age TPR gap on NIH of all the considered CL strategies.</em></p>
</div>

<div style="text-align: center;">
  <img src="https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/assets/107349467/a64d1309-aece-4e79-96a3-f31d2df2864e" alt="Label distribution for CXP dataset" width="500"/>
  <p><em>Figure 13: TPR of each age group considering the LwF approach.</em></p>
</div>

<div style="text-align: center;">
  <img src="https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/assets/107349467/7f9484f4-ba50-49a9-9fee-8c085b8057fc" alt="Label distribution for CXP dataset" width="500"/>
  <p><em>Figure 14: TPR of each age group considering the Pseudo-Label approach.</em></p>
</div>

<div style="text-align: center;">
  <img src="https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/assets/107349467/1f13d384-42b8-4255-99ab-bcf4e67d17bc" alt="Label distribution for CXP dataset" width="500"/>
  <p><em>Figure 15: TPR of each age group considering the LwF Raplay approach.</em></p>
</div>

Additionally, we report the results of TPR and TPR disparity relative to each age group.
The results on the joint training show that the group with the highest TPR is patients between 40 and 60, while the most unfavored group is patients younger than 20, and the gap is of 0.053.

As depicted in the previous sections, we define the gap as the difference between the TPR of the youngest and the oldest group, and we plot it in Figure 12, for each strategy, after training on each task.
Instead, the results on the TPR for all age groups relative to the three best methods (LwF, Pseudo-Label and LwF Replay) are displayed in Figures 13, 14 and 15.

From the plots we can notice that, considering the LwF and Pseudo-Label approaches, after training on all tasks, the TPR is the highest on people younger than 20 and the lowest on people older than 60. Moreover, the two strategies display very similar gaps: in the case of LwF the gap is 0.046, while considering Pseudo-Label it's 0.043. The two gaps are slightly smaller with respect to the ones noticed in the CXP dataset.

When considering the LwF Replay approach, we observe that the disparity between the most and the least advataged groups is marginally smaller: it takes the value of 0.032, favoring patients older than 60 and disfavoring patients between 20 and 40. On the other hand, the TPRs on the youngest and oldest groups are very similar, hence the TPR gap in this case is -0.002.

## References
[1] Laleh Seyyed-Kalantari, Guanxiong Liu, Matthew McDermott, Irene Chen, and Marzyeh Ghassemi. Chexclusion: Fairness gaps in deep chest x-ray classifiers. pages 232–243, 11 2020.

