# EX. NO: 5
# Image Smoothing and Sharpening Using OpenCV

## Aim

To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.


## The program performs the following operations:

- Read and display an input image  
- Apply Averaging filter  
- Apply Weighted Averaging filter  
- Apply Gaussian filter  
- Apply Median filter  
- Apply Laplacian sharpening using kernel  
- Apply Laplacian operator  
- Display all outputs for comparison  

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image (e.g., `image.jpg`).

### Step 3:
Convert the image from BGR to RGB format for display.

### Step 4:
Apply Averaging Filter using `cv2.blur()`.

### Step 5:
Apply Weighted Averaging Filter using a custom kernel with `cv2.filter2D()`.

### Step 6:
Apply Gaussian Filter using `cv2.GaussianBlur()`.

### Step 7:
Apply Median Filter using `cv2.medianBlur()`.

### Step 8:
Apply Laplacian Sharpening using Kernel with `cv2.filter2D()`.

### Step 9:
Convert image to grayscale and apply Laplacian Operator using `cv2.Laplacian()`.

### Step 10:
Display all filtered images using a grid layout for comparison.

##  Developed By

- **Name:** NANDIKA S
- **Register No:** 212224230175

      import cv2
      import matplotlib.pyplot as plt
      import numpy as np
      image1=cv2.imread("myimage.jpeg")
      image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
      kernel=np.ones((11,11),np.float32)/169
      image3=cv2.filter2D(image2,-1,kernel)
      plt.figure(figsize=(9,9))
      plt.subplot(1,2,1)
      plt.imshow(image2)
      plt.title("Original Image")
      plt.axis("off")
      plt.subplot(1,2,2)
      plt.imshow(image3)
      plt.title("Average Filter Image")
      plt.axis("off")
      plt.show()
      
      kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
      image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
      image3=cv2.filter2D(image2,-1,kernel1)
      plt.subplot(1,2,1)
      plt.imshow(image2)
      plt.title("Original Image")
      plt.axis("off")
      plt.subplot(1,2,2)
      plt.imshow(image3)
      plt.title("Weighted Average Filter Image")
      plt.axis("off")
      plt.show()
      
      gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
      plt.subplot(1,2,1)
      plt.imshow(image2)
      plt.title("Original Image")
      plt.axis("off")
      plt.subplot(1,2,2)
      plt.imshow(gaussian_blur)
      plt.title("Gaussian Blur")
      plt.axis("off")
      plt.show()
      
      median=cv2.medianBlur(image2,13)
      plt.figure(figsize=(9,9))
      plt.subplot(1,2,1)
      plt.imshow(image2)
      plt.title("Original Image")
      plt.axis("off")
      plt.subplot(1,2,2)
      plt.imshow(median)
      plt.title("Median Blur")
      plt.axis("off")
      plt.show()
      
      kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
      image3=cv2.filter2D(image2,-1,kernel2)
      plt.subplot(1,2,1)
      plt.imshow(image2)
      plt.title("Original Image")
      plt.axis("off")
      plt.subplot(1,2,2)
      plt.imshow(image3)
      plt.title("Laplacian Kernel")
      plt.axis("off")
      plt.show()
      
      laplacian=cv2.Laplacian(image2,cv2.CV_64F)
      plt.subplot(1,2,1)
      plt.imshow(image2)
      plt.title("Original Image")
      plt.axis("off")
      plt.subplot(1,2,2)
      plt.imshow(laplacian)
      plt.title("Laplacian Operator")
      plt.axis("off")
      plt.show()

##  Output: 
#### AVERAGE FILTER IMAGE
<img width="713" height="348" alt="image" src="https://github.com/user-attachments/assets/675585c7-1979-4ffd-8d69-6d05e15fb958" />

#### WEIGHTED AVERAGE FILTER IMAGE
<img width="704" height="357" alt="image" src="https://github.com/user-attachments/assets/dedba162-d257-44c8-b5c4-1fb9cf7f27e7" />

#### GAUSSIAN BLUR
<img width="696" height="353" alt="image" src="https://github.com/user-attachments/assets/44305e39-afd5-41a1-8d79-30622d241277" />

#### MEDIAN BLUR
<img width="720" height="345" alt="image" src="https://github.com/user-attachments/assets/6cc2c940-21ad-488c-bd5d-826602c54a70" />

#### LAPLACIAN KERNEL
<img width="698" height="353" alt="image" src="https://github.com/user-attachments/assets/29b27949-eefe-4f74-a41a-1cae63438aa0" />

#### LAPLACIAN OPERATOR
<img width="682" height="347" alt="image" src="https://github.com/user-attachments/assets/266ee698-1b1f-4836-80e0-664831a81270" />

##  Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
