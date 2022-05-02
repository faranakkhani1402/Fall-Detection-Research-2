# A more comprehensive approach for fall detection


In this project, I will carry out a further work that have been proposed in [previous project](https://github.com/hoangNguyen210/Fall-Detection-Project-/blob/main/README.md) mainly for camera dataset (C1 and C2).
. Due to our work haven't been done yet, I would just update our proposed method as well as our result. Our code will be updated after submiting. 


## System requirement 
- numpy - version 1.21.5
- pandas - version 1.3.5
- cv2 -version 4.1.2
- sklearn -version 1.0.2
- tensorflow - version 2.8.0
- keras - version 2.8.0


**Here is the short form of our paper.** 
## Table of Contents
<!-- * [Acknowledgements](#acknowledgements) -->
* [Introduction](#introduction)
* [General Info](#general-information)
* [Dataset description](#dataset-description)
* [Data preprocessing](#d-p)
* [Proposed method](#proposed-method)
* [Result](#result)
* [Conclusion and Furture Work](#cc)
* [Room for Improvement](#room-for-improvement)
* [Contact](#contact)

<a name="introduction"></a>
## Introduction
<a name="general-information"></a>
## General Information
<a name="dataset-description"></a>
## Dataset description
- You can download UP-Fall Detection dataset in this [link](https://sites.google.com/up.edu.mx/har-up/) . This dataset includes over 850 GB of data from wearable sensors, ambient sensors, and vision equipment. 17 young healthy people with age ranging from 18–24 years old were invited to perform 11 different activities. Here is the summary of activities. 

| Activity ID | Description  | Duration (s)  |
| :-----:     | :-:          | :-:           |
|     1        | Falling forward using hands          | 10           |
| 2     | Falling forward using knees          | 10           |
| 3    | Falling backwards         | 10           |
| 4     | Falling sideward          | 10           |
| 5     | Falling sitting in empty chair         | 10           |
| 6     | Walking          | 60           |
| 7     | Standing         | 60           |
| 8     | Sitting          | 60           |
| 9     | Picking up an object         | 10           |
| 10     | Jumping          | 30           |
| 11     | Laying          | 60           |

|![Location of measure device](./PICTURE/location.png)|
|:--:| 
| *Location of measurement devices* |
You can read more about this dataset at this [paper](https://www.mdpi.com/1424-8220/19/9/1988).

<a name="d-p"></a>
## Data preprocessing :

<a name="proposed-method"></a>
## Proposed methods :
|![MoE_1](./PICTURE/MoE_1.png)|
|:--:| 
| *Mixture of Experts models for C1 dataset* |

|![MoE_2](./PICTURE/MoE_2.png)|
|:--:| 
| *Mixture of Experts models for C2 dataset* |

|![MoE_12](./PICTURE/Concat_MoE.png)|
|:--:| 
| *Mixture of Experts models for C1 and C2 dataset* |

<a name="result"></a>
## Result 
<!-- | Data | Model  | Accuracy  | Precision | Recall | F1-Score |
|---------------|-----------|-----------|--------|----------|
| S | XGBoost <br> CatBoost <br> MLP  |  | 99.21 <br> 99.05 <br> 99.04 <br> | 99.19 <br> 99.02 <br> 99.05 <br> | 99.21 <br> 99.05 <br> 99.03 <br>| 99.20 <br> 99.02 <br> 99.03 <br> | -->

- Performance of our proposed method for each dataset :

| Data | Model  | Accuracy  | Precision | Recall | F1-Score |
| :-----:     | :-:          | :-:           |  :-:           |  :-:           |  :-:           |
|     **C1**  | MoE-1 <br> MoE-1 + Data Augmentation <br> 3D-CNN1 <br> | 99.48 <br> 99.50   <br>  99.38 <br>     | 99.47 <br> 99.49 <br>  99.38 <br>         | 99.48 <br> 99.50 <br> 99.38 <br> |99.47<br> 99.49 <br> 99.38 <br> |
| **C2**  | MoE-2 <br> MoE-2 + Data Augmentation <br> 3D-CNN2 <br> | 99.59 <br> 99.61   <br>  99.41 <br>     | 99.59 <br> 99.61 <br>  99.41 <br>         | 99.59 <br> 99.61 <br> 99.41 <br> |99.59<br> 99.61 <br> 99.41 <br> |
| **C12**  | Concatenate MoE <br> Max MoE <br> Average MoE <br> Concatenate MoE + Data Augmentation <br> Average MoE + Data Augmentation <br> Max MoE + Data Augmentation <br> Concatenate 3D-CNN <br> Max 3D-CNN <br> Average 3D-CNN  | 99.62 <br> 99.64 <br> 99.66 <br> 99.62 <br> **99.67** <br> 99.66 <br> 99.44 <br> 99.43 <br> 99.49| 99.62 <br> 99.64 <br> 99.66 <br> 99.62 <br> **99.67** <br> 99.66 <br> 99.44 <br> 99.42 <br> 99.49 | 99.62 <br> 99.64 <br> 99.66 <br> 99.62 <br> **99.67** <br> 99.66 <br> 99.44 <br> 99.43 <br> 99.49 |99.62 <br> 99.64 <br> 99.66 <br> 99.62 <br> **99.67** <br> 99.66 <br> 99.44 <br> 99.42 <br> 99.49  |

- Comparing with recent work :

| Data | Name | Model  | Acc | WPre | WRec | WF1 |
| :-----:     | :-:          | :-:           |  :-:           |  :-:           |  :-:           | :-: |
|     **C1**  | [Martinez et al.](https://www.mdpi.com/1424-8220/19/9/1988) <br> [Espinosa et al.](https://sci-hub.se/10.1016/j.compbiomed.2019.103520) <br> [Chahyati et al.](https://sci-hub.se/10.1109/icacsis51025.2020.9263201)<br> [Ramirez et al.](https://sci-hub.se/10.1109/access.2021.3061626) <br> [Research 1](https://github.com/hoangNguyen210/Fall-Detection-Project-1)   <br>  **Ours** <br> | 2D-CNN <br> 2D-CNN <br> 2D-CNN <br> Random Forest <br> 2D-CNN <br> MoE 2D-CNN     | 78.49 <br> 98.06 <br>  88.25 <br>  99.45 <br> 99.17 <br> **99.49** <br> |74.92 <br> 97.94 <br>  85.22 <br> 96.60 <br> 99.24 <br> **99.48**     | 78.49 <br> 98.06 <br> 88.25 <br> 89.99 <br> 99.12 <br> **99.49** | 76.33 <br> 97.88 <br> 86.57 <br> 92.34 <br> 99.16 <br> **99.48** |
|     **C2**  | [Martinez et al.](https://www.mdpi.com/1424-8220/19/9/1988) <br> [Espinosa et al.](https://sci-hub.se/10.1016/j.compbiomed.2019.103520) <br> [Chahyati et al.](https://sci-hub.se/10.1109/icacsis51025.2020.9263201)<br> [Research 1](https://github.com/hoangNguyen210/Fall-Detection-Project-1)   <br>  **Ours** <br> | 2D-CNN <br> 2D-CNN <br> 2D-CNN <br> 2D-CNN <br> MoE 2D-CNN     | 87.93 <br> 97.58 <br>  88.35 <br>  99.39 <br> **99.61** <br>  | 84.7 <br> 96.96 <br>  85.06 <br>  99.40 <br> **99.60**     | 87.93 <br> 97.58 <br>  88.35 <br>  99.39 <br> **99.61**  | 85.69 <br> 97.19 <br> 86.36 <br> 9.40 <br> **99.60** |
|     **C12**  | [Espinosa et al.](https://sci-hub.se/10.1016/j.compbiomed.2019.103520)  <br> [Espinosa et al.](https://sci-hub.se/10.1016/j.compbiomed.2019.103520) <br> [Research 1](https://github.com/hoangNguyen210/Fall-Detection-Project-1) <br>  **Ours** <br> | Concatenate 2D-CNN <br> Concatenate VGG-16 <br> Concatenate 2D-CNN <br> Combining MoE    | 98.81 <br> 27.86 <br>  99.46 <br>  **99.67**  |98.81 <br> 7.76 <br>  99.47 <br>  **99.67**  | 98.81 <br> 27.86 <br>  99.46 <br>  **99.67**  | 98.78 <br> 12.14 <br>  99.46 <br>  **99.67**  |


<a name="cc"></a>
## Conclusion and Future Work 


## Acknowledgements
- This project was also a part of my **Graduate Thesis** in my final year at university.
- This project was inspired by 2 of my teachers at HCMUS: Thao. V Ha and Binh Nguyen.
- My main responsibilities in this project were implementing code, visualizating our methods as well as results, and writing a paper.
- Our teacher helped me correct my writing mistakes and submitted the paper.



## Project Status
Project is: **_in progress_**. Our goal is to submit to **ISI Q2 Journal**( or Q1 if possible). I have finished our experiment proccess (implement code and visualize result) and currently I am  writting a paper. Other authors help me to revise code as well as check grammar mistakes in our paper. 

## Contact
Created by [hoangng210a@gmail.com] - feel free to contact me!




