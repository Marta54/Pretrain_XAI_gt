# Update 2025-03-21: 
A bug in the lesion generation process resulted in rectangular bounding box artifacts. This issue has been fixed, and due to the consistent nature of the artifacts, no changes in experimental results are expected.
# Benchmarking the influence of pre-training on explanation performance in MR image classification

The corresponding paper can be found here: [Paper](https://doi.org/10.3389/frai.2024.1330919).

The MRI raw dataset can be found on OSF: [Dataset](https://www.doi.org/10.17605/OSF.IO/XNWAJ).


In this project random lesions are created and added to a background that consists in MRI slices from the HCP project.
The objective here is to study the correctness of XAI methods applied to pre-trained VGG models and understand the influence on the explanations. 
Two VGG models were pre-trained with two different corpora: ImageNet and MRI data (classification between female and male genders).
The VGG models were then fine-tuned to several degrees of finetuning that corresponded to a different number of layers fine-tuned and others left unchanged (frozen). 5 degrees of finetuning were obtained based on the blocks shown bellow:

![alt text](https://github.com/Marta54/Pretrain_XAI_gt/blob/main/VGG%20architecture.png)

The XAI method used came from the Captum library and were Integrated Gradients, GradientSHAP, DeepLift, Saliency, InputXGradient, Guided Backpropagation, Deconvolution and LRP.

In the folder saves several results for incorrectly classified images obtained with the XAI methods applied to the models that were pre-trained with ImageNet (for the best performing models and the models that performed similarly).
In new results are the results obtained for the teo types of pre-trained corpora. These results correspond to the images that were correctly classified by all the models (3 models for each degree of finetuning).

+ **Finetuning_on_2500_images.ipynb** - corresponds to the Jupyter notebook used to generate data (2500 images) and train the models with different parameters. 
+ **Boxplot_incorrect_classified.ipynb** - corresponds to the Jupyter notebook used to obtain the incorrected classified boxplots from the saves folder.
+ **Examples Heatmaps.ipynb** - corresponds to the Jupyter notebook used to obtain the heatmaps in the saves folder (incorrectly classified)
+ **classification_metrics.ipynb** - corresponds to the Jupyter notebook used to obtain the AUROC, AUPRC, Accuracy, Sensitivity and Specificity of each model
+ **explanation_metrics.ipynb** -  corresponds to the Jupyter notebook used to obtain the incorrectly classified TP; TN; FP and FN.
+ **explanation_metrics2.ipynb**-  corresponds to the Jupyter notebook used to obtain the boxplots of the TPR (and TNR) of the correctly classified images
+ **find_intersections.ipynb** -  corresponds to the Jupyter notebook used to obtain the correctly classified TP; TN; FP and FN.

## Packages Versions
+ torchvision: 0.12.0+cu102
+ nibabel: 3.2.2
+ pandas: 1.3.4
+ numpy: 1.22.4
+ matplotlib: 3.4.3
+ scipy: 1.7.1
+ skimage: 0.18.3
+ ot: 0.8.2
+ torch: 1.11.0+cu102
+ torchmetrics: 0.11.4
+ PIL: 9.1.1
