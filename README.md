## Automatic Identification and Counting of Blood Cells
## Dataset
The [```Complete Blood Count (CBC) Dataset```](https://github.com/MahmudulAlam/Complete-Blood-Cell-Count-Dataset) has been used for automatic identification and counting of blood cells. Download the dataset, unzip and put the ```Training```, ```Testing```, and ```Validation``` folder in the working directory.

## Requirements
- [x] TensorFlow-GPU==1.11.0
- [x] OpenCV==3.4.2
- [x] Cython==0.29.2
- [x] Weights: Download the trained weights file for blood cell detection and put the ```weights``` folder in the working directory.

[![Download](https://img.shields.io/badge/download-weights-brightgreen.svg?longCache=true&style=flat)](https://mega.nz/#F!2kVUnKjS!z15tM9WLfga3l1gCNSLNGw)

## How to Run the Code
A step by step guideline of how to run the blood cell detection code in your computer is provided in the [wiki](https://github.com/MahmudulAlam/Automatic-Identification-and-Counting-of-Blood-Cells/wiki/A-Step-by-Step-Guide-of-How-to-Run-the-Code).

## Blood Cell Detection Output
<p align="center">
  <img src="https://user-images.githubusercontent.com/37298971/44617785-17eb0980-a88b-11e8-9018-c84f8be5cefa.png" width="480">
</p>

## Impact of KNN and IOU
In some cases, our model predicts the same platelet twice. To solve this problem we propose k-nearest neighbor (KNN) and intersection over union (IOU) based verification system where we find the nearest platelet of a platelet and calculate their overlap. We are allowing only 10% of overlap between two platelets. If the overlap is more than that then it will be a spurious prediction and we will ignore the prediction.

### Prediction Before Verfication 
<p align="center">
  <img src="https://user-images.githubusercontent.com/37298971/46260207-b27ede00-c504-11e8-9d00-7d7be151ee5d.jpg" width="380">
</p>

### Prediction After Verfication
<p align="center">
  <img src="https://user-images.githubusercontent.com/37298971/46260504-a268fd80-c508-11e8-9ef0-5230d00f47a3.jpg" width="380">
</p>

## Prediction on High-Resolution Image (HRI)
We have used our model to detect and count blood cells from high-resolution blood cell smear images. These test images are of the size of ```3872 x 2592``` way higher than the size of our trained images of ```640 x 480```. So, to match the cell size of our trained images we divide those images into grid cells and run prediction in each grid cell and then combine all the prediction results. 

### Dividing Image into Grid/Patch
<p align="center">
  <img src="https://user-images.githubusercontent.com/37298971/45962420-a39ab600-c042-11e8-975f-9b0a077f0e0f.jpg" width="640">
</p>

### Combined Output
<p align="center">
  <img src="https://user-images.githubusercontent.com/37298971/45961699-055a2080-c041-11e8-95b0-1c8ac3c8875b.jpg" width="640">
</p>

## Paper
For more detail explanation, please go through the [paper](http://ietdl.org/t/kmgztb). Cite this paper as:
```
@article{alam2019machine,
  title={Machine learning approach of automatic identification and counting of blood cells},
  author={Alam, Mohammad Mahmudul and Islam, Mohammad Tariqul},
  journal={Healthcare Technology Letters},
  volume={6},
  number={4},
  pages={103--108},
  year={2019},
  publisher={IET}
}
```

## How to Train on Your Dataset
A seven-step guideline of how to train on your own dataset is provided in this [wiki](https://github.com/MahmudulAlam/Automatic-Identification-and-Counting-of-Blood-Cells/wiki/How-to-Train-on-Your-Dataset). 
