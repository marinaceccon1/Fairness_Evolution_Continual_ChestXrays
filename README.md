# Fairness Evolution in Continual Learning for Medical Imaging - Appendix
## Label distribution for CXP and NIH dataset
Here we present the visual representation of the frequency of each pathology in each task for CXP and NIH datasets respectively. 
The blue bars correspond to the pathologies associated with the current task, while the light blue bars correspond to the other pathologies, and the blue contour represents the frequency of each disease in the original dataset. During each task, we keep all the images in the dataset containing at least one of the pathologies associated to the task; however, other diseases may be present even though the information on the presence of such pathologies is not available, hence they’re hidden pathologies.

![componentCounts1](https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/assets/107349467/ff765ec4-7700-4f5e-9ccd-e32a0d61db7a)
*Figure 1: Visual representation of the frequency of each pathology in each task on CXP.*
![componentCountsNIH](https://github.com/marinaceccon1/Fairness_Evolution_Continual_ChestXrays/assets/107349467/b62afd44-dd11-4bbc-8076-a0077c615cef)
*Figure 2: Visual representation of the frequency of each pathology in each task on NIH.*
