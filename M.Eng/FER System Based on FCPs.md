# FER System Based on FCPs

## Keywords
* **FER:** Facial Expression Recognition
* **FCP:** Facial Characteristics Points
* **AU:** Action Unit
* **FACS:** Facial Action Coding System

## Applications of Facial Expression Recognition (FER) Systems
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

## Action Units (AUs) and Universal Facial Expressions
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

## CK+ (Extended Cohn-Kanade Dataset)
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
  * from a total of 123 different subjects
  * ranging from 18 to 50 years of age
  * with a variety of genders and heritage
* Each video shows:
  * a facial shift from the neutral expression to a targeted peak expression
  * recorded at 30 frames per second (FPS)
  * with a resolution of either 640x490 or 640x480 pixels
## Folders in CK+
* a. cohn-kanade-images
 * Contains the image sequences for all subjects.
 * Organized by subject IDs (e.g., S001, S002), where each folder corresponds to a single subject.
 * Each subject folder contains subfolders for individual expression sequences, named sequentially (e.g., 001, 002).
 * Image sequences progress from a neutral expression to the peak expression.
