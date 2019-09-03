# Mammography Diagnosis with Deep Learning

This project is developped for the Laboratoire d'Imagerie Médicale et de Bio-Informatique at École Supérieure Polytechnique de Dakar. It's purpose is to create a model using Deep Learning to automatically diagnose signs of breast cancer. We will work on the CBIS-DDSM dataset with cropped images available on this [link](https://wiki.cancerimagingarchive.net/display/Public/CBIS-DDSM#b674062e551748f28134c7bde344094f%20dd).
You can find all the code in the file project.ipynb .

The project and data are organized by this way :

```
project
│   README.md
│   project.ipynb    
│
└───CBIS-DDSM
|   │   calc_case_description_train_set.csv
|   |   calc_case_description_test_set.csv
│   │   mass_case_description_train_set.csv
│   │   mass_case_description_test_set.csv
|   |
│   └───all_cases
│   |    └───Mass-Test_P_XXXXX_LEFT_CC_1
│   |    └───...
│   |    └───Calc-Train_P_XXXXX_RIGHT_CC_1
|   |
|   └───test_crop_jpg
|    |     |   Mass-Test_P_XXXXX_LEFT_CC_1.jpg
|    |     |   ...
|    |     |   Calc-Test_P_XXXXX_LEFT_CC_1.jpg
|    |
|    └───train_crop_jpg
|    |     |   Mass-Train_P_XXXXX_LEFT_CC_1.jpg
|    |     |   ...
|    |     |   Calc-Train_P_XXXXX_LEFT_CC_1.jpg
│   
└───results
    │   res1.png
    │   res2.png
    |   ...
```

There are two different types of potential cancerous lesions in a breast : masses and micro-calcifications (MCs). Both of them can be classified either as benign or malignant, which is the point of this work. We obtain generally better classification results if we train separately a neural network for masses or MCs.

To train our network, we use pre-cropped regions of interest (ROI) in mammographies labeled as malignant or benign from the database CBIS-DDSM. 
