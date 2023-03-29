# Pretrain_XAI_gt

In this project random lesions are created and added to a background that consists in MRI slices from the HCP project.
The objective here is to study the correctness of XAI methods applied to pre-trained VGG models. 
The VGG were pre-trained with two different corpora: ImageNet and MRI (classification between female and male genders).
The VGG was then fine-tuned to several degrees of finetuning that corresponded to a different number of layers fine-tuned and others left unchanged (frozen). 5 degrees of finetuning were obtained based on the blocks shown bellow:

![alt text](https://github.com/Marta54/Pretrain_XAI_gt/blob/main/VGG%20architecture.png)

The XAI method used came from the Captum library and were Integrated Gradients, GradientSHAP, DeepLift, Saliency, InputXGradient, Guided Backpropagation, Deconvolution and LRP.

In the folder saves several results for incorrectly classified images obtained with the XAI methods applied to the models that were pre-trained with ImageNet (for the best performing models and the models that performed similarly).
In new results are the results obtained for the teo types of pre-trained corpora. These results correspond to the images that were correctly classified by all the models (3 models for each degree of finetuning).

+ Boxplot_incorrect_classified.ipynb - corresponds to the Jupyter notebook used to obtain the incorrected classified boxplots from the saves folder.
+ Examples Heatmaps.ipynb - corresponds to the Jupyter notebook used to obtain the heatmaps in the saves folder (incorrectly classified)
+ classification_metrics.ipynb - corresponds to the Jupyter notebook used to obtain the AUROC, AUPRC, Accuracy, Sensitivity and Specificity of each model
+ explanation_metrics.ipynb -  corresponds to the Jupyter notebook used to obtain the incorrectly classified TP; TN; FP and FN.
+ explanation_metrics2.ipynb -  corresponds to the Jupyter notebook used to obtain the boxplots of the TPR (and TNR) of the correctly classified images
+ find_intersections.ipynb -  corresponds to the Jupyter notebook used to obtain the correctly classified TP; TN; FP and FN.
