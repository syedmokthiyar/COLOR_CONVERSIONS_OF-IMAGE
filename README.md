# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

##### Program:
### Developed By: S.M.Syed Mokthiyar
### Register Number: 212222230156


## Output:

### i) Read and display the image
```python
import cv2
image=cv2.imread('fort.jpg',1)
image=cv2.resize(image,(400,300))
cv2.imshow('syed',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
# Output:
![dipt 1](https://github.com/syedmokthiyar/COLOR_CONVERSIONS_OF-IMAGE/assets/118787294/72ac2e09-75a1-48ef-be9b-637a7a8e8e53)

### ii)Write the image
```python
image=cv2.imread('fort.jpg',0)
cv2.imwrite('d.jpg',image)
```
# output:
![Screenshot 2024-02-16 091955](https://github.com/syedmokthiyar/COLOR_CONVERSIONS_OF-IMAGE/assets/118787294/3fae7599-2263-40e3-8cfd-8b924bf56a65)

### iii)Shape of the Image
```python
image=cv2.imread('fort.jpg',1)
print(image.shape)
```
# output:
![Screenshot 2024-02-16 091946](https://github.com/syedmokthiyar/COLOR_CONVERSIONS_OF-IMAGE/assets/118787294/176d49c2-c6ae-4341-8eea-7bb862e24abf)

### iv)Access rows and columns
```python
import cv2
import random
image=cv2.imread('fort.jpg',1)
image=cv2.resize(image,(400,400))
for i in range (150,200):
    for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,255),
                     random.randint(0,255),
                     random.randint(0,255)] 
cv2.imshow('part image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
# output:
![dipt4](https://github.com/syedmokthiyar/COLOR_CONVERSIONS_OF-IMAGE/assets/118787294/c461b195-6059-4239-a341-3bd03959fada)


### v)Cut and paste portion of image
```python
image=cv2.imread('fort.jpg',1)
image=cv2.resize(image,(400,400))
tag =image[130:200,110:190]
image[110:180,120:200] = tag
cv2.imshow('partimage1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
# Output:
![dipt5](https://github.com/syedmokthiyar/COLOR_CONVERSIONS_OF-IMAGE/assets/118787294/d4569c33-84d2-4f71-95ea-c6ac6117d00f)


### vi) BGR and RGB to HSV and GRAY
```python
img = cv2.imread('fort.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)
hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)
hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)
gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)
gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
# output:
![dipt6](https://github.com/syedmokthiyar/COLOR_CONVERSIONS_OF-IMAGE/assets/118787294/25262b3d-4692-4ab6-9fbc-36afc7d92338)

### vii) HSV to RGB and BGR
```python
img = cv2.imread('p-3.jpg')
img = cv2.resize(img,(300,200))
img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)
RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)
BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)
cv2.waitKey(0)
cv2.destroyAllWindows()on
```
# output:


### viii) RGB and BGR to YCrCb
```python
img = cv2.imread('fort.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)
YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)
YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
# output:
![dipt8](https://github.com/syedmokthiyar/COLOR_CONVERSIONS_OF-IMAGE/assets/118787294/f55d6ed5-0432-482c-8656-cd459b289380)


### ix) Split and merge RGB Image
```python
img = cv2.imread('fort.jpg',1)
img = cv2.resize(img,(300,200))
R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]
cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)
merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
# output:
![dipt9](https://github.com/syedmokthiyar/COLOR_CONVERSIONS_OF-IMAGE/assets/118787294/e9772ca6-4ae4-4917-bc1d-c321badafd05)


### x) Split and merge HSV Image
```python
img = cv2.imread("p-3.jpg",1)
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
H,S,V=cv2.split(img)
cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)
merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
# output:
![Uploading dipt10.jpeg…]()


## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







