# Helmet-Detection

## Datasets Used
+ <a href="https://www.kaggle.com/andrewmvd/helmet-detection">Kaggle Dataset</a>
+ <a href="https://universe.roboflow.com/bike-helmets/bike-helmet-detection-2vdjo">Roboflow Dataset</a>

## Models Trained
## Yolov5 on the Kaggle dataset
The Kaggle Dataset has 764 images belonging to 2 classes(with helmet and without helmet).
<br>
The dataset was split into train(75%), validation(15%) and test(10%) sets. The images were auto-oriented and resized to 416x416 using Roboflow. The Xml annotations were converted to the YOLO v5 PyTorch using Roboflow.
<br>
<a href="https://github.com/mudit14224/Helmet-Detection/tree/main/Models/model%201/weights">Model Weights</a>
<br>
<a href="https://drive.google.com/drive/folders/1qmE-gOCXjTi6vfe8fOMGjQuEqTpztD9W?usp=sharing">Results on given videos</a>
### Confusion Matrix
![alt text](https://github.com/mudit14224/Helmet-Detection/blob/main/Images/cm_m1.png)
### Results
![alt text](https://github.com/mudit14224/Helmet-Detection/blob/main/Images/results_m1.png)
### Validation batch labels
![alt text](https://github.com/mudit14224/Helmet-Detection/blob/main/Images/val_batch0_labels_m1.jpg)
### Validation batch predictions
![alt text](https://github.com/mudit14224/Helmet-Detection/blob/main/Images/val_batch0_pred_m1.jpg)

## Yolov5 on the Roboflow Dataset
This dataset (v1) is composed of 1,371 images of people with and without bike helmets.
<br>
The training set has 1.2k images, validation set has 126 images and the test set has 63 images. 
<br>
The images in this dataset has been auto-oriented and resized to 416x416. Further augmentations prior to import have been applied(Bounding Box Blur - upto 10 px)
<br>
<a href="https://github.com/mudit14224/Helmet-Detection/tree/main/Models/model%202/weights">Model Weights</a>
<br>
<a href="https://drive.google.com/drive/folders/1u8PrC36wX-3HFuuzdv6iiq2oFvJ9hQRY?usp=sharing">Results on given videos</a>
### Confusion Matrix
![alt text](https://github.com/mudit14224/Helmet-Detection/blob/main/Images/cm_m2.png)
### Results
![alt text](https://github.com/mudit14224/Helmet-Detection/blob/main/Images/results_m2.png)
### Validation batch labels
![alt text](https://github.com/mudit14224/Helmet-Detection/blob/main/Images/val_batch0_labels_m2.jpg)
### Validation batch predictions
![alt text](https://github.com/mudit14224/Helmet-Detection/blob/main/Images/val_batch0_pred_m2.jpg)
To Count the number of helmets, we just need to iterate over the output of the model and count the no. of times the class 0 shows up in the output. 
## Running Instructions
Open the terminal and type the following 
```
$ git clone https://github.com/mudit14224/Helmet-Detection.git
$ cd helmet-detection/yolov5
$ python -m venv helmet-detect-env
$ .\helmet-detect-env\Scripts\activate
$ pip3 install -r requirements.txt
$ python detect.py --weights "Path to model weights" --source "Path to image or video"
```
