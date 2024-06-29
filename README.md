# Fairness Evolution in Continual Learning for Medical Imaging - Appendix
## Label distribution for CXP and NIH dataset
Here we present the visual representation of the frequency of each pathology in each task for CXP and NIH datasets respectively. 
The blue bars correspond to the pathologies associated with the current task, while the light blue bars correspond to the other pathologies, and the blue contour represents the frequency of each disease in the original dataset. During each task, we keep all the images in the dataset containing at least one of the pathologies associated to the task; however, other diseases may be present even though the information on the presence of such pathologies is not available, hence they’re hidden pathologies.

![componentCounts1](https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/assets/107349467/ff765ec4-7700-4f5e-9ccd-e32a0d61db7a)
*Figure 1: Visual representation of the frequency of each pathology in each task on CXP.*

![componentCountsNIH](https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/assets/107349467/b62afd44-dd11-4bbc-8076-a0077c615cef)
*Figure 2: Visual representation of the frequency of each pathology in each task on NIH.*

In the case of CXP, Task 0 contains information on the classes Consolidation, Pneumonia, and Pneumothorax, Task 1 involves Lung Opacity, Enlarged Cardiomediastinum, and Fracture, Task 2 considers Lung Lesion and Pleural Other, while Task 3 includes Atelectasis and Cardiomegaly and finally Task 4 revolves around Edema and Effusion.

Instead, concerning the NIH dataset, Task 0 contains information on the classes Consolidation, Pneumonia, and Pneumothorax, Task 1 involves Atelectasis, Cardiomegaly, Edema, Task 2 considers Effusion, Emphysema and Fibrosis, while Task 3 includes Hernia and Infiltration and finally Task 4 revolves around Mass, Nodule and Pleural Thickening.

![genderStatistics1](https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/assets/107349467/239d4eba-fcd3-46d7-ae0d-140c1329904c)
![genderStatistics2](https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/assets/107349467/e876d514-4ed6-4155-b753-a999f9e21d19)
*Figure 3: Visual representation of the frequency of the two genders in the whole dataset (on the top) and in all tasks (on the bottom), considering the CXP dataset.*
