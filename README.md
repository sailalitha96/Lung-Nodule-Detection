# Lung-Nodule-Detection

 In this project deep learning architectures will be applied on the dataset from Lung Nodule Analysis 2016 which consists of 3D CT scan of patients. The initial task is to use segmentation techniques to detect nodule images from non-nodule images. Data Preprocessing and Data Augmentation constitute two most important steps in the Image preprocessing.
 
## Data Description
The primary dataset is the Lung Image Database Consor-tium image collection (LIDC-IDRI)[6]consists of diagnos-tic and lung cancer screening thoracic computed tomogra-phy (CT) scans with marked-up annotated lesions. The an-notations and associated candidates files are provided to usin .csv format.  The dataset itself has images as.mhdfiles(512  x  512).   The  characteristics  of  the  data  are  detailed below

1.For each patient the data consists of CT scan data anda label (0 for no cancer, 1 for cancer).

2.The candidates file is a csv file that contains nodulecandidate per line. Each line holds the scan name, thex, y, and z position of each candidate in world coordi-nates, and the corresponding class.

3.The annotation file is a csv file that contains one find-ing per line.  Each line holds the SeriesInstanceUIDof the scan, the x, y, and z position of each finding inworld coordinates; and the corresponding diameter inmm. The annotation file contains 1186 nodules.

###Data Augmentation 
Dealt  with  the  class  imbalance  usingdownsampling.  To further resolve the issue, we chose an-other popular technique ofdata augmentation.  We createnew  images  by  applying  minor  transformations  onto  theimages  dataset  obtained  after  processing  through  section2.2. Minor changes such as flips or translations or rotationsalters the image such that our neural network would inter-pret these as distinct images

Minor transformation iclude - 180 horziontal flip, 90 horizontal flip. 

I did take the help from Swetha Subramamniam who had worked on the Mhd dataset for the imaeg analysis part. 

## Model selection

It has long been experimented to train heavy networks suchas  AlexNet  ,  ResNet  for  nodule  detection.With  equiva-lent accuracy, smaller CNN architectures offer at least twoadvantages:   (1)  Smaller  CNNs  require  less  communication across servers during distributed training.  (2) SmallerCNNs  are  more  feasible  to  deploy  on  FPGAs  and  otherhardware with limited memory such as mobile phones.

Using Low memory networks for these applications is interesting.Therefore using the famous MobileNet ,SqueezeNet was new.Spatial convolution is used in Mobilenet which is computationally better than using bottleneck layers. 


## Model Performance

Accuracy isnt always the best measure for the determining the model performance.For such applications specificity and sensitivity need to be accounted as well. The graphs below showcase the evaluation paramters. 


![j](https://user-images.githubusercontent.com/25079132/61990538-66aba100-b010-11e9-8688-07b1e22b205f.JPG)

As seen the SqueezeNet has better Specificity.It is 0.883 currently, the specificity can be improved by using more gaussian blurred images increasing the training size. 





