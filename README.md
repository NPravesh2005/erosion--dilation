# EROSION -- DILATION

### DEVELOPED BY : PRAVESH N
### REG NO : 212223230154

## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
## Step-1:
Create a black image of size 100x600 pixels.

## Step-2:
Use a specified font to write the word "Lifestyle" on the image at a defined position.

## Step-3:
Show the image containing the text without axis labels.

## Step-4:
Define a structuring element for morphological operations (e.g., a cross-shaped kernel).

## Step-5:
Apply erosion to the image using the defined structuring element to reduce the size of white regions.

## Step-6:
Apply dilation to the original image using the same structuring element to increase the size of white regions.

 
## Program:

# Import the necessary packages
```py
# DEVELOPED BY : PRAVESH N
# REG NO : 212223230154
# EXPT NO : 9

import numpy as np
import cv2
import matplotlib.pyplot as plt
```

# Create the Text using cv2.putText
```py
img = np.zeros((100, 600, 3), dtype='uint8')  # Black background (RGB: 0, 0, 0)
font = cv2.FONT_HERSHEY_COMPLEX
text_color = (255, 255, 255)  # White text (RGB: 255, 255, 255)
cv2.putText(img, 'JANARTHANAN K', (60, 70), font, 2, text_color, 5, cv2.LINE_AA)
plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
plt.axis('off')
plt.show()
```


# Create the structuring element

```py
kernel = np.ones((5,5),np.uint8)
kernel1 = cv2.getStructuringElement(cv2.MORPH_CROSS,(5,5))
cv2.erode(img,kernel)
```

# Erode the image
```py
img_erode = cv2.erode(img,kernel1)
plt.imshow(img_erode)
plt.axis('off')
```



# Dilate the image

```py
img_dilate = cv2.dilate(img,kernel1)
plt.imshow(img_dilate)
plt.axis('off')



```
## Output:

### Display the input Image
<br>
<br>

<img width="553" height="114" alt="Screenshot 2025-10-23 211113" src="https://github.com/user-attachments/assets/3ea39db3-9437-46e8-b652-de8f71345418" />



<br>
<br>
<br>

### Display the structured elements
<br>
<br>

<img width="696" height="796" alt="Screenshot 2025-10-23 211130" src="https://github.com/user-attachments/assets/e43edc06-be75-405c-96e3-1d081f3babd9" />


<br>
<br>
<br>


### Display the Eroded Image
<br>
<br>

<img width="518" height="104" alt="Screenshot 2025-10-23 211143" src="https://github.com/user-attachments/assets/cc61ebf7-cd59-404d-bf29-231cbc3fd261" />


<br>
<br>
<br>

### Display the Dilated Image
<br>
<br>

<img width="531" height="126" alt="Screenshot 2025-10-23 211154" src="https://github.com/user-attachments/assets/1e00abf4-eb18-4d67-a120-093f11c721d4" />


<br>
<br>
<br>

## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
