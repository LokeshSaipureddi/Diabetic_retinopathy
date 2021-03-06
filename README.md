## Preliminary Diabetic Retinopathy Detection using Feature Pyramid Network
### Dataset
 In this study we have used Messidor-2( Methods to Evaluate Segmentation and Indexing Techniques in the field of Retinal Ophthalmology) dataset, which is a standard and publicly available dataset provided by ADCIS[10,11] and is imported from kaggle for this work. This dataset consists of 1742 high-resolution fundus eye images segregated into 5 classes by severity 0, 1, 2, 3, 4 and each class corresponds to no DR, mild DR, moderate DR, severe proliferative DR.</br>
Table 1: Table representing the number of images and their class before preprocessing</br>
![alttext](https://github.com/LokeshSaipureddi/Diabetic_retinopathy/blob/main/Screenshot%202022-02-08%20142427.png)</br>
Table 2 : Table representing the number of images and their class after preprocessing</br>
But For this study we are more focused on the binary classification so, we have combined images under classes 1, 2, 3, 4 and made it into a single class depicting the presence of DR while class 0 depicts images with No DR paving a way to have a binary classification.</br>
![alttext](https://github.com/LokeshSaipureddi/Diabetic_retinopathy/blob/main/Screenshot%202022-02-08%20142456.png)
### Image preprocessing
  To improve the performance of the model and remove overfitting image argumentation techniques like rescale, horizontal and vertical flip, horizontal and vertical shift and rotation. The images are converted into grayscale, then Fast NonLocal Means Denoising(fast NLMD) is applied to reduce noise in the image. Finally to improve the contrast of images a variant of adaptive histogram equalisation named  Contrast Limited Adaptive Histogram Equalisation (CLAHE) is applied.
![alttext](https://github.com/LokeshSaipureddi/Diabetic_retinopathy/blob/main/Screenshot%202022-02-08%20142534.png)

### Proposed Architecture
 In the long history of deep learning, the convolutional neural networks have played a curtail role in the process of feature extraction. CNN has done an exceedingly good job for the process of image classification. Transfer learning accompanied with hyper parameter tuning, we have used Resnet50V2 ,InceptionV3, MobilenetV2 for the process of classification. Feature Pyramid Network (FPN)  was initially introduced in [12] for object detection and was used by M Rahimdeh et.al in [13] for the purpose of Image Classification
 ![alttext](https://github.com/LokeshSaipureddi/Diabetic_retinopathy/blob/main/Screenshot%202022-02-08%20142642.png)
 ### Results
 From the above sections we can understand the need for appropriate features for prediction of diabetic retinopathy and in this section, we mainly concentrate on performance of our model on these images. We have used feature pyramid networks with inception V3, Resnet50V2, MobilenetV2 as backbone networks for prediction. Using transfer learning we are able to understand that InceptionV3 is able to produce good results when compared to other 2 learning models with precision of 75.18 percent, recall of 81.07 percent, specificity of 73.23 percent, area under curve of 83.01 percent. Once FPN is used the results of these transfer learning models have escalated.
 Table no 1: without Feature Pyramid Network </br>
 ![alttext](https://github.com/LokeshSaipureddi/Diabetic_retinopathy/blob/main/Screenshot%202022-02-08%20142829.png)</br>
 Table no 2: with Feature Pyramid Network </br>
  ![alttext](https://github.com/LokeshSaipureddi/Diabetic_retinopathy/blob/main/Screenshot%202022-02-08%20142849.png)</br>
 Table no 3: Comparison with the Existing Approaches</br> 
  ![alttext](https://github.com/LokeshSaipureddi/Diabetic_retinopathy/blob/main/Screenshot%202022-02-08%20142918.png)</br>
