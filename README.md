# Miniproject
#Blur image
import numpy as np 
import cv2
import matplotlib.pyplot as plt

def plotImages(imp):
  plt.imshow(img, cmap = "gray")
  plt.axis('off')
  plt.style.use('seaborn')
  plt.show()
image = cv2.imread('my_ing_jpg')
image = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plotImages(image)

face_detect = cv2.CascadeCLassifier('haarcascade_frontalface_alt.xml')
face_data = face_detectMultiScale(image,1.3,5)

for (x,y,w,h) in face_data:
  cv2.rectangle(image,(x,y),(x+w,y+h),(0,255,0),2)
  roi = image[y:y+h,x:x+w]
  roi = cv2.GaussianBlur(roi,(23,23),30)
  image[y:y+roi,shape[0],x:x+roi.shape(1)] = roi
plotImages(image)
