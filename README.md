# Image-Transformation
## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
## Step1:

Import the necessary libraries and read the original image and save it as a image variable.

## Step2:

Translate the image using M=np.float32([[1,0,20],[0,1,50],[0,0,1]]) translated_img=cv2.warpPerspective(input_img,M,(cols,rows))

## Step3:

Scale the image using M=np.float32([[1.5,0,0],[0,2,0],[0,0,1]]) scaled_img=cv2.warpPerspective(input_img,M,(cols,rows))

## Step4:

Shear the image using M_x=np.float32([[1,0.2,0],[0,1,0],[0,0,1]]) sheared_img_xaxis=cv2.warpPerspective(input_img,M_x,(cols,rows))

## Step5:

Reflection of image can be achieved through the code M_x=np.float32([[1,0,0],[0,-1,rows],[0,0,1]]) reflected_img_xaxis=cv2.warpPerspective(input_img,M_x,(cols,rows))

## Step6:

Rotate the image using angle=np.radians(45) M=np.float32([[np.cos(angle),-(np.sin(angle)),0],[np.sin(angle),np.cos(angle),0],[0,0,1]]) rotated_img=cv2.warpPerspective(input_img,M,(cols,rows))

## Step7:

Crop the image using cropped_img=input_img[20:150,60:230]

## Step8:

Display all the Transformed images and end the program.

## Program:
```python
Developed By:P.SYAM TEJ   
Register Number:212221240056
i)Image Translation
import numpy as np
import cv2
import matplotlib.pyplot as plt
inputImage=cv2.imread("gray.jpeg")
inputImage=cv2.cvtColor(inputImage, cv2.COLOR_BGR2RGB)
plt.axis("off")
plt.imshow(inputImage)
plt.show()
rows, cols, dim = inputImage.shape
M= np.float32([[1, 0, 100],
                [0, 1, 200],
                 [0, 0, 1]])
translatedImage =cv2.warpPerspective (inputImage, M, (cols, rows))
plt.imshow(translatedImage)
plt.show()


ii) Image Scaling
import numpy as np
import cv2
import matplotlib.pyplot as plt
inputImage=cv2.imread("gray.jpeg")
inputImage=cv2.cvtColor(inputImage, cv2.COLOR_BGR2RGB)
plt.axis("off")
plt.imshow(inputImage)
plt.show()
rows, cols, dim = inputImage.shape
M = np. float32 ([[1.5, 0 ,0],
                 [0, 1.8, 0],
                  [0, 0, 1]])
scaledImage=cv2.warpPerspective(inputImage, M, (cols * 2, rows * 2))
plt.imshow(scaledImage)
plt.show()


iii)Image shearing
import numpy as np
import cv2
import matplotlib.pyplot as plt
inputImage=cv2.imread("gray.jpeg")
inputImage=cv2.cvtColor(inputImage, cv2.COLOR_BGR2RGB)
plt.axis("off")
plt.imshow(inputImage)
plt.show()
rows, cols, dim = inputImage.shape
matrixX = np.float32([[1, 0.5, 0],
                      [0, 1 ,0],
                      [0, 0, 1]])

matrixY = np.float32([[1, 0, 0],
                      [0.5, 1, 0],
                      [0, 0, 1]])
shearedXaxis = cv2.warpPerspective (inputImage, matrixX, (int(cols * 1.5), int (rows * 1.5)))
shearedYaxis = cv2.warpPerspective (inputImage, matrixY, (int (cols * 1.5), int (rows * 1.5)))
plt.imshow(shearedXaxis)
plt.show()
plt.imshow(shearedYaxis)
plt.show()



iv)Image Reflection
import numpy as np
import cv2
import matplotlib.pyplot as plt
inputImage=cv2.imread("gray.jpeg")
inputImage=cv2.cvtColor(inputImage, cv2.COLOR_BGR2RGB)
plt.axis("off")
plt.imshow(inputImage)
plt.show()
rows, cols, dim = inputImage.shape
matrixx=np.float32([[1, 0, 0],
                    [0,-1,rows],
                    [0,0,1]])
matrixy=np.float32([[-1, 0, cols],
                    [0,1,0],
                    [0,0,1]])
reflectedX=cv2.warpPerspective(inputImage, matrixx, (cols, rows))
reflectedY=cv2.warpPerspective(inputImage, matrixy, (cols, rows))
plt.imshow(reflectedY)
plt.show()



v)Image Rotation
import numpy as np
import cv2
angle=np.radians(45)
inputImage=cv2.imread("gray.jpeg")
M=np.float32([[np.cos(angle),-(np.sin(angle)),0],
               [np.sin(angle),np.cos(angle),0],
               [0,0,1]])
rotatedImage = cv2.warpPerspective(inputImage,M,(int(cols),int(rows)))
plt.axis('off')
plt.imshow(rotatedImage)
plt.show()



vi)Image Cropping
import numpy as np
import cv2
import matplotlib.pyplot as plt
angle=np.radians(45)
inputImage=cv2.imread("gray.jpeg")
CroppedImage= inputImage[20:150, 60:230]
plt.axis('off')
plt.imshow(CroppedImage)
plt.show()




```

## Output:
## i)Image Translation
<img width="245" alt="Screenshot 2022-05-08 at 8 09 20 PM" src="https://user-images.githubusercontent.com/93427224/167301746-10f10324-414d-4b27-8e7d-0229c4040693.png">



### ii) Image Scaling
<img width="241" alt="Screenshot 2022-05-08 at 8 09 30 PM" src="https://user-images.githubusercontent.com/93427224/167301764-71ae78e9-d7a0-4943-bf79-add901ec67d4.png">



### iii)Image shearing
<img width="214" alt="Screenshot 2022-05-08 at 8 10 38 PM" src="https://user-images.githubusercontent.com/93427224/167301794-1336d2eb-2ca1-4d64-8579-6d01a87d9760.png">



### iv)Image Reflection
<img width="269" alt="Screenshot 2022-05-08 at 8 12 28 PM" src="https://user-images.githubusercontent.com/93427224/167301809-ebb1151e-782c-4aed-85c9-83a90872af10.png">



### v)Image Rotation
<img width="226" alt="Screenshot 2022-05-08 at 8 12 49 PM" src="https://user-images.githubusercontent.com/93427224/167301817-c137962c-10d8-42de-9588-aeeed711ab68.png">



### vi)Image Cropping
<img width="346" alt="Screenshot 2022-05-08 at 8 13 33 PM" src="https://user-images.githubusercontent.com/93427224/167301830-0b03c262-9f28-4398-958f-fdf0ae2193c8.png">





## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
