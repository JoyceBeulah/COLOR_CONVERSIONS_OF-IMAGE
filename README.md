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

![image](https://github.com/JoyceBeulah/COLOR_CONVERSIONS_OF-IMAGE/assets/118343698/b42d4e70-1867-4fd6-b030-07de8cdf9efd)

<br>
<br>

### ii)Write the image
```
    import cv2
    image=cv2.imread('dog.jpg',0)
    cv2.imwrite('demos.jpg',image)
```
##OUTPUT:

![image](https://github.com/JoyceBeulah/COLOR_CONVERSIONS_OF-IMAGE/assets/118343698/6ee8338e-ec91-40f8-9f97-2513f7c1a690)

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

![image](https://github.com/JoyceBeulah/COLOR_CONVERSIONS_OF-IMAGE/assets/118343698/b98721e1-ab5e-492d-bb22-dfb8d29864f1)

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

![image](https://github.com/JoyceBeulah/COLOR_CONVERSIONS_OF-IMAGE/assets/118343698/c8d0a661-6341-4849-8ecf-1510c91587f6)

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
## OUTPUT:

![image](https://github.com/JoyceBeulah/COLOR_CONVERSIONS_OF-IMAGE/assets/118343698/aee3f2d8-ee30-495f-b27c-eac62f0c7f7e)

<br>
<br>

### ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('dog.jpg',1)
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

![image](https://github.com/JoyceBeulah/COLOR_CONVERSIONS_OF-IMAGE/assets/118343698/fee596fe-37b3-47d3-87ba-9833350e2a5b)

<br>
<br>

### x) Split and merge HSV Image
```
import cv2
img = cv2.imread("dog.jpg",1)
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

![image](https://github.com/JoyceBeulah/COLOR_CONVERSIONS_OF-IMAGE/assets/118343698/cad57e9e-4776-4d87-855c-ecaf537c9750)

<br>
<br>

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.
