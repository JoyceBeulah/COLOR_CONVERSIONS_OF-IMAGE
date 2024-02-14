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
### Developed By:
### Register Number: 


## Output:

### i) Read and display the image
```
    import cv2
    image=cv2.imread('dog.jpg',1)
    image=cv2.resize(image,(300,300))
    cv2.imshow('BEULAH',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
##OUTPUT:
![image](https://github.com/JoyceBeulah/COLOR_CONVERSIONS_OF-IMAGE/assets/118343698/57106508-8b0f-4e2a-a118-3172d3eb6751)

<br>
<br>

### ii)Write the image
```
    import cv2
    image=cv2.imread('dog.jpg',0)
    cv2.imwrite('demos.jpg',image)
```
##OUTPUT:
![image](https://github.com/JoyceBeulah/COLOR_CONVERSIONS_OF-IMAGE/assets/118343698/e30d6450-e4fb-4138-8c47-513ca7cebc17)

<br>
<br>

### iii)Shape of the Image
```
    import cv2
    image=cv2.imread('dop.jpg',1)
    print(image.shape)
```
##OUTPUT:
![image](https://github.com/JoyceBeulah/COLOR_CONVERSIONS_OF-IMAGE/assets/118343698/be0229d5-68c0-4268-a6d2-c60d8c4b4297)

<br>
<br>

### iv)Access rows and columns
```
    import random
    import cv2
    image=cv2.imread('dog.jpg',1)
    image=cv2.resize(image,(500,500))
    for i in range (250,500):
      for j in range(image.shape[1]):
          image[i][j]=[random.randint(0,255),
                       random.randint(0,255),
                       random.randint(0,255)] 
    cv2.imshow('part image',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
## OUTPUT:
![image](https://github.com/JoyceBeulah/COLOR_CONVERSIONS_OF-IMAGE/assets/118343698/1152ea66-a9a7-45c2-8ff5-f5da6d16c998)

<br>
<br>

### v)Cut and paste portion of image
```
  import cv2
  image=cv2.imread('dog.jpg',1)
  image=cv2.resize(image,(300,300))
  tag =image[150:200,110:160]
  image[110:160,150:200] = tag
  cv2.imshow('image1',image)
  cv2.waitKey(0)
  cv2.destroyAllWindows()
```
## OUTPUT:
![image](https://github.com/JoyceBeulah/COLOR_CONVERSIONS_OF-IMAGE/assets/118343698/f0b78eca-5b3b-4b8f-9d3d-bdb347516790)

<br>
<br>

### vi) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('dog.jpg',1)
img = cv2.resize(img,(200,200))
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
## OUTPUT:
![image](https://github.com/JoyceBeulah/COLOR_CONVERSIONS_OF-IMAGE/assets/118343698/8e9c4d1f-925a-4fc5-9282-24dc68c23355)
<br>
<br>

### vii) HSV to RGB and BGR
```
import cv2
img = cv2.imread('dog.jpg')
img = cv2.resize(img,(200,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
## OUTPUT:
![image](https://github.com/JoyceBeulah/COLOR_CONVERSIONS_OF-IMAGE/assets/118343698/7335c0ad-3393-4d8a-93e0-a52e2e17855e)

<br>
<br>

### viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('dog.jpg')
img = cv2.resize(img,(200,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
##OUTPUT:
![image](https://github.com/JoyceBeulah/COLOR_CONVERSIONS_OF-IMAGE/assets/118343698/d43afc46-1f4e-493c-a59b-8d543b6ea8d1)

<br>
<br>

### ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('blue.jpg',1)
img = cv2.resize(img,(200,200))

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
## OUTPUT:
![image](https://github.com/JoyceBeulah/COLOR_CONVERSIONS_OF-IMAGE/assets/118343698/6d589a2d-9108-4948-886f-9502e91f5914)

<br>
<br>

### x) Split and merge HSV Image
```
import cv2
img = cv2.imread("blue.jpg",1)
img = cv2.resize(img,(200,200))
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
## OUTPUT:
![image](https://github.com/JoyceBeulah/COLOR_CONVERSIONS_OF-IMAGE/assets/118343698/ad90cd24-1216-4eea-bba9-310f6ed22b65)

<br>
<br>




## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







