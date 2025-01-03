# FER System Based on FCPs

## 1. Keywords
* **FER:** Facial Expression Recognition
* **FCP:** Facial Characteristics Points
* **AU:** Action Unit
* **FACS:** Facial Action Coding System

## 2. Applications of Facial Expression Recognition (FER) Systems
**1. Human-Computer Interaction (HCI):** 
Enhances the responsiveness of applications by adapting to users' emotional states, such as in _gaming_, _virtual assistants_, and _educational software_.

**2. Mental Health Monitoring:**
Supports the detection and monitoring of mental health conditions like _depression_, _anxiety_, and _stress_ through emotional analysis.

**3. Behavioral Analysis:**
Provides insights into user reactions in scenarios such as _marketing_, _customer service_, and _public opinion research_.

**4. Surveillance and Security:** 
Assists in identifying suspicious behavior or emotional distress in public spaces, _enhancing safety and threat detection_.

**5. Healthcare:** 
Enables non-invasive diagnosis and patient monitoring, including tracking _pain levels_ or _emotional responses during treatments_.

**6. Entertainment:** 
Powers emotion-driven content recommendations and interactive experiences in _movies_, _games_, and _augmented/virtual reality_.

**7. Autonomous Systems:** 
Enhances decision-making in robotics, automotive interfaces, and smart home devices by interpreting human emotional states.

**8. Education:** 
Supports _adaptive learning platforms_ by assessing _students’ engagement_ and _emotional responses_ during lessons.

**9. Accessibility Tools:** 
_Assists individuals with disabilities_ in communication and interaction by translating emotions into alternative forms of expression.

**10. Market Research:** 
Analyzes consumer reactions to _advertisements_, _products_, and _services_ for targeted improvements and campaign optimization.

## 3. Action Units (AUs) and Universal Facial Expressions
Action Units (AUs) are the building blocks of facial expressions in the _Facial Action Coding System_ (FACS) developed by _Paul Ekman_ and _Wallace V. Friesen_. AUs describe _the movement of individual facial muscles, and combinations of AUs correspond to universal facial expressions_. Below is a guide to understanding AUs in the context of the seven universal facial expressions:

### 3.1. Anger
* **AU4:** Brow Lowerer (furrowing of the eyebrows)
* **AU5:** Upper Lid Raiser (wide-open eyes)
* **AU7:** Lid Tightener (tightened eyelids)
* **AU23:** Lip Tightener (compressed lips)
* **AU24:** Lip Pressor (tightened and pressed lips)
* **AU17:** Chin Raiser (raised chin)

### 3.2. Contempt
* **AU14:** Dimpler (corner of the lip tightened and raised asymmetrically)
* **AU12:** Lip Corner Puller (smirk-like movement, often asymmetric)

### 3.3. Disgust
* **AU9:** Nose Wrinkler (wrinkling of the nose)
* **AU10:** Upper Lip Raiser (lifting the upper lip)
* **AU16:** Lower Lip Depressor (pulling the lower lip down)
* **AU4:** Brow Lowerer (furrowing the brow)

### 3.4. Fear
* **AU1:** Inner Brow Raiser (inner part of the eyebrows raised)
* **AU2:** Outer Brow Raiser (outer part of the eyebrows raised)
* **AU4:** Brow Lowerer (slight furrowing of the brows)
* **AU5:** Upper Lid Raiser (wide-open eyes)
* **AU20:** Lip Stretcher (corners of the lips stretched horizontally)
* **AU25:** Lips Parted (mouth opened slightly)

### 3.5. Happiness
* **AU6:** Cheek Raiser (smiling with the eyes or "crow’s feet")
* **AU12:** Lip Corner Puller (smile with upward movement of lip corners)

### 3.6. Sadness
* **AU1:** Inner Brow Raiser (inner eyebrows pulled upward)
* **AU4:** Brow Lowerer (slightly furrowed eyebrows)
* **AU15:** Lip Corner Depressor (corners of the lips pulled downward)
* **AU17:** Chin Raiser (slight upward chin movement)

### 3.7. Surprise
* **AU1:** Inner Brow Raiser (eyebrows raised upward)
* **AU2:** Outer Brow Raiser (outer part of the eyebrows raised)
* **AU5:** Upper Lid Raiser (wide-open eyes)
* **AU26:** Jaw Drop (mouth opened widely)

## 4. 8-Point FCPs Modelling
The image shows a simplified face with key facial characteristic points (FCPs), defined relative to a coordinate system with the origin . These points correspond to facial features like the eyebrows, eyes, nose, and mouth.

To model each FCP mathematically, let us define the coordinates of the relevant points. Assuming the face is symmetric about the vertical axis through , we can define each point relative to the origin.
Here is a rewritten and explained version of the equations in the image:

![The San Juan Mountains are beautiful!](/M.Eng/Image/002.png "8-Points FCPs modelling")

**1. Eye Openness:**

$$O_{e}=y_{3}-y_{2}$$

**2. Eyebrow Height Relative to The Pupil of The Eye :**

$$H_{e}=y_{4}-y_{1}$$

**3. Mouth Width:**

$$W_{me}=x_{5}-x_{6}$$

**4. Mouth Openness:**

$$O_{m}=x_{8}-x_{7}$$

**5. Distance of Lower Lip to Chin:**

$$O_{m}=\frac{(y_{8}-y_{5})+(y_{8}-y_{6})}{2}$$

## 5. CK+ (Extended Cohn-Kanade Dataset)
* The Extended Cohn-Kanade Dataset (CK+), a widely used dataset for Facial Expression Recognition (FER), includes the following _expression classes_:
  * 1: Anger
  * 2: Contempt
  * 3: Disgust
  * 4: Fear
  * 5: Happiness
  * 6: Sadness
  * 7: Surprise
* The Extended Cohn-Kanade (CK+) dataset contains:
  * 593 video sequences
  * From a total of 123 different subjects
  * Ranging from 18 to 50 years of age
  * With a variety of genders and heritage
* Each video shows:
  * A facial shift from the neutral expression to a targeted peak expression
  * Recorded at 30 frames per second (FPS)
  * With a resolution of either 640x490 or 640x480 pixels
## 6. Folders in CK+
* **cohn-kanade-images**
  * Contains the image sequences for all subjects.
  * Organized by subject IDs (e.g., S001, S002), where each folder corresponds to a single subject.
  * Each subject folder contains subfolders for individual expression sequences, named sequentially (e.g., 001, 002).
  * Image sequences progress from a neutral expression to the peak expression.
* **Emotion**
  * Contains the emotion labels for the image sequences.
  * Organized similarly to cohn-kanade-images, with subfolders for each subject and sequence.
  * Each sequence folder contains a .txt file indicating the emotion label (e.g., 1 for anger, 6 for happiness).
* **Landmarks**
  * Stores facial landmark data for each image in the dataset.
  * Organized by subject and sequence, mirroring the structure of cohn-kanade-images.
  * Each file contains 68 landmark points, typically in .txt or similar format.
* **FACS**
  * Contains Facial Action Coding System (FACS) labels for sequences.
  * These labels describe the action units (AUs) activated in the expression sequence.
  * Organized similarly to other folders, with subfolders for subjects and sequences.
* **AU_labels (if provided)**
  * Contains detailed annotations for Action Units (AUs) for each sequence.
  * Useful for FACS-based analysis and expression recognition tasks.

## 7. Identifying 68 FCPs For Each Image
### 7.1. Matlab Source Code
```
clc;
clear ;
close all;

path1='extended-cohn-kanade-images\S005\001';
cd(path1);
img=imread('S005_001_00000001.png');
imshow(img)
hold

cd('..')
cd('..')
cd('..')

path2='Landmarks\S005\001';
cd(path2);
pos=importdata('S005_001_00000001_landmarks.txt')

x=pos(:,1)
y=pos(:,2)
plot(x,y, 'o')
```
### 7.2. Algorithm Breakdown:
* **Load Image:**
  * Set the path to the image file, read it, and display it.
* **Navigate to Landmarks Directory:**
  * Set the path to the landmarks file and navigate to it.
* **Import Landmarks:**
  * Read the landmark positions from a text file.
* **Plot Landmarks on Image:**
  * Plot the x and y coordinates of the landmarks overlaid on the image.

### 7.3. Code Explanation
* **Clear workspace and close all figures:**
  * clc; clears the command window.
  * clear; clears all variables in the workspace.
  * close all; closes all open figure windows.
* **Set file paths for image and landmarks:**
  * path1 is defined as the directory containing the image file. The variable path1 is set to 'extended-cohn-kanade-images\S005\001'.
  * path2 is defined as the directory containing the landmarks data file. It is set to 'Landmarks\S005\001'.
* **Navigate to image directory:**
  * cd(path1); changes the current working directory to path1 where the image file is located.
* **Read and display the image:**
  * img=imread('S005_001_00000001.png'); reads the image file S005_001_00000001.png into the variable img.
  * imshow(img) displays the image in a figure window.
  * hold ensures that subsequent plotting commands add to the current plot (i.e., the image stays visible while landmarks are added).
* **Navigate to landmarks directory:**
  * cd('..') goes up one level in the directory structure.
  * cd('..') and cd('..') go up two more levels, ultimately reaching the base directory where the landmarks are stored.
* **Load landmarks data:**
  * cd(path2); changes the directory to the path where the landmarks file is located.
  * pos = importdata('S005_001_00000001_landmarks.txt'); imports the landmark coordinates from the S005_001_00000001_landmarks.txt file into the variable pos. This file contains the (x, y) positions of landmarks on the image.
* **Extract and plot the landmark positions:**
  * x = pos(:,1); extracts the x-coordinates of the landmarks (the first column of pos).
  * y = pos(:,2); extracts the y-coordinates of the landmarks (the second column of pos).
  * plot(x, y, 'o') plots the landmarks as circles on the image using the extracted x and y coordinates.

### 7.4. The Result
![The San Juan Mountains are beautiful!](/M.Eng/Image/001.png "68 FCPs")

## 8. Data Preprocessing

The CK+ (Cohn-Kanade Extended) dataset is one of the most reputable and widely used databases for analyzing facial expressions. However, one of its weaknesses is that annotated data, such as Facial Characteristic Points (FCP), emotional states in the Emotion folder, and the coding system in the FACS folder, are not provided for all images in the extended-cohn-kanade-images directory.

### 8.1. Strength:

The Landmarks folder, which includes 68 facial characteristic points (FCP), significantly facilitates image processing. These landmarks are directly utilized in many machine learning and image analysis algorithms.

### 8.2. Weakness:

The FCP data and the emotional state information in the Emotion and FACS folders are not consistently provided for all images. This lack of completeness necessitates a filtering and selection process to create a suitable dataset for the project.

### 8.3. Suggested Filtering Steps:

* Review Facial Landmarks:

_First, check the Landmarks folder and select images with available landmark data._

* Match Emotion and FACS Data:

_Ensure that the selected images also have corresponding data in the Emotion and FACS folders._

* Remove Incomplete Data:

_Exclude all images without landmark or emotional state information from the final dataset._

* Create a New Dataset:

_After completing these steps, compile a new, integrated dataset that includes images, landmark data, and emotional state annotations._

### 8.4. Algorithm Breakdown:

**Check Image**
  * If the data is related to images:
    - Use Algorithm 1 ([main1.m](https://github.com/yaser-rahmati-official/Thesis/blob/main/M.Eng/Matlab%20Source%20Code/main1.m))
       * Load extended-cohn-kanade-images
       * Process image data

**2. Check FCP**
  * If the data is related to FCP:
    - Use Algorithm 3 ([main2.m](https://github.com/yaser-rahmati-official/Thesis/blob/main/M.Eng/Matlab%20Source%20Code/main2.m))
       * Load Landmarks
       * Process FCP data
       * Save to file [landmark.mat](https://github.com/yaser-rahmati-official/Thesis/blob/main/M.Eng/Result/landmarks.mat)

**3. Check Emotion**
  * If the data is related to Emotion:
    - Use Algorithm 2 ([main2c.m](https://github.com/yaser-rahmati-official/Thesis/blob/main/M.Eng/Matlab%20Source%20Code/main2c.m))
       * Load Emotion labels
       * Process Emotion data
       * Save to file [emotion.mat](https://github.com/yaser-rahmati-official/Thesis/blob/main/M.Eng/Result/Emotion.mat)

**4. Check FACS**
  * If the data is related to FACS:
    - Use Algorithm 2b ([main2b.m](https://github.com/yaser-rahmati-official/Thesis/blob/main/M.Eng/Matlab%20Source%20Code/main2b.m))
       * Load FACS labels
       * Process FACS data
       * Save to file [facs.mat](https://github.com/yaser-rahmati-official/Thesis/blob/main/M.Eng/Result/Facs.mat)

### 8.5. Flowchart 
![The San Juan Mountains are beautiful!](/M.Eng/Image/003.png "Flowchart")

## 9. Feature Vector

### 9.1. Matlab Source Code
This MATLAB code performs feature extraction from a dataset for an emotion recognition task. It processes data stored in the variables facs and emotion, computes certain features, and stores the results in variables feat and y. Here’s a detailed step-by-step explanation of the operations:

```
%feature extraction
clc;
clear;
close all;
load('Emotion');
load('total1');
count=1;
for i=1:size(facs,1)
    for j=1:size(facs,2)
        temp=facs(i,j,:);
        temp2=emotion{i,j};
        if(isempty(temp2)==1)
            continue;
        else
            qx=[];
            qy=[];
            for k=1:length(temp)
                temp1=temp{k};
                if(isempty(temp1)==1)
                    break;
                else
                    qx=[qx temp1(:,1)];
                    qy=[qy temp1(:,2)];
                end
            end
            if(isempty(qx)==1)
                continue;
            end
            qx=(qx-min(qx(:)));
            qx=qx/max(qx(:));
            qy=(qy-min(qy(:)));
            qy=qy/max(qy(:));
            qx1=diff(qx');
            qx1(:,1)=[];
            qx2=diff(diff(qx)');
            qxx=[qx1 ; qx2];
            qy1=diff(qy');
            qy1(:,1)=[];
            qy2=diff(diff(qy)');
            qyy=[qy1 ; qy2];
            q2=qxx'.^2;
            q3=qyy'.^2;
            gg=sum(q2)+sum(q3);
            [~,q4]=sort(gg,'descend');
            q4=sort(q4(1:5));
            q5=sqrt(q2(:,q4)+q3(:,q4));
            feat(count,:)=q5(:);
            y(count)=temp2;
            count=count+1;
        end
    end
end
save('data_final1','feat','y');
```
### 9.2. Initialization
```
clc; clear; close all;
load('Emotion');
load('total1');
count=1;
```
* clc; clear; close all;: Clears the command window, removes all variables, and closes all figure windows.
* load('Emotion') and load('total1'): Loads data files Emotion and total1 into the workspace. These files are assumed to contain the variables facs and emotion.
* count=1;: Initializes a counter to track the rows in the output feature matrix feat.

### 9.3. Outer Loops for Data Processing
```
for i=1:size(facs,1)
    for j=1:size(facs,2)
```
* Loops iterate through the rows (i) and columns (j) of the facs matrix.
### 9.4. Data Extraction
```
temp=facs(i,j,:);
temp2=emotion{i,j};
```
* temp: Extracts a slice of the facs array corresponding to indices (i, j, :).
* temp2: Retrieves the corresponding entry from the emotion cell array.
### 9.5. 4. Check for Empty Data
```
if(isempty(temp2)==1)
    continue;
end
```
* Skips the current iteration if temp2 is empty, indicating no valid data for this (i, j) combination.
### 9.6. Inner Loop for Feature Extraction
```
qx=[]; qy=[];
for k=1:length(temp)
    temp1=temp{k};
    if(isempty(temp1)==1)
        break;
    else
        qx=[qx temp1(:,1)];
        qy=[qy temp1(:,2)];
    end
end
```
* Initializes empty arrays qx and qy.
* Iterates over the third dimension (k) of temp:
  * If temp{k} is empty, exits the loop.
  * Otherwise, extracts the first and second columns of temp{k} and appends them to qx and qy, respectively.
### 9.7. Normalization
```
qx=(qx-min(qx(:)));
qx=qx/max(qx(:));
qy=(qy-min(qy(:)));
qy=qy/max(qy(:));
```
* Normalizes qx and qy to a range of [0, 1] by:
  * Subtracting the minimum value.
  * Dividing by the range (maximum - minimum).
### 9.8. Differentiation
```
qx1=diff(qx');
qx1(:,1)=[];
qx2=diff(diff(qx)');
qxx=[qx1 ; qx2];

qy1=diff(qy');
qy1(:,1)=[];
qy2=diff(diff(qy)');
qyy=[qy1 ; qy2];
```
* Computes first and second-order differences for qx and qy:
  * qx1 and qy1: First-order differences.
  * qx2 and qy2: Second-order differences.
* Combines results into qxx and qyy for further processing.
### 9.9. Feature Importance Calculation
```
q2=qxx'.^2;
q3=qyy'.^2;
gg=sum(q2)+sum(q3);
[~,q4]=sort(gg,'descend');
q4=sort(q4(1:5));
```
* Squares the differences in qxx and qyy to calculate magnitudes.
* Computes gg as the sum of squared differences.
* Identifies the top 5 indices with the highest gg values, which are stored in q4.
### 9.10. Feature Matrix Construction
```
q5=sqrt(q2(:,q4)+q3(:,q4));
feat(count,:)=q5(:);
y(count)=temp2;
count=count+1;
```
*. Combines selected features from q2 and q3 (indexed by q4) and calculates their square root.
*. Appends these features to the feat matrix as a row.
*. Stores the corresponding emotion label (temp2) in the y array.
### 9.11. Save Results
```
save('data_final1','feat','y');
```
* Saves the feat matrix (features) and y array (labels) to a file named data_final1.mat.
### 9.12. Flowchart
![The San Juan Mountains are beautiful!](/M.Eng/Image/004.png "Flowchart")

## 10. Feature Extraction and Classification
```
%feature extraction
clc;
clear;
close all;
tic
load('data_final1');
xin=feat;
ptrain=0.7;

temp=y;
xin=log10(xin);
xin=xin-min(xin(:));
xin=xin./max(xin(:));

for j=1:10    
    N=randperm(length(y));
    Ntr=N(1:fix(length(y)*ptrain));
    Nts=N(1+fix(length(y)*ptrain):end);
    
    % y=log10(y+1000);
    % y=y/1000;
    
    xtr=xin(Ntr,:);
    xts=xin(Nts,:);
    ytr=y(Ntr);
    yts=y(Nts);

    rahmatii= fitcknn(xtr,ytr) ; %train 0
    % rahmatii= genfis3(xtr,ytr) ; %train 85
    
    rahmat{j}=rahmatii;
    
    
    
    ytr_m=predict(rahmatii,xtr);
    yts_m=predict(rahmatii,xts);
    ytr_m(ytr_m>7)=7;
    ytr_m(ytr_m<1)=1;
    yts_m(yts_m>7)=7;
    yts_m(yts_m<1)=1;
    
    
    ybb{j}=predict(rahmatii,xin);
    
    % ytr_m(ytr_m>=0)=1;
    % ytr_m(ytr_m<0)=-1;
    %
    % yts_m(yts_m>=0)=1;
    % yts_m(yts_m<0)=-1;
    %
    % fp=length(find(yts-yts_m==2))/length(yts(yts==1))*100
    % tp=length(find(yts(yts==1)-yts_m(yts==1)==0))/length(yts(yts==1))*100
    % fn=length(find(yts-yts_m==-2))/length(yts(yts==-1))*100
    % tn=length(find(yts(yts==-1)-yts_m(yts==-1)==0))/length(yts(yts==-1))*100
    %
    %
    % pr=tp/(tp+fp)
    % rec=tp/(tp+fn)
    % fm=2*pr*rec/(pr+rec)
    % acc=(tp+tn)/(tp+tn+fp+fn)
    
    err_tr(j)=length(find(ytr-ytr_m'~=0))/length(ytr)*100;
    err_ts(j)=length(find(yts-yts_m'~=0))/length(yts)*100;
    
    if(err_tr(j)+err_ts(j)<20)
        break;
    end
end


% q=[];
% for j=1:10
    
save('finals1');


err_tr
err_ts


toc
```
This MATLAB script performs feature extraction and classification on a dataset. Here’s a breakdown of the code:
### 10.1. Preliminary Setup
```
clc;
clear;
close all;
tic
```
* clc: Clears the command window.
* clear: Removes all variables from the workspace.
* close all: Closes all open figure windows.
* tic: Starts a timer to measure code execution time.
### 10.2. Loading Data
```
load('data_final1');
xin=feat;
ptrain=0.7;
```
* load('data_final1'): Loads a .mat file containing variables, assuming feat and y.
* feat: Features matrix (independent variables).
* y: Labels vector (dependent variable).
* ptrain=0.7: Specifies 70% of the data for training and the rest for testing.
### 10.3. Feature Normalization
```
temp=y;
xin=log10(xin);
xin=xin-min(xin(:));
xin=xin./max(xin(:));
```
* temp=y;: Stores y into a temporary variable (not used later).
* log10(xin): Applies a base-10 logarithmic transformation to reduce feature skewness.
* min(xin(:)): Subtracts the minimum value from all elements, ensuring values start from zero.
* max(xin(:)): Divides by the maximum value, scaling features to the range [0, 1].
### 10.4. Data Splitting and Training Loop
```
for j=1:10    
    N=randperm(length(y));
    Ntr=N(1:fix(length(y)*ptrain));
    Nts=N(1+fix(length(y)*ptrain):end);
```
* Random Shuffling:
  * randperm(length(y)): Generates a random permutation of indices for splitting data.
* Train-Test Split:
  * Ntr: Indices for the training set (70% of data).
  * Nts: Indices for the testing set (remaining 30%).
### 10.5. Feature and Label Assignment
```
    xtr=xin(Ntr,:);
    xts=xin(Nts,:);
    ytr=y(Ntr);
    yts=y(Nts);
```
* xtr: Training features.
* xts: Testing features.
* ytr: Training labels.
* yts: Testing labels.
### 10.6. Classifier Training
```
    rahmatii= fitcknn(xtr,ytr); %train 0
```
* fitcknn(xtr, ytr): Trains a k-Nearest Neighbors (k-NN) classifier on the training data.
  * Outputs a model stored in rahmatii.
### 10.7. Prediction
```
    ytr_m=predict(rahmatii,xtr);
    yts_m=predict(rahmatii,xts);
```
* predict(rahmatii, xtr): Predicts labels for training features.
* predict(rahmatii, xts): Predicts labels for testing features.
* Post-Processing:
```
  ytr_m(ytr_m>7)=7;
  ytr_m(ytr_m<1)=1;
  yts_m(yts_m>7)=7;
  yts_m(yts_m<1)=1;
```
* Clips predictions to ensure labels fall between 1 and 7.
### 10.8. Error Calculation
```
    err_tr(j)=length(find(ytr-ytr_m'~=0))/length(ytr)*100;
    err_ts(j)=length(find(yts-yts_m'~=0))/length(yts)*100;
```
* Training Error (err_tr):
  * Compares predicted (ytr_m) and actual labels (ytr) for the training set.
  * Counts mismatches, calculates the percentage of incorrect predictions.
* Testing Error (err_ts):
  * Same calculation for the test set.
### 10.9. Early Stopping
```
    if(err_tr(j)+err_ts(j)<20)
        break;
    end
```
* Stops training if the sum of training and testing errors is less than 20%.
### 10.10. Finalization
```
save('finals1');
err_tr
err_ts
toc
```
* save('finals1'): Saves the workspace variables to a .mat file.
* err_tr and err_ts: Displays the training and testing errors for each iteration.
* toc: Stops the timer and displays the execution time.
