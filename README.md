# XDecompo



 we propose a robust self-supervised model, called XDecompo, to improve the transferability of features from the pretext task to the downstream  task. XDecompo has been designed based on an affinity propagation-based class decomposition to effectively encourage learning of the class boundaries in the downstream task.
 The results confirm the effective of XDecompo with high accuracy of 96.16% and 94.30% for histopathology colorectal cancer and brain tumour images, respectively. Furthermore, the feature transferability has been validated using an explainable post-hoc method, resulting in highly accurate feature representations.

## **Dataset description**

1-  **Colorectal cancer images dataset**, we used the labelled and unlabelled dataset from the NCT Biobank, (Heidelberg, Germany), and the UMM pathology archive (Mannheim, Germany). A large set of 100,000 samples from ``NCT-CRC-HE-100K'' used as an unlabelled data set, and a set of 7180 image from ``CRC-VAL-HE-7K'' used as a labelled dataset.In our experiment, we only used three classes, Adipose (ADI), stroma (STR) and tumour epithelium (TUM) which contain 1338, 421 and 1233, respectively.

2- **Brain tumour images dataset**, we used a total of 253 images from a public open source, which contains 155 and 98 samples of tumours and without tumours respectively as an unlabelled dataset. For labelled dataset, we used a set of 3064 with three kinds of brain tumours acquired from Nanfang and General Hospitals, Tianjin Medical University, China: 1426 glioma, 708 meningiomas, and 930 pituitary tumour (with size 400x400 pixels). 
 
 

```python
open source for Brain tumour images dataset:
 https://www.kaggle.com/datasets/navoneel/brain-mri-images-for-brain-tumor-detection
```
## **Requirement**

Matlab R2021a - window 10 or later version
python 3.9 - keras

## A guidance for usage

1. Consist of four parts :
 - Run (convolutional_autoencoder.ipynb) matlab file on the unlabelled dataset (Pseudo Labels),
 - get the clusters of the image data (pseudo-labelled) to use them for the pretext task.
2. Run (pretext_training.ipynb) matlab file for classification of the pseudo labelled images, and using them as a coarse transfer learning.
3. Run (class_Downstream Training.ipynb) to apply the Affinity propagation clustering algorithm.
4. Run (XDecompo model.ipynb) to apply our proposal model (XDecompo).

## **Results**

XDecompo has achieved an overall accuracy of 97.44% with a specificity of 90.87% and sensitivity of 97.82% to classify the CRC test set into three classes. Furthermore, XDecompo has achieved a high accuracy of 96.21% with a specificity of 93.28% and sensitivity of 97.04% on the brain dataset. In terms of explainability, the Grad-CAM maps demonstrated that XDecompo can correctly localise the most important texture (and region of interests) in an input image that contributes to the accurate prediction.


**Table 1:** Overall classification performance of 4S-DT++ model based on testing set of CRC and brain tumour datasets.

| Dataset       | ACC           | SN    |  SP   |
| ------------- |:-------------:| -----:|-------|
| CRC           | 96.16         | 90.87 | 97.82 |
|Brain tumour   | 94.30         | 93.27 | 97.04 |


Fig: Visualisation of deep features for each model of CRC test set

![1]( https://github.com/Asmaa-AbbasHassan/XDecompo/blob/main/images/CRC.png)

Fig: Visualisation of deep features for each model of brain tumour test set

![2]( https://github.com/Asmaa-AbbasHassan/XDecompo/blob/main/images/brain.png)



## Contact
Please do not hesitate to contact us if you have any question. asmaa.husien@mail.bcu.ac.uk

## Citation

 If you used XDecompo and found it useful, please cite the following papers:
 
 •	Abbas A, Abdelsamea MM, Gaber MM. DeTraC: **4s-dt: Self-supervised super sample decomposition for transfer learning with application to covid-19 detection. IEEE Transactions on Neural Networks and Learning Systems 32 (7), 2798-2808**. 

 
## License
[MIT](https://github.com/AsmaaAbbasHassan/XDecompo/blob/master/LICENSE)


