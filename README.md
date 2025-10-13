# Ex.no-05-Implementation-of-filter

## Aim:

To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:

Anaconda - Python 3.7

## Algorithm:

### Step1

Import Required Libraries

### Step2

Read and Convert the Image

### Step3

Apply Smoothing Filter

### Step4

Apply Sharpening Filter


### Step5

Display the Results

## Program:

### Developed By   :Piritharaman R

### Register Number:212223230148

### 1. Smoothing Filters

i) Using Averaging Filter
```
average_filter = cv2.blur(image, (30,30))
```
```
plt.figure(figsize = (18, 6))
plt.subplot(121); plt.imshow(image [:, :, ::-1]); plt.title('Input Image')
plt.subplot(122); plt.imshow(average_filter[:, :, ::-1]); plt.title('Output Image ( Average Filter)')
```

ii) Using Weighted Averaging Filter
```
kernel = np.array([[1,2,1],
                   [2,4,2],
                   [1,2,1]])/16
weighted_average_filter = cv2.filter2D(image, -1, kernel)
```
```
plt.figure(figsize = (18, 6))
plt.subplot(121);plt.subplot(121); plt.imshow(image [:, :, ::-1]); plt.title('Input Image')
plt.subplot(122);plt.imshow(weighted_average_filter[:, :, ::-1]); plt.title('Output Image(weighted_average_filter)');plt.show()

```
iii) Using Gaussian Filter
```
gaussian_filter = cv2.GaussianBlur(image, (29,29), 0, 0)
```
```

plt.figure(figsize = (18, 6))
plt.subplot(121); plt.imshow(image [:, :, ::-1]); plt.title('Input Image')
plt.subplot(122); plt.imshow(gaussian_filter[:, :, ::-1]); plt.title('Output Image ( Gaussian Filter)')

```
iv)Using Median Filter
```
median_filter = cv2.medianBlur(image, 19)
```
```
plt.figure(figsize = (18, 6))
plt.subplot(121); plt.imshow(image [:, :, ::-1]); plt.title('Input Image')
plt.subplot(122); plt.imshow(median_filter[:, :, ::-1]); plt.title('Output Image ( Median_filter)')
```

### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```
laplacian_kernel = np.array([[0, -1, 0],
                             [-1, 5, -1],
                             [0, -1, 0]])
sharpened_laplacian_kernel = cv2.filter2D(image, -1, kernel = laplacian_kernel)
```
```
plt.figure(figsize = (18, 6))
plt.subplot(121); plt.imshow(image [:, :, ::-1]); plt.title('Input Image')
plt.subplot(122); plt.imshow(sharpened_laplacian_kernel[:, :, ::-1]); plt.title('Output Image ( Laplacian_filter)')

```
ii) Using Laplacian Operator
```
gray_image = cv2.cvtColor(image, cv2.COLOR_RGB2GRAY)
laplacian_operator = cv2.Laplacian(gray_image, cv2.CV_64F)
laplacian_operator = np.uint8(np.absolute(laplacian_operator))
```
```
plt.figure(figsize = (18, 6))
plt.subplot(131); plt.imshow(image [:, :, ::-1]); plt.title('Input Image')
plt.subplot(132); plt.imshow(gray_image, cmap='gray'); plt.title('Gray_image')
plt.subplot(133); plt.imshow(laplacian_operator,cmap='gray'); plt.title('Output Image ( Laplacian_filter)')
```

## OUTPUT:
### 1. Smoothing Filters

i) Using Averaging Filter

<img width="837" height="377" alt="image" src="https://github.com/user-attachments/assets/365e42eb-2da3-4527-a42e-a87eab3d7ab9" />

ii)Using Weighted Averaging Filter

<img width="836" height="341" alt="image" src="https://github.com/user-attachments/assets/34eaf9f9-3b34-400f-a782-8496043aaeb3" />


iii)Using Gaussian Filter

<img width="841" height="372" alt="image" src="https://github.com/user-attachments/assets/8b75a4b0-b67c-4497-be82-c8d7be523f63" />


iv) Using Median Filter

<img width="840" height="372" alt="image" src="https://github.com/user-attachments/assets/b737bc42-cb3a-488b-95c4-e69ffd7f74ed" />


### 2. Sharpening Filters

i) Using Laplacian Kernal

<img width="842" height="383" alt="image" src="https://github.com/user-attachments/assets/e982ba3f-7768-4a3f-bf30-8d052092a64b" />


ii) Using Laplacian Operator

<img width="840" height="306" alt="image" src="https://github.com/user-attachments/assets/0a5a8809-8f2f-4da9-beee-5e6fa7dbf6d3" />

## Result:

Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
