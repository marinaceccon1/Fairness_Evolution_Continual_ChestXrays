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

##Age groups frequency for each task

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
  <img src="https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/aassets/107349467/a2ab1b9b-0499-495a-b5a0-477730a6f5cd" alt="Label distribution for CXP dataset" width="400"/>
  <p><em>Figure 7: Learning without Forgeting algorithm.</em></p>
</div>


