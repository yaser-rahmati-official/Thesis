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

### 1. Anger
* **AU4:** Brow Lowerer (furrowing of the eyebrows)
* **AU5:** Upper Lid Raiser (wide-open eyes)
* **AU7:** Lid Tightener (tightened eyelids)
* **AU23:** Lip Tightener (compressed lips)
* **AU24:** Lip Pressor (tightened and pressed lips)
* **AU17:** Chin Raiser (raised chin)

### 2. Contempt
* **AU14:** Dimpler (corner of the lip tightened and raised asymmetrically)
* **AU12:** Lip Corner Puller (smirk-like movement, often asymmetric)

### 3. Disgust
* **AU9:** Nose Wrinkler (wrinkling of the nose)
* **AU10:** Upper Lip Raiser (lifting the upper lip)
* **AU16:** Lower Lip Depressor (pulling the lower lip down)
* **AU4:** Brow Lowerer (furrowing the brow)

### 4. Fear
* **AU1:** Inner Brow Raiser (inner part of the eyebrows raised)
* **AU2:** Outer Brow Raiser (outer part of the eyebrows raised)
* **AU4:** Brow Lowerer (slight furrowing of the brows)
* **AU5:** Upper Lid Raiser (wide-open eyes)
* **AU20:** Lip Stretcher (corners of the lips stretched horizontally)
* **AU25:** Lips Parted (mouth opened slightly)

### 5. Happiness
* **AU6:** Cheek Raiser (smiling with the eyes or "crow’s feet")
* **AU12:** Lip Corner Puller (smile with upward movement of lip corners)

### 6. Sadness
* **AU1:** Inner Brow Raiser (inner eyebrows pulled upward)
* **AU4:** Brow Lowerer (slightly furrowed eyebrows)
* **AU15:** Lip Corner Depressor (corners of the lips pulled downward)
* **AU17:** Chin Raiser (slight upward chin movement)

### 7. Surprise
* **AU1:** Inner Brow Raiser (eyebrows raised upward)
* **AU2:** Outer Brow Raiser (outer part of the eyebrows raised)
* **AU5:** Upper Lid Raiser (wide-open eyes)
* **AU26:** Jaw Drop (mouth opened widely)

## 4. 8-Point FCPs Modelling
The image shows a simplified face with key facial characteristic points (FCPs), defined relative to a coordinate system with the origin . These points correspond to facial features like the eyebrows, eyes, nose, and mouth.

To model each FCP mathematically, let us define the coordinates of the relevant points. Assuming the face is symmetric about the vertical axis through , we can define each point relative to the origin.
Here is a rewritten and explained version of the equations in the image:

![The San Juan Mountains are beautiful!](/M.Eng/Image/002.png "San Juan Mountains")

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

## 7. Identifying FCPs For Each Image
### 7.1. Source Code
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

### The Result
![The San Juan Mountains are beautiful!](/M.Eng/Image/001.png "San Juan Mountains")
